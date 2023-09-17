# Usando OAuth2 e JWT em ApiRest

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

Este projeto utiliza **Java, Spring Boot , Flyway Migrations, PostgresSQL, Spring Security e JWT para autenticação.**

## Links

- [Instalação](#instalacap)
- [Configuracao](#configuracao)
- [Teste](#teste)
- [API Endpoints](#api-endpoints)
- [Authentication](#autenticacao)
- [Database](#database)

## Instalacao

1. Clone o repositório:

```bash
git clone {o caminho}
```

2. Instale as dependências do Maven (Obs caso esteja com X vermelho faça um updated Maven)

3. Instale o Postgres (Deixo o link aqui caso não tenha instalado [PostgresSQL](https://www.postgresql.org/) )

## Configuracao 

- Vá em **application.properties**

  
```bash
spring.jpa.database=POSTGRESQL
spring.datasource.platform=postgres

spring.datasource.url=jdbc:postgresql://localhost:5432/postgres
spring.datasource.username= 
spring.datasource.password=

api.security.token.secret=${JWT_SECRET:my-secret-key}

spring.jpa.show-sql=true
spring.jpa.generate-ddl=true
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
```

## Teste

1. Inicie sua aplicação
2. Teste para ver se está tudo ok http://localhost:8080


## API Endpoints
Teste os Endpoints :

```markdown
GET /product - busca a lista dos produtos. (lembrando que precisa está autenticado caso contrário ocorrerá erro)

POST /product - Registrar um novo produto (Apenas usuários ADMIN irão conseguir).

POST /auth/login - Faça login após registrar uma conta logo em seguida terá o Token de acesso

POST /auth/register - Registre a sua conta
```

## Autenticacao
Tipos de Usuário

```
USER -> Funções padrões
ADMIN -> Admin possui funções padrões e adicionais
```

## Database
 [PostgresSQL](https://www.postgresql.org/) Necessário o banco para criar as migrations e usar Flyway.

