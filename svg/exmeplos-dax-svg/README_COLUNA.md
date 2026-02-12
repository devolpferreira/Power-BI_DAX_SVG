📌 Objetivo

A medida PRODUTO_PRINCIPIO_VSGV é responsável por gerar um SVG dinâmico em DAX que exibe:

Nome do produto

Nome técnico / princípio ativo

Barra lateral de status

Cores e tipografia dinâmicas conforme o status do estoque

Ela retorna um SVG embutido (data:image/svg+xml), pronto para uso em:

Tabelas

Matrizes

Cards customizados

Visuais com URL de imagem

🧠 Conceito Geral

Essa medida implementa um mini–card visual dentro do Power BI, usando apenas DAX + SVG, sem visuais customizados externos.

O layout é composto por:

Barra vertical lateral (indicador de status)

Linha principal com descrição do produto

Linha secundária com nome técnico (estilo itálico)

Tudo é controlado dinamicamente por status, cores, fontes e dados do modelo.

📐 Configuração de Layout
VAR vSVG_Width  = 320
VAR vSVG_Height = 52


Define o tamanho fixo do SVG, garantindo:

Alinhamento consistente

Altura suficiente para duas linhas de texto

Uso eficiente em tabelas/matrizes

🏷️ Tratamento do Status
VAR vStatus =
    UPPER (
        TRIM (
            COALESCE ( fEstoqueGeral[STATUS AJUSTADO], "-" )
        )
    )


Boas práticas aplicadas:

COALESCE evita BLANK

TRIM remove espaços indevidos

UPPER padroniza comparação

Uso de "-" como fallback técnico

Isso garante robustez contra dados inconsistentes.

🎨 Mapeamento de Cores por Status
VAR vCorBarra =
    SWITCH (
        TRUE(),
        vStatus = "VENCIDO",               vCorVermelhoForte,
        vStatus = "VENCENDO",              vCorAmarelo,
        vStatus = "A VENCER",               vCorVerde,
        vStatus = "-",                     vCorVermelhoClaro,
        vStatus = "SEM DATA VENCIMENTO",   vCorPreto,
        [_Cor_Cinza_Medio_Neutro]
    )

Estratégia adotada:

Uso de medidas de cor centralizadas (Design System)

Mesmo status controla:

Cor da barra lateral

Cor do texto

Fallback neutro evita erro visual

Isso facilita:

Troca de tema

Padronização visual

Manutenção futura

🧪 Dados do Produto
Produto
VAR vProdutoNomeCompleto =
    RELATED ( dBaseProdutos[DESCRIÇÃO PRODUTO] )


Usa RELATED para buscar a descrição oficial

Mantém separação entre fato e dimensão

Nome Técnico / Princípio Ativo
VAR vNomeRaw = fEstoqueGeral[NOME_TECNICO_VALIDO]


Tratamento aplicado:

Remove espaços

Detecta valores inválidos (<SEM PRINCIPIO ATIVO>)

Evita quebra visual quando vazio

✍️ Texto Dinâmico (SVG <tspan>)
Nome Técnico (linha secundária)
VAR vTextoNomeTecnico =
    "<tspan font-size='9px'
            font-weight='400'
            font-style='italic'
            fill='" & vCorTextoStatus & "'>"


Características visuais:

Fonte menor

Itálico

Cor dependente do status

Mantém hierarquia visual clara

🔐 Sanitização de Texto (SVG-safe)
SUBSTITUTE("&", "&amp;")
SUBSTITUTE("<", "&lt;")
SUBSTITUTE(">", "&gt;")


Evita:

Quebra de SVG

Erros silenciosos no render

Problemas com caracteres especiais

👉 Boa prática essencial para SVG em DAX.

🖼️ Construção Final do SVG

A medida retorna:

data:image/svg+xml;utf8,<svg>...</svg>


Componentes do SVG:

<path> → barra lateral de status

<text> linha 1 → descrição do produto

<text> linha 2 → nome técnico

Tudo com:

Fonte padronizada (_Fonte_Padrao)

Cores dinâmicas

Layout consistente

✅ Benefícios dessa Abordagem

✔ Não depende de visual customizado
✔ Totalmente versionável em Git
✔ Altamente reutilizável
✔ Integra Design System + DAX
✔ Escala bem para tabelas grandes
✔ Controle visual fino dentro do Power BI

⚠️ Observações Importantes

SVG em DAX exige sanitização de texto

Comentários extensos devem ficar no README (não no TMDL)

Recomenda-se usar medidas de cor e fonte centralizadas

🧭 Possíveis Evoluções

Tooltip SVG

Ícones por status

Truncamento inteligente de texto

Responsividade por largura

Animações simples (stroke / opacity)
