Titulo do Projeto
=============================

Informação Geral
=============================
> *Breve descrição negocial do projeto
Incluir links para informações do projeto no Confluence e Jira se necessário*

Microservice de Notificação. 



Changelog
=============================
Agrupar mudanças descrevendo seus impactos no projeto, como segue:

## [03/06/2020]
- [PB-1091] - Conforme alinhado anteriormente, seguem as alterações realizadas no microservice next-notification para o projeto JOY.
Foram alterados/criados 4 endpoints no microservice next-notification, e são eles:
`/v2/notification/inAppMessages (Alterado)`
Esse endpoint passou a considerar para qual cliente a notificação PUSH deveria ser enviada, ou seja, para o Next ou para o JOY. A assinatura desse endpoint não foi alterada, então ele leva em consideração o ID do evento enviado no request e faz uma busca na nova tabela criada, chamada Application, para fazer essa distinção.  
`v3/notification/expressPushMessage (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint `v2/notification/expressPushMessage`, porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para um CPF em específico enviado no request.
`v3/notification/expressPushMessage/list (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint 
`v2/notification/expressPushMessage/list`
porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para uma lista de CPF’s informada no request.
`v3/notification/expressPushMessage/all (Criado)`
Esse endpoint é novo e foi criado para ser utilizado diretamente pelo sistema de gestão. Ele faz o mesmo que o endpoint `v2/notification/expressPushMessage/all`, porém com um novo campo chamado applicationId, que é responsável por distinguir se a mensagem será enviada para o Next ou para o JOY (NEXT=1, JOY=2). O objetivo deste endpoint é mandar notificações PUSH para todos os clientes Next ou JOY.


Configuração
=============================
> *Informações de configuração do projeto e dependencias.


![Diagrama de Contexto](https://github.com/alvaroqv/changelog/blob/master/diagrama_contexto.png)


Exemplo de Utilização
=============================
> *Descrever como validar a configuração e instalação do Microserviço utilizando um exemplo de Jornada*

Para testar a  configuração do Micro Serviço PreOnboarding executar as seguintes tasks:

1 - Gerar um token de acesso 
```
Codigo fonte para gerar o token
```

2 - Acessar o Endpoint POST /v1/preonboarding/devicevalidation

Utilizar o JSON:
```
Codigo fonte para gerar o token
```
3 - Validar se no retorno da execução existe a confirmação do envio do SMS 
```
Exemplo de retorno
```

Contatos:
=============================
- Versão 1:

DS Leader - Devan: devan.j.nack@XXXXX.com.br - (41) XXXX-XXXX / Ramal: 34-XXXX
Squad - Nome da Squad 

- Versão 2:

DS Leader - Devan: devan.j.nack@XXXXXX.com.br - (41) XXXX-XXXX / Ramal: 34-XXXX
Squad - Nome da Squad 



////
*Importar informações do Readme Atual*

Building
=============================


Testing
=============================




