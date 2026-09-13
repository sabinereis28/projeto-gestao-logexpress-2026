# projeto-gestao-logexpress-2026

## Sobre o projeto
A LogExpress é uma empresa de logística focada em soluções de logística e transporte de encomendas. Com o projeto iremos melhorar processos operacionais, reduzir custos de transporte, evitar atrasos de entregas e garantir a segurança e privacidade dos dados dos clientes.

## Objetivo
Desenvolver e aplicar soluções de Gestão de Projetos, Análise de Dados, Segurança da Informação e Pesquisa Operacional para otimizar rotas, melhorar os indicadores de entrega e adequar o sistema de acordo com as normas da LGPD.

## Os Problemas e Soluções do Projeto
A LogExpress é uma empresa de logística que enfrenta gargalos operacionais no fluxo diário de entregas (*last-mile*), custos operacionais elevados e riscos no tratamento de dados de clientes. Para resolver esses problemas, o projeto estruturará as seguintes soluções através das 4 disciplinas:

### 1. Custos logísticos elevados e falta de previsibilidade de entregas
* **O Problema:** Atrasos frequentes de entregas e alto consumo de combustível devido ao planejamento ineficiente de rotas e alocação inadequada de cargas nos veículos.
* **Como será resolvido (Pesquisa Operacional):** Desenvolveremos algoritmos em Python (utilizando a biblioteca `pulp`) para resolver dois problemas matemáticos:
  - **Maximização de Carga/Lucro:** Definir o mix ideal de encomendas enviadas por viagem respeitando limites de peso e volume.
  - **Minimização de Custos Logísticos:** Otimizar as rotas de distribuição dos hubs para os centros de entregas com o menor custo de frete.

### 2. Falta de indicadores (KPIs) e dados descentralizados
* **O Problema:** A gestão da LogExpress não possui visibilidade em tempo real sobre a taxa de entregas concluídas no prazo, o custo médio por frete nem sobre o histórico de atrasos.
* **Como será resolvido (Análise de Dados em Python):** Implementaremos rotinas de limpeza de dados (ETL em Pandas) para processar os históricos de transporte da empresa, calculando KPIs essenciais (Taxa de Entregas no Prazo, Custo Médio por Frete) e gerando gráficos analíticos (Scatter Plots e Histogramas) para tomada de decisão.

### 3. Vulnerabilidade de dados e riscos de não conformidade com a LGPD
* **O Problema:** Tratamento de dados sensíveis de clientes (nome, CPF, endereço de entrega) sem controle estrito de acessos, com risco de vazamentos ou penalidades legais.
* **Como será resolvido (Segurança da Informação):** Mapearemos vulnerabilidades críticas do sistema através da **Matriz GUT**, definiremos políticas de acesso de identidades (IAM / RBAC) e implementaremos os requisitos da **LGPD** (Base Legal para tratamento de dados e portal de atendimento ao titular).

### 4. Falta de controle de escopo, prazos e orçamento
* **O Problema:** Riscos de estouro de custos e atrasos nas entregas de melhorias operacionais por falta de um planejamento estruturado de projeto.
* **Como será resolvido (Gestão de Projetos):** Formalizaremos a governança do projeto através do **Termo de Abertura (TAP)** com Metas SMART, **Estrutura Analítica do Projeto (EAP)**, **Matriz RACI**, **Gráfico de Gantt** para controle de prazos e **Matriz de Riscos/Comunicação**.

## Estrutura do Repositório
- `01-empresa-e-problema/`: Caracterização da LogExpress e diagnóstico do problema.
- `02-gestao-de-projetos/`: Documentos de planejamento (TAP, EAP, Cronograma, Custos).
- `03-analise-de-dados/`: Bases de dados, notebooks de ETL, gráficos e análises.
- `04-seguranca-da-informacao/`: Matriz GUT, políticas IAM e adequação à LGPD.
- `05-pesquisa-operacional/`: Modelos matemáticos de otimização e notebooks executáveis.
- `06-evidencias/`: Comprovações organizacionais e atas.
- `07-video/`: Roteiro e link da apresentação final.
- `08-referencias/`: Referências bibliográficas e fontes consultadas.

## Como Executar os Códigos
Os scripts desenvolvidos nas disciplinas de Análise de Dados e Pesquisa Operacional foram criados para execução no Google Colab ou Jupyter Notebook.
1. Abra os arquivos `.ipynb` localizados nas pastas `03-analise-de-dados/` e `05-pesquisa-operacional/`.
2. Certifique-se de carregar as bases de dados `.csv` indicadas.
3. Execute as células em ordem sequencial.
   
## Vídeo de Apresentação
- Link do vídeo (Não Listado): Pendente

## Privacidade
Este repositório público não contém nomes completos, RAs ou outros dados pessoais dos integrantes do grupo, atendendo às diretrizes do projeto integrador. A identificação acadêmica consta exclusivamente no documento final enviado ao professor.
