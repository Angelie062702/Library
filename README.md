# Library API Documentation

*Welcome to the Library API! This API offers a comprehensive solution for managing library resources, including users, authors, and books. Designed with simplicity and scalability in mind, the API allows developers to seamlessly integrate library management features into their applications. Whether you're building a library management system, a book cataloging app, or any system requiring robust CRUD functionality, this API is built to handle your needs.*

*With clear and structured endpoints, the Library API ensures secure access to resources and efficient data handling. From user authentication to managing relationships between books and authors, this API streamlines every aspect of library operations, making it an ideal choice for developers and library administrators alike.*

---

## Table of Contents
1. [User Endpoints](#user-endpoints)  
2. [Author Endpoints](#author-endpoints)  
3. [Books Endpoints](#books-endpoints)


##### User REGISTRATION
#### URL: POST /user/register
####  Method: POST

### Payload
```bash
{
  "username": "your_username",
  "password": "your_password"
}
```
### Response
### SUCCESS
```bash
{
  "status": "success",
  "token": null,
  "data": null
}
```

##### User Authentication
#### URL: POST /user/auth
####  Method: POST

### Payload
```bash
{
  "username": "your_username",
  "password": "your_password"
}
```
### Response
### SUCCESS
```bash
{
  "status": "success",
  "token": "token from auth",
  "data": null
}
```
## User Endpoints
##### SHOW Users
#### URL: POST /user/show
####  Method: POST

### Payload
```bash
{
    "token": "token from auth"
}

```
### Response
### SUCCESS
```bash
{
  "status": "success",
  "users": [
    {
      "id": 1,
      "username": "user1"
    },
    {
      "id": 2,
      "username": "user2"
    }
  ]
}

```

##### Update USER
#### URL: POST /user/update{id}
####  Method: POST

### Payload
```bash
{
    "new_username": "321",
    "new_password": "321"
}

```
### Response
### SUCCESS
```bash

{
  "status": "success",
  "message": "User updated successfully."
}

```
#### Delete USER
#### URL: DELETE /user/delete/{id}
####  Method: DELETE

### Payload
```bash
{
  "token": "token from auth",
}

```
### Response
```bash
{
  "status": "success",
  "message": "User deleted successfully."
}
```

## Author Endpoints
#### Register Author
#### URL: POST /author/register
####  Method: POST

### Payload
```bash
{
  "username": "123",
  "password": "123"
}

```
### Payload
```bash
{
  "status": "success",
  "message": "Author registered successfully."
}
```

### Update POST
**URL:** `POST /author/post`  
**Method:** `POST`  

#### Payload  
```
{
  "token": "from auth",
  "title": "book title"
}
```
#### Response
```
{
  "status": "success",
  "message": "Post updated successfully."
}
```

### Show AUTHOR
**URL:** `POST /author/show`  
**Method:** `POST`  

#### Payload  
```
{
  "token": "token from auth"
}
```
#### Response
```
{
  "status": "success",
  "data": [
    {
      "author_id": "1",
      "name": "Author Name",
      "books": [
        "Book Title 1",
        "Book Title 2"
      ]
    }
  ]
}

```

### Delete AUTHOR
**URL:** `DELETE /author/delete{id} 
**Method:** `DELETE`  

#### Payload  
```
{
  "token": " token from auth"
}
```
#### Response
```
{
  "status": "success",
  "message": "Author deleted successfully."
}

```
## Books Endpoints

### Show BOOKS
**URL:** POST /book/show 
**Method:** `POST`  

#### Payload  
```
{
  "token": "token from auth"
}
```
#### Response
```
{
  "status": "success",
  "data": [
    {
      "book_id": "35",
      "title": "Book Title",
      "author_id": "24"
    }
  ]
}

```

### Update Book
**URL:** PUT /book/update{id}
**Method:** `PUT`  

#### Payload  
```
{
"bookid": 35,
"token": "from auth",
"title": "book title"
}
```
#### Response
```
{
  "status": "success",
  "message": "Book updated successfully."
}
```
### Delete Book
**URL:** DELETE /book/delete{id}
**Method:** `DELETE`  

#### Payload  
```
{
  "bookid": 35,
  "token": "token from auth"
}

```
#### Response
```
{
  "status": "success",
  "message": "Book deleted successfully."
}

```

### View All Book-Author Relations
**URL:** POST /book/author/view
**Method:** `POST`  

#### Payload  
```
{
  "authorid": 24,
  "bookid": 36,
  "token": "token from auth"
}


```
#### Response
```
{
  "status": "success",
  "data": [
    {
      "relation_id": "11",
      "book_id": "7",
      "author_id": "4"
    }
  ]
}

```
## CREATED BY:
Angelie Mae V. Almen / BS INFOTECH 4D


















