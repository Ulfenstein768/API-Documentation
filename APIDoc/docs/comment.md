---
sidebar_position: 5
---

# Comment section. 
## Here is how you can add, delete comments and how to view all comments or a specified comment.

### Endpoints to view comments and add a comment.
--- 
---

### Get all comments on selected article.
**GET** (website_handle)**/articles/:article_id/comment**

To view comments on an article, you will need (like when viewing an article) the article's id.
- To view all comments on an article do a **GET** request to the **api/articles/:article_id/comment** endpoint

Output example
```bash

```
--- 
### Create a new comment on an article
**POST** (website_handle)**/articles/:article_id/comment**

Edit an article
- To edit an article.
...

--- 

### Get comments on a specified article.
**GET** (website_handle)**/articles/:article_id/comment/:comment_id**
Get a specified comment
- To get a specified comment
---

### Delete a comment.
**DELETE** (website_handle)**/articles/:article_id/comment/:comment_id**
Delete a specified comment.
- to delete a specified comment do a **DELETE** request on the **/articles/:article_id/comment/:comment_id** endpoint.

Epxected output
```bash
    - article deleted.
```

---