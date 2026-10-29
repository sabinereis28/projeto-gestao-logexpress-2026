# 05 - Resultados das Otimizações e Análise Crítica

## 1. Resultados da Maximização (Problema 1)
- **Cenário Base:** Solução ótima encontrada de **80 Fretes Locais** e **0 Fretes Estaduais**, gerando **Lucro Máximo de R$ 24.000,00**.
- **Análise What-If (Crise de Combustível - Redução para 500L):** O algoritmo ajustou a alocação para **33 Fretes Locais** e **0 Fretes Estaduais**, garantindo o lucro possível de **R$ 9.900,00** e evitando o colapso da frota.

## 2. Resultados da Minimização (Problema 2)
- **Cenário Base:** Distribuição ótima com **Custo Mínimo Total de R$ 10.550,00**.
- **Análise What-If (Bloqueio de Rodovia SP-C3):** O algoritmo redirecionou o fornecimento do Cliente C3 para vir do Galpão RJ, contornando o gargalo sem custos excessivos.

---

## 3. Análise Crítica Exigida (Conexão com a Gestão do Projeto)

**Pergunta Obrigatória:** *Os resultados matemáticos obtidos no Python fazem sentido para a realidade da empresa? Como a Análise de Cenários (What-If) ajuda a gerência a se preparar para imprevistos?*

**Resposta Técnico-Operacional:**
Os resultados calculados em Python mostram como a otimização pode apoiar a gestão logística da LogExpress. No cenário-base, o modelo priorizou os fretes locais, pois, considerando as restrições de horas e combustível definidas, essa combinação gera o maior lucro total de R$ 24.000,00. Na simulação de crise, com a redução da disponibilidade de combustível para 500 litros, o lucro possível caiu para R$ 9.900,00, mantendo 33 fretes locais e nenhum estadual. A análise What-If permite comparar cenários e preparar alternativas para imprevistos, ajudando a gerência a tomar decisões com base nos recursos disponíveis.
