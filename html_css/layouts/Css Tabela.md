🎨 Medida _Css_Tabela
📌 O que é

A medida Css_Tabela é um bloco de CSS dinâmico encapsulado em DAX, utilizado para estilizar tabelas HTML renderizadas no Power BI (via visual de HTML / SVG / Web Content).

Ela funciona como parte de um Design System em DAX, centralizando cores, fontes e comportamentos visuais em uma única medida reutilizável.

🧠 Objetivo da Medida

Padronizar o visual de tabelas HTML

Garantir consistência de cores e tipografia

Permitir fácil manutenção (troca de cores/fonte em um único lugar)

Criar comportamento responsivo (desktop + mobile)

Integrar CSS com medidas DAX de estilo (_Cor_*, _Font_*)

🧱 Estrutura Geral do CSS
🔹 Estilos Globais
body {
  font-family: 'Segoe UI', Arial, sans-serif;
  margin: 0;
}


Define a fonte padrão e remove margens, garantindo alinhamento visual com o Power BI.

🔹 Estrutura da Tabela
table {
  width: 100%;
  border-collapse: collapse;
  min-width: 1200px;
}


Tabela ocupa 100% da largura

min-width força scroll horizontal em telas menores

border-collapse garante linhas mais limpas

🔹 Cabeçalho Fixo (Sticky Header)
thead {
  position: sticky;
  top: 0;
  z-index: 10;
}


Cabeçalho permanece visível ao rolar a tabela

Ideal para grandes volumes de dados

Cores e fontes são controladas por medidas DAX (_Cor_*, _Font_*)

🔹 Células (th e td)
th, td {
  padding: 6px 8px;
  font-size: 10px;
  border-bottom: 1px solid;
}


Espaçamento compacto

Tipografia leve

Linhas de separação discretas

🔹 Linhas Alternadas e Hover
tbody tr:nth-child(even) { background-color: #f9f9f9; }
tbody tr:hover { background-color: #eefaf0; }


Melhora a leitura

Destaque visual ao passar o mouse

Experiência de usuário aprimorada

🟢 Cápsulas de Status (Badges)
Status Normal
.status-normal {
  border-radius: 999px;
}


Visual em formato de cápsula

Indica estados positivos ou normais

Cores controladas por medidas semânticas

Status Urgente
.status-urgente {
  border-radius: 999px;
}


Destaque para estados críticos

Contraste alto e leitura rápida

Ideal para vencimentos, alertas e riscos

📱 Layout Responsivo (Mobile)

Quando a largura da tela é menor que 700px, a tabela se transforma em cards verticais:

✔ O que muda:

Cabeçalho (thead) é ocultado

Cada linha vira um card

Cada célula exibe:

Nome da coluna (via data-label)

Valor centralizado

Bordas arredondadas e sombra leve

@media (max-width:700px) { ... }


➡️ Esse padrão melhora drasticamente a usabilidade em:

Celulares

Tablets

Dashboards incorporados (iframe)

🔁 Integração com DAX (Design System)

A medida consome diretamente:

Cores: _Cor_*

Fontes: _Fonte_Padrao, _Font_Size_*, _Font_Weight_*

👉 Isso permite:

Trocar o tema inteiro alterando poucas medidas

Reutilizar o CSS em vários relatórios

Manter consistência visual entre SVG, HTML e DAX

✅ Quando usar essa medida

Tabelas HTML no Power BI

Relatórios com grande volume de linhas

Dashboards responsivos

Projetos que exigem padrão visual corporativo

Casos onde o visual nativo do Power BI é limitado

🏁 Conclusão

A medida _Css_Tabela funciona como um style guide técnico em DAX, elevando o nível visual das tabelas HTML no Power BI, sem depender de temas externos ou custom visuals.

Ela exemplifica como DAX pode ser usado além de cálculos, atuando também como camada de apresentação.
