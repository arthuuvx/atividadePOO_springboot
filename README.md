
# Atividade SpringBoot e FlyWay

Este guia fornece instruções para configurar e testar o seu projeto Spring Boot com banco de dados PostgreSQL, incluindo como clonar o repositório, configurar o PostgreSQL e realizar testes utilizando cURL.

## 1. Clonando o Repositório

Primeiro, clone o repositório para sua máquina local.

```bash
git clone https://github.com/arthuuvx/atividadePOO_springboot.git
```

## 2. Configuração do PostgreSQL

### 2.1 Instalando o PostgreSQL

Se você ainda não tem o PostgreSQL instalado, pode seguir estas instruções para instalar em sua máquina:

- **Linux (Ubuntu)**:

  ```bash
  sudo apt update
  sudo apt install postgresql postgresql-contrib
  ```

- **Mac (Homebrew)**:

  ```bash
  brew install postgresql
  ```

- **Windows**:

  Baixe e instale o PostgreSQL do site oficial: https://www.postgresql.org/download/windows/

### 2.2 Criando o Banco de Dados

Após instalar o PostgreSQL, crie um banco de dados para o projeto:

```bash
sudo -u postgres psql
CREATE DATABASE seu_banco_de_dados;
CREATE USER seu_usuario WITH PASSWORD 'sua_senha';
ALTER ROLE seu_usuario SET client_encoding TO 'utf8';
ALTER ROLE seu_usuario SET default_transaction_isolation TO 'read committed';
ALTER ROLE seu_usuario SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE seu_banco_de_dados TO seu_usuario;
\q
```

Substitua `seu_banco_de_dados`, `seu_usuario`, e `sua_senha` com os valores desejados.

## 3. Configuração do `application.properties`

Configure o acesso ao banco de dados no arquivo `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/seu_banco_de_dados
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

Substitua os valores de `seu_banco_de_dados`, `seu_usuario` e `sua_senha` conforme sua configuração.

## 4. Executando o Projeto

Para executar o projeto localmente, basta rodar o seguinte comando:

```bash
mvn spring-boot:run
```

A aplicação estará rodando em `http://localhost:8080`.

## 5. Testando com cURL

Agora que a aplicação está rodando, você pode testá-la utilizando cURL.

### 5.1 Teste de GET

Para fazer uma requisição GET, por exemplo, para listar todos os registros:

```bash
curl -X GET http://localhost:8080/api/seu-endpoint
```

### 5.2 Teste de POST

Para enviar uma requisição POST com dados no formato JSON:

```bash
curl -X POST http://localhost:8080/api/seu-endpoint      -H "Content-Type: application/json"      -d '{
           "campo1": "valor1",
           "campo2": "valor2"
         }'
```

### 5.3 Teste de PUT

Para enviar uma requisição PUT (atualizar um recurso):

```bash
curl -X PUT http://localhost:8080/api/seu-endpoint/1      -H "Content-Type: application/json"      -d '{
           "campo1": "novo-valor1",
           "campo2": "novo-valor2"
         }'
```

### 5.4 Teste de DELETE

Para enviar uma requisição DELETE:

```bash
curl -X DELETE http://localhost:8080/api/seu-endpoint/1
```

## 6. Testes Unitários

Se o projeto já contém testes unitários, você pode rodá-los com o comando:

```bash
mvn test
```

Isso irá executar os testes definidos no projeto e exibir os resultados no terminal.