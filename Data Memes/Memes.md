## Memes 
---

**POST** `/memes`

Headers

**X-Access-Token:** Bearer `<token>`

**Content-Type:** mutlipart/form-data

> name = "image"

Body

```json
{
    "description": "Description message"
}
```

Response

```json
{
    "id": 1,
    "image": "/memes/juratbekoff_smilecat_00192.png"
}
```

Errors

> 400 - File "image" not provided

> 400 - Invlalid body parameters

---

**GET** `/memes?cat=1&page=3&limit=10`

Params

> cat - category id. if not provided must be return all memes

> page - page index. if not provided must be return memens by category without paging (all)

> limit - memes count per page. if not provided must be return 20 memes per page by default

Headers

**X-Access-Token:** Bearer `<token>`


Response

```json
{
    "page": 3,
    "limit": 10,
    "items": [
        {
            "id": 1,
            "author": {
                "id": 1,
                "nickname": "juratbekoff",
                "avatar": "/avatars/juratbekoff.png"
            },
            "createAt": "2023-04-12",
            "description": "Description message",
            "thumbnail": "/memes/juratbekoff_smilecat_00192_128px.png"
        }
        // ...
    ]
}
```


---

**GET** `/memes/:id`

Params

> id - requested meme id

Headers

**X-Access-Token:** Bearer `<token>`


Response

```json
{
    "id": 1,
    "author": {
        "id": 1,
        "nickname": "juratbekoff",
        "avatar": "/avatars/juratbekoff.png"
    },
    "createAt": "2023-04-12",
    "description": "Description message",
    "thumbnail": "/memes/juratbekoff_smilecat_00192_128px.png",
    "image": "/memes/juratbekoff_smilecat_00192.png",
    "likes": 12,
    "shares": 32,
    "comments": 5
}
```

---

**POST** `/memes/:id/comments`

Params

> id - requested meme id

Headers

**X-Access-Token:** Bearer `<token>`

```json
{
    "comment": "Comment text"
}
```

Response

```json
{
    "id": 132,
    "memeId": 1,
    "comment": "Comment text"
}
```

Errors

> 404 - Meme by id not found

> 400 - Invlalid body parameters


---

**GET** `/memes/:id/comments`

Params

> id - requested meme id

Headers

**X-Access-Token:** Bearer `<token>`

```json
[
    {
        "id": 132,
        "comment": "Comment text",
        "author": {
            "id": 12,
            "nickname": "alibek"
        }
    }
]
```

Errors

> 404 - Meme by id not found

---

**PATCH** `/memes/:id/like`

Params

> id - requested meme id

Headers

**X-Access-Token:** Bearer `<token>`

Response

```json
{
    "liked": true
}
```

Errors

> 404 - Meme by id not found

---

**GET** `/memes/:id/share`

Params

> id - requested meme id

Headers

**X-Access-Token:** Bearer `<token>`

Response

```json
{
    "shareLink": "https://{domain}/public/meme/{{uuid}}"
}
```

Errors

> 404 - Meme by id not found
