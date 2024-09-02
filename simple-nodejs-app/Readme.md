# Node.js Application - Docker Containerization

This project demonstrates my learning journey of containerizing a Node.js application using Docker. The application is a simple Node.js app built with server.js, and it has been containerized to ensure it runs consistently across different environments.

## Project Overview

The purpose of this project is to explore how Docker can be used to containerize a Node.js application. Docker is a powerful tool that enables developers to package applications and their dependencies into a standardized unit, making it easier to deploy and manage applications across various environments.

## Features

- **Simple Node.js App**: A basic server.js server serving a sample API endpoint.
- **Dockerized**: The application has been fully containerized using Docker, allowing it to run in a consistent environment regardless of where it is deployed.
- **Environment Configuration**: The application supports environment variables for configuring the server port and other settings.

## Getting Started

### Prerequisites

To run this application, you will need:

- **Node.js** (v14.x or later)
- **Docker** (v20.x or later)

### Running Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/simple-nodejs-app.git
   cd simple-nodejs-app

2. Building and Running with Docker

    docker build -t simple-nodejs-app:latest .

    docker run -p 3000:80 simple-nodejs-app:latest

### Key Learnings

    Containerization: Gained an understanding of how to package a Node.js application and its dependencies into a Docker container, ensuring consistency across development, testing, and production environments.
    Port Mapping: Learned how to map container ports to host machine ports, allowing the application to be accessed from outside the container.
