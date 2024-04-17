# Avaliação Técnica Kenlo - Fernando Menezes

Este projeto consiste em duas principais APIs desenvolvidas como parte da avaliação técnica para Kenlo.

## URLs de Produção

1. **Usuários API**: [usuarios.kenlo.fmrodrigues.dev](https://usuarios.kenlo.fmrodrigues.dev)
    - Esta API gerencia um CRUD para usuários.
2. **ChatGPT API**: [chatgpt.kenlo.fmrodrigues.dev](https://chatgpt.kenlo.fmrodrigues.dev)
    - Esta API permite interações com um modelo de ChatGPT.

## APIs

### Usuários API

- **CRUD de Usuários**: `/users`
  - **GET**: Retorna todos os usuários.
  - **POST**: Cria um novo usuário. Exemplo de corpo da requisição:
    ```json
    {
      "name": "Nome do Usuário",
      "email": "email@exemplo.com",
      "phone": "99999-9999"
    }
    ```
  - **GET** `/users/{id}`: Retorna um usuário específico pelo ID.
  - **PUT** `/users/{id}`: Atualiza um usuário existente pelo ID.
  - **DELETE** `/users/{id}`: Deleta um usuário pelo ID.

### ChatGPT API

- **Interagir com ChatGPT**: `/chatgpt/interaction/{user_id}/ask`
  - **POST**: Envia uma pergunta ao ChatGPT e recebe a resposta. Exemplo de corpo da requisição:
    ```json
    {
      "question": "Say this is a test!"
    }
    ```

## Rodando o Projeto Localmente

Para rodar o projeto em ambiente local, siga os passos abaixo:

1. Clone os repositórios dos projetos para o mesmo diretório:
    ```bash
    mkdir Projeto-fernando
    cd Projeto-fernando
    git clone <url-repositorio-usuarios-api>
    git clone <url-repositorio-chatgpt-api>
    ```

2. Navegue até o diretório do docker-compose:
    ```bash
    cd docker-compose
    ```

3. Execute o comando para subir os serviços:
    ```bash
    docker-compose up
    ```