# 📊 Power BI • DAX • SVG • HTML  
### Repositório de Estudos, Padrões e Exemplos Reutilizáveis

Este repositório reúne **exemplos práticos, padrões técnicos e soluções reutilizáveis** voltadas para **Power BI**, com foco em:

- Medidas **DAX avançadas**
- **Design System em DAX** (cores, fontes, estilos)
- **SVG dinâmico** integrado ao Power BI
- Uso de **HTML + SVG** para UI customizada
- Boas práticas de modelagem, organização e performance

O objetivo é servir como **base de referência**, **repositório de aprendizado** e **acervo técnico reutilizável**.

---

## 📁 Estrutura do Repositório

```text
/
├── dax/
│   ├── medidas/
│   │   ├── _Medidas.tmdl
│   │   ├── README.md
│   │
│   ├── indicadores/
│   ├── tempo/
│   ├── estoque/
│   └── exemplos-avancados/
│
├── svg/
│   ├── cards/
│   ├── badges/
│   ├── status/
│   └── exemplos-dax-svg/
│
├── html_css/
│   ├── layouts/
│   ├── templates/
│   └── svg-embutido/
│
│
└── README.md


🧠 Conceitos-Chave do Repositório
🔹 DAX como Camada de Negócio

Medidas semânticas

Reutilização de lógica

Evitar cálculos duplicados

Separação entre medidas base, derivadas e visuais

🔹 Design System em Power BI

Centralização de:

🎨 Cores (HEX)

🔤 Fontes

📐 Tamanhos

⚖️ Pesos tipográficos

Tudo controlado por medidas DAX, permitindo:

Consistência visual

Troca de tema sem refatorar visuais

Uso em SVG e formatação condicional

🔹 SVG + DAX

Uso de SVG para:

Cards customizados

Status visuais

Badges e indicadores

Barras e layouts avançados

Características:

SVG gerado via DAX

Cores e fontes dinâmicas

Total controle visual dentro do Power BI

🔹 HTML + SVG (Exploratório)

Exemplos de:

Layouts visuais

Estruturas reaproveitáveis

Prototipação de UI

⚠️ Conteúdo HTML/Css é experimental e focado em estudo e conceito.

📊 Conteúdo DAX (Exemplos)

Dentro da pasta dax/ você encontrará:

📈 Indicadores de estoque

⛔ Controle de vencimento (Vencido / Vencendo / A Vencer)

📆 Análises temporais (Mês, Mês Anterior, Variações)

📐 Medidas técnicas (Eixo Y dinâmico)

🏷️ Textos dinâmicos para títulos e cards

🎨 Medidas de estilo (cores, fontes, tamanhos)

🎯 Boas Práticas Aplicadas

✔ Organização por domínio funcional
✔ Nomenclatura semântica
✔ Uso de displayFolder
✔ Evita comentários extensos em TMDL
✔ Documentação externa (README / docs)
✔ Compatível com Power BI / Tabular Editor

⚠️ Observações Importantes

O TMDL do Power BI é restritivo:

Comentários no código devem ser mínimos

Documentação extensa fica fora do código

Este repositório prioriza:

Clareza

Reutilização

Manutenção fácil

🚀 Como Usar Este Repositório

Navegue pelas pastas (dax, svg, html)

Copie os exemplos desejados

Ajuste nomes de tabelas/colunas para seu modelo

Reutilize medidas base sempre que possível

Consulte os arquivos em /docs para padrões
