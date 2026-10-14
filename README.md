# python-cicd-docker-demo
A Python web application with Docker and automated CI/CD using GitHub Actions
# Python CI/CD Pipeline with Docker and GitHub Actions

A beginner-friendly DevOps project demonstrating automated testing, Docker containerization, and CI/CD using GitHub Actions.

## Architecture

Developer → GitHub Repository → GitHub Actions → Automated Tests → Docker Build → GitHub Container Registry

## Technology Stack

- **Application:** Python, Flask
- **Testing:** pytest
- **Containerization:** Docker
- **CI/CD:** GitHub Actions
- **Container Registry:** GitHub Container Registry (GHCR)

## Features

- Flask application with home and health-check endpoints
- Automated tests for application endpoints
- Docker image built from a lightweight Python base image
- Application runs as a non-root user inside the container
- GitHub Actions workflow automatically runs tests on pushes and pull requests
- Docker image is published to GHCR after successful tests on pushes to `main`

## Docker Image

Pull the published image:

`docker pull ghcr.io/viditlaad/python-cicd-demo:latest`

Run the application:

`docker run --rm -p 5000:5000 ghcr.io/viditlaad/python-cicd-demo:latest`

Open the health endpoint:

`http://localhost:5000/health`

Expected response:

`{"status":"healthy"}`

## Run Locally

Clone the repository:

`git clone https://github.com/ViditLaad/python-cicd-docker-demo.git`

Enter the project directory:

`cd python-cicd-docker-demo`

Install dependencies:

`python -m pip install -r requirements.txt`

Run tests:

`python -m pytest -v`

Build the Docker image:

`docker build -t python-cicd-demo .`

Run the container:

`docker run --rm -p 5000:5000 python-cicd-demo`

## CI/CD Workflow

1. Check out the repository.
2. Set up Python 3.12.
3. Install dependencies.
4. Run automated tests using pytest.
5. Build the Docker image after the tests pass.
6. Publish the image to GitHub Container Registry.

Pull requests run the test job. The Docker publishing job runs on pushes to the `main` branch.

## Learning Outcomes

This project demonstrates practical experience with Git, Python, automated testing, Docker, GitHub Actions, and container image publishing.

## Future Improvements

- Add code quality checks and container vulnerability scanning.
- Add deployment to a cloud platform.
- Deploy the application to Kubernetes.
- Add monitoring using Prometheus and Grafana.

## Disclaimer

This is a learning project and is not intended as a production-ready deployment.
