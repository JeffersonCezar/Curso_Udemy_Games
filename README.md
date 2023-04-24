# API de Games
Esta API fornece informações sobre o cadastro de Games para a plataforma do Microsoft XBox.

## ENDPOINTS
### GET /games
Listar todos os games do banco de Dados.
#### Parâmetros
Nenhum
#### Respostas
##### 200 - OK
Esta resposta indica que a listagem foi acessada e carregada corretamente
```
Exemplo de resposta:
    {
        "id": 6487,
        "game_name": "\"ZAZEN\", zen meditation game",
        "game_web": null,
        "game_publisher": "Nangok Software",
        "game_developer": "Nangok Software",
        "game_release": "2021-01-01",
        "release": "07 June 2017",
        "game_plataform": "Xbox One",
        "game_genre": "Simulation, Health & Fitness",
        "game_hardware": "Kinect Required",
        "game_notes": null,
        "game_medium": "Digital only",
        "game_size": "1.51GB",
        "game_completion_est": "200+ hours",
        "game_links": null,
        "game_features": null,
        "createdAt": null,
        "updatedAt": null
    },
```
##### 400 - Bad Request
Requisição encaminhada para listagem do catálogo não pôde ser atendida pelo Servidor.
##### 401 - Unauthorized
Falha na autenticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{
    "err": "Token Inválido"
}
```
##### 404 - Not Found
Registros especificado não encontrado

### GET /game/:id
Resgatar um registro em Games.
#### Parâmetros
id --> Chave de identificação do registro do Game no catálogo.
#### Respostas
##### 200 - OK
Esta resposta indica que o registro solicitado foi retornado.
##### 400 - Bad Request
Parâmetro passado para a requisição é inválido.
##### 401 - Unauthorized
Falha na autenticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{
    "err": "Token Inválido"
}
```
##### 404 - Not Found
Registros especificado pelo parâmetro não pôde ser retornado.

### POST /game
Cadastrar um Game no catálogo.
#### Parâmetros
Nenhum
#### Respostas
##### 200 - OK
Esta resposta indica que o cadastro do game foi realizado corretamente.
##### 401 - Unauthorized
Falha na autenticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{
    "err": "Token Inválido"
}
```

### POST /auth
Autenticação de acesso à API, exibindo informações customizadas e alterações nos registros cadastrados.
#### Parâmetros
email: email do usuário cadastrado no sistema.
password: senha do usuário cadastrado no sistema.
```
Exemplo:
{
    "email": "xxxx@email.com",
    "password": "xxxxx"
}
```
#### Respostas
##### 200 - OK
Retorno do Token de aplicação bem sucedida.
```
Exemplo:
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwibmFtZSI6IkFkbWluaXN0cmFkb3IiLCJlbWFpbCI6ImFkbWluQGVtYWlsLmNvbSIsImlhdCI6MTY4MjM3NDQzMiwiZXhwIjoxNjgyMzc4MDMyfQ.ZqMxURAgabp_70wdTF_sVgl1YBjbsL8lGofKzWBqlZ8"
}
```
##### 401 - Unauthorized
Falha na autênticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{err: "Usuário/Senha inválido"}
```

### DELETE /game/:id
Excluir Game do catálogo
#### Parâmetros
id --> Chave de identificação do registro a ser excluído do catálogo.
#### Respostas
##### 200 - OK
Esta resposta indica que a exclusão foi realizada corretamente
##### 400 - Bad Request
Requisição encaminhada para exclusão do registro do catálogo, não pôde ser atendida pelo Servidor.
##### 401 - Unauthorized
Falha na autênticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{
    "err": "Token Inválido"
}
```
##### 404 - Not Found
Registros especificado não encontrado

### PUT /game/:id
Atualixar Game do catálogo
#### Parâmetros
id --> Chave de identificação do game no catálogo.
#### Respostas
##### 200 - OK
Esta resposta indica que a atualização aconteceu corretamente.
##### 400 - Bad Request
Requisição encaminhada para atualização do catálogo, não pôde ser atendida pelo Servidor.
##### 401 - Unauthorized
Falha na autênticação da aplicação. Possível Token inválido para o pedido da requisição.
```
Exemplo de Resposta:
{
    "err": "Token Inválido"
}
```
##### 404 - Not Found
Registros especificado não encontrado
