# PROJETO PITANG

Este projeto é uma aplicação Spring Boot que inclui funcionalidades de CRUD para clientes, segurança com Spring Security, e um sistema de login e logout para administradores.

## Funcionalidades

Adicionar, atualizar, deletar, listar clientes e reativar clientes.

Soft delete para clientes, permitindo que sejam marcados como inativos em vez de serem excluídos permanentemente.

Sistema de login e logout para administradores.

Segurança com Spring Security, incluindo criptografia de senhas.

## Requisitos

Java 17 ou superior

Maven

MySQL

## Configuração do Banco de Dados

Crie um banco de dados MySQL e configure as credenciais no arquivo application.yml:

```
server:
  port: 8081
  error:
    include-message: always

spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    username: seu_usuario
    url: jdbc:mysql://localhost:3306/nome_do_seu_banco_de_dados
    password: sua_senha
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
    open-in-view: true
```

## Executando a Aplicação

Clone o repositório:

```
git clone https://github.com/seu-usuario/seu-repositorio.git
```

Navegue até o diretório do projeto:

```
cd seu-repositorio
```

Compile e execute a aplicação

## Bibliotecas Utilizadas

```
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-validation</artifactId>
		</dependency>
		<dependency>
			<groupId>com.mysql</groupId>
			<artifactId>mysql-connector-j</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>com.auth0</groupId>
			<artifactId>java-jwt</artifactId>
			<version>4.4.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-security</artifactId>
		</dependency>
		<!-- https://mvnrepository.com/artifact/io.jsonwebtoken/jjwt-api -->
		<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-api</artifactId>
			<version>0.12.3</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/io.jsonwebtoken/jjwt-impl --><!-- https://mvnrepository.com/artifact/io.jsonwebtoken/jjwt-impl -->
		<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-impl</artifactId>
			<version>0.12.3</version>
			<scope>runtime</scope>
		</dependency>
		<!-- https://mvnrepository.com/artifact/io.jsonwebtoken/jjwt-jackson -->
		<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-jackson</artifactId>
			<version>0.12.3</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>
```
## Endpoints

### Clientes

**Adicionar Cliente**

* URL: /client/add
* Método: POST
* Corpo: JSON com os detalhes do cliente

**Listar Clientes**

* URL: /client
* Método: GET

**Obter Cliente por ID**

* URL: /client/get
* Método: GET
* Parâmetro: id (UUID)

**Atualizar Cliente**

* URL: /client/update/{id}
* Método: PUT
* Corpo: JSON com os novos detalhes do cliente

**Deletar Cliente**

* URL: /client/delete/{id}
* Método: DELETE

**Reativar Cliente** 

* URL: /client/activate/{id}
* Método: PATCH

### Administradores

**Login Administrador**

* URL: /login
* Método: POST
* Corpo: JSON com os detalhes do administrador

**Logout Administrador**

* URL: /logout
* Método: GET
* Corpo: JSON com os detalhes do administrador

## Licença

Este projeto está licenciado sob os termos da licença MIT.
