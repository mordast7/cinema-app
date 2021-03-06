# Cinema Application

## Overview
Cinema-app is a web application where registered user clients can purchase tickets for a movie. Also, it gives a lot of tools for Admin users to perform CRUD operations on Movies, Cinema Halls, and Movie Sessions.

Service includes such tools as:

* Email validation
* Password hashing (BCrypt)

## Application functions
When you enter the application website you enter like a guest, and you have access only to these actions:

* Login 
* Register as a new user

When you will log in as a user with role `USER`, you could perform these actions:

* See all existing cinema halls, movies and movie-sessions 
* Add a ticket to the shopping cart after choosing movie-session 
* Create order from previously added tickets 
* See order history and purchased tickets of the current user account 
* Logout

When you will log in as a user with role `ADMIN`, you could perform these actions:

* See all existing cinema halls, movies, and movie-sessions 
* Create, modify and delete cinema-hall, movies, and movie sessions from the database 
* Get user info by email 
* Logout


## Table relations
The diagram below represents classes and connections between entities, built inside this app

![Table relations](images/entitySchema.png)

## Project is based on 3-layered architecture:

* Data access layer (DAO)
* Application layer (service)
* Presentation layer (controllers)

## REST end points:
```
POST: /login - all
POST: /register - all
GET: /cinema-halls - user/admin
POST: /cinema-halls - admin
GET: /movies - user/admin
POST: /movies - admin
GET: /movie-sessions/available - user/admin
POST: /movie-sessions - admin
PUT: /movie-sessions/{id} - admin
DELETE: /movie-sessions/{id} - admin
GET: /orders - user
POST: /orders/complete - user
PUT: /shopping-carts/movie-sessions - user
GET: /shopping-carts/by-user - user
GET: /users/by-email - admin
```

## Technologies used

* Java 11
* Spring (MVC, Security, Web)
* Hibernate
* Apache Tomcat (9.0.50)
* MySQL
* Maven

## How to run this project

1. Install MySQL
1. Load dependencies which are described in `pom.xml`
1. Change `username`, `password`, and `URL` values in the `resources/db.properties` file to open a connection with your database
1. Configure Apache Tomcat (v9.0.50) for your IDE
1. Launch the application and start using it at `http://localhost:%your_port%`
1. Interact with end points using <a href="https://www.postman.com">Postman</a>