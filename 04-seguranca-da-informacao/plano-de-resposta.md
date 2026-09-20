# Plano de Resposta a Incidentes e Mitigação Técnica

## 1. Análise Crítica do Risco Mais Grave (SQL Injection)
A vulnerabilidade de maior impacto e urgência identificada em nossa Matriz GUT (Nota 125) foi a **Injeção de SQL (SQL Injection - OWASP A03)** na tela de busca e autenticação de usuários. Em um cenário real, um invasor poderia inserir instruções maliciosas como `' OR 1=1 --` nos campos de formulário para burlar a autenticação ou apagar tabelas essenciais do banco de dados MySQL.

## 2. Técnica de Mitigação e Correção Adotada
Para anular essa vulnerabilidade de forma definitiva no código da LogExpress, adotamos:
1. **Consultas Preparadas (*Prepared Statements*) e ORM:** No backend Python, utilizamos abstrações de banco (SQLAlchemy / Pandas) que sanitizam automaticamente qualquer entrada de usuário, tratando caracteres especiais como literais e nunca como instruções executáveis.
2. **Princípio do Menor Privilégio:** O usuário da aplicação web possui permissões restritas no banco de dados, sendo impedido de executar comandos destrutivos de estrutura (ex: `DROP TABLE` ou `ALTER TABLE`).

## 3. Protocolo de Resposta a Vazamentos de Dados (LGPD)
Em caso de confirmação de incidente ou vazamento de dados:
1. **Contenção Imediata:** Isolamento do servidor afetado e revogação das chaves de API/sessões ativas em até 2 horas.
2. **Investigação e Auditoria:** Análise dos logs imutáveis para identificar a origem e os dados impactados.
3. **Notificação Oficial:** Comunicação formal à Autoridade Nacional de Proteção de Dados (ANPD) e aos titulares afetados no prazo legal.
