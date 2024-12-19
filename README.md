# Backend Cliente

## Descrição
Atividade Spring Boot que implementa um backend para gerenciar clientes usando Flyway para versionamento do banco de dados.

## Utilizados
- Spring Boot
- Flyway
- PostgreSQL

## Como rodar
1. Configure o banco de dados PostgreSQL com as credenciais no arquivo `application.properties` localizado na pasta resources dentro da pasta main.
2. Rode o comando `mvn spring-boot:run` para iniciar o servidor: Vá em View > Tool Windows > Terminal.
Execute o Comando: Digite o seguinte e pressione Enter: `mvn spring-boot:run`. 
3. Se desejar, use ferramentas como Postman para testar os endpoints REST.

## Endpoints
- `GET /api/clientes`: Retorna todos os clientes.
- `GET /api/clientes/{id}`: Retorna um cliente pelo ID.
- `POST /api/clientes`: Cria um novo cliente.
- `PUT /api/clientes/{id}`: Atualiza um cliente existente.
- `DELETE /api/clientes/{id}`: Deleta um cliente pelo ID.
