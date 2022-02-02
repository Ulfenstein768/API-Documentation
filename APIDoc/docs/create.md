---
sidebar_position: 3
---
# Article Creation.

---
## How to view articles.

### Get all articles.
**GET** (website_handle)**/api/articles**
- To get all articles in the database, do a GET request to the **api/articles** enpoint

Output example
```bash
{
    "status": "success",
    "message": "Articles retrieved successfully",
    "data": [
        {
            "_id": "314159265359",
            "title": "Article title",
            "subtitle": "This is an article",
            "published": true,
            "content": "Content for article",
            "author": "61f6d1f74b33436e479b9b65",
            "slug": "slug-2022-01-29",
            "created": "2022-01-29T13:52:39.134Z",
            "__v": 15,
            "comments": [],
            "posted_at": "2035-01-29T20:39:39.474Z",
            "slug_history": [
                "slug-2022-01-29-2",
                "slug-2022-01-29-1",
                "slug-2022-01-29"
            ]
        },
        ...
            ...
}
```
---
### Get specified article.
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
## How to create, edit and delete articles.
### Create a new article.
 **POST** (website_handle)**/api/articles**

- When doing a POST request on the **api/articles** endpoint, the server will respond with a 400 HTTP status request with the message:

```bash
{
    "message": "'title' is required"
}
```
- To add a title, add title in as a key and then the key's value is supposed to be you desired *title* for you article and then send a POST request again: 
      
|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`title`|   // Your title // |Title of article    

- When you have added a title and sent another POST request, the server tells you that you will need *content* for the article: 
```bash
{
    "message": "'content' is required"
}
```
|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`title`|   **--Your title --** |Title of article    
|`content`| **-- Your content --** | Content you want in article
- When finished adding the content for you article, this message will pop up on the sever side: 
```bash
{
    "message": "'author' is required"
}
```
- Add you author **_id** in the author field:

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`title`|   **-- Your Title --** |Title of article    
|`content`| **-- Here you write your article --** | Content you want in article
|`author`| **-- Your _id --** | Name of author

- After adding the author for the article, this message will show: 
```bash
{
    "message": "New article created!",
    "data": {
        "_id": "314159265359",
        "slug_history": [
            "hello-2022-01-30"
        ],
        "posted_at": "2022-01-30T16:48:21.482Z",
        "title": "// Your Title // ",
        "content": "// Here you write your article //",
        "author": "314159265359",
        "slug": "hello-2022-01-30",
        "__v": 0
    }
}
```
#### **Congratulations!!!**

#### You just posted your first article.
--- 
### Edit an article
**PATCH** (website_handle)**/articles/article_id**

Remember when we edited our author data? The same goes for when editing an article. You want to put in the same keys as when creating an article, but change the keys' value to something different:


|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`title`|   **-- New title --** |
|`conntent`| **-- New content --** | 

- To edit an article send a **PATCH** request to **/articles/article_id** 

Expected output: 
```bash
{
    "message": "Article Info updated",
    "data": {
        "published": false,
        "_id": "314159265359",
        "comments": [],
        "slug_history": [
            "my-article-2022-02-02",
            "my-new-article-2022-02-02"
        ],
        "posted_at": "2022-02-02T08:54:39.194Z",
        "title": "Updated title",
        "content": "Updated content",
        "author": "314159265359",
        "slug": "my-new-test-2022-02-02",
        "__v": 1
    }
}
```

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
If a success status is not displayed in the body, then there might be something wrong with the article's *_id*
