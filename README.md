# Introduction - Online Assignment

The application is to create a Microservices backend to securely store data in a file format and allow the user to read and update when required.
This Assignment has Microservices to securely store data in a file format and allow the user to read and update when required.  Fiel format can be both CSV and XML file format. Each is independently built & deployable.

## Implementaion of services [Microservices]
 We have developed 2 micro services , services name called as service-one and service-two, functionality and implementaions explained as below,
 Service One :
 Its an independant deployable sercvice and follwed by clean code Architecuture pattern with TDD and DDD, it has an user CRUD with File operations and the below technologies we have used

 -Nodejs Version 14.X
 -Docker
 -NoSQL -ODM MongoDB -v4.0.27
 -Queue -RabbitMq - meesage broker

Packages and Frameworks with versions:
    amqplib- ^0.8.0,
    axios- ^0.21.4,
    chai- ^4.3.4,
    chai-http- ^4.3.0,
    dotenv- ^10.0.0,
    fastify- ^3.21.1,
    fastify-serve-swagger-ui- ^1.0.0,    
    fastify-swagger- ^4.12.0,    
    mocha- ^9.1.1,
    mongoose- ^6.0.6,
    protobufjs- ^6.11.2

###**ARCHTECUTURE PATTERN**
![image](https://user-images.githubusercontent.com/78136945/133961010-a1faa2d9-9ebe-4ed6-ba43-628b4f85ba27.png)

###**EXECUTION LIFE CYCLE:**
![image](https://user-images.githubusercontent.com/78136945/133961043-deeb3a5b-b8ff-4971-b434-3bad10ad4edb.png)

### Services

Microservices are developed in Node JS using [ Fastify](https://www.fastify.io/docs/latest/). Fastify is a web framework highly focused on providing the best developer experience with the least overhead and a powerful plugin architecture. It is inspired by Hapi and Express and as far as we know, it is one of the fastest web frameworks in town.

Fastify Framework favors developer joy with a consistent and expressive API to build full-stack web applications or micro API servers.

Following packages from AdonisJs are used to make service more effective. 
- [Servers And Routes](https://www.fastify.io/docs/latest/)
- [Vaidator](https://www.fastify.io/docs/latest/Validation-and-Serialization)
- [ODM](https://mongoosejs.com/docs/guide.html)
- [Exception handling](https://nodejs.org/en/knowledge/errors/what-is-try-catch/)
- [Logs](https://www.fastify.io/docs/latest/Logging)
- [Unit & Functionality Test](https://mochajs.org/ )(https://www.chaijs.com/api/)
- [Encryption](https://www.npmjs.com/package/crypto-js)

### Message broker

[Rabbit MQ](https://www.rabbitmq.com/) user for communication between services. It is one of the most popular message brokers that run on top of Advanced Message Queuing Protocol (AMQP). There are four main components forming AMQP protocol: Publisher, Exchange, Queue, Consumer. 

Our application uses the Exchange method Direct for communication. We can also configure it in our applications. I have used [amqplib]() npm package to implement Rabbit MQ. Here Service one will be Publisher and Service two will be a consumer. 

### Protocol buffer

Here I have used [Google protocol buffer](https://developers.google.com/protocol-buffers) to encode the messages between services. I have achieved this in Node Js using [protobufjs](https://www.npmjs.com/package/protobufjs)

### Database

[MongoDB](https://docs.mongodb.com/manual/installation/) database is used for storing user file information. 

### REST API
Rest API is used for only reading data from service two. That API call is also encrypted using aes-256-cbc Algorithm. Secret keys are stored in Env for decryption.

## Requirements

1. NodeJS
2. MongoDB
3. Docker
4. Below Repositories 

- https://github.com/prakashDoss/services-prerequisites.git
- https://github.com/prakashDoss/service-one
- https://github.com/prakashDoss/service-two.git

# Installation & Setup

1. First install Nodejs for Microservices. [Refer](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) 

2. Second install Docker to run RabitMq and MongoDB. [Refer](https://docs.docker.com/engine/install/)
 
3. Run Rabbit Mq and MongoDB docker composer. Please make sure docker is up and running.

```bash

git clone https://github.com/prakashDoss/services-prerequisites.git

cd services-prerequisites

docker compose -f docker-compose.yml up

```

5. Run service one

```bash

git clone https://github.com/prakashDoss/service-one

cd service-one

npm i --save

npm run start

```

Now you can see below:

```
> serviceone@1.0.0 start
> node index.js

{"level":30,"time":1632108924114,"msg":"Server listening at http://0.0.0.0:2082"}
App listening on port is : 2082!

```

6. Run service two

```bash

git clone https://github.com/prakashDoss/service-two.git

cd service-two

npm i --save

```

The start service

```bash

npm run start

```

Now you can see below:

```
> servicetwo@1.0.0 start
> node index.js

{"level":30,"time":1632109093071,"msg":"Server listening at http://0.0.0.0:2083"}
App listening on port is : 2083!
{"level":30,"time":1632109093072,"RABBIT_MQ_CONSUMER_STATUS":"CONSUMER_STARTED"}
{"level":30,"time":1632109093096,"MONGO_CONNETION_STATUS":"Mongoose default connection opened"}

```

## Test & Execute Application

- Running test cases. (both service same comment)

```
npm run test

```
Note: To pass all integration tests in Service one please make sure Service two is running. Because it verifies the data from service two. 

- Test APIs: Once everything is up and running use the below URL to swagger document.

```
http://0.0.0.0:2082/api-docs
````
Here we go! Now we can test everything using a swagger. :)

Thanks! :)
