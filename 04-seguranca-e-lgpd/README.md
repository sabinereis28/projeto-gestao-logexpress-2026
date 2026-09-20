# 04 - Segurança da Informação e Privacidade (SecOps & LGPD)

**Disciplina:** Segurança da Informação e Privacidade  
**Projeto:** Otimização e Segurança LogExpress  
**Papel da Equipe:** Blue Team / SecOps  

---

## 3.1 Mapeamento de Ameaças e Matriz GUT (OWASP / CVE)

Abaixo estão listadas 20 ameaças reais pesquisadas em bases como OWASP Top 10 e CVE, analisadas sob a matriz GUT ($G \times U \times T$) para a operação da LogExpress.

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
| 11 | **Armazenamento de Senha em Texto** | OWASP A02 | Salvar senhas sem criptografia no banco e vazá-las caso o banco seja copiado. | 4 | 3 | 2 | **24** |
| 12 | **Injeção de Código em Uploads** | OWASP A03 | Subir um arquivo `.php` ou `.exe` no lugar do comprovante de entrega (foto). | 4 | 2 | 2 | **16** |
| 13 | **Dependências Desatualizadas** | OWASP A06 | Usar biblioteca antiga do Python com falha de segurança conhecida na leitura de CSV. | 3 | 2 | 2 | **12** |
| 14 | **Ataque de Força Bruta no Login** | OWASP A07 | Robô testar milhares de senhas por segundo na tela de login até acertar a senha. | 3 | 2 | 2 | **12** |
| 15 | **Exposição de Dados no Error Log** | OWASP A05 | Erro no sistema mostrar o caminho de pastas do servidor ou senha do banco na tela. | 2 | 2 | 2 | **8** |
| 16 | **CSRF (Cross-Site Request Forgery)**| OWASP A01 | Fazer o admin clicar em link falso e confirmar uma entrega sem querer. | 2 | 2 | 2 | **8** |
| 17 | **Backup Exposto na Web** | OWASP A05 | Deixar arquivo `backup.sql` salvo na pasta pública do servidor web. | 3 | 2 | 1 | **6** |
| 18 | **Envio de e-mail Inseguro (Spoofing)**| CVE / Geral | Enviar e-mail falso se passando pela LogExpress para dar golpe nos clientes. | 2 | 2 | 1 | **4** |
| 19 | **Redirecionamento Inseguro** | OWASP A01 | Sistema redirecionar o motorista para um site falso de pagamento de pedágio. | 2 | 1 | 1 | **2** |
| 20 | **Navegador sem Atualização** | Geral | Usar navegador muito antigo no computador da expedição para acessar o sistema. | 1 | 1 | 1 | **1** |

---

## 3.2 Políticas de Acesso e Identidade (IAM e Zero Trust)

Abaixo foram definidas 20 políticas de autenticação e autorização para proteger o sistema da LogExpress:

1. **Hashing de Senhas (bcrypt):** As senhas dos usuários nunca serão salvas em texto puro, usando bcrypt com *salt*. *Justificativa:* Caso o banco seja vazado, os invasores não conseguem ler as senhas.
2. **Autenticação de Dois Fatores (2FA):** Obrigatório 2FA via aplicativo para o perfil Admin. *Justificativa:* Evita invasão mesmo se a senha do administrador for descoberta.
3. **Controle de Acesso Baseado em Cargos (RBAC):** Separar perfis em Cliente, Motorista e Admin. *Justificativa:* Garante que motoristas não alterem o valor do frete e clientes não vejam cargas de terceiros.
4. **Uso de Tokens JWT com Validade:** Requisições via API usarão tokens JWT com tempo de expiração de 2 horas. *Justificativa:* Evita que tokens antigos sejam reutilizados se forem capturados.
5. **Bloqueio por Tentativas Incorretas:** Bloquear a conta por 15 minutos após 5 erros de senha. *Justificativa:* Anula tentativas de invasão por força bruta na tela de login.
6. **Política de Senha Forte:** Exigir mínimo de 8 caracteres, com letras, números e símbolos. *Justificativa:* Dificulta que os funcionários criem senhas óbvias como "123456".
7. **Timeout de Sessão Inativa:** Deslogar o usuário após 15 minutos sem uso. *Justificativa:* Impede acessos não autorizados em computadores esquecidos abertos no galpão.
8. **Forçar HTTPS (SSL/TLS):** Todo o tráfego da aplicação deve rodar obrigatoriamente sobre criptografia HTTPS. *Justificativa:* Protege o envio de senhas e dados em redes Wi-Fi abertas.
9. **Princípio do Menor Privilégio:** O usuário do banco de dados usado pelo sistema não será o root/admin. *Justificativa:* Se a aplicação for invadida, o estrago no banco fica limitado.
10. **Sanitização de Entradas na API:** Validação rigorosa dos campos enviados na API de entregas. *Justificativa:* Bloqueia códigos maliciosos antes de chegarem ao banco.
11. **Revogação de Tokens no Logout:** Cancelar o token JWT quando o usuário clicar em "Sair". *Justificativa:* Garante que a sessão seja encerrada de verdade no servidor.
12. **Ocultação de Versões do Servidor:** Desativar os cabeçalhos HTTP que mostram a versão exata do sistema/servidor. *Justificativa:* Dificulta que invasores busquem brechas específicas daquela versão.
13. **Assinatura Digital nos Comprovantes:** Salvar a foto do comprovante com verificação de hash. *Justificativa:* Garante que a foto do comprovante de entrega não foi adulterada depois.
14. **Proteção contra Fixação de Sessão:** Gerar um novo ID de sessão logo após o login do usuário. *Justificativa:* Impede que um invasor reutilize a sessão criada antes do login.
15. **Restrição de IP para o Painel Admin:** Liberar o acesso administrativo apenas para a faixa de IP do galpão/escritório. *Justificativa:* Impede que tentativas de invasão ao painel venham da internet aberta.
16. **Validação de Tipo de Arquivo no Upload:** Aceitar apenas `.png` e `.jpg` até 5MB nos comprovantes. *Justificativa:* Impede que usuários subam arquivos com scripts maliciosos.
17. **Troca de Senha Obrigatória no Primeiro Acesso:** Criar senha temporária que deve ser mudada no primeiro login do motorista. *Justificativa:* Evita que motoristas continuem usando a senha padrão enviada no cadastro.
18. **Logs de Acesso Imutáveis:** Registrar IP, data, hora e usuário em todas as alterações críticas. *Justificativa:* Permite auditar exatamente quem alterou o status ou valor de uma entrega.
19. **Anulamento de Parâmetros na URL (Prevenção de IDOR):** Validar se o ID da rota solicitada pertence ao motorista logado. *Justificativa:* Impede que o motorista veja entregas de outros alterando a URL.
20. **Bloqueio de Reutilização de Senhas:** O sistema não permitirá cadastrar as últimas 3 senhas usadas. *Justificativa:* Evita que o usuário altere a senha e volte imediatamente para a senha antiga insegura.

---

## 3.3 Mapeamento de Privacidade e Adequação à LGPD (RoPA)

Mapeamento dos 20 principais dados pessoais e processos operacionais tratados na LogExpress, especificando finalidade, base legal e direito do titular:

| nº | Dado / Processo | Finalidade no Sistema | Base Legal (LGPD) | Exercício do Direito do Titular |
| :---: | :--- | :--- | :--- | :--- |
| 01 | **Nome do Cliente** | Identificar o destinatário no momento da entrega da carga. | Execução de Contrato (Art. 7º, V) | Edição pelo aplicativo ou solicitação de exclusão do cadastro. |
| 02 | **CPF do Cliente** | Emissão de Nota Fiscal Eletrônica de transporte. | Cumprimento de Obrigação Legal (Art. 7º, II) | Não pode excluir antes de 5 anos devido a regras da Receita. |
| 03 | **Endereço do Destinatário** | Definir a rota física do caminhão e entregar o pacote. | Execução de Contrato (Art. 7º, V) | Atualização no painel antes do despacho da mercadoria. |
| 04 | **Telefone/WhatsApp do Cliente**| Enviar avisos sobre o horário que o motorista vai chegar. | Execução de Contrato (Art. 7º, V) | Opção de descadastramento de SMS/mensagens a qualquer momento. |
| 05 | **E-mail do Cliente** | Enviar o comprovante do frete e cópia da nota fiscal. | Execução de Contrato (Art. 7º, V) | Alteração cadastral simples no perfil do usuário. |
| 06 | **CPF e CNH do Motorista** | Validar se o motorista está habilitado a transportar. | Cumprimento de Obrigação Legal (Art. 7º, II) | Retenção obrigatória durante o contrato de trabalho/prestação. |
| 07 | **Geolocalização do Motorista**| Rastreamento da frota em tempo real no mapa. | Legítimo Interesse / Segurança (Art. 7º, IX) | Coleta ativa apenas durante a rota de entrega. |
| 08 | **Placa do Veículo** | Controle de entrada e saída do galpão de cargas. | Execução de Contrato (Art. 7º, V) | Edição permitida mediante aprovação do setor de frota. |
| 09 | **Foto do Comprovante (Assinatura)**| Provar que a mercadoria foi entregue para a pessoa certa. | Execução de Contrato (Art. 7º, V) | Armazenado com acesso restrito para contestação de entrega. |
| 10 | **Dados de Pagamento (Cartão)**| Cobrança do valor do frete do cliente. | Execução de Contrato (Art. 7º, V) | Não salvamos o cartão completo; titular pode remover cartões salvos. |
| 11 | **IP de Acesso do Usuário** | Registrar o acesso para segurança e auditoria do sistema. | Cumprimento de Obrigação Legal (Marco Civil da Internet) | Retenção obrigatória por 6 meses pelo artigo 15 do MCI. |
| 12 | **Cookies de Sessão** | Manter o usuário logado no sistema web durante o uso. | Consentimento (Art. 7º, I) | Opção de limpar cookies diretamente no navegador. |
| 13 | **Histórico de Pedidos** | Exibir para o cliente a lista de compras antigas. | Execução de Contrato (Art. 7º, V) | O titular pode solicitar a ocultação do histórico no app. |
| 14 | **Dados Fiscais (Razão Social)**| Faturamento corporativo B2B da transportadora. | Cumprimento de Obrigação Legal (Art. 7º, II) | Alteração mediante envio de cartão CNPJ atualizado. |
| 15 | **Log de Erros do Motorista**| Identificar falhas no aplicativo em celulares antigos. | Legítimo Interesse (Art. 7º, IX) | Anonimizado automaticamente após a correção da falha. |
| 16 | **Nome do Vendedor (Parceiro)**| Saber quem solicitou o despacho no e-commerce parceiro. | Execução de Contrato (Art. 7º, V) | Atualizado através do painel da empresa parceira. |
| 17 | **Valor do Frete / Declaração**| Seguro da carga contra roubo e acidentes. | Execução de Contrato / Obrigação Legal | Retido junto com a apólice do seguro do frete. |
| 18 | **Avisos de Preferência de Entrega**| Registrar orientações (ex: "Deixar na portaria"). | Consentimento (Art. 7º, I) | O cliente pode editar ou apagar as observações a qualquer hora. |
| 19 | **Registro de Login (Data/Hora)**| Controlar horário de uso para evitar acessos fora do expediente.| Legítimo Interesse (Art. 7º, IX) | Consulta disponível via relatório para o próprio funcionário. |
| 20 | **Dados de Contato de Emergência**| Contatar familiares do motorista em caso de acidente. | Proteção da Vida (Art. 7º, VII) | Atualização ou remoção direta pelo perfil do motorista. |

---

## 3.4 Análise Crítica (Diagnóstico e Mitigação de Segurança)

**Resposta Obrigatória ao Relatório Técnico:**

A vulnerabilidade que recebeu a nota mais alta em nossa Matriz GUT (Nota 125) foi a **Injeção de SQL (SQL Injection - OWASP A03)** na tela de busca e login do sistema de entregas. No contexto operacional da LogExpress, um invasor mal-intencionado poderia digitar comandos maliciosos como `' OR 1=1 --` nos campos de busca de cargas ou no formulário de login. Isso forçaria o banco de dados MySQL a interpretar o texto como um comando executável, concedendo acesso irrestrito ao painel administrativo ou permitindo a exclusão completa das tabelas de entregas e motoristas.

Para anular esse risco criticamente alto no projeto, a equipe adotou duas camadas definitivas de proteção técnica: no desenvolvimento da aplicação, abandonamos consultas SQL manuais montadas por concatenação de texto e passamos a utilizar consultas preparadas (*Prepared Statements*) e mapeamento objeto-relacional (ORM via `pandas`/`SQLAlchemy`). O ORM trata automaticamente todas as entradas digitadas pelos usuários como texto puro (literais) e não como instrução de banco, higienizando qualquer caractere especial antes de chegar ao banco de dados. Adicionalmente, aplicamos o Princípio do Menor Privilégio no usuário do banco de dados, bloqueando comandos de exclusão direta de tabelas (`DROP TABLE`) pela aplicação web.
