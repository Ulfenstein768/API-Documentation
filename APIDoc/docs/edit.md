---
sidebar_position: 4
---

# How to get article, update and deletes. 
## Here is some info

### Endpoints to view, update and delete and article.
--- 
---

### Get specified article from article's id
**GET** (website_handle)**/articles/article_id**

To view a specified article you will need the ID of said article. 
- To view a specified article do a **GET** request to the **api/articles/(article_id)** endpoint
Output example
```bash
{
    "message": "Article details loading...",
    "data": {
        "_id": "314159265359",
        "title": "Article title",
        "subtitle": "This is an article",
        "published": false,
        "content": "Content for article",
        "author": "61f6d1f74b33436e479b9b65",
        "slug": "Article-title-2022-01-29",
        "created": "2022-01-29T14:10:49.333Z",
        "__v": 4,
        "comments": [],
        "posted_at": "2035-01-29T20:39:29.199Z",
        "slug_history": [
            "Article-title-2022-01-29"
        ]
    }
}
```
--- 
### Edit and Update an article
**PATCH** (website_handle)**/articles/article_id**

Edit an article
- To edit an article.
...
--- 

### Delete an article
**DELETE** (website_handle)**/articles/article_id**

Delete and article from the data base.
- To delete an article do a **DELETE** request to the **/articles/article_id** (Remember article's id)
Expected output:

```bash
{
    "status": "success",
    "message": "Article deleted"
}
}
```
If a success status is not displayed in the body, then there might be something wrong with the article's id.
