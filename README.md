# Python Flask Docker App

A simple Python Flask web application packaged and deployed using Docker. This project demonstrates how to build a Flask application, create a Docker image, run the application in a container, and access it through a published port.

## Project Overview

This project uses:

* Python
* Flask
* Docker

The Flask application runs inside a Docker container and is exposed through port `5000`.

## Project Structure

```text
python-flask-docker-app/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

## Prerequisites

Make sure the following are installed:

* Python 3
* Docker

## Run the Application Without Docker

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python app.py
```

The application will be available at:

```text
http://localhost:5000
```

## Build the Docker Image

Build the Docker image from the project directory:

```bash
docker build -t python-flask-app .
```

Check the image:

```bash
docker images
```

## Run the Docker Container

Run the application using:

```bash
docker run -d -p 5000:5000 --name flask-container python-flask-app
```

Check the running container:

```bash
docker ps
```

View application logs:

```bash
docker logs flask-container
```

## Test the Application

Open a browser and go to:

```text
http://localhost:5000
```

You can also test using:

```bash
curl http://localhost:5000
```

## Docker Hub

The Docker image can be pushed to Docker Hub and downloaded on another machine.

Tag the image:

```bash
docker tag python-flask-app <chaitanya4k>/python-flask-app:latest
```

Login to Docker Hub:

```bash
docker login
```

Push the image:

```bash
docker push <chaitanya4k>/python-flask-app:latest
```

Pull the image:

```bash
docker pull <chaitanya4k>/python-flask-app:latest
```

Run the image downloaded from Docker Hub:

```bash
docker run -d -p 5000:5000 --name flask-container <dockerhub-username>/python-flask-app:latest
```

## Docker Workflow

```text
Flask Source Code
       ↓
requirements.txt
       ↓
Dockerfile
       ↓
Docker Image
       ↓
Docker Hub
       ↓
Docker Container
       ↓
Flask Application
       ↓
Port 5000
```

## Author

Chaitanya
