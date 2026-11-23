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

---

## Jenkins CI/CD Pipeline

### Overview
This project implements a Jenkins Continuous Integration and Continuous Delivery (CI/CD) pipeline to automate the building, testing, and deployment simulation of a Python Flask application.

### Technologies Used
- Jenkins 2.580.2
- Docker
- Python 3.13 (Jenkins environment)
- Flask 3.1.1
- Git and GitHub
- Python unittest
- Gunicorn

### Environment Setup
Jenkins was installed using Docker Desktop on macOS.

A custom Jenkins Docker image was created to install Python 3, pip, and Git.

Jenkins was configured to run on:

http://localhost:8080

The Jenkins pipeline was connected to the GitHub repository using Pipeline script from SCM.

### Pipeline Stages

**1. Build**
- Checks out the application from GitHub.
- Creates a Python virtual environment.
- Installs application dependencies from requirements.txt.

**2. Test**
- Runs automated Flask application tests.
- Uses Python's unittest framework.
- Ensures the pipeline fails if tests fail.
- Both automated tests passed successfully.

**3. Deploy**
- Simulates application deployment.
- Compiles Python application files.
- Confirms the deployment simulation completed successfully.

### Jenkinsfile
The Jenkinsfile is stored in the root directory of the GitHub repository.

It defines the Build, Test, and Deploy stages using Declarative Pipeline syntax.

### Pipeline Results

| Stage | Result |
|---|---|
| Checkout SCM | SUCCESS |
| Build | SUCCESS |
| Test | SUCCESS |
| Deploy | SUCCESS |
| Overall Pipeline | SUCCESS |

Automated tests: 2 passed.

Final Jenkins console output:

```text
Ran 2 tests in 0.033s

OK

Deployment simulation completed!

Finished: SUCCESS
```

### Challenges and Solutions

**Challenge 1: Python was unavailable in Jenkins.**

Solution: Created a custom Jenkins Docker image with Python 3 and pip installed.

**Challenge 2: Jenkins required application dependencies.**

Solution: Configured the Build stage to create a virtual environment and install dependencies.

**Challenge 3: Automating application testing.**

Solution: Created a tests directory containing automated Flask tests and integrated them into the Jenkinsfile.

### Evidence
Screenshots of the successful Jenkins pipeline are stored in the screenshots directory.

The screenshots demonstrate successful Build, Test, and Deploy stages.

### Conclusion
The Jenkins CI/CD pipeline successfully automates source code checkout, dependency installation, automated testing, and deployment simulation.

All pipeline stages completed successfully.

