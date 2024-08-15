# User Api Spec

## Register User
Endpoint : POST `/api/users/register`

Request Body :

```json
{
    "username": "adinuegroho",
    "password": "password",
    "name": "Adi Nugroho"
 }
```
Response Body (Success):

```json
{
  "data" : "OK"
}
```

Response Body (Failed):

```json
{
  "errors" : "Username already exist/Not valid"
}
```

## Login User

Endpoint : POST `/api/auth/login`

Request Body :

```json
{
    "username": "adinuegroho",
    "password": "password"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "token" : "Token",
    "expiredAt" : 2323232 // milliseconds
  }
}
```

Response Body (Failed, 401):

```json
{
  "errors" : "Username Password not match"
}
```

## Update User

Endpoint : PATCH `/api/users/current`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
    "name": "Adi Nuegroho",
    "password": "password"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "username" : "adinuegroho",
    "name" : "Adi Nuegroho" 
  }
}
```

Response Body (Failed, 401):

```json
{
  "errors" : "Unauthorized"
}
```

## Get User

Endpoint : GET `/api/users/current`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : {
    "username" : "adinuegroho",
    "name" : "Adi Nugroho" 
  }
}
```

Response Body (Failed, 401):

```json
{
  "errors" : "Unauthorized"
}
```

## Logout User

Endpoint : DELETE `/api/auth/logout`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : "OK"
}
```