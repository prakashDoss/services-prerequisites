# Introduction - Online Assignment

The application is to create a Microservices backend to securely store data in a file format and allow the user to read and update when required. This Assignment has Microservices to securely store data in a file format and allow the user to read and update when required.  Fiel format can be both CSV and XML file format. Each is independently built & deployable.

## Implementaion of services [Microservices]
 We have developed 2 micro services Implement the RESET API Services, services name called as service-one and service-two, functionality and implementaions explained as below, we have used for AES-256 Alogorith while encrypt and decrypt the data's across the services

 ##Service One
 Its an independant deployable sercvice and follwed by clean code Architecuture pattern with TDD and DDD, it has an user CRUD with File operations and the below technologies we have used will list it out.

##Service Two
Its an independant deployable sercvice and follwed by clean code Architecuture pattern with TDD and DDD , it will encryptd the user data and store the details in requested the file formats such as CSV or XML,

##Technologies used for both Services:

- [Nodejs Version 14.X]()
- [Docker]()
- [NoSQL -ODM MongoDB -v4.0.27]()
- [Queue -RabbitMq - meesage broker]()


##Packages and Frameworks with versions
1. amqplib- ^0.8.0,
2. axios- ^0.21.4,
3. chai- ^4.3.4,
4. chai-http- ^4.3.0,
5. dotenv- ^10.0.0,
6. fastify- ^3.21.1,
7. fastify-serve-swagger-ui- ^1.0.0, 
8. fastify-swagger- ^4.12.0,      
9.  mocha- ^9.1.1,
10. mongoose- ^6.0.6,
11. protobufjs- ^6.11.2


###**ARCHTECUTURE PATTERN**
![image](https://user-images.githubusercontent.com/78136945/133961010-a1faa2d9-9ebe-4ed6-ba43-628b4f85ba27.png)

###**EXECUTION LIFE CYCLE:**
![image](https://user-images.githubusercontent.com/78136945/133961043-deeb3a5b-b8ff-4971-b434-3bad10ad4edb.png)


### REST API SERVICES
Rest API is used for only reading data from service two. That API call is also encrypted using aes-256-cbc Algorithm. Secret keys are stored in Env for decryption.

## Repositories

- https://github.com/prakashDoss/services-prerequisites.git
- https://github.com/prakashDoss/service-one
- https://github.com/prakashDoss/service-two.git

# How to run ?

1. Download the Nodejs from the official site - downlaod here (https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

2. Downlaod the MongoDB from the official site download here (https://docs.mongodb.com/manual/administration/install-enterprise/)

3. Downlod the RabbitMQ from the offficial site  download here (https://www.rabbitmq.com/download.html) - its an optinal we can use Docker composer from the services-prerequisites repo

# Setup and  Execution - services-prerequisites Repo

1. clone the services-prerequisites Repo and Run Rabbit Mq and MongoDB docker composer. Please make sure your machine docker is up and running.

# Command
1. cd services-prerequisites
2. docker compose -f docker-compose.yml up

# Setup and  Execution - service-one Repo

1. clone the service-one Repo , we can use 2 ways to run the Application via docker or Noraml node application command

# Command - Run through Docker
1. cd service-one
2. sudo docker build -t service-one .
3. sudo docker images
4. sudo docker run --name service-one -p 2082 -d service-one

# Command - Run throgh Node App Commands

1. cd service-one
2. npm i --save
3. npm run start
4. npm run test  - Test the Applications

# Setup and  Execution - service-two Repo

1. clone the service-two Repo , we can use 2 ways to run the Application via docker or Noraml node application command

# Command - Run through Docker
1. cd service-two
2. sudo docker build -t service-two .
3. sudo docker images
4. sudo docker run --name service-two -p 2082 -d service-two

# Command - Run throgh Node App Commands

1. cd service-two
2. npm i --save
3. npm run start
4. npm run test  - Test the Applications


Once Everything has set it up , we will Play with our Microservices applications, :)

# API DOCS
1. Play our App using Swagger - http://0.0.0.0:2082/api-docs
2. Play our App using postman -  https://www.getpostman.com/collections/d30ee7be05c40a3ef197

Thanks & Regards :)
Prakash.k
