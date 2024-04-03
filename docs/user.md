# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "refaldy",
  "password": "rahasia",
  "name": "Refaldy Bagas Anggana"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "refaldy",
    "name": "Refaldy Bagas Anggana"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username already registered"
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "refaldy",
  "password": "rahasia"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "refaldy",
    "name": "Refaldy Bagas Anggana",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username or Password is wrong"
}
```

## Get User

Endpoint : GET /api/users/current

Headers :

- Authorization : token

Response Body (Success) :

```json
{
  "data": {
    "username": "refaldy",
    "name": "Refaldy Bagas Anggana"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint : PATCH /api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "password": "rahasia", // optional, if went to change password
  "name": "Refaldy Bagas Anggana" // optional, if went to change name
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "refaldy",
    "name": "Refaldy Bagas Anggana"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized"
}
```

## Logout User

Endpoint : DELETE /api/users/current

Headers :

- Authorization : token

Response Body (Success) :

```json
{
  "data": true
}
```
