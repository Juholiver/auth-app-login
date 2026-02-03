# Login Auth API

## Descrição

Esta é uma API de autenticação de login simples, construída com Java e Spring Boot. Ela fornece endpoints para registrar novos usuários e autenticá-los usando JWT (JSON Web Tokens).

## Tecnologias Utilizadas

*   **Java 17**
*   **Spring Boot 3**
*   **Spring Security:** Para autenticação e autorização.
*   **JWT (JSON Web Tokens):** Para gerar tokens de autenticação.
*   **Lombok:** Para reduzir o código boilerplate.
*   **H2 Database:** Banco de dados em memória para desenvolvimento.
*   **Maven:** Para gerenciamento de dependências.

## Endpoints da API

A API expõe os seguintes endpoints:

### Autenticação

*   **`POST /auth/login`**: Autentica um usuário e retorna um token JWT.
    *   **Request Body:**
        ```json
        {
          "email": "user@example.com",
          "password": "password123"
        }
        ```
    *   **Response (Success):**
        ```json
        {
          "name": "User Name",
          "token": "your.jwt.token"
        }
        ```

*   **`POST /auth/register`**: Registra um novo usuário.
    *   **Request Body:**
        ```json
        {
          "name": "New User",
          "email": "newuser@example.com",
          "password": "password123"
        }
        ```
    *   **Response (Success):**
        ```json
        {
          "name": "New User",
          "token": "your.jwt.token"
        }
        ```

### Usuário

*   **`GET /user`**: Endpoint protegido que retorna uma mensagem de sucesso se o usuário estiver autenticado.
    *   **Headers:**
        ```
        Authorization: Bearer your.jwt.token
        ```
    *   **Response (Success):**
        ```
        "sucesso!"
        ```

## Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/seu-usuario/login-auth-api.git
    ```

2.  **Navegue até o diretório do projeto:**
    ```bash
    cd login-auth-api
    ```

3.  **Execute o projeto usando o Maven Wrapper:**
    *   No Windows:
        ```bash
        ./mvnw spring-boot:run
        ```
    *   No Linux/Mac:
        ```bash
        ./mvnw spring-boot:run
        ```

A aplicação estará disponível em `http://localhost:8080`.
