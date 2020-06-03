Microserviço de Notificação
=============================

Informação Geral
=============================
Documentação no Confluence:

Template & Notification
http://192.168.245.51:8090/pages/viewpage.action?pageId=55268671

PROPOSED - Template & Notification Services
http://192.168.245.51:8090/pages/viewpage.action?pageId=22686933

O componente de notificação é responsável pelo envio de notificações através de quatro canais para os clientes NEXT e não clientes. 

* Serviço de Notificação
As responsabilidades do Serviço de Notificação incluem:
   - Gerenciando todos os metadados de notificação, incluindo as informações do evento de negócios que acionarão a notificação
   - Gerenciando todas as informações que envolvem os modelos necessários no serviço de Gerenciamento de Modelos
   - Conexão com serviços que enviam a mensagem pelo canal de destino, como SMS, Push, email
   - Fornece uma trilha de auditoria de todas as notificações
   - O Serviço de Notificação requer um estado de banco de dados de armazenamento de persistência para registrar metadados para cada notificação no sistema. Todas as informações de auditoria necessárias para as notificações também são armazenadas.


- Tipos de notificação
   - Email - notificação com corpo (HTML) e assunto (String) enviados para a caixa de entrada de email padrão do destinatário. Nexters e Non-Nexters podem receber.
   - SMS - notificação de texto enviada ao número de celular do destinatário. Nexters e Non-Nexters podem receber.
   - Notificação push-text enviada para um dispositivo Nexter. Pode ser visualizado mesmo se o cliente não estiver usando o aplicativo no momento, como em uma tela de telefone bloqueada.
   - No aplicativo - notificação de texto enviada para um Nexter. Só pode ser visualizado dentro do aplicativo, tanto no centro de notificações quanto em um cartão.

Entidades de banco de dados
   - BUSINESS_FUNCTION - define o conjunto de componentes que possui eventos de notificação. Pode ser usado, no futuro, para desativar um grupo de notificações.
   - BUSINESS_EVENT_TYPE - define todos os eventos de notificação que a plataforma pode manipular. BUSINESS_EVENT_NAME deve corresponder aos valores da enumeração definidos em BusinessEvent.java
   - BUS_EVENT_NOTIFICATION - define a notificação real para cada evento. É um relacionamento de 1 para muitos, pois um evento pode ter até 4 linhas nesta tabela, uma para cada tipo de notificação. Também controla se uma notificação específica por canal está ativa ou não (coluna ENABLED_IND).
   - IN_APP_MESSAGE - armazena todas as notificações no aplicativo com status.
   - SCHEDULED_NOTIFICATION - controla as notificações enviadas por lote para evitar o envio de duplicatas.



Changelog
=============================

## [03/06/2020]
- [PB-1091] - Conforme alinhado anteriormente, seguem as alterações realizadas no microservice next-notification para o projeto JOY.
Foram alterados/criados 4 endpoints no microservice next-notification, e são eles:
*`/v2/notification/inAppMessages (Alterado)`
Esse endpoint passou a considerar para qual cliente a notificação PUSH deveria ser enviada, ou seja, para o Next ou para o JOY. A assinatura desse endpoint não foi alterada, então ele leva em consideração o ID do evento enviado no request e faz uma busca na nova tabela criada, chamada Application, para fazer essa distinção.  
*`v3/notification/expressPushMessage (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint *`v2/notification/expressPushMessage`, porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para um CPF em específico enviado no request.
*`v3/notification/expressPushMessage/list (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint 
*`v2/notification/expressPushMessage/list`
porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para uma lista de CPF’s informada no request.
*`v3/notification/expressPushMessage/all (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint *`v2/notification/expressPushMessage/all`, porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para todos os clientes Next ou JOY.


Configuração
=============================
> *Informações de configuração do projeto e dependencias.


![Diagrama de Contexto](https://github.com/alvaroqv/changelog/blob/master/diagrama_notification-up.png)


Exemplo de Utilização
=============================


Contatos:
=============================
- Versão 1:
DS Leader - Everson Cruzara: everson.crusara@bradesco.com.br
Squad - IBM

- Versão 2:
DS Leader - Filipi Cunha: filipe.cunha@bradesco.com.br
Squad - Refino



////
*Importar informações do Readme Atual*

Building
=============================


Testing
=============================




