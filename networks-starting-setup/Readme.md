# Node.js Application with MongoDB and SWAPI Integration: Learning Docker Networking

## Introduction

This project is part of my learning journey to build and manage a multi-container Node.js application using Docker. In this setup, my Node.js application contacts the **SWAPI (Star Wars API)** to fetch data about Star Wars films and stores the data in a **MongoDB** database.

The application consists of two containers:
- **Node.js App Container**: A simple Node.js application that fetches Star Wars film data from the SWAPI and stores it in MongoDB.
- **MongoDB Container**: A MongoDB database that acts as the backend storage for the fetched data.

## Project Overview

The project consists of two main services:

1. **Node.js Application**: 
   - A REST API built with Node.js and Express.
   - This service makes requests to the external **SWAPI** to retrieve Star Wars film data.
   - The fetched film data is stored in the **MongoDB** database.
   
2. **MongoDB Database**:
   - A MongoDB instance running in a separate container.
   - The Node.js application stores and retrieves film data from this database.
   - MongoDB data is persisted using Docker volumes.

## Key Learnings

### 1. **Using Postman to Test HTTP Communication**
- I used **Postman** to send HTTP requests to the Node.js application's REST API, making it easier to test the API’s functionality.
- This includes sending **GET** requests to retrieve data (e.g., list of films) and **POST** requests to manually add new data to the MongoDB database.
- Postman allowed me to view the response data, test error handling, and debug issues in the API.

### 2. **Running MongoDB on the Host Machine**
- I configured MongoDB to run directly on the host machine instead of inside a Docker container.
- By updating the MongoDB connection string in the Node.js application to point to the host machine’s IP address (`host.docker.internal' with exposed ports on Linux), I could access the MongoDB instance from the Node.js container.
- This setup allowed me to explore how to manage data between services running on different environments (container vs host).

Update MongoDB connection in Node.js:
MONGO_URI=mongodb://host.docker.internal:27017/mydatabase

### 3. **Networking Between Containers**
- The Node.js app and MongoDB containers are on the same Docker network, allowing the Node.js app to communicate with the MongoDB container.
- The Node.js app connects to MongoDB using the container name (`mongodb`) as the hostname, thanks to Docker’s internal DNS feature.

Update MongoDB connection in Node.js:
MONGO_URI=mongodb://"name of the DB container":27017/mydatabase

## Running the Application

To run the Node.js and MongoDB containers locally and fetch data from SWAPI, follow these steps:

2. docker network create app-network
2. docker run -d --name mongodb -network app-network mongo
3. docker run -d --name nodejs-app -p 3000:3000 --network app-network my-nodejs-app

