# 05 - Resultados das Otimizações e Análise Crítica

## 1. Resultados da Maximização (Problema 1)
- **Cenário Base:** Solução ótima encontrada de **33 Fretes Locais** e **14 Fretes Estaduais**, gerando **Lucro Máximo de R$ 21.100,00**.
- **Análise What-If (Crise de Combustível - Redução para 500L):** O algoritmo ajustou a alocação para **33 Fretes Locais** e **0 Fretes Estaduais**, garantindo o lucro possível de **R$ 9.900,00** e evitando o colapso da frota.

## 2. Resultados da Minimização (Problema 2)
- **Cenário Base:** Distribuição ótima com **Custo Mínimo Total de R$ 10.550,00**.
- **Análise What-If (Bloqueio de Rodovia SP-C3):** O algoritmo redirecionou o fornecimento do Cliente C3 para vir do Galpão RJ, contornando o gargalo sem custos excessivos.

---

## 3. Análise Crítica Exigida (Conexão com a Gestão do Projeto)

**Pergunta Obrigatória:** *Os resultados matemáticos obtidos no Python fazem sentido para a realidade da empresa? Como a Análise de Cenários (What-If) ajuda a gerência a se preparar para imprevistos?*

**Resposta Técnico-Operacional:**
Os resultados calculados em Python confirmam que a intuição sozinha não basta para gerir frotas logísticas. Na maximização, ficou provado que focar apenas em fretes de longa distância (que possuem maior valor bruto) consome rapidamente a cota de combustível e inviabiliza a operação em momentos de escassez. A simulação *What-If* permitiu à gerência da LogExpress criar planos de contingência pré-calculados para crises de abastecimento e bloqueios de rodovias. Assim, quando um imprevisto ocorre no mundo real, a tomada de decisão é imediata e respaldada por algoritmos, mitigando riscos financeiros e operacionais.
