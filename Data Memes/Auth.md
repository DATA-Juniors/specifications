## Auth 
---

<br>

> Route `/auth`

<br>

**POST** `/register`

```json
{
    "name": "Juratbek",
    "surname": "Off",
    "nickname" : "juratbekoff",
    "password" : "ielts7"
}
```

Response

```json
{
    "userId": 1,
    "nickname": "juratbekoff",
    "name": "Juratbek",
    "surname": "Off",
    "token": "yJhbGciOiJIUzI1NiJ9.eyJSb2xlIjoiQWRtaW4iLCJJc3N1ZXIiOiJ"
}
```
Errors

> 400 - Invalid body params

> 409 - username already taken



---

**POST** `/login`

```json
{
    "nickname" : "juratbekoff",
    "password" : "ielts7"
}
```

Response

```json
{
    "userId": 1,
    "nickname": "juratbekoff",
    "name": "Juratbek",
    "surname": "Off",
    "token": "yJhbGciOiJIUzI1NiJ9.eyJSb2xlIjoiQWRtaW4iLCJJc3N1ZXIiOiJ"
}
```

Errors

> 400 - Invalid body params


> 403 - User not found or wrong credentials

---

**GET** `/verify`

Headers

**X-Access-Token:** Bearer `<token>`

Response

```
200 OK
```

Errors

> 400 - access token not provided

> 401 - invalid or expired token