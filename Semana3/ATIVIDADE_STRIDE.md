# Modelagem de Ameaças STRIDE para Funcionalidade de Cadastro de Usuário

Considerada aqui uma aplicação genérica que permitisse que os usuários realizassem cadastro.

## S - Spoofing (Falsificação de identidade)

- **Existe risco?** Sim.
- **Qual seria?** Possibilidade de um atacante se passar por um usuário legítimo ou forjar a origem de uma requisição de cadastro, através da criação de contas falsas, por exemplo.
- **Quem se beneficiaria?** Concorrentes poderiam sobrecarregar a base de dados com informações falsas; Bots poderiam criar contas automaticamente para exercer atividades maliciosas na plataforma.

## T - Tampering (Manipulação indevida de dados)

- **Existe risco?** Sim.
- **Qual seria?** Possibilidade de um atacante interceptar e alterar os dados enviados durante o processo de cadastro. Por exemplo, ao modificar dados pessoais no momento do envio do formulário, antes que cheguem ao servidor, ou injetando códigos maliciosos (ex: SQL Injection, Cross-Site Scripting - XSS) nos campos de cadastro para manipular o banco de dados ou a interface do usuário.
- **Quem se beneficiaria?** Atacentes poderiam executar códigos maliciosos no lado do servidor ou cliente.

## R - Repudiation (Ações sem rastreabilidade)

- **Existe risco?** Sim.
- **Qual seria?** Possibilidade de usuários alegarem que a conta foi criada sem seu consentimento, ou que não forneceram determinado dado pessoal, dificultando a auditoria.
- **Quem se beneficiaria?** Usuários mal-intencionados poderiam evitar responsabilidade por ações realizadas com a conta recém-criada ou para fins de fraude; Atacantes poderiam dificultar a investigação de incidentes de segurança.

## I - Information Disclosure (Vazamento de informações)

- **Existe risco?** Sim.
- **Qual seria?** Possibilidade de mensagens de erro reveladoras (indicando a existência de um e-mail ou nome de usuário), revelação de IDs de usuário, códigos de erro internos ou configurações do sistema em respostas de API ou mensagens de log.
- **Quem se beneficiaria?** Atacantes poderiam coletar informações para ataques; Concorrentes poderiam coletar informações sobre a base de usuários ou padrões de cadastro.

## D - Denial of Service (Interrupção do serviço)

- **Existe risco?** Sim.
- **Qual seria?** Possibilidade de atacantes sobrecarregarem funcionalidade de cadastro, impedindo que usuários reais criem novas contas. Por exemplo, enviando milhares de requisições de cadastro em um curto período, sobrecarregando o servidor, o banco de dados ou o serviço de e-mail de confirmação.
- **Quem se beneficiaria?** Concorrentes poderiam tentar prejudicar o cadastro de novos usuários pela aplicação; Atacantes poderiam realizar ataques em busca de recompensas monetárias para cessar a operação.

## E - Elevation of Privilege (Elevação de privilégios)

- **Existe risco?** Sim.
- **Qual seria?** POssibilidade de atacantes manipularem a requisição de cadastro para que a conta criada receba privilégios de administrador indevidamente, ou contornando a verificação de e-mail ou telefone, permitindo que um atacante crie contas e as use sem validação.
- **Quem se beneficiaria?** Atacantes poderiam obter acesso ilimitado para acesso a dados confidenciais ou funcionalidades restritas; Usuários mal-intencionados poderiam obter acesso a recursos pagos ou restritos sem autorização.