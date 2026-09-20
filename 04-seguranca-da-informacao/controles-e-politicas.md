# Controles de Segurança, Políticas IAM e Conformidade LGPD

## Políticas de Acesso e Identidade (IAM / Zero Trust)
1. **Hashing de Senhas (bcrypt):** Senhas nunca serão salvas em texto puro, usando bcrypt com salt.
2. **Autenticação de Dois Fatores (2FA):** Obrigatoriedade de 2FA para contas de nível Admin.
3. **Controle de Acesso Baseado em Cargos (RBAC):** Perfis divididos em Cliente, Motorista e Admin.
4. **Uso de Tokens JWT com Validade:** Tokens de API expiram em 2 horas.
5. **Bloqueio por Tentativas Incorretas:** Conta bloqueada por 15 min após 5 erros seguidos.
6. **Política de Senha Forte:** Mínimo de 8 caracteres com letras, números e símbolos.
7. **Timeout de Sessão Inativa:** Desconexão automática após 15 minutos sem uso.
8. **Forçar HTTPS (SSL/TLS):** Criptografia obrigatória em todo o tráfego da aplicação.
9. **Princípio do Menor Privilégio:** Usuário da aplicação no banco não possui permissões administrativas globais.
10. **Sanitização de Entradas na API:** Validação rigorosa dos campos de formulário e requisições HTTP.
11. **Revogação de Tokens no Logout:** Invalidação imediata da sessão do lado do servidor.
12. **Ocultação de Versões do Servidor:** Desativação de cabeçalhos HTTP que exponham versões do software.
13. **Assinatura Digital nos Comprovantes:** Validação do hash de integridade das imagens enviadas.
14. **Proteção contra Fixação de Sessão:** Regeneração de ID de sessão após a autenticação.
15. **Restrição de IP no Painel Admin:** Acesso restrito a redes e IPs autorizados.
16. **Validação do Tipo de Arquivo em Uploads:** Permissão exclusiva para `.jpg` e `.png` até 5MB.
17. **Troca de Senha Obrigatória no Primeiro Acesso:** Alteração forçada na primeira entrada do motorista.
18. **Logs de Acesso Imutáveis:** Registro de data, hora, IP e ação realizada para fins de auditoria.
19. **Anulamento de Parâmetros na URL (Anti-IDOR):** Validação de escopo de acesso por ID de usuário.
20. **Bloqueio de Reutilização de Senhas:** Impede o reuso das últimas 3 senhas cadastradas.

---

## Mapeamento de Privacidade (LGPD / RoPA)

| nº | Dado / Processo | Finalidade no Sistema | Base Legal (LGPD) | Exercício do Direito do Titular |
| :---: | :--- | :--- | :--- | :--- |
| 01 | **Nome do Cliente** | Identificar o destinatário na entrega. | Execução de Contrato (Art. 7º, V) | Edição ou solicitação de exclusão do cadastro. |
| 02 | **CPF do Cliente** | Emissão de Nota Fiscal Eletrônica. | Cumprimento de Obrigação Legal (Art. 7º, II) | Retenção obrigatória por 5 anos (Receita). |
| 03 | **Endereço do Destinatário**| Execução da rota física de entrega. | Execução de Contrato (Art. 7º, V) | Atualização cadastral no painel. |
| 04 | **Telefone do Cliente** | Avisos de entrega via SMS/WhatsApp. | Execução de Contrato (Art. 7º, V) | Cancelamento do envio de notificações. |
| 05 | **E-mail do Cliente** | Envio de comprovantes e notas. | Execução de Contrato (Art. 7º, V) | Alteração direta no perfil do usuário. |
| 06 | **CPF e CNH do Motorista** | Validação de cadastro e segurança. | Cumprimento de Obrigação Legal (Art. 7º, II) | Retenção vinculada ao contrato de trabalho. |
| 07 | **Geolocalização** | Rastreamento de carga em tempo real. | Legítimo Interesse (Art. 7º, IX) | Ativa apenas durante a viagem ativa. |
| 08 | **Placa do Veículo** | Controle de entrada e saída do galpão.| Execução de Contrato (Art. 7º, V) | Edição via setor de frotas. |
| 09 | **Foto do Comprovante** | Prova de entrega concluída. | Execução de Contrato (Art. 7º, V) | Acesso restrito para auditoria e contestação. |
| 10 | **Dados de Pagamento** | Processamento do frete. | Execução de Contrato (Art. 7º, V) | Remoção de cartões salvos a qualquer momento. |
| 11 | **IP de Acesso** | Auditoria e segurança do sistema. | Cumprimento de Obrigação Legal (MCI) | Guarda obrigatória por 6 meses (Marco Civil). |
| 12 | **Cookies de Sessão** | Manter login ativo na aplicação. | Consentimento (Art. 7º, I) | Limpeza permitida via navegador. |
| 13 | **Histórico de Pedidos** | Consulta de entregas anteriores. | Execução de Contrato (Art. 7º, V) | Ocultação mediante solicitação no app. |
| 14 | **Dados Fiscais (CNPJ)** | Faturamento de fretes B2B. | Cumprimento de Obrigação Legal (Art. 7º, II) | Alteração mediante envio de Cartão CNPJ. |
| 15 | **Logs de Erros** | Correção de falhas no aplicativo. | Legítimo Interesse (Art. 7º, IX) | Anonimização automática pós-correção. |
| 16 | **Nome do Vendedor** | Origem do despacho do produto. | Execução de Contrato (Art. 7º, V) | Atualização via plataforma parceira. |
| 17 | **Valor Declarado** | Cobertura do seguro da carga. | Execução de Contrato / Obrigação Legal | Retido junto à apólice do seguro. |
| 18 | **Observações de Entrega**| Instruções específicas de descarga. | Consentimento (Art. 7º, I) | Edição ou exclusão pelo cliente. |
| 19 | **Registro de Horário** | Controle de jornada e acessos. | Legítimo Interesse (Art. 7º, IX) | Consulta disponível via relatório do usuário. |
| 20 | **Contato de Emergência** | Comunicação em casos de acidentes. | Proteção da Vida (Art. 7º, VII) | Atualização direta pelo perfil do motorista. |
