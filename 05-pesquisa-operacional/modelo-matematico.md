# 05 - Modelagem Matemática (Pesquisa Operacional)

## 1. Problema 1: Maximização de Lucro (Alocação de Fretes)

### Variáveis de Decisão:
- $x_A$: Quantidade de Fretes Locais (Curta distância)
- $x_B$: Quantidade de Fretes Estaduais (Longa distância)

### Função Objetivo:
$$\text{Max } Z = 300x_A + 800x_B$$

### Restrições Operacionais:
1. **Jornada de Trabalho (Horas):** $2x_A + 6x_B \le 160$
2. **Cota de Combustível (Litros):** $15x_A + 50x_B \le 1200$
3. **Não-Negatividade e Integridade:** $x_A, x_B \ge 0 \quad (\text{Inteiros})$

---

## 2. Problema 2: Minimização de Custos (Rede de Transporte)

### Variáveis de Decisão:
- $x_{ij}$: Quantidade de cargas enviadas do Galpão $i$ ($i \in \{\text{SP}, \text{RJ}\}$) para o Cliente $j$ ($j \in \{\text{C1}, \text{C2}, \text{C3}\}$).

### Função Objetivo:
$$\text{Min } Z = \sum_{i=1}^{2} \sum_{j=1}^{3} c_{ij} x_{ij}$$

### Restrições Operacionais:
1. **Capacidade Máxima dos Galpões (Oferta):**
   - $\sum x_{\text{SP}, j} \le 50$
   - $\sum x_{\text{RJ}, j} \le 40$
2. **Demanda Obrigatória dos Clientes:**
   - $\sum x_{i, \text{C1}} = 30$
   - $\sum x_{i, \text{C2}} = 35$
   - $\sum x_{i, \text{C3}} = 25$
