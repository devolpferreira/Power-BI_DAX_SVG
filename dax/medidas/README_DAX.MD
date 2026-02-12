📌 Visão Geral
A tabela _Medidas centraliza todas as medidas DAX do modelo, organizadas por domínio funcional, tempo, status de estoque, pedidos, programação, configurações visuais (cores/fontes) e textos auxiliares.
Objetivos principais:
•	Padronização de cálculos
•	Reutilização de lógica
•	Clareza semântica
•	Separação entre lógica, visual e configuração

🧱 Estrutura Geral
•	Tipo: Measures Table (tabela técnica)
•	Sem relacionamento
•	Uso: Cálculos, indicadores, rótulos, SVG, formatação condicional e UI
•	Organização: via displayFolder

🕒 1.0 – Tempo / Estoque Geral
🔹 Medidas Base
•	1 Total Estoque
Valor total do estoque (R$), respeitando contexto de data.
Evita exibir zero quando não há valor no nível diário.
•	1 Total Estoque Formatado
Versão textual do total (K / MI / BI), usada em cards e títulos.
•	1.1 Total Mês Anterior
Total do estoque no mês anterior (base para variações).
•	1.1.1 Percentual Diferença Total Mês a Mês
Variação percentual do estoque em relação ao mês anterior.

⛔ 1.1 – Vencido
•	1.1 Total Vencido
Total do estoque com status VENCIDO.
•	1.1 Percentual Vencido
Percentual do estoque vencido sobre o total.
•	1.1.2 Total Vencido Mês Anterior
Total vencido no mês anterior.
•	1.1.2 Percentual Diferença Vencido Mês a Mês
Variação percentual do vencido mês a mês.

⚠️ 1.2 – Vencendo
•	1.2 Total Vencendo
Total do estoque com status VENCENDO.
•	1.1.2 Percentual Vencendo
Percentual do estoque vencendo sobre o total.
•	1.2 Total Vencendo Mês Anterior
Valor vencendo no mês anterior.
•	1.1.2 Percentual Diferença Vencendo Mês a Mês
Variação percentual mês a mês.

✅ 1.3 – A Vencer
•	1.3 Total A Vencer
Total do estoque com status A VENCER.
•	1.3 Percentual A Vencer
Percentual sobre o estoque total.
•	1.1.3 Total A Vencer Mês Anterior
Base de comparação mensal.
•	1.1.3 Percentual Diferença A Vencer Mês a Mês
Variação percentual mensal.

📐 1.4 – Configuração (Gráficos)
•	1.1 Eixo y Maximo Estoque Total
•	1.1 Eixo y Maximo Estoque Total Status
•	1.1 Eixo y Maximo Total Aplicado
Medidas técnicas usadas para:
•	Definir limites de eixo Y
•	Criar espaçamento visual em gráficos
•	Evitar “estouro” de colunas

🧪 1.5 – Estoque Químicos
🔹 Valores
•	Valor Estoque Atual
•	Valor Total Vencido
•	Valor Total Vencendo
•	Valor Total A Vencer
🔹 Percentuais
•	Perc. Vencido
•	Perc. Vencendo
•	Perc. A Vencer
🔹 Quantidades
•	2.1 Qtd Vencidos
•	2.1 Qtd Vencendo
•	2.1 Qtd A Vencer
•	2.1 Qtd Total Estoque
•	2.1 Total Estoque Geral
🔹 Resumos Textuais
•	Resumo Estoque Produtos
•	Resumo Produtos Estoque

📆 Faixas de Vencimento (Dias)
🔹 Valor (R$)
•	2 Vencimento em 30 Dias
•	2 Vencimento em 60 Dias
•	2 Vencimento em 90 Dias
•	2 Vencimento em 120 Dias
🔹 Quantidade
•	2.1 Qtd Vencimento em 30 Dias
•	2.1 Qtd Vencimento em 60 Dias
•	2.1 Qtd Vencimento em 90 Dias
•	2.1 Qtd Vencimento em 120 Dias

📦 1.6 – Pedidos
•	Total de Pedidos
•	Total de Pedidos Ano Anterior
•	Variação % Ano Anterior
•	Total de Pedidos Pendentes
•	Quantidade de Pedido

🛠️ Programação / Operação
•	Total Permitido
•	Total Adicional
•	Total Em O.S
•	Saldo Restante
•	% Executado
•	QuantidadeProgramadoItens
•	QuantidadeEntreguePorProduto
•	Eixo y Maximo Total Programado
•	Eixo y Maximo Total Programado Operacao

🏷️ Textos Auxiliares / UI
•	Mes Selecionado (1,2,3,4 / Status / Listagem)
•	Tipo Selecionado
•	Tipo Selecionado Status
•	Tipo Selecionado Vencido A Vencer
•	Qtd O.S Texto Auxiliar
•	Tempo de Estoque
•	Ultima Atualização / Ultima Atualização Novo
•	Status Dias

🎨 Styles Config (Design System)
🔹 Fontes
•	_Fonte_Padrao
•	_Font_Size_9 / 10 / 12 / 13 / 14
•	_Font_Weight_Normal / Semi_Bold / Bold
🔹 Cores (HEX)
•	Amarelos, Verdes, Vermelhos, Neutros
•	Usadas em:
o	SVG
o	Formatação condicional
o	UI dinâmica
Exemplo:
•	_Cor_Verde_Esmeralda_Profundo → sucesso
•	_Cor_Vermelho_Escuro → erro crítico
•	_Cor_Amarelo_Pastel_Muito_Claro → fundo suave

🧠 Boas Práticas Aplicadas
•	✔ Separação entre lógica e visual
•	✔ Medidas base reutilizadas
•	✔ Textos dinâmicos centralizados
•	✔ Design System em DAX
•	✔ Evita duplicação de lógica

