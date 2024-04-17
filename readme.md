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
    git clone https://github.com/fmrodrigues92/kenlo-docker-compose
    git clone https://github.com/fmrodrigues92/kenlo-usuarios-api
    git clone https://github.com/fmrodrigues92/kenlo-chatgpt-api
    ```
2. Configure o ambiente para a API ChatGPT:
    - Navegue até o diretório da API ChatGPT:
      ```bash
      cd kenlo-chatgpt-api
      ```
    - Crie o arquivo `.env` a partir do `.env.example`:
      ```bash
      cp .env.example .env
      ```
    - Edite o arquivo `.env` e insira a chave da API do ChatGPT:
      ```bash
      echo "CHATGPT_KEY=xpto" >> .env
      ```
    - Volte para o diretório principal:
      ```bash
      cd ..
      ```

3. Navegue até o diretório do docker-compose:
    ```bash
    cd docker-compose
    ```

4. Execute o comando para subir os serviços:
    ```bash
    docker-compose up
    ```
