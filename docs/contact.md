# Contact API Spec

## Create Contact

Endpoint : POST `/api/contacts`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
    "firstname": "Adi Nugroho",
    "lastname": "Bagus",
    "email": "adinugroho@example.com",
    "phone": "08123456789"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "firstname": "Adi Nugroho",
    "lastname": "Bagus",
    "email": "adinugroho@example.com",
    "phone": "08123456789"
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Email Not valid"
}
```

## Update Contact

Endpoint : PUT `/api/contacts/{idContact}`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
    "firstname": "Adi Nugroho",
    "lastname": "New Bagus",
    "email": "adinugroho@example.com",
    "phone": "08123456789"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "firstname": "Adi Nugroho",
    "lastname": "New Bagus",
    "email": "adinugroho@example.com",
    "phone": "08123456789"
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Email Not valid"
}
```

## Get Contact

Endpoint : GET `/api/contacts/{idContact}`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "firstname": "Adi Nugroho",
    "lastname": "Bagus",
    "email": "adinugroho@example.com",
    "phone": "08123456789"
  }
}
```

Response Body (Failed, 404):

```json
{
  "errors" : "Contact Not Found"
}
```

## Search Contact

Endpoint : GET `/api/contacts`

Query Param :
- name : String, contact first name or last name, using like query, optional
- phone : String, contact phone, using like query, optional
- email : String, contact email, using like query, optional
- page : Integer, start from 0, default 0
- size : Integer, default 10

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : [
    {
      "id": "random-string",
      "firstname": "Adi Nugroho",
      "lastname": "Bagus",
      "email": "adinugroho@example.com",
      "phone": "08123456789"
    }
  ],
  "paging" : {
    "currentpage": 0,
    "size": 10,
    "totalpage": 10
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Unauthorized"
}
```

## Delete Contact

Endpoint : DELETE `/api/contacts/{idContact}`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : "OK"
}
```

Response Body (Failed):

```json
{
  "errors" : "Contact is Not Found"
}
```