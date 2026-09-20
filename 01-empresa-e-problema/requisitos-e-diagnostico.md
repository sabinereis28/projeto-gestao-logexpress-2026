# 01 - Requisitos e Diagnóstico de Problemas

## Os Problemas e Soluções do Projeto (Diagnóstico)

### 1. Custos logísticos elevados e falta de previsibilidade de entregas
* **O Problema:** Atrasos frequentes de entregas e alto consumo de combustível devido ao planejamento ineficiente de rotas e alocação inadequada de cargas nos veículos.
* **Solução Proposta (Pesquisa Operacional):** Algoritmos em Python (biblioteca `pulp`) para resolver problemas de Maximização de Carga/Lucro e Minimização de Custos Logísticos.

### 2. Falta de indicadores (KPIs) e dados descentralizados
* **O Problema:** A gestão da LogExpress não possui visibilidade em tempo real sobre a taxa de entregas concluídas no prazo, o custo médio por frete nem sobre o histórico de atrasos.
* **Solução Proposta (Análise de Dados):** Rotinas de limpeza de dados (ETL em Pandas) para processar os históricos de transporte, calculando KPIs essenciais e gerando gráficos analíticos.

### 3. Vulnerabilidade de dados e riscos de não conformidade com a LGPD
* **O Problema:** Tratamento de dados sensíveis de clientes (nome, CPF, endereço) sem controle estrito de acessos, com risco de vazamentos ou penalidades legais.
* **Solução Proposta (Segurança da Informação):** Mapeamento de vulnerabilidades através da Matriz GUT, definição de políticas IAM/RBAC e cumprimento dos requisitos da LGPD (RoPA e bases legais).

### 4. Falta de controle de escopo, prazos e orçamento
* **O Problema:** Riscos de estouro de custos e atrasos nas entregas de melhorias operacionais por falta de um planejamento estruturado.
* **Solução Proposta (Gestão de Projetos):** Governança através do Termo de Abertura (TAP), Estrutura Analítica do Projeto (EAP), Matriz RACI, Cronograma de Gantt e Matriz de Riscos/Custos.
