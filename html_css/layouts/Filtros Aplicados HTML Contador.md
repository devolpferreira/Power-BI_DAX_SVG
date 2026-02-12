Medida Filtros Aplicados HTML Contador
📌 O que é

A medida Filtros_Aplicados_HTML_Contador é um componente visual em HTML + CSS gerado via DAX, responsável por exibir de forma clara e elegante quais filtros estão aplicados no relatório, além de apresentar um contador dinâmico de filtros ativos.

Ela funciona como um painel de contexto, ajudando o usuário a entender rapidamente como os dados estão sendo filtrados naquele momento.

🎯 Objetivo da Medida

Mostrar todos os filtros ativos de forma legível

Diferenciar visualmente:

Nenhum filtro aplicado

Filtro único

Múltiplas seleções

Exibir um contador agregado de filtros ativos

Melhorar a experiência do usuário (UX)

Centralizar estilos usando o Design System em DAX

🧠 Arquitetura da Medida

A medida está organizada conceitualmente em cinco camadas principais:

1️⃣ Camada de Tema (Cores e Tipografia)

No início da medida, são definidas cores semânticas:

Cor padrão (“Todos”)

Cor de item selecionado

Cor para múltiplas seleções

Cor do texto

Cor dinâmica do contador

Essas cores utilizam:

Medidas de cor (_Cor_*)

Valores HEX diretos apenas quando necessário

📌 Benefício:
O visual se mantém consistente com o restante do relatório e pode ser facilmente ajustado.

2️⃣ Camada de Leitura de Filtros

Para cada dimensão relevante (exemplo):

Tipo de Insumo

Intervalo de Dias

Tipo de Local

Status de Vencimento

Status de Estoque

Armazém

A medida:

Detecta se há filtro aplicado (ISFILTERED)

Concatena valores quando há múltiplas seleções (CONCATENATEX)

Exibe "Todos" quando não há filtro

📊 Isso garante que o texto reflita exatamente o contexto do relatório.

3️⃣ Contador de Filtros Ativos

A variável _QtdeFiltrosAtivos:

Soma a quantidade de valores filtrados em cada dimensão

Considera apenas filtros realmente ativos

Retorna um número único representando o nível de filtragem do relatório

🎨 Cor dinâmica do contador

Verde: nenhum filtro ativo

Azul: um ou mais filtros ativos

Isso cria um feedback visual sutil, sem poluir a interface.

4️⃣ Classificação Visual (CSS Classes)

Cada filtro recebe uma classe CSS dinâmica:

Situação	Classe aplicada
Sem filtro	fx-val--all
Seleção única	fx-val
Múltiplas seleções	fx-val--multi

📌 Isso permite:

Diferenciar visualmente o tipo de filtro

Melhor leitura em dashboards complexos

UX consistente e intuitiva

5️⃣ Camada de Apresentação (HTML + CSS)
📦 Estrutura Visual

Card com bordas arredondadas

Sombra suave

Layout em grid vertical

Labels fixos + valores destacados

🧮 Cabeçalho

Título: “Filtros aplicados”

Contador circular com número de filtros ativos

🎨 CSS

Totalmente embutido na medida

Fontes, pesos e cores vindos do Design System

Layout moderno e corporativo

🔁 Integração com Power BI

Essa medida foi pensada para:

Visuais HTML / Web Content

Dashboards complexos com muitos filtros

Relatórios compartilhados com usuários não técnicos

Ela resolve um problema comum:

❝ O usuário não sabe por que os números mudaram ❞

✅ Quando usar essa medida

Relatórios com muitos slicers

Dashboards executivos

Ambientes com múltiplos filtros cruzados

Quando transparência de contexto é essencial

Projetos que exigem UX refinada

🏁 Conclusão

A medida Filtros Aplicados HTML Contador demonstra como o DAX pode ser usado como camada de experiência, indo além de cálculos numéricos e atuando diretamente na comunicação visual e contextual do relatório.

Ela é um excelente exemplo de:

Integração DAX + HTML + CSS

UX aplicada em Power BI

Componentes reutilizáveis

Governança visual
