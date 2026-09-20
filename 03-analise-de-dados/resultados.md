# 03 - Análise de Dados e Indicadores Operacionais (LogExpress)

**Disciplina:** Análise de Dados / Inteligência de Negócios  
**Projeto:** Otimização e Segurança LogExpress  

---

## 2.1 Tratamento de Dados (ETL) e KPIs
- **Tratamento de Dados (ETL):** Executada a remoção de registos nulos na coluna de dias decorridos via biblioteca `pandas` no Google Colab.
- **KPI 1 - Taxa de Entregas no Prazo:** 63.6% das entregas foram efetuadas dentro do prazo limite.
- **KPI 2 - Custo Médio por Frete:** R$ 321.41 por viagem realizada.
- **Faturamento Total Mapeado:** R$ 3,535.50.

---

## 2.2 Análise Estatística Descritiva
- **Média de Dias Decorridos:** 4.73 dias.
- **Desvio Padrão dos Atrasos:** 3.44 (indica alta variação e instabilidade nos prazos de rotas mais longas).
- **Correlação de Pearson (Distância vs. Custo de Combustível):** **0.98** (correlação fortíssima, comprovando matematicamente que o aumento da distância impacta diretamente o custo de combustível).

---

## 2.3 Visualização de Dados
O notebook `analise_entregas.ipynb` gera três gráficos principais para análise operacional:
1. **Gráfico de Barras:** Comparativo entre entregas no prazo e entregas em atraso.
2. **Gráfico de Dispersão:** Relação linear entre a distância percorrida (km) e o custo com combustível (R$).
3. **Boxplot:** Identificação de *outliers* de tempo nos fretes de longa distância.

![Painel com os 3 Gráficos de Análise](graficos.md/graficos.md)

---

## 2.4 Análise Crítica (Conexão com a Gestão do Projeto)

**Pergunta Exigida:** *Baseado nas correlações estatísticas, nos outliers encontrados e no principal KPI calculado, qual é o maior gargalo operacional da empresa?*

**Resposta e Diagnóstico:**
Com base na análise de estatística descritiva e no gráfico Boxplot, identificou-se que o maior gargalo operacional da LogExpress está concentrado nas rotas de longa distância (acima de 300 km), onde os atrasos geram acréscimos discrepantes (*outliers*) no tempo de entrega que chegam a 12 dias. A taxa de sucesso de apenas 63.6% e a forte correlação de Pearson (0.98) entre distância e custo de combustível comprovam que fretes longos executados sem otimização consomem a margem financeira da empresa. Estes dados numéricos justificam diretamente as metas e o escopo definidos no nosso TAP (Disciplina 1), confirmando a necessidade imperativa de desenvolver algoritmos de otimização de rotas e cargas na etapa de Pesquisa Operacional para estancar o prejuízo operacional.
