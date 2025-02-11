# 2404-api-node-express

## Legenda Linkedin

Olá pessoal, queria apresentar minha primeira API, feita com NodeJS, Express e MongoDB.Basicamente temos duas entidades: `Livros` e `Autores`, relacionadas por referência em duas coleções separadas, com a cardinalidade de um para muitos, ou seja, neste projeto um autor pode ter escrito vários livros, mas um livro possui apenas um autor.

Com o desenvolvimento desta API, aprendi conceitos importantes como:

- Arquitetura básica de uma API (modelos, controladores e rotas), conexão com o Banco de Dados e inicialização do servidor.

- CRUD com as entidades Livros e Autores (buscar, adicionar, atualizar e excluir) através dos métodos do mongoose

- Criação do middleware de tratamento de erros do Express, utilizando classes para os principais tipos de erros:Não encontrado (404), Erro de validação, Requisição incorreta

- Validação de dados através das validações nativas do mongoose, validações personalizadas e validações globais.

- Buscas e filtros. Buscar pelos títulos de livros de forma dinâmica através de expressões regulares (regex), filtrar por número de páginas (min e max) e buscar livros pelo nome do autor.

- Paginar uma rota, ordenar os resultados e reutilizar a lógica de paginização em um middleware.

Link do projeto: 
Link do repositório com a documentação: 

#api #express #mongoDB #

## Documentação

# Minha API

Esta é a documentação da API para o projeto "Minha API". Esta API permite gerenciar recursos de livros.

## Endpoints

### 1. **GET** /livros
Retorna uma lista de todos os livros.

**URL**: `/livros`

**Método**: `GET`

**Resposta de Sucesso**:
- **Código**: `200 OK`
- **Corpo**:
    ```json
    [
      {
        "id": 1,
        "titulo": "O Senhor dos Anéis",
        "autor": "J.R.R. Tolkien",
        "ano": 1954
      },
      {
        "id": 2,
        "titulo": "Harry Potter e a Pedra Filosofal",
        "autor": "J.K. Rowling",
        "ano": 1997
      }
    ]
    ```

### 2. **GET** /livros/:id
Retorna um livro específico pelo ID.

**URL**: `/livros/:id`

**Método**: `GET`

**Parâmetros de URL**:
- **id**: ID do livro a ser retornado (número inteiro).

**Resposta de Sucesso**:
- **Código**: `200 OK`
- **Corpo**:
    ```json
    {
      "id": 1,
      "titulo": "O Senhor dos Anéis",
      "autor": "J.R.R. Tolkien",
      "ano": 1954
    }
    ```

**Resposta de Erro**:
- **Código**: `404 Not Found`
- **Corpo**:
    ```json
    {
      "error": "Livro não encontrado"
    }
    ```

### 3. **POST** /livros
Cria um novo livro.

**URL**: `/livros`

**Método**: `POST`

**Cabeçalhos**:
- `Content-Type: application/json`

**Corpo da Requisição**:
```json
{
  "titulo": "O Hobbit",
  "autor": "J.R.R. Tolkien",
  "ano": 1937
}
```

**Resposta de Sucesso**:
- **Código**: `201 Created`
- **Corpo**:
    ```json
    {
      "id": 3,
      "titulo": "O Hobbit",
      "autor": "J.R.R. Tolkien",
      "ano": 1937
    }
    ```

**Resposta de Erro**:
- **Código**: `400 Bad Request`
- **Corpo**:
    ```json
    {
      "error": "Dados inválidos"
    }
    ```

### 4. **PUT** /livros/:id
Atualiza um livro existente.

**URL**: `/livros/:id`

**Método**: `PUT`

**Parâmetros de URL**:
- **id**: ID do livro a ser atualizado (número inteiro).

**Cabeçalhos**:
- `Content-Type: application/json`

**Corpo da Requisição**:
```json
{
  "titulo": "O Hobbit",
  "autor": "J.R.R. Tolkien",
  "ano": 1937
}
```

**Resposta de Sucesso**:
- **Código**: `200 OK`
- **Corpo**:
    ```json
    {
      "id": 3,
      "titulo": "O Hobbit",
      "autor": "J.R.R. Tolkien",
      "ano": 1937
    }
    ```

**Resposta de Erro**:
- **Código**: `404 Not Found`
- **Corpo**:
    ```json
    {
      "error": "Livro não encontrado"
    }
    ```

### 5. **DELETE** /livros/:id
Remove um livro.

**URL**: `/livros/:id`

**Método**: `DELETE`

**Parâmetros de URL**:
- **id**: ID do livro a ser removido (número inteiro).

**Resposta de Sucesso**:
- **Código**: `204 No Content`

**Resposta de Erro**:
- **Código**: `404 Not Found`
- **Corpo**:
    ```json
    {
      "error": "Livro não encontrado"
    }
    ```

## Variáveis de Ambiente

Para rodar este projeto, você precisará adicionar as seguintes variáveis de ambiente ao seu arquivo `.env`:

- `MONGODB_URI`: URL de conexão ao MongoDB Atlas.
- `PORT`: Porta em que o servidor será executado (padrão é 3000).

## Instruções de Instalação

1. Clone o repositório:
   ```sh
   git clone https://github.com/usuario/minha-api.git
   ```

2. Navegue até o diretório do projeto:
   ```sh
   cd minha-api
   ```

3. Instale as dependências:
   ```sh
   npm install
   ```

4. Crie um arquivo `.env` na raiz do projeto e adicione suas variáveis de ambiente:
   ```
   MONGODB_URI=sua-url-do-mongodb
   PORT=3000
   ```

5. Inicie o servidor:
   ```sh
   npm run dev
   ```

6. A API estará disponível em `http://localhost:3000`.

## Tecnologias Utilizadas

- Node.js
- Express
- Mongoose
- MongoDB Atlas


