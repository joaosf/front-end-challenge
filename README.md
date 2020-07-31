# Bravosul Front-End Challenge

The AngularApp consists of the need to serve a small business with a simple product control system:

Create an application with the following features:
* Authentication, public;
* Product CRUD, with restrict access;
* Page showing only active products, public;
* Page describing how to run your application (be creative), public.

Any extra features is welcome to add to the proposed basic solution. The layout is up to you. Architecture is up to you, be smart. You will be evaluated by the quality of the code, the modularity, the readability, the creativity, the amount of basic and extra features.

# Instructions:

* With `Angular 2+`;
* With `bootstrap 4+` for layouts;
* Take your time! We will evaluate the quality of your code, even incomplete and mainly its semantics.

# Extra points:
* Unit testing;
* Clean code and organization;
* Code documentation;
* Project documentation (readme);
  
# Deadline?
48 hours

# How to delivery?
The code must be delivered to a Public Git repository

# Endpoints
#### Base URL
```sh
https://bravosul-app.herokuapp.com/
```

#### Authentication API
```sh
/auth/local
```
Request POST `https://bravosul-app.herokuapp.com/auth/local`
```sh
{
  "identifier": "dev@bravosul.com.br",
  "password": "Brvsl@2020"
}
```
Response
```sh
{
    "jwt": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNTc2OTM4MTUwLCJleHAiOjE1Nzk1MzAxNTB9.UgsjjXkAZ-anD257BF7y1hbjuY3ogNceKfTAQtzDEsU",
    "user": {
        "id": 1,
        "username": "bravosul",
        ...
    }
}
```
#### Products API
| Method | Path | Description | Permission| 
| ------ | ------ | ------ | ------ |
| GET | `/products` | Get a list of products | Public |
| GET | `/products/:id` | Get a specific product | Authenticated |
| GET | `/products/count` | Count products | Authenticated |
| POST | `/products` | Create a product | Authenticated |
| DELETE | `/products/:id` | Delete a product | Authenticated |
| PUT | `/products/:id` | Update a product | Authenticated |

#### Create Product

The request must use JWT to can create a product.

Request POST `https://bravosul-app.herokuapp.com/products`
```sh
{
  "name": "Nome do Produto",
  "description": "Mussum Ipsum, cacilds vidis litro abertis. Posuere libero varius. Nullam a nisl ut ante blandit hendrerit. Aenean sit amet nisi. Quem num gosta di mé, boa gentis num é.",
  "enabled": 1
}
```
Response
```sh
{
  "id": 3,
  "name": "Nome do Produto",
  "description": "Mussum Ipsum, cacilds vidis litro abertis. Posuere libero varius. Nullam a nisl ut ante blandit hendrerit. Aenean sit amet nisi. Quem num gosta di mé, boa gentis num é.",
  "enabled": true,
  "created_by": null,
  "updated_by": null,
  "created_at": "2020-07-31T05:11:54.993Z",
  "updated_at": "2020-07-31T05:11:54.993Z"
}
```
