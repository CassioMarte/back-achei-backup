# back-achei-backup

## Sistema de Prestação de Serviços

Sistema similar ao Uber para prestação de serviços como pintura, elétrica, manicure, etc...


### Requisitos Funcionais (RF)

#### Autenticação e Cadastro Base
- [ ] Implementar cadastro com e-mail e senha
- [ ] Implementar seleção de tipo de usuário (prestador/cliente)
- [ ] Implementar autenticação JWT
- [ ] Implementar recuperação de senha
- [ ] Implementar verificação de e-mail
- [ ] Implementar logout

#### Prestador de Serviço - Cadastro
*Dados Obrigatórios*
- [ ] Implementar cadastro de foto de perfil
- [ ] Implementar cadastro de endereço
- [ ] Implementar cadastro de telefone
- [ ] Implementar cadastro de skills/serviços
- [ ] Implementar validação de dados obrigatórios
- [ ] Implementar geolocalização do endereço

*Dados Opcionais*
- [ ] Implementar upload de fotos de serviços anteriores que quer mostrar 3 free

#### Cliente - Cadastro
*Dados Obrigatórios*
- [ ] Implementar cadastro de foto de perfil
- [ ] Implementar cadastro de telefone
- [ ] Implementar validação de dados obrigatórios

#### Prestador de Serviço - Funcionalidades
- [ ] Implementar dashboard com número de serviços realizados
- [ ] Implementar sistema de média de avaliações
- [ ] Implementar histórico de avaliações
- [ ] Implementar sistema de aceite de serviço com datas
- [ ] Implementar calendário de disponibilidade
- [ ] Implementar sistema de fotos de conclusão de trabalho
  - Fotos expiram em 7 dias
- [ ] Implementar sistema de propostas/orçamentos
- [ ] Implementar notificações de novos serviços na área

#### Cliente - Funcionalidades
- [ ] Implementar publicação de solicitação de serviço
- [ ] Implementar busca de prestadores por categoria
- [ ] Implementar filtro de prestadores por distância (10km)
- [ ] Implementar sistema de avaliação (0-5 estrelas)
- [ ] Implementar agendamento de serviço
- [ ] Implementar marcação de urgência
- [ ] Implementar sistema de recebimento de propostas
- [ ] Implementar notificações de propostas recebidas

#### Sistema de Notificações
- [ ] Implementar integração com WhatsApp
- [ ] Implementar sistema de e-mails
- [ ] Implementar notificações in-app
- [ ] Implementar notificações de conclusão de serviço
- [ ] Implementar solicitação de avaliação pós-serviço

### Regras de Negócio (RN)

#### Gerais
- [ ] E-mail único por categoria
- [ ] Perfil deve estar completo para usar o sistema
- [ ] Prestador deve manter nota mínima de ex.:3.8  estrelas

#### Prestador de Serviço
- [ ] Bloqueio de visualização sem cadastro completo
- [ ] Validação de nota mínima para aceitar serviços
- [ ] Validação de conflito de datas
- [ ] Limite de serviços simultâneos 1 ou 2

#### Cliente
- [ ] Sistema de confirmação de conclusão
- [ ] Prazo para avaliação após conclusão
- [ ] Sistema de cancelamento com regras

### Requisitos Não Funcionais (RNF)

#### Segurança
- [ ] Criptografia de senha
- [ ] Autenticação via JWT
- [ ] Validação de tokens
- [ ] Proteção contra SQL injection
- [ ] Logs de segurança

#### Banco de Dados
- [ ] MySQL em produção
- [ ] UUIDs como IDs
- [ ] Backup automático

#### Performance
- [ ] Sistema de cache
- [ ] Compressão de imagens
- [ ] Paginação nas listagens

#### Monitoramento
- [ ] Logs de erro
- [ ] Monitoramento de performance
- [ ] Sistema de alertas
- [ ] Métricas de uso

## 🚀 Features Futuras

- [ ] Chat interno
- [ ] Sistema de pagamentos
- [ ] Sistema de disputas
- [ ] Sistema de reembolso
- [ ] Sistema de fidelidade
- [ ] Sistema de indicações

## 📝 Documentação

- [ ] Documentação da API
- [ ] Documentação do banco de dados
- [ ] Manual do usuário
- [ ] Documentação de deployment
- [ ] Documentação de manutenção

## 🛠 Tecnologias

* Node.js
* TypeScript
* Prisma
* MySQL (produção), sqlite3 (teste)
* JWT
* Bcrypt
* dotEnv
* cors
* zod
* jest
* superTest
* Express
* Express-async-errors
* WhatsApp API
* Email Service

Opção para doc
* swagger
* documentação notion


<!-- 
## RFs (Requisitos funcionais)

- [] Deve ser possível se cadastrar usando e-mail, senha e escolhendo um tipo de usuario (prestador de serviço || cliente);

### Prestador de serviço
- [] Deve ser obrigatorio após cadastro simples fazer o cadastro completo para poder divulgar ou se cadastrar para prestar serviço;
  Dados obrigatorios = Foto, endereço, telefone, skill (serviços que presta), 
  Dados opcionais = Fotos de serviços

  ### Usuario
- [] Deve ser obrigatorio após cadastro simples fazer o cadastro completo para poder divulgar ou se cadastrar pedidos;
  Dados obrigatorios = Foto, telefone,  
  
  ### Rota login 
- [] Deve ser possível obter o perfil de um usuário logado;
- [] Deve ser possível se autenticar;

 ### Prestador de serviço
- [] Deve ser possível obter o número de serviços realizados pelo usuário;
- [] Deve ser possível obter media de notas dos serviços prestados;
- [] Deve ser possível obter o histórico de avaliações dos serviços prestados;
- [] Deve ser obrigatorio ao aceitar um serviço colocar datas inicial e possivel data final do serviço;
- [] Deve ser possível colocar datas livres ou ocupadas no calendario;
- [] Deve ser obrigatorio colocar foto (duração da foto no sistema 7 dias) e informar a conclusão de trabalho;



### Usuario
- [] Deve ser possível o usuário publicar uma descrição de serviço e endereço que nescessita do mesmo e solicitar orçamento global;
- [] Deve ser possível o usuário buscar por categoria prestadores de serviço próximos (até 10km) que façam serviço que o usuario busca;
- [] Deve ser possível o usuário avaliar como nota 0 a 5 o serviço prestado;
- [] Deve ser possível o usuário colocar data para o serviço;
- [] Deve ser possível o usuário colocar urgencia;


## RNs (Regras de negócio)

- [] O usuário não deve poder se cadastrar com o mesmo e-mail na mesma categoria;


### Prestador de serviço
- [] O usuário não pode fazer check-in se não estiver perto (100m) da academia;
- [] O usuário não deve poder visualizar solicitações de serviço se cadastro não estiver completo;
- [] O usuário não deve poder aceitar solicitações de serviço se sua nota estiver abaixo de ??? (ex.: 3);
- [] O usuário não deve poder aceitar solicitações de serviço com datas iguais ou na data que ja esta em serviço;


### Usuario
- [] O usuário deve receber um aviso via whats e e-mail após serviço que solicitou seja dada pelo prestador de serviço como concluido;
  OBS: junto ao aviso deve haver uma solicitação de avaliação do mesmo.



## RNFs (Requisitos não-funcionais)

- [] A senha do usuário precisa estar criptografada;
- [] Os dados da aplicação precisam estar persistidos em um banco MySQL em produção;
- [] O usuário deve ser identificado por um JWT (JSON Web Token);
- [] O id no banco deve ser UUID

START_SECTION:footer -->