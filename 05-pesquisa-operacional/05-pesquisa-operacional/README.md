# 05 - Pesquisa Operacional e Otimização Algorítmica

**Disciplina:** Pesquisa Operacional  
**Projeto:** Otimização e Segurança LogExpress  
**Tecnologia:** Python 3 (Biblioteca PuLP no Google Colab)  

---

## 4.1 Problema 1: Maximização de Lucros na Alocação de Fretes

### Cenário de Negócio:
A LogExpress dispõe de recursos operacionais limitados no mês (160 horas totais de jornada de motoristas e cota mensal de 1.200 litros de combustível). A empresa precisa decidir a combinação ideal entre **Fretes Locais ($x_A$)** e **Fretes Estaduais ($x_B$)** para obter o maior lucro possível.

### Modelagem Matemática:
- **Variáveis de Decisão:**  
  - $x_A$: Quantidade de Fretes Locais (Lucro Líquido: R$ 300,00)  
  - $x_B$: Quantidade de Fretes Estaduais (Lucro Líquido: R$ 800,00)
- **Função Objetivo:**  
  $$\text{Max } Z = 300x_A + 800x_B$$
- **Restrições Técnicas:**  
  - Jornada de Trabalho: $2x_A + 6x_B \le 160$ horas  
  - Consumo de Combustível: $15x_A + 50x_B \le 1200$ litros  
  - Não-negatividade e Integridade: $x_A, x_B \ge 0 \quad (\text{Inteiros})$

### Resultados Obtidos via Algoritmo (PuLP):
- **Cenário Base:** O algoritmo determinou como solução ótima a realização de **33 Fretes Locais** e **14 Fretes Estaduais**, atingindo o **Lucro Máximo de R$ 21.100,00**.
- **Análise de Cenário (What-If - Crise de Combustível):** Simula-se uma restrição na oferta de combustível de 1.200L para 500L. O algoritmo recalculou a decisão, orientando a realização de **33 Fretes Locais** e apenas **0 Fretes Estaduais**, resultando em um lucro ajustado de **R$ 9.900,00**. Isso prova que, em escassez de combustível, os fretes estaduais consomem muito insumo e travam a operação.

---

## 4.2 Problema 2: Minimização de Custos de Distribuição e Transporte

### Cenário de Negócio:
A empresa precisa enviar cargas a partir de 2 galpões centrais (SP e RJ) para 3 polos de clientes (C1, C2 e C3), respeitando a capacidade máxima das sedes e atendendo integralmente à demanda dos clientes pelo menor custo de frete/pedágio.

### Modelagem Matemática:
- **Variáveis de Decisão:** $x_{ij}$ = Quantidade de cargas enviadas da Sede $i$ para o Cliente $j$.
- **Função Objetivo:**  
  $$\text{Min } Z = \sum_{i=1}^{2} \sum_{j=1}^{3} c_{ij} x_{ij}$$
- **Restrições Técnicas:**  
  - Oferta SP $\le 50$; Oferta RJ $\le 40$  
  - Demanda C1 $= 30$; Demanda C2 $= 35$; Demanda C3 $= 25$

### Resultados Obtidos via Algoritmo (PuLP):
- **Cenário Base:** A distribuição ótima enviou 30 cargas de SP para C1, 20 cargas de SP para C2, 15 cargas de RJ para C2 e 25 cargas de RJ para C3. **Custo Mínimo Total: R$ 10.550,00**.
- **Análise de Cenário (What-If - Aumento de Custo de Rota):** Simula-se um bloqueio na rodovia de SP para C3 que aumenta o custo de frete nessa rota de R$ 200 para R$ 450. O algoritmo automaticamente redirecionou todas as cargas de C3 para virem do Galpão do RJ, absorvendo a demanda com um **Custo Ajustado de R$ 10.550,00**, provando a resiliência da malha logística sem elevar custos desnecessariamente.

---

## 4.3 Análise Crítica Exigida (Otimização e Negócios)

**Resposta Obrigatória ao Relatório Técnico:**

Os resultados matemáticos obtidos através dos algoritmos em Python fazem total sentido para a realidade operacional da LogExpress. Na maximização, a matemática comprovou que focar apenas em fretes de longa distância (que parecem mais lucrativos à primeira vista) não é a melhor escolha quando há gargalos de combustível ou horas de trabalho, pois os fretes curtos entregam maior margem relativa por hora trabalhada. Já na minimização, o algoritmo de transporte identificou a combinação exata de rotas que atende 100% dos clientes zerando o desperdício de viagens vazias.

A Análise de Cenários (*What-If*) é uma ferramenta indispensável para a gestão de riscos do projeto. Em vez de a gerência tomar decisões baseadas em palpites durante uma crise (como um aumento no preço do combustível ou interdição de estradas), os modelos preditivos em Python permitem rodar simulações em segundos. Isso garante que a LogExpress já tenha planos de contingência pré-calculados, sabendo exatamente quais rotas priorizar e onde cortar custos para manter a empresa lucrativa mesmo diante de imprevistos do mercado.
