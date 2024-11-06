# api-games-docs
Esta API fornece operações CRUD (Criar, Ler, Atualizar e Excluir) para gerenciar uma coleção de jogos. Ela permite listar os jogos existentes, criar novos jogos, atualizar informações de jogos selecionados e excluir jogos.
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games

Exemplo de resposta:
```
[
    {
        "id": 10,
        "title": "Call of Duty Mw",
        "year": 2019,
        "price": 60
    },
    {
        "id": 15,
        "title": "God of War",
        "year": 2018,
        "price": 50
    },
    {
        "id": 20,
        "title": "Assassin's Creed",
        "year": 2017,
        "price": 40
    }
]
```

##
### GET /games/:id
Esse endpoint retorna os detalhes de um jogo específico, filtrado pelo seu ID.
#### Parâmetros
id: ID do jogo a ser consultado.
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games

###### Descrição:
Retorna os detalhes do jogo solicitado, no formato JSON.

##### Bad Request! 400

###### Descrição:
Indica que o parâmetro id informado não é um número válido.

##### Not Found! 404

###### Descrição:
Indica que não foi encontrado nenhum jogo com o id informado.

##
### POST /game
Esse endpoint permite cadastrar um novo jogo no banco de dados.
#### Parâmetros
title: Título do jogo
price: Preço do jogo
year: Ano de lançamento do jogo

#### Respostas
##### OK! 200

###### Descrição:
Indica que o jogo foi cadastrado com sucesso.

##### Unauthorized! 401

###### Descrição:
Indica que o usuário não está autenticado, verifique o token que está sendo utilizado para autenticação na API!


##
### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e=mail.

Exemplo:
```
{
    "email": "luccasoctavio@gmail.com",
    "password": "nodejs<3"
}
```

#### Respostas

##### Falha Interna! 400
Caso essa resposta aconteça, isso significa que ocorreu uma falha interna durante o processo de autenticação. Motivos podem ser problemas na conexão com o servidor (como erro de porta) ou falhas no processamento da requisição pelo servidor. É importante verificar a estabilidade da conexão e, se o problema persistir, investigar a causa raiz.

Exemplo de resposta:
```
{err:"Falha interna"}
```

##### OK! 200

Exemplo de resposta:

```
{token: token}

```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado!

Exemplos de resposta:

```
{err: "Credenciais inválidas!"}
```

##### Email não encontrado ou Email inválido! 404 ou 400
Caso a autenticação falhe, a API retornará um erro com o código 404 ou 400, dependendo do motivo. A resposta conterá uma mensagem de erro informando que o e-mail enviado não existe na base de dados ou é inválido

Exemplos de resposta:

```
{err: "O Email enviado não existe na base de dados!"} -- 404

```

```
{err: "O Email enviado é inválido"} -- 400

```
##
### DELETE /games/:id




##
### PUT /games/:id
