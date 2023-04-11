# Todos

**POST** `/account`

```json
{
    "name": "John",
    "username": "john-doe",
    "password": "1234"
}
```

Response

```json
{
    "id": 1,
    "name": "John Doe",
    "username": "john-doe",
    "token": "a839cfbe6465e713f3485bc1d73d6c6feb1036a3"
}
```

* `token` - generated unique key with SHA1 or MD5 hash, store them to database

---

**DELETE** `/account`

Token: `<token>`

```json
{
    "message": "Account and todos has been deleted",
    "todos": 13
}
```