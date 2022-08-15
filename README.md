# API_REST_JWT_and_CONSUME_API
This API is used to list and register games on a page, like a web store.
## EndPoints
### GET /games
This endpoint is responsible for returning all games registered in the database.
#### Parans
None
#### Answers
##### OK! 200
If this answer happens you will get a list of all games.

Example answer:
```
[
    {
        "id": 13,
        "title": "Battlefield 7",
        "year": 2025,
        "produtora": "EA",
        "price": 375,
        "createdAt": "2022-08-12T07:19:45.000Z",
        "updatedAt": "2022-08-12T07:20:45.000Z"
    },
    {
        "id": 14,
        "title": "Resident Evil 4 Remake",
        "year": 2023,
        "produtora": "CAPCON",
        "price": 220,
        "createdAt": "2022-08-12T07:24:58.000Z",
        "updatedAt": "2022-08-12T07:24:58.000Z"
    },
    {
        "id": 15,
        "title": "Resident Evil 6",
        "year": 2017,
        "produtora": "PUBG CORP",
        "price": 75,
        "createdAt": "2022-08-12T07:39:45.000Z",
        "updatedAt": "2022-08-12T07:39:45.000Z"
    }
]
```

##### Authentication failed! 401
If this answer happens, means that there was a failure during the authentication process of the request. Motivos: Invalid Token, Expired Token.

Example answer:
```
{
    "erro": "Token inválido"
}
```

### POST /auth
This endpoint is responsible for logging in.
#### Parans
email: User email registered in the system.

password: User password registered in the system, with that particular email.

Exemplo:
```
{
    "email": "email@email.com",
    "password": "password123"

}
```

#### Answers
##### OK! 200
If this answer happens you will receive the JWT token to be able to access protected endpoints in the API.

Exemplo answer: 
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IlpXVCJ9.eyJpZCI6NCwiZW1haWwiOiJ0YXNzaWFuZUBob3RtYWlsLmNvbSIsImlhdCI6MTY2MDU3MTIzNSwiZXhwIjoxNjYwNzQ0MDM1fQ.Nyu2l43dZkkSE3-Nlz-8Nnvdw_It_Q--Xoe4a3msSmE"
}
```
##### Authentication failed! 401
If this answer happens, means that there was a failure during the authentication process of the request. Motivos: Invalid email or password.

Exemplo answer:
```
{
    "erro": "Senha inválida"
}
```

