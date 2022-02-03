--- 
sidebar_position: 2
---
# Author Creation

---
## How to view and create authors.

### Creating an author.
**POST** **/api/authors**
- To create an author send a **POST** request to the **/api/authors** endpoint. 
The server will return with a 400 HTTP status and display an error message:
```bash
{
    "message": "'name' is required"
}
```
Add name as the key and the key's value should be your desired author *name* and send the **POST** request again:

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- Your author name --** |   

When you have added your author name,  the server tells you that you will need to add your *email*.
```bash
{
    "message": "'email' is required"
}
```
Put in your email adress and send again:

|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- Your author name --** |
|`email`| **-- Your email --** | 

When you have sent a **POST** request with you *name* and *email* a message will show up: 
```bash
{
    "message": "New author created!",
    "data": {
        "articles": [],
        "_id": "314159265359",
        "name": "yourName",
        "email": "example@gmail.com",
        "__v": 0
    }
}
```
#### And now you have an authors account!

#### **!!! IMPORTANT !!!**
####  *BE SURE TO REMEMBER YOU _id FOR LATER USE* 
--- 
### Authors' information.
**GET** **/api/authors**
- To view all authors, send a **GET** request to the **/api/authors** endpoint. 

expected data: 
```bash
"status": "success",
    "message": "Authors retrieved successfully",
    "data": []
```
The list of authors should be displayed in the ```data``` array.
--- 

## How to edit and, or delete authors.
### View a specified author.
**GET** **/authors/:author_id**

Remember when we asked you to remember you author's id?

This is why: 

- If you want to see articles from another author you will need his/hers author **_id**

When you have the author **_id** from the author you will have to do a **GET** request to **/authors/:author_id** to view a specified author.

Expected output: 
```bash
{
    "message": "Loading author",
    "data": {
        "_id": "314159265359",
        "articles": [],
        "name": "authorName",
        "email": "example@gmail.com",
        "__v": 0
    }
}
```

--- 
### Update author information
**PATCH** **/api/authors/:authors_id**

Earlier, when creating an author you had to put in your author's name and your email. So when a updating an author, you want to put the *keys* "name" and "email" in and change the value to the desired *name* and *email*.

- To update an author, send an updated "name" and "email" values to the **PATCH** request to the **/api/authors:authors_id** endpoint. 


|KEY  |VALUE             |DESCRIPTION
|----------|----------------------------|---------------
|`name`|   **-- New author name --** |
|`email`| **-- New email --** | 

Expected output: 
```bash
{
    "message": "Author updated",
    "data": {
        "_id": "314159265359",
        "articles": [],
        "name": "yourNewName ",
        "email": "NewExample@gmail.com",
        "__v": 0
    }
}
```

---
### Delete an author.

**DELETE** **/api/authors/:authors_id**

- To delete an author. Simply send a **DELETE** request to the **/api/authors/:authors_id** endpoint.

Expected output:
```bash
{
    "status": "success",
    "message": "Author deleted"
}
```
