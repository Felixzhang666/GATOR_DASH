# Backend API
## Customer API

### 1. Customer Register API

```java
POST    http://localhost:1016/customer/register
```
Create a new customer with the provided information

#### *Example Request*
```java
POST    http://localhost:1016/customer/register
```
Body:
```java
{
    "username":"root",
    "password":"123456",
    "addressLine1":"3824 SW Archer Road",
    "addressLine2":"Apt 5-501",
    "phone":"7839291765",
    "email":"kdlaif@gmail.com"
}
```
#### *Example Response*

```java

{
    "code": 200,
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2VybmFtZSI6IlN1blpob25nazIyMmFpIiwiZXhwIjoxNjQ2ODU4Njk4LCJpYXQiOjE2NDYyNTM4OTgsImlzcyI6IkdhaW5EYXNoLnRlY2giLCJzdWIiOiJjdXN0b21lciB0b2tlbiJ9.MG6d-gA_FzW2afuqxDXUdGuJY69AiYnE5cizLoRNVp0"
    },
    "msg": "Successfully"
}

```


#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error
- **500**: System error


### 2. Customer Login API

```java
GET    http://localhost:1016/customer/login
```

Login if username and password are correct

#### *Example Request*

```java
GET    http://localhost:1016/customer/login
```

Parameters:

- username:root
- password:123456

#### *Example Response*

```java
{
    "code": 200,
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2VybmFtZSI6Ilpob25na2FpU3VuIiwiZXhwIjoxNjQ2ODU5MzI2LCJpYXQiOjE2NDYyNTQ1MjYsImlzcyI6IkdhaW5EYXNoLnRlY2giLCJzdWIiOiJjdXN0b21lciB0b2tlbiJ9.fxlfySWO7evdcKNxzvm_LulnMs_qGYdgOzGYtefM9Ro"
    },
    "msg": "Successfully log in"
}
```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

### 3. Customer Delete API

```java
GET    http://localhost:1016/customer/delete
```

Delete the account if username and password are correct

#### *Example Request*

```java
GET    http://localhost:1016/customer/delete
```

Parameters:

- username:root
- password:123456

#### *Example Response*

```java
{
    "code": 200,
    "data": null,
    "msg": "Successfully deleted"
}
```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

### 4. Read Customerte API

```java
GET    http://localhost:1016/customer/read
```

Read the customer's information if the token is valid

#### *Example Request*

```java
GET    http://localhost:1016/customer/token_value
```

Parameters:


#### *Example Response*

```java
"code": 200,
    "data": {
        "username": "root",
        "password": "123456",
        "addressLine1": "3824 SW Archer Road",
        "addressLine2": "Apt 5-501",
        "phone": "7839291765",
        "email": "kdlaif@gmail.com",
        "city": "Gainesvill",
        "state": "FL",
        "zipcode": "32600"
    },
    "msg": "Successfully"
}
```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

## Rating API

### 1. Rating Create API

```java
POST    http://localhost:1016/rating/create
```
Create a new rating with the provided information

#### *Example Request*
```java
POST    http://localhost:1016/rating/create
```
Body:
```java
{
    "username": "root",
    "restaurantName": "Popeyes",
    "star": 5,
    "comment": "Taste so good !!!!",
    "ratingDate": "2022/01/06"
}
```
#### *Example Response*

```java

{
    "code": 200,
    "data": null,
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

### 2. Rating GET API

```java
GET    http://localhost:1016/rating/get
```

Get the rating of one restaurant if restaurant exists

#### *Example Request*

```java
GET    http://localhost:1016/rating/get
```

Parameters:
- restaurantName:Popeyes

#### *Example Response*
```java
{
    "code": 200,
    "data": [
        {
            "username": "ZhongkaiSun",
            "restaurantName": "Popeyes",
            "star": 5,
            "comment": "Yummy!!",
            "ratingDate": "2022/02/04"
        },
        {
            "username": "ZhongkaiSun",
            "restaurantName": "Popeyes",
            "star": 5,
            "comment": "Taste so good !!!!",
            "ratingDate": "2022/01/04"
        },
        {
            "username": "ZhongkaiSun",
            "restaurantName": "Popeyes",
            "star": 5,
            "comment": "Taste so good !!!!",
            "ratingDate": "2022/01/06"
        },
        {
            "username": "ZhongkaiSun",
            "restaurantName": "Popeyes",
            "star": 5,
            "comment": "I would like to come again",
            "ratingDate": "2021/01/03"
        },
        {
            "username": "Nugget",
            "restaurantName": "Popeyes",
            "star": 5,
            "comment": "Taste so good !!!!",
            "ratingDate": "2022/01/06"
        }
    ],
    "msg": "Successfully"
}
```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error


## Cuisine API

### 1. Cuisine Create API

```java
POST    http://localhost:1016/cuisine/create
```
Create a new cuisine for a restaurant

#### *Example Request*
```java
POST    http://localhost:1016/cuisine/create
```
Request Body:
```java
{
"name":"banana pie",        
"restaurantName":"Popeyes", 
"price":2.0,        
"calories":3
}
```
#### *Example Response*

```java

{
    "code": 200,
    "data": null,
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

### 2. Cuisine Read API


```java
GET    localhost:1016/cuisine/read?restaurantName=
```
Read a cuisine from a restaurant

#### *Example Request*
```java
GET   ocalhost:1016/cuisine/read?restaurantName=Popeyes
```

#### *Example Response*

```java
     
{
    "code": 200,
    "data": [
        {
            "name": "8PC Nuggets A La Carte",
            "restaurantName": "Popeyes",
            "price": 4.79,
            "calories": 400,
            "imgPath": "picture/Popeyes/Nuggets_A_La_Carte.jpeg"
        },
        {
            "name": "Cajun Fries",
            "restaurantName": "Popeyes",
            "price": 4.19,
            "calories": 430,
            "imgPath": "picture/Popeyes/Cajun_Fries.jpeg"
        },
        {
            "name": "Chicken Combo (3 Pcs)",
            "restaurantName": "Popeyes",
            "price": 14.39,
            "calories": 410,
            "imgPath": "picture/Popeyes/Chicken_Combo.jpeg"
        },
        {
            "name": "Chicken Dinner (2 Pcs)",
            "restaurantName": "Popeyes",
            "price": 5.99,
            "calories": 420,
            "imgPath": "picture/Popeyes/Chicken_Dinner.jpeg"
        },
        {
            "name": "Homestyle Mac & Cheese",
            "restaurantName": "Popeyes",
            "price": 4.19,
            "calories": 440,
            "imgPath": "picture/Popeyes/Homestyle_Mac_Cheese.jpeg"
        },
        {
            "name": "Spicy Chicken Sandwich",
            "restaurantName": "Popeyes",
            "price": 5.39,
            "calories": 450,
            "imgPath": "picture/Popeyes/Spicy_Chicken_Sandwich.jpeg"
        }
    ],
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

### 3. Cuisine Delete API

```java
POST    http://localhost:1016/cuisine/delete
```
Delete the cuisine from a restaurant

#### *Example Request*
```java
POST    http://localhost:1016/cuisine/delete
```
Request Body:
```java
{
"name":"banana pie",        
"restaurantName":"Popeyes", 
"price":2.0,        
"calories":3
}
```
#### *Example Response*

```java

{
    "code": 200,
    "data": null,
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

## Order API

### 1. Order Create API

```java
POST    http://localhost:1016/order/create
```
Create a new order for a customer

#### *Example Request*
```java
POST    http://localhost:1016/order/create
```
Request Body:
```java
{
    "userName":"Raindrop",
	"restaurantName":"Checkers",
	"orderDate":"03/02/2022",
	"price":8.88,
	"cuisineName":"burger"
}
```
#### *Example Response*

```java

{
    "code": 200,
    "data": null,
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error
  
### 2. Order Read API

```java
GET    http://localhost:1016/order/read?username=Raindrop
```
Create a new cuisine for a restaurant

#### *Example Request*
```java
GET    http://localhost:1016/order/read?username=Raindrop
```

#### *Example Response*

```java

{
    "code": 200,
    "data": [
        {
            "username": "Raindrop",
            "restaurantName": "Checkers",
            "orderDate": "03/02/2022",
            "price": 8.88,
            "cuisineName": "burger"
        }
    ],
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error
- 
## Restaurant API

### 1. Restaurant Read API
```java
GET    http://localhost:1016/restaurant/read
```
Read a restaurant or get the restaurant list 

#### *Example Request*
```java
GET    http://localhost:1016/restaurant/read?name=Popeyes
```
#### *Example Response*

```java

{
    "code": 200,
    "data": {
        "name": "Popeyes",
        "address": "1412N Main St, Gainesville, FL 32601, USA",
        "deliveryFee": 3.99,
        "imgPath": "",
        "typeofMeal": "Chicken",
        "rating": 4.1
    },
    "msg": "Successfully"
}

```

#### *Example Request*
```java
GET    http://localhost:1016/restaurant/read
```
#### *Example Response*

```java

{
    "code": 200,
    "data": [
        {
            "name": "Popeyes",
            "address": "1412N Main St, Gainesville, FL 32601, USA",
            "deliveryFee": 3.99,
            "imgPath": "",
            "typeofMeal": "Chicken",
            "rating": 4.1
        },
        {
            "name": "Checkers",
            "address": "3325 W University Ave, Gainesville, FL 32607, USA",
            "deliveryFee": 1.99,
            "imgPath": "",
            "typeofMeal": "Burgers",
            "rating": 4.2
        }
    ],
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error

## Payment API

### 1. Payment Read API
```java
GET    http://localhost:1016/payment/read
```
Read a user's existed payment information

#### *Example Request*
```java
GET    http://localhost:1016/payment/read?username=ZhongkaiSun
```
#### *Example Response*

```java

{
    "code": 200,
    "data": {
        "username": "ZhongkaiSun",
        "cardNumber": "123456789XXXX",
        "expDate": "05/26",
        "securityCode": "001",
        "addressLine1": "4000 SW 24th St",
        "addressLine2": "Apt 2-309",
        "city": "Gainesville",
        "state": "Florida",
        "zipcode": "32600"
    },
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **300**: The payment doesn't exist
- **422**: Internal Server Error

### 2. Payment Create API
```java
POST    http://localhost:1016/payment/create
```
Read a restaurant or get the restaurant list

#### *Example Request*
```java
POST    http://localhost:1016/payment/create
```

Request Body:
```java
{
    "username":"Raindrop",
    "cardHolder": "Yudi Zheng",
    "cardNumber":"8888888XXXX",
    "expDate":"06/26",
    "securityCode":"002",
    "addressLine1":"3700SW 27th",
    "addressLine2":"apt110",
    "city":"Gainesville",
    "state":"Florida",
    "zipcode":"32608"
}
```

#### *Example Response*

```java

{
    "code": 200,
    "data": null,
    "msg": "Successfully"
}

```

#### *Status Codes*

- **200**: No error
- **422**: Internal Server Error