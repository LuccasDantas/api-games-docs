# api-games-docs
Esta API é utilizada para TAl e TAL...
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
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado!

Exemplo de resposta:

```
{
    "err": "Token Inválido"
}
```
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
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJsdWNjYXNvY3RhdmlvQGdtYWlsLmNvbSIsImlhdCI6MTczMDgzNTAyNSwiZXhwIjoxNzMxMDA3ODI1fQ.dZ6I44Ze3O2WjGbo6UbENyB7ueA6fskmOMg9TC6keUA"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:

```
{err: "Credenciais inválidas!"}
```
