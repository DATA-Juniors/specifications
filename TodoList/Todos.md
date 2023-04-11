# Todos

**GET** `/todos`

Token: `<token>`

```json
[
    {
        "id": 1,
        "title": "Complete homework",
        "isCompleted": false
    },
    ...
]
```
---
**POST** `/todos`

Token: `<token>`


Request
```json
{
    "title": "Complete homework"
}
```

Response

```json
{
    "id": 2,
    "title": "Complete homework",
    "isCompleted": false
}
```
---
**PUT** `/todos/:id`

Token: `<token>`


```json
{
    "title": "Complete homework"
}
```

Response

```json
{
    "id": 2,
    "title": "Complete homework",
    "isCompleted": false
}
```

---

**PATCH** `/todos/:id`

Token: `<token>`


```json
{
    "isCompleted": true
}
```

Response

```json
{
    "id": 2,
    "title": "Complete homework",
    "isCompleted": true
}
```


---

**DELETE** `/todos/:id`

Token: `<token>`

Response

```json
{
    "id": 2,
    "title": "Complete homework",
    "isCompleted": true
}
```


