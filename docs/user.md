# User API

## Register User API

### Endpoint : POST api/user/register

Request Body :

```json
{
  "username": "yurino",
  "name": "yurino ahmad",
  "email": "yurino@mail.co",
  "password": "exampletest"
}
```

Response Success :

```json
{
  "code": 201,
  "message": "Created",
  "data": {
    "username": "yurino",
    "name": "yurino ahmad",
    "email": "yurino@mail.co"
  }
}
```

Response Error :

- status : 400

```json
{
  "code": 400,
  "message": "Bad Request",
  "errors": "Username already exist"
}
```

- status : 401

```json
{
  "code": 401,
  "message": "Unauthorized",
  "errors": "Username already exist"
}
```

## Login User API

### Endpoint : POST api/user/login

Request body:

```json
{
  "username": "yurino",
  "password": "exampletest"
}
```

Response success:

```json
{
  "code": 200,
  "message": "Ok",
  "data": {
    "token": "$2y$10$DLZ/9Obv.oladzt7oPT2Jurbnz3JyYneFYkUwtjXqA5whLbi3Qpza"
  }
}
```

Response Error:

```json
{
  "code": 400,
  "message": "Bad request",
  "errors": "Username or Password wrong"
}
```

## Update User API

### Endpoint: PATCH api/user/current

Headers:

```json
{
  "Authorization": "$2y$10$DLZ/9Obv.oladzt7oPT2Jurbnz3JyYneFYkUwtjXqA5whLbi3Qpza"
}
```

Request Body:

```json
{
  "username": "yudina", // optional
  "name": "yudini burma", // optional
  "email": "yudina@gmail.com" // optional
}
```

Response success:

```json
{
  "code": 200,
  "message": "Ok",
  "data": {
    "username": "yudina",
    "name": "yudini burma",
    "email": "yudina@gmail.com"
  }
}
```

Response Error:

```json
{
  "code": 401,
  "message": "Unauthorized",
  "errors": "not allowed to access"
}
```

## GET user API

### Endpoint: GET api/user/current

Headers:

```json
{
  "Authorization": "$2y$10$DLZ/9Obv.oladzt7oPT2Jurbnz3JyYneFYkUwtjXqA5whLbi3Qpza"
}
```

Response Succes:

```json
{
  "code": 200,
  "message": "Ok",
  "data": {
    "username": "yudina",
    "name": "yudini burma",
    "email": "yudina@gmail.com"
  }
}
```

Response Error:

```json
{
  "code": 401,
  "message": "Unauthorized",
  "errors": "Not allowed to access"
}
```

## Logout User API

### Endpoint: DELETE api/user/logout

Headers:

```json
{
  "Authorization": "$2y$10$DLZ/9Obv.oladzt7oPT2Jurbnz3JyYneFYkUwtjXqA5whLbi3Qpza"
}
```

Response Succes:

```json
{
  "code": 200,
  "message": "Ok",
  "data": {}
}
```

Response Error:

```json
{
  "code": 401,
  "message": "Unauthorized",
  "errors": "Not allowed to access"
}
```
