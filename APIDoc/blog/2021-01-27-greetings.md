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
---

API is short for ‘Application Programming Interface’ . An API is a set of rules that lets programs talk to each other, exposing data and functionality across the Internet in a consistent format.

REST stands for ‘Representational State Transfer’. This is an architectural pattern that describes how distributed systems can expose a consistent interface. When people use the term ‘REST API’, they are generally referring to an API accessed using the HTTP protocol at a predefined set of URLs.

These URLs represent various resources — any information or content accessed at that location, which can be returned as JSON, HTML, audio files, or images. Often resources have one or more methods that can be performed on them over HTTP, like GET, POST, PUT, and DELETE. The action represented by the first and last of these is clear, but POST and PUT have specific meanings. How they are defined is confusing, but the general rule is: use POST to create resources, and PUT to update resources.

---




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

