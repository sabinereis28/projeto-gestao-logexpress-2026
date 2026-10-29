# 03 - Análise de Dados e Indicadores Operacionais (LogExpress)

**Disciplina:** Análise de Dados / Inteligência de Negócios  
**Projeto:** Otimização e Segurança LogExpress  

---

## 2.1 Tratamento de Dados (ETL) e KPIs
- **Tratamento de Dados (ETL): Foi realizada a remoção dos registros com valores nulos na coluna "dias_decorridos", utilizando a biblioteca "pandas" no Google Colab.
- **KPI 1 - Taxa de Entregas no Prazo: 54,5% das entregas foram realizadas dentro do prazo.
- **KPI 2 - Custo Médio por Frete: R$ 319,14.
- **Faturamento Total Mapeado:** R$ R$ 3.510,50.

---

## 2.2 Análise Estatística Descritiva
- **Média de Dias Decorridos:** 5,00 dias.
- **Desvio Padrão dos Atrasos:** 3.38 dias (indica alta variação e instabilidade nos prazos de rotas mais longas).
- **Correlação de Pearson (Distância vs. Custo de Combustível):** **0.93** (indicando forte associação positiva entre a distância percorrida e o custo de combustível na base analisada.).

---

## 2.3 Visualização de Dados
O notebook `analise.ipynb` gera três gráficos principais para análise operacional:
1. **Gráfico de Barras:** Comparativo entre entregas no prazo e entregas em atraso.
2. **Gráfico de Dispersão:** Relação linear entre a distância percorrida (km) e o custo com combustível (R$).
3. **Boxplot:** Identificação de *outliers* de tempo nos fretes de longa distância.

![Painel de Gráficos e KPIs da LogExpress](graficos.png)

---

## 2.4 Análise Crítica (Conexão com a Gestão do Projeto)

**Pergunta Exigida:** *Baseado nas correlações estatísticas, nos outliers encontrados e no principal KPI calculado, qual é o maior gargalo operacional da empresa?*

**Resposta e Diagnóstico:**
Com base nos indicadores calculados, observa-se que a taxa de entregas no prazo é de 54,5%, indicando que há oportunidades de melhoria na pontualidade. A correlação de Pearson de 0,93 aponta uma forte associação positiva entre a distância percorrida e o custo de combustível na base analisada. Esses resultados sugerem a importância de melhorar o planejamento logístico e avaliar a distribuição das cargas. A análise fornece subsídios para as propostas de otimização apresentadas na etapa de Pesquisa Operacional. Como os resultados se referem à base de dados utilizada, eles devem ser interpretados dentro dos limites dessa amostra.
