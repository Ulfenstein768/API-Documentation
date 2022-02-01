---
sidebar_position: 2
---

# How to get and create articles.
### Here are some info on how you can use postman, to post, get and delete the articles.

### Endpoints to get all articles and to delete an article.
When doing a HHTP request the server talks back to you.

---

**GET** (website_handle)/articles

Fetch all articles on the server

- To fetch all articles in the database, do a GET request to the *articles* enpoint: 

---



**POST** (website_handle)/articles 

create a new article.

- When doing a POST request on the *articles* endpoint, the server will respond with a 400 status quote with the message:

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
### **Congratulations!!!**

#### You just posted your first article.