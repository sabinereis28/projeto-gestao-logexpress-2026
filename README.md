# Projeto de Gestão — LogExpress 2026

## Sobre o projeto
A LogExpress é uma empresa do segmento de logística e transporte de encomendas (*last-mile* e rotas interestaduais). Este projeto aborda a resolução de gargalos operacionais relacionados com atrasos de fretes em longas distâncias, alto consumo de combustível sem planejamento de rotas e riscos de vulnerabilidade de dados e privacidade nos sistemas de transporte.

## Objetivo
Desenvolver e aplicar soluções integradas de Gestão de Projetos, Análise de Dados, Segurança da Informação e Pesquisa Operacional para otimizar rotas de entrega, melhorar os indicadores de pontualidade (KPIs), mitigar riscos cibernéticos e adequar o sistema às normas da LGPD.

## Disciplinas integradas
- **Gestão de Projetos:** Planejamento e governança do projeto (TAP, EAP, RACI, Cronograma de Gantt e Custos).
- **Análise de Dados:** Tratamento ETL em Python, cálculo de KPIs operacionais e visualização de dados (Data Viz).
- **Segurança da Informação:** Matriz GUT de ameaças (OWASP/CVE), políticas IAM/Zero Trust e adequação à LGPD (RoPA).
- **Pesquisa Operacional:** Modelagem matemática e algoritmos de otimização em Python (biblioteca PuLP) para maximização de lucros e minimização de custos de transporte.

## Estrutura do repositório
- `01-empresa-e-problema/`: caracterização, requisitos e diagnóstico.
- `02-gestao-de-projetos/`: planejamento e documentos de gestão.
- `03-analise-de-dados/`: base, notebook, gráficos e resultados.
- `04-seguranca-da-informacao/`: riscos, controles e políticas.
- `05-pesquisa-operacional/`: modelo, código e resultados.
- `06-evidencias/`: evidências técnicas sem dados pessoais.
- `07-video/`: roteiro e link do vídeo não listado.
- `08-referencias/`: fontes consultadas.

## Como executar
Os scripts desenvolvidos foram criados para execução direta no **Google Colab** ou **Jupyter Notebook** (Python 3):

1. **Análise de Dados:**
   - Abra o notebook em `03-analise-de-dados/2_analise_entregas.ipynb`.
   - Garanta que a base `1.dados_entregas.csv` está acessível e execute as células sequencialmente.

2. **Pesquisa Operacional:**
   - Abra o notebook em `05-pesquisa-operacional/2_otimizacao_pesquisa_operacional.ipynb`.
   - Execute a célula inicial de instalação da biblioteca (`!pip install pulp`) e rode os modelos de otimização e análises *What-If*.

## Vídeo
- **Link do Vídeo (YouTube - Não Listado):** [Link a ser inserido na entrega da Fase 5]

## Privacidade
Este repositório público não contém nomes completos, RAs ou outros dados pessoais dos integrantes. A identificação acadêmica consta somente no documento final enviado ao professor.
