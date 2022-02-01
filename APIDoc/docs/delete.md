---
sidebar_position: 4
---

# How to get comments on articles and create new comment.

### How to view articles, edit them and / or delete them.


**GET** (website)/article/:article_id:/comment
Get all comments on an article. 
- To get all comments on an article.
    - Make sure that you have the articles ID and put that in the endpoint.
    - 
---
**POST** (website)/article/:article_id:/comment
Create new comment on an article.
- To create a comment on an article.

---
    /articles/:article_id/comment
        GET, get all comments on selected article
        POST, create a new comment on article
    /articles/:article_id/comment/:comment_id
        GET, get a comment by ID on selected article
        DELETE, delete a comment by ID