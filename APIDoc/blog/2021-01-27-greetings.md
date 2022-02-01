---
slug: greetings
title: Project Introduction and Description
authors:
  - name: Úlfur Þór
    title: Student at Reykjavík Academy of Web Development
    url: https://github.com/Ulfenstein789
    image_url: https://github.com/Ulfenstein768.png
---


## Back End and Infastructure

### Who are we?
We are a student group in the Reykjavík Academy of Web Development and we are doing a group project in school. 
This group porject is in the theme of Back-end and Infrastructure and about learning the basics of and essentials of backe end development.
The project is to create a back-end application in the form of an API.

### What are we doing?

We decided to go with a showroom and we wanted to make it possible for the user to get all the articles posted on our server, edit and / or delete your own posts, comment and view comments for others on relevant posts.


## Do the introduction here, Tech stack, ect. Check evaluation to check




    *website*/articles
        GET, get all articles
        POST, create new article
    /articles/:article_id
        GET, view a single article
        PATCH, update an article
        DELETE, delete an article
    /articles/:article_id/comment
        GET, get all comments on selected article
        POST, create a new comment on article
    /articles/:article_id/comment/:comment_id
        GET, get a comment by ID on selected article
        DELETE, delete a comment by ID

