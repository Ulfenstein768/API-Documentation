---
sidebar_position: 5
---
# Comment section. 

---
## Comment section
### Get all comments on selected article.
**GET** **/articles/:article_id/comment**

To view comments on an article, you will need (like when viewing an article) the article's id.

- To view all comments on an article do a **GET** request to the **api/articles/:article_id/comment** endpoint

Output example:
```bash
{
    "message": "Loading comments...",
    "data": [
        {
            "_id": "314159265359",
            "posted_at": "2022-02-02T09:29:12.911Z",
            "name": "author1",
            "email": "authorEmail@gmail.com",
            "comment": "This is a comment",
            "article_id": "61fa46cf4aa66ca4a1e4310c"
        },
        {
            "_id": "2.71828",
            "posted_at": "2022-02-02T09:30:36.895Z",
            "name": "author2",
            "email": "anotherAuthor@gmail.com",
            "comment": "This is a comment another",
            "article_id": "61fa46cf4aa66ca4a1e4310c"
        },
    ]
}
```
--- 
### Create a new comment on an article
**POST** **/articles/:article_id/comment**
To post a comment on an article, do the same thing like when you create an article.

- Send a **POST** request to **/articles/:article_id/comment** endpoint
The server will respond with an error:
```bash
{
    "message": "'name' is required"
}
```
Add a key with the value of *"name"* and send again: 

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- Your author *_id* --** | 

Again the server will respond with:
```bash
{
    "message": "'email' is required"
}
```
Add another key with the value of *email* and send again:

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- Your author *_id* --** | 
|`email`|   **-- Your *email* --** |

The server will respond with: 
```bash
    "message": "'comment' is required"
```

The last thing to is to add the comment as a key with the value *comment*.

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- Your author *_id* --** | 
|`email`|   **-- Your *email* --** |
|`comment`|   **-- The greatest comment --** |

And then send again.

Expected output:
```bash
    {
    "message": "New comment created",
    "data": {
        "_id": "314159265359",
        "posted_at": "2022-02-02T09:44:28.564Z",
        "name": "Your author _id",
        "email": "your email",
        "comment": "The greatest comment",
        "article_id": "61fa46cf4aa66ca4a1e4310c"
    }
}
```
--- 

### Get comments on a specified article.
**GET** **/articles/:article_id/comment/:comment_id**
To get a specified comment you will need the *id* of the desired article and then the *id* of a comment you want to view.

- To get a specified comment send a **GET** request to the **/articles/:article_id/comment/:comment_id** endpoint.

expected output:
```bash
{
    "message": "Loading comment...",
    "data": {
        "_id": "314159265359",
        "posted_at": "2022-02-02T09:29:12.911Z",
        "name": "author _id",
        "email": "Authors comment",
        "comment": "The greatest comment",
        "article_id": "61fa46cf4aa66ca4a1e4310c"
    }
}
```

---
### Delete a comment.
**DELETE** **/articles/:article_id/comment/:comment_id**

Like when getting a specified comment, you will need the *id* of the article and the *id* of the comment you want to delete.

- to delete a specified comment do a **DELETE** request on the **/articles/:article_id/comment/:comment_id** endpoint.

Epxected output
```bash
        "message": "Comment deleted",
    "data": {
        "_id": "61fa46cf4aa66ca4a1e4310c",
        "comments": [
            {
                "_id": "61fa4f3c4aa66ca4a1e43122",
                "posted_at": "2022-02-02T09:30:36.895Z",
                "name": "author _id",
                "email": "Authors email",
                "comment": "The greatest comment",
                "article_id": "61fa46cf4aa66ca4a1e4310c"
            },
```

---