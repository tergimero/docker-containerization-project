# Docker Containerization Project

## Overview
A Flask web application containerized using Docker and served with Gunicorn.

## Technologies
- Python 3.12
- Flask 3.1.1
- Gunicorn 23
- Docker

## Build the Docker Image
```bash
docker build -t flask-docker-app:2.0.0 .
```

## Run the Container
```bash
docker run -d -p 5001:5000 --name flask-container flask-docker-app:2.0.0
```

## Test the Application
Visit http://localhost:5001

Health check:
```bash
curl http://localhost:5001/health
```

## Container Management
```bash
docker ps
docker logs flask-container
docker stop flask-container
docker start flask-container
docker rm -f flask-container
```

## Optimisation
- Uses the lightweight Python slim base image
- Uses Docker layer caching for dependencies
- Excludes unnecessary files with .dockerignore
- Runs Flask using Gunicorn

## Evidence
Screenshots of the running application, health checks and Docker commands are stored in the screenshots directory.
