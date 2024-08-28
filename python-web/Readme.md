# Python Web Application

## Overview

This is a Python web application that runs inside a Docker container. The application is built using [Flask](https://flask.palletsprojects.com/) (or another web framework of your choice), and Docker is used to containerize the application, ensuring consistent development, testing, and production environments.

## Features

- **Python-based Web Application:** Built with Flask (or other Python web frameworks).
- **Dockerized:** Runs in a Docker container for easy deployment and scaling.
- **Simple Configuration:** Uses Dockerfile for building the application image.

## Prerequisites

To run this project, you need:

- [Docker](https://docs.docker.com/get-docker/) (installed and running)
- [Docker Compose](https://docs.docker.com/compose/install/) (if using Docker Compose)

## Getting Started

Follow these instructions to set up and run the application.

### 1. Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/SupriyaKarnati/DockerProjects.git
cd python-web

### 2. Build the Docker image using the provided Dockerfile

docker build -t SupriyaKarnati/python-web .

### 3. Run the Docker container from the image with setting env variables

docker run -p 5000:5000 -e mysql_user= -e mysql_password= -e mysql_db= SupriyaKarnati/python-web

