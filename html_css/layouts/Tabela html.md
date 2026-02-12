🧩 Medida Tabela Html
📌 O que é

A medida Tabela Html_3 é um componente completo de tabela HTML responsiva, gerado inteiramente via DAX, combinando:

🎨 CSS com variáveis de tema

🧱 HTML estruturado

📊 Layout de tabela avançado

📱 Comportamento responsivo (desktop e mobile)

Tudo encapsulado em uma única medida, pronta para ser usada em visuais de HTML/Web Content no Power BI.

🎯 Objetivo da Medida

Criar uma tabela altamente customizada, além das limitações dos visuais nativos

Centralizar cores, fontes e espaçamentos em variáveis DAX

Permitir padronização visual corporativa

Garantir boa experiência em desktop e mobile

Servir como template reutilizável para outras tabelas HTML

🧠 Arquitetura Geral

A medida é dividida conceitualmente em quatro camadas:

1️⃣ Camada de Tema (DAX → CSS Variables)

No início da medida, todas as decisões visuais ficam centralizadas em variáveis DAX, como:

Cores primárias e secundárias

Estados (aprovado, aguardando, urgente)

Tipografia

Bordas e radius

Tamanhos de fonte e padding

Essas variáveis alimentam diretamente o bloco:

:root {
  --primary-green: ...
  --status-approved-bg: ...
}


📌 Benefício:
Trocar o tema inteiro exige alterar apenas as variáveis DAX — o HTML e CSS permanecem intactos.

2️⃣ Estrutura Visual da Tabela
📋 Cabeçalho

Estilo limpo e corporativo

Fundo diferenciado

Tipografia em destaque

Separação visual clara do corpo da tabela

📄 Corpo da Tabela

Linhas com hover

Bordas discretas

Texto com ellipsis para evitar quebra excessiva

Alinhamento específico por tipo de dado:

Quantidades → direita

Unidades → centro

Texto → esquerda

3️⃣ Componentes Visuais Semânticos
🟢 Status (Aprovação)

Classes CSS:

.status.approved

.status.waiting

Usadas para:

Indicar aprovação

Aguardando validação

Melhor leitura visual por cor e forma

🚨 Prioridade

Classes:

.priority.urgent

.priority.normal

.priority.low

Utilizadas para:

Diferenciar níveis de prioridade

Criar leitura rápida do risco

Substituir colunas puramente textuais por semântica visual

📦 Quantidade Pendente

Classe:

.pend-qty

Destaca valores pendentes sem poluir o layout, mantendo foco no dado crítico.

4️⃣ Responsividade (Mobile First)

Quando a tela é menor que 800px, o layout muda completamente:

✔ Cabeçalho é ocultado
✔ Cada linha vira um card
✔ Cada célula passa a exibir:

Nome da coluna (data-title)

Valor correspondente
✔ Layout otimizado para toque e leitura vertical

📱 Ideal para:

Tablets

Smartphones

Dashboards incorporados (iframe)

🔁 Integração com Power BI

Essa medida foi pensada para funcionar com:

Visuais HTML / Web Content

Dados dinâmicos vindos do modelo

Atualização automática conforme filtros e contexto

Ela demonstra que o DAX pode atuar além de cálculos, funcionando também como:

🧠 Camada de apresentação e layout

✅ Quando usar Tabela Html_3

Quando o visual de tabela nativo não atende

Quando é necessário layout responsivo

Para relatórios corporativos com identidade visual

Para exibir status, prioridades e indicadores visuais

Em projetos que exigem controle fino de UI

🏁 Conclusão

A medida Tabela Html_3 é um exemplo avançado de UI em Power BI usando DAX + HTML + CSS, mostrando como:

Criar componentes reutilizáveis

Centralizar estilos

Elevar o nível visual dos relatórios

Manter governança e padronização

Ela se encaixa perfeitamente como exemplo de referência dentro do repositório.
