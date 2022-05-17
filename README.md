# Spring Boot Micro-Services

## Content

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Scope](#scope)

## About <a name = "about"></a>

A simple project to demonstrate how micro-services can communicate and share data between each other.

## Getting Started <a name = "getting_started"></a>

The follow instructions will guide you on how to have a  copy of the project up and running on your computer for development and testing purposes.


### Prerequisites

- Java 11 or later
- Docker

### Dependencies
The project is a combination of three (independent) git repos:

- Customer Service: https://github.com/adedotunalausa/b-customer-service
- Billing Service: https://github.com/adedotunalausa/b-billing-service
- Billing Worker Service: https://github.com/adedotunalausa/b-billing-worker-service

Git Submodules is used to sync the dependencies.


### Installing


- Clone this repo
- Pull submodules

```
git submodule update --init --recursive 
```
cd into individual service and build them to create the .jar file using this below command

```
mvn clean install -DskipTests=true
```

Run Docker compose

```
docker-compose up --build

# OR run detached
docker-compose up --build -d
```


## Usage <a name = "usage"></a>

See the postman [api docs](https://documenter.getpostman.com/view/11267944/UyxkijwT)


## Scope <a name = "scope"></a>
The project demonstrates a *simple* microservices communication setup using RabbitMQ and Webhooks.

The scope does not includes:
- Authenticated RESTful-based communication between customer-service and billing-service.
- Billing-service and billing-worker-service communicates using rabbitmq
- Some level of request validation

