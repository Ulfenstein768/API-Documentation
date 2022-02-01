---
sidebar_position: 3
---

# How to get and create articles.
## Here are some info on how you can use postman to add, get and delete the articles.

#### Endpoints to get all articles and to delete an article.
When doing a HHTP request the server talks back to you.

---


### Get all articles on the server
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
|`title`|   // Your title // |Title of article    
|`content`| // Your content // | Content you want in article
- When finished adding the content for you article, this message will pop up on the sever side: 
```bash
{
    "message": "'author' is required"
}
```
- Add you name in the author field:

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`title`|   // Your Title // |Title of article    
|`content`| // Here you write your article // | Content you want in article
|`author`| // Author's name // | Name of author

- After adding the author for the article, this message will show: 
```bash
{
    "message": "New article created!",
    "data": {
        "_id": "61f6c15597a694b0323bb738",
        "slug_history": [
            "hello-2022-01-30"
        ],
        "posted_at": "2022-01-30T16:48:21.482Z",
        "title": "// Your Title // ",
        "content": "// Here you write your article //",
        "author": "// Authors name //",
        "slug": "hello-2022-01-30",
        "__v": 0
    }
}
```
#### **Congratulations!!!**

#### You just posted your first article.