# 05 - Resultados das Otimizações e Análise Crítica

## 1. Resultados da Maximização (Problema 1)
- **Cenário Base:** Solução ótima encontrada de **80 Fretes Locais** e **0 Fretes Estaduais**, gerando **Lucro Máximo de R$ 24.000,00**.
- **Análise What-If (Crise de Combustível - Redução para 500L):** O algoritmo ajustou a alocação para **33 Fretes Locais** e **0 Fretes Estaduais**, garantindo o lucro possível de **R$ 9.900,00** e evitando o colapso da frota.

## 2. Resultados da Minimização (Problema 2)
- **Cenário Base:**No cenário simulado, o modelo encontrou um custo mínimo total de R$ 10.400,00, atendendo às demandas dos três clientes e respeitando as capacidades dos dois galpões. Os custos unitários utilizados são hipotéticos e foram definidos para demonstrar o funcionamento do modelo, não representando custos reais levantados pela empresa.

---

## 3. Análise Crítica Exigida (Conexão com a Gestão do Projeto)

**Pergunta Obrigatória:** *Os resultados matemáticos obtidos no Python fazem sentido para a realidade da empresa? Como a Análise de Cenários (What-If) ajuda a gerência a se preparar para imprevistos?*

**Resposta Técnico-Operacional:**
Os resultados calculados em Python mostram como a otimização pode apoiar a gestão logística da LogExpress. No cenário-base, o modelo priorizou os fretes locais, pois, considerando as restrições de horas e combustível definidas, essa combinação gera o maior lucro total de R$ 24.000,00. Na simulação de crise, com a redução da disponibilidade de combustível para 500 litros, o lucro possível caiu para R$ 9.900,00, mantendo 33 fretes locais e nenhum estadual. A análise What-If permite comparar cenários e preparar alternativas para imprevistos, ajudando a gerência a tomar decisões com base nos recursos disponíveis.

**Pergunta Obrigatória:** *Como a Pesquisa Operacional pode contribuir para a redução dos custos de transporte da LogExpress?*

**Resposta Técnico-Operacional:**
Do ponto de vista técnico, o modelo de minimização utilizou a programação linear inteira para distribuir as entregas entre os galpões de São Paulo e do Rio de Janeiro, respeitando suas capacidades e atendendo à demanda dos três clientes. Na simulação, o custo total mínimo calculado foi de R$ 10.400,00, considerando os custos unitários hipotéticos definidos para o modelo.

Do ponto de vista operacional, a aplicação desse método pode auxiliar a LogExpress a escolher combinações de rotas mais econômicas, aproveitar melhor a capacidade dos galpões e planejar a distribuição das cargas. Entretanto, como os custos utilizados são hipotéticos, o resultado demonstra o funcionamento do modelo, mas não comprova uma economia real. Para aplicá-lo à operação da empresa, seria necessário utilizar dados reais de transporte.
