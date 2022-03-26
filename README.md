# Ticketing API

## A full scale production grade micro services backend application for selling tickets to attend a sports event

# Architecture of Multi-Service Apps
    $ npm install -g typescript

<br/>

    $ cd app
    $ mkdir auth
    $ npm init -y
    $ npm install --save typescript  express @types/express
    $ npm install --save-dev ts-node-dev

    $ tsc --init
    $ npm start

<br/>

    $ cd skaffold
    $ skaffold dev

<br/>

<br/>

    $ minikube --profile my-profile ip
    172.17.0.2

<br/>

    $ sudo vi /etc/hosts

```
#---------------------------------------------------------------------
# Minikube
#---------------------------------------------------------------------
172.17.0.2 ticketing.dev
```

<br/>

browser --> https://ticketing.dev/api/users/currentuser

<br/>

---
# Response Normalization Strategies

<br/>

### 01. Creating Route Handlers

<br/>

### 02. Scaffolding Routes

<br/>

### 03. Adding Validation

    $ cd app/auth
    $ npm install --save express-validator

<br/>

### 04. Handling Validation Errors

```
$ curl \
--data '{"email":"notValidEmail", "password":"1"}' \
--header "Content-Type: application/json" \
--request POST http://ticketing.dev/api/users/signup \
| python -m json.tool
```

**response:**

```
[
    {
        "location": "body",
        "msg": "Email must be valid",
        "param": "email",
        "value": "notValidEmail"
    },
    {
        "location": "body",
        "msg": "Password must be between 4 and 20 characters",
        "param": "password",
        "value": "1"
    }
]
```

<br/>

### 06. Surprising Complexity Around Errors

<br/>

### 07. Other Sources of Errors

<br/>

### 08. Solution for Error Handling

<br/>

### 09. Building an Error Handling Middleware

<br/>

### 10. Communicating More Info to the Error Handler

<br/>

### 11. Encoding More Information In an Error

<br/>

### 12. Subclassing for Custom Errors

<br/>

### 13. Determining Error Type

<br/>

### 14. Converting Errors to Responses

<br/>

### 15. Moving Logic Into Errors

<br/>

### 16. Verifying Our Custom Errors

<br/>

### 17. Final Error Related Code

<br/>

### 18. How to Define New Custom Errors

<br/>

### 19. Uh Oh... Async Error Handling


# 08. Database Management and Modeling

<br/>

### 01. Creating Databases in Kubernetes

    $ cd app/auth
    $ npm install --save mongoose

<br/>

    $ kubectl get pods
    NAME                                     READY   STATUS    RESTARTS   AGE
    auth-deployment-5985769fb8-j5k79         1/1     Running   0          57s
    auth-mongo-deployment-55d6d9cc49-jrzsc   1/1     Running   0          57s

<br/>

### 02. Connecting to MongoDB

    $ cd app/auth
    $ npm install --save @types/mongoose

<br/>

### 03. Understanding the Signup Flow


### 04. Getting TypeScript and Mongoose to Cooperate

<br/>

### 05. Creating the User Model

<br/>

### 06. Type Checking User Properties

<br/>

### 07. Adding Static Properties to a Model

<br/>

### 08. Defining Extra Document Properties

<br/>

### 09. What's That Angle Bracket For

<br/>

### 10. User Creation

<br/>

```
$ curl \
--data '{"email":"marley@example.com", "password":"123456789"}' \
--header "Content-Type: application/json" \
--request POST http://ticketing.dev/api/users/signup \
| python -m json.tool
```

<br/>

**response:**

```
{
    "__v": 0,
    "_id": "5eb40ea00b8b66048cc1564e",
    "email": "marley@example.com",
    "password": "123456789"
}
```

<br/>

### 11. Proper Error Handling

<br/>

### 14. Adding Password Hashing

<br/>

### 13. Reminder on Password Hashing

<br/>

### 15. Comparing Hashed Password

<br/>

### 16. Mongoose Pre-Save Hooks

```
$ curl \
--data '{"email":"marley1@example.com", "password":"123456789"}' \
--header "Content-Type: application/json" \
--request POST http://ticketing.dev/api/users/signup \
| python -m json.tool
```

<br/>

**response:**

```
{
    "__v": 0,
    "_id": "5eb4248c1650af0359d5170f",
    "email": "marley1@example.com",
    "password": "8229ab93d0751b4cbd0f396fd8e701e36089fff0d0c848d5617e65cee9eb830fc7619135058815873d24a4adcbd1779cff1c8efec79a38647810e5b14f15ae33.ef63680bfb5151ed"
}

```

<br/>

---

<br/>
