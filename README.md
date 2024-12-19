# Client Backend

## Descrição
Este é um projeto Spring Boot que implementa um backend para gerenciar clientes usando Flyway para versionamento do banco de dados.

## Tecnologias
- Spring Boot
- Flyway
- PostgreSQL

## Como rodar o projeto
1. Configure o banco de dados PostgreSQL com as credenciais no arquivo `application.properties` localizado na pasta resources dentro da pasta main.
2. Rode o comando `mvn spring-boot:run` para iniciar o servidor.
3. Use ferramentas como Postman para testar os endpoints REST.

## Endpoints
- `GET /api/clientes`: Retorna todos os clientes.
- `GET /api/clientes/{id}`: Retorna um cliente pelo ID.
- `POST /api/clientes`: Cria um novo cliente.
- `PUT /api/clientes/{id}`: Atualiza um cliente existente.
- `DELETE /api/clientes/{id}`: Deleta um cliente pelo ID.
