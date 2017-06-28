# Users

**erdiko/users package**

The `erdiko/users` is a package adding Service Models and AJAX endpoints for user management in a Erdiko application.

### Package Installation:

Install the package via composer:

`composer require erdiko/users`
    

## Intro

This package provides ORM entities & service models to manage user records, and exposes AJAX endpoints to allow your application to interact with these service models.


## Setup / Configuration

### Create / Install the DB

Add required tables into your database running in order the .sql files placed in sql directory inside the package.

### Add the required routes to your Erdiko application

#### Add Login controller's route.

#### Add UserAuthenticationAjax controller's route.

#### Add \admin\Userajax controller's route.

#### Add Userajax controller's route.


## Current Directory Structure


```
├── composer.json
├── scripts
├── sql
│   ├── dumps
│   └── updates
├── src
│   ├── controllers
│   ├── entities
│   ├── models
│   ├── shared
│   ├── validators
│   └── views
└── tests
```