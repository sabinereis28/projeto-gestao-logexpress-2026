# Matriz de Riscos de Segurança (GUT / OWASP / CVE)

Análise de vulnerabilidades identificadas na infraestrutura tecnológica da LogExpress com base na Matriz GUT ($G \times U \times T$):

| ID | Ameaça / Vulnerabilidade | Fonte / Padrão | Justificativa no Contexto LogExpress | G | U | T | Nota GUT |
| :--- | :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| 01 | **SQL Injection (A03:2021)** | OWASP A03 | Invasor injetar comando no campo de busca de entregas e apagar o banco de dados. | 5 | 5 | 5 | **125** |
| 02 | **Broken Access Control / IDOR** | OWASP A01 | Motorista alterar o ID na URL e conseguir visualizar dados e rotas de outros motoristas. | 5 | 5 | 4 | **100** |
| 03 | **Ataque DDoS** | CVE / Geral | Inundar o servidor de requisições e derrubar o rastreamento de cargas em tempo real. | 4 | 5 | 4 | **80** |
| 04 | **Credenciais Padrão / Inseguras** | OWASP A07 | Manter a senha "admin123" no painel da transportadora e sofrer invasão direta. | 5 | 4 | 4 | **80** |
| 05 | **Ransomware no Servidor** | CVE / Geral | Invasor criptografar os dados de frete e pedir resgate em criptomoeda para liberar. | 5 | 4 | 4 | **80** |
| 06 | **Vazamento de Chaves API** | OWASP A05 | Subir no GitHub a chave da API do Google Maps usada para calcular as rotas. | 4 | 4 | 4 | **64** |
| 07 | **Cross-Site Scripting (XSS)** | OWASP A03 | Injetar código malicioso no campo de observações da entrega para roubar sessão do admin. | 4 | 3 | 4 | **48** |
| 08 | **Falta de Logs de Auditoria** | OWASP A09 | Alguém alterar o valor do frete e a equipe não conseguir descobrir quem fez a mudança. | 3 | 4 | 3 | **36** |
| 09 | **Sessão Aberta Sem Timeout** | OWASP A07 | Deixar a sessão do sistema aberta no computador do galpão e outro funcionário mexer. | 3 | 3 | 3 | **27** |
| 10 | **Man-in-the-Middle (MitM)** | OWASP A02 | Trafegar senhas em HTTP puro na rede Wi-Fi do galpão e ter os dados interceptados. | 4 | 3 | 2 | **24** |
| 11 | **Armazenamento de Senha em Texto**| OWASP A02 | Salvar senhas sem criptografia no banco e vazá-las caso o banco seja copiado. | 4 | 3 | 2 | **24** |
| 12 | **Injeção de Código em Uploads** | OWASP A03 | Subir um arquivo `.php` ou `.exe` no lugar do comprovante de entrega (foto). | 4 | 2 | 2 | **16** |
| 13 | **Dependências Desatualizadas** | OWASP A06 | Usar biblioteca antiga do Python com falha de segurança conhecida na leitura de CSV. | 3 | 2 | 2 | **12** |
| 14 | **Ataque de Força Bruta no Login** | OWASP A07 | Robô testar milhares de senhas por segundo na tela de login até acertar a senha. | 3 | 2 | 2 | **12** |
| 15 | **Exposição de Dados no Error Log**| OWASP A05 | Erro no sistema mostrar o caminho de pastas do servidor ou senha do banco na tela. | 2 | 2 | 2 | **8** |
| 16 | **CSRF (Cross-Site Request Forgery)**| OWASP A01| Fazer o admin clicar em link falso e confirmar uma entrega sem querer. | 2 | 2 | 2 | **8** |
| 17 | **Backup Exposto na Web** | OWASP A05 | Deixar arquivo `backup.sql` salvo na pasta pública do servidor web. | 3 | 2 | 1 | **6** |
| 18 | **Envio de e-mail Inseguro (Spoofing)**| CVE / Geral | Enviar e-mail falso se passando pela LogExpress para dar golpe nos clientes. | 2 | 2 | 1 | **4** |
| 19 | **Redirecionamento Inseguro** | OWASP A01 | Sistema redirecionar o motorista para um site falso de pagamento de pedágio. | 2 | 1 | 1 | **2** |
| 20 | **Navegador sem Atualização** | Geral | Usar navegador muito antigo no computador da expedição para acessar o sistema. | 1 | 1 | 1 | **1** |
