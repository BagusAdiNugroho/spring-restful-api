# Address API Spec

## Create Address

Endpoint : POST `/api/contacts/{idContact}/addresses`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
    "street": "Jalan Jalan",
    "city": "Kota",
    "province": "Provinsi",
    "country": "Negara",
    "postal_code": "12345"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "street": "Jalan Jalan",
    "city": "Kota",
    "province": "Provinsi",
    "country": "Negara",
    "postal_code": "12345"
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Address Not valid"
}
```

## Update Address

Endpoint : PUT `/api/contacts/{idContact}/addresses/{idAddress}`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
    "street": "Jalan Jalan",
    "city": "Kota",
    "province": "Provinsi",
    "country": "Negara",
    "postal_code": "12345"
 }
```
Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "street": "Jalan Jalan",
    "city": "Kota",
    "province": "Provinsi",
    "country": "Negara",
    "postal_code": "12345"
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Address Not valid"
}
```

## Get Address

Endpoint : GET `/api/contacts/{idContact}/addresses/{idAddress}`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : {
    "id": "random-string",
    "street": "Jalan Jalan",
    "city": "Kota",
    "province": "Provinsi",
    "country": "Negara",
    "postal_code": "12345"
  }
}
```

Response Body (Failed):

```json
{
  "errors" : "Address Not Found"
}
```

## Delete Address

Endpoint : DELETE `/api/contacts/{idContact}/addresses`

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
  "errors" : "Address Not Found"
}
```

## List Address

Endpoint : GET `/api/contacts/{idContact}/addresses`

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success):

```json
{
  "data" : [
    {
      "id": "random-string",
      "street": "Jalan Jalan",
      "city": "Kota",
      "province": "Provinsi",
      "country": "Negara",
      "postal_code": "12345"
    },
    {
      "id": "random-string",
      "street": "Jalan Jalan",
      "city": "Kota",
      "province": "Provinsi",
      "country": "Negara",
      "postal_code": "12345"
    }
  ]
}
```

Response Body (Failed):

```json
{
  "errors" : "Address Not Found"
}
```