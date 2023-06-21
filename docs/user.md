# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body : 

```json
{
    "username" : "embuncode",
    "password" : "password",
    "name" : "Sigit Wasis Subekti"
}
```

Response Body Success : 

```json
{
    "data" : {
        "username" : "embuncode",
        "name" : "Embun Code"
    }
}
```

Response Body Error : 

```json
{
    "errors" : "Username already registered"
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body : 

```json
{
    "username" : "embuncode",
    "password" : "password"
}
```

Response Body Success : 

```json
{
    "data" : {
        "token" : "unique-token"
    }
}
```

Response Body Error : 

```json
{
    "errors" : "Username or password wrong"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers : 
- Authorization : token

Request Body : 

```json
{
    "name" : "Embun Code Sigit", // optional
    "password" : "new password"  // optional
}
```

Response Body Success : 

```json
{
    "data" : {
        "username" : "Embun Code",
        "name" : "Sigit Wasis Subekti"
    }
}
```

Response Body Error : 

```json
{
    "errors" : "Name length max 100"
}
```

## Get User API

Endpoint : GET /api/users/current

Headers : 
- Authorization : token

Response Body Success : 

```json
{
    "data" : {
        "username" : "embuncode",
        "name" : "Sigit Wasis Subekti"
    }
}
```

Response Body Error : 

```json
{
    "errors" : "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers : 
- Authorization : token

Response Body Success : 

```json
{
    "data" : "OK"
}
```

Response Body Error : 

```json
{
    "errors" : "Unauthorized"
}
```