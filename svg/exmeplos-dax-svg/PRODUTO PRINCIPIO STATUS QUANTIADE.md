Objetivo

A medida PRODUTO_PRINCIPIO_ATIVO_STATUS_QUANTIADE_SVG gera um card horizontal em SVG, pensado para ser usado como linha de tabela/matriz no Power BI, exibindo de forma visual e compacta:

Nome do produto

Nome técnico (princípio ativo)

Quantidade em estoque

Status de validade (Vencido / Vencendo / A Vencer)

Status de estoque (Com Estoque / Sem Estoque)

Tudo isso é renderizado via SVG dinâmico em DAX, sem necessidade de visuais customizados externos.

🧠 Conceito Visual

O SVG representa um row-card com a seguinte composição:

Borda externa → indica status de validade

Barra esquerda → status de validade do produto

Barra direita vertical → status de estoque (com / sem)

Área central → dados do produto

Badge superior → status de validade (quando aplicável)

Esse layout permite leitura rápida e hierarquia visual clara.

📐 Configuração de Layout
VAR vWidth  = 430
VAR vHeight = 70


Dimensão fixa para evitar quebra em tabelas

Altura suficiente para 3 linhas de texto

Compatível com visual de tabela/matriz

🔤 Fonte Global
VAR vFontGlobal = [_Fonte_Padrao]


Fonte centralizada no Design System

Garante consistência visual em todo o relatório

Facilita troca futura de tipografia

📦 Dados do Produto
VAR vProduto = RELATED ( dBaseProdutos[DESCRIÇÃO PRODUTO] )
VAR vNomeTecnico = fEstoqueGeral[NOME_TECNICO_VALIDO]
VAR vEstoqueTexto = fEstoqueGeral[Estoque Unidade]


Produto vem da dimensão (RELATED)

Nome técnico direto da fato

Estoque exibido como texto, respeitando formatação do modelo

🏷️ Status e Regras de Negócio
Status de validade
VAR vStatusValidade =
    UPPER ( TRIM ( fEstoqueGeral[STATUS AJUSTADO] ) )


Normalização (UPPER + TRIM)

Evita inconsistência visual

Base para cores, badge e barra esquerda

Status de estoque
VAR vStatusEstoque =
    UPPER ( TRIM ( fEstoqueGeral[STATUS ESTOQUE] ) )


Define se o item está COM ESTOQUE ou SEM ESTOQUE.

🎨 Cores por Status de Validade
VAR vCorStatus =
    SWITCH (
        vStatusValidade,
        "VENCIDO", "#E74C3C",
        "VENCENDO", "#F1C40F",
        "A VENCER", "#16A085",
        "SEM DT VENCIMENTO", "#A8A4A4",
        "#A8A4A4"
    )


Uso das cores:

Vermelho → vencido (atenção crítica)

Amarelo → vencendo (alerta)

Verde → a vencer (situação ok)

Cinza → sem data ou indefinido

Essas cores alimentam:

Barra esquerda

Borda do card

Badge de status

⛔ Tratamento para “Sem Estoque”
VAR vSemEstoque = vStatusEstoque = "SEM ESTOQUE"


Quando SEM ESTOQUE:

Borda fica branca

Barra direita fica cinza

Texto vertical muda para Sem Estoque

Cor do estoque muda para vermelho

Isso evita conflito visual entre:

Status de validade

Status físico de estoque

📊 Barra Direita (Status de Estoque)
VAR vTextoVertical =
    IF ( vSemEstoque, "Sem Estoque", "Com Estoque" )


Texto rotacionado em 90°

Comunicação rápida do estado do estoque

Cor do texto se adapta ao fundo

🏷️ Badge de Status
VAR vTextoBadge =
    IF (
        vSemEstoque
            || vStatusValidade = "-"
            || vStatusValidade = ""
            || ISBLANK ( vStatusValidade ),
        "",
        vStatusValidade
    )


Regras:

Badge não aparece quando:

Sem estoque

Status inválido

Status em branco

Evita ruído visual

Mostra apenas informação relevante

🖼️ Estrutura do SVG

Componentes principais:

<rect> → fundo com borda dinâmica

<rect> → barra esquerda (status validade)

<rect> → barra direita (status estoque)

<text> → rótulos e valores

<rect + text> → badge de status

Tudo posicionado de forma absoluta para evitar variação entre linhas.

✅ Benefícios da Medida

✔ Substitui visual customizado
✔ Total controle visual via DAX
✔ Escalável para grandes tabelas
✔ Integra Design System
✔ Versionável em Git
✔ Fácil manutenção
