

https://user-images.githubusercontent.com/59303181/178954035-8d84e568-2e82-425e-811a-0380895fe522.mp4


# π Getting Started with the server Backend of Chat Application API 

## π€ What is the ChatApplication Backend API? 
It is the API that allows you to fetch,update,delete and perform CRUD operations for the DaveList API using redis memory cache database that used in the project.This is a Restful API for the Redis Memory Cache Database so that it can be used with the frontEnd.It is basically used at the front end of DaveListApp.

## π§ͺ Tools used for Testing
Testing is one of the major part of development and without an application can't be reliable. So we used the following tools for testing the application.
- [jest](https://www.npmjs.com/package/jest): Used for testing the API
- [supertest](https://www.npmjs.com/package/supertest): Used for testing the API
- [PostMan](https://www.postman.com/): Used for testing the API
- Manual Testing: Used for testing the API

## π Running the tests
To run the tests you can use the following command.
`npm test`. It will execute the jest tests.

## π§ Tools Used 
- [NodeJS](https://nodejs.org/en/)
- [ExpressJS](https://expressjs.com/)
- [Next JS](https://nextjs.org/)
- [Redis](https://redis.com/) for Memory Cache Database
- [jest](https://www.npmjs.com/package/jest): Used for testing the API
- [supertest](https://www.npmjs.com/package/supertest): Used for testing the API
- [PostMan](https://www.postman.com/): Used for testing the API

## π§ Operations that can be performed on the RealTimeChatApplication API
It performs the following operations:
- **GET** β an HTTP request to Read (Used to read an existing resource)
- **POST** β an HTTP request to Create (Used to create and add a resource)
- **PUT** βan HTTP request to Update(client sends data that updates the entire resource)(Used to update an entire resource)
- **PATCH** β HTTP request to Update (client sends partial data that is to be updated without modifying the entire data)(Used to partially update a resource)
- **DELETE** β HTTP request to Delete (Used to delete an entire resource)

## πͺ API Routes
  ### 1. The API has the following routes for **user** repository to perform CRUD operations on the RealTimeChatApp API:
  - **GET [http://localhost:8000/user](http://localhost:8000/user)** β returns a list of all users that have registered in the RedisDatabase
  - **GET [http://localhost:8000/user/id](http://localhost:8000/user/id)** β returns a single user by provided id
  - **POST [http://localhost:8000/user/](http://localhost:8000/user)** β to Post a JSON object to create a new user
  - **PUT [http://localhost:8000/user/id](http://localhost:8000/user/id)** β to Update a user by provided id 
  - **DELETE [http://localhost:8000/user/id](http://localhost:8000/user/id)** β to Delete a user by provided id

  ### 2. The API has the following routes for **listing** repository:
  - **GET [http://localhost:8000/listing](http://localhost:8000/listing)** β returns a list of all listings that are saved in the RedisDatabase
  - **GET [http://localhost:8000/listing/id](http://localhost:8000/listing/id)** β returns a single listing by provided id
  - **POST [http://localhost:8000/listing/](http://localhost:8000/listing)** β to Post a JSON object to create a new listing
  - **PUT [http://localhost:8000/listing/id](http://localhost:8000/listing/id)** β to Update a listing by provided id 
  - **DELETE [http://localhost:8000/listing/id](http://localhost:8000/listing/id)** β to Delete a listing by provided id

 ### 3. The API has the following routes for **comment** repository:
  - **GET [http://localhost:8000/comment](http://localhost:8000/comment)** β returns a list of all comments that are saved in the RedisDatabase
  - **GET [http://localhost:8000/comment/id](http://localhost:8000/comment/id)** β returns a single comment by provided id
  - **POST [http://localhost:8000/comment/](http://localhost:8000/comment)** β to Post a JSON object to create a new comment
  - **PUT [http://localhost:8000/comment/id](http://localhost:8000/comment/id)** β to Update a comment by provided id 
  - **DELETE [http://localhost:8000/comment/id](http://localhost:8000/comment/id)** β to Delete a comment by provided id

 ### 4. The API has the following routes for **chat** repository:
  - **GET [http://localhost:8000/chat](http://localhost:8000/chat)** β returns a list of all chats that are saved in the RedisDatabase 
  - **GET [http://localhost:8000/chat/id](http://localhost:8000/chat/id)** β returns a single chat by provided id
  - **POST [http://localhost:8000/chat/](http://localhost:8000/chat)** β to Post a JSON object to create a new chat
  - **PUT [http://localhost:8000/chat/id](http://localhost:8000/chat/id)** β to Update a comment by provided id 
  - **DELETE [http://localhost:8000/chat/id](http://localhost:8000/chat/id)** β to Delete a chat by provided id

## π₯οΈ How do I use the RealTimeChatApp API?
- **IMPORTANT**:Remember that you need to sign up for redis cloud to get your username,password and end point so that this will work. Although it will work on localhost but it will not work on the cloud with my end point and username.

## π Repositories Created in the RedisDatabase API for the Redis Memory Cache Database
- **user** ββ> The schema contains the name, password, timeRegistered and a boolean to track if user is signedIn or not = isSignedIn.As shown below:
  ```js
  export const userSchema = new Schema(User, {
    name: {
        type: 'string'
    },
    password: {
        type: 'string'
    },
    timeRegistered: {
        type: 'string'
    },
    isSignedIn: {
        type: 'boolean'
    }
  }, {
    dataStructure: 'JSON'
  });
  ```
  - **comment** ββ> The schema contains the  listingID, comment, userWhoCommented and timeCommented. As shown below:
  ```js
  export const commentSchema = new Schema(Comment, {
    listingID: {
        type: 'string'
    },
    comment: {
        type: 'string'
    },
    userWhoCommented: {
        type: 'string'
    },
    timeCommented: {
        type: 'string'
    }
  }, {
    dataStructure: 'JSON'
  });
  ```
  - **chat** ββ> The schema contains the  userIDSender, userNameSender, userIDReceiver,userNameReceiver,message and timeSent. As shown below:
  ```js
  export const chatSchema = new Schema(Chat, {
    userIDSender: {
        type: 'string'
    },
    userNameSender: {
        type: 'string'
    },
    userIDReceiver: {
        type: 'string'
    },
    userNameReceiver: {
        type: 'string'
    },
    message: {
        type: 'string'
    },
    timeSent: {
        type: 'string'
    },
    isUserOnline: {
        type: 'boolean'
    },
}, {
    dataStructure: 'JSON'
});
  ```

## ππΎ Starting the project
- Download the repository and run `npm install`. The node modules will be installed that are essential for running the project.
- In the root of the project run `npm start`. This will start the server.
- π Congratulations. You definately did great if you followed till now.
- Now you can use the apis along with the front end of ChatApplication.

## Find Me 
- Follow me on [Linkedin](https://www.linkedin.com/in/muhammad-bilal-028843199/) for useful updates regarding development
- My [Github Profile](https://github.com/Muhammad-Bilal-7896) 

## Resources
Blogs are much faster than videos so I mostly consult blogs but you can consult video tutorials if you want to
- [https://www.linkedin.com/pulse/how-develop-todo-app-next-js-redis-database-from-scratch-bilal/?trackingId=9GEisJ%2BHSHCxL5SJGyQNHw%3D%3D](https://www.linkedin.com/pulse/how-develop-todo-app-next-js-redis-database-from-scratch-bilal/?trackingId=9GEisJ%2BHSHCxL5SJGyQNHw%3D%3D)
- [https://dev.to/nedsoft/testing-nodejs-express-api-with-jest-and-supertest-1km6](https://dev.to/nedsoft/testing-nodejs-express-api-with-jest-and-supertest-1km6)
