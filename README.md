Titulo do Projeto
=============================

Informação Geral
=============================
> *Breve descrição negocial do projeto
Incluir links para informações do projeto no Confluence e Jira se necessário*

PreOnboarding - Microserviço com funcionalidades  para realizar o pré onboarding dos cliente no Next.



Changelog
=============================
> *Um changelog contém uma lista selecionada, ordenada cronologicamente, de mudanças significativas para cada versão de um projeto*


Agrupar mudanças descrevendo seus impactos no projeto, como segue:

## [Atual]
- [PB-650] - Validação de SMS e E-mail na adesão.  EndPoint para gerar um código de verificação, a ser enviado via SMS e email, no início da adesão. Este código será utilizado pelo usuário do app para validar  o telefone e email informados no início da adesão. Documentação do PB: (https://pages.github.com/)

### 3.X.X - (20-01-2019)
- [PB-456] - Descrição da PB com link para documentação na pasta doc/ (https://pages.github.com/)

### 2.X.X (20-01-2019) 
- [PB-321] - Descrição da PB com link para documentação na pasta doc/ (https://pages.github.com/)

### [1.X.X] - (20-01-2019 )
- [PB-111] - Descrição da PB com link para documentação na pasta doc/ (https://pages.github.com/)


Configuração
=============================
> *Informações de configuração do projeto e dependencias.
Apresentar dependencia para outros MicroServiços ou do Monolito.*

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

DS Leader - Devan: devan.j.nack@bradesco.com.br - (41) 2107-6402 / Ramal: 34-6402
Squad - Nome da Squad 

- Versão 2:

DS Leader - Devan: devan.j.nack@bradesco.com.br - (41) 2107-6402 / Ramal: 34-6402
Squad - Nome da Squad 



////
*Importar informações do Readme Atual*

Building
=============================


Testing
=============================




