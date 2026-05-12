# Docker Python App

A simple Dockerized Python application that prints:

```text
Hello Raj
```

This project demonstrates Docker installation on Ubuntu EC2, Dockerfile creation, building Docker images, running containers, and pushing images to Docker Hub.

---

# Project Structure

```text
Docker/
└── example/
    ├── app.py
    └── first-docker-file/
        ├── Dockerfile
        └── app.py
```

---

# Application Code

## app.py

```python
print("Hello Raj")
```

---

# Dockerfile

```dockerfile
FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Copy files
COPY . /app

# Install Python
RUN apt-get update && apt-get install -y python3 python3-pip

# Environment Variable
ENV NAME World

# Run application
CMD ["python3", "app.py"]
```

---

# Step-by-Step Setup

## 1. Install Docker

```bash
sudo apt update
sudo apt install docker.io -y
```

## 2. Verify Docker Service

```bash
sudo systemctl status docker
```

Expected Output:

```text
active (running)
```

## 3. Add Current User to Docker Group

```bash
sudo usermod -aG docker ubuntu
```

Then logout and login again.

## 4. Verify Docker Installation

```bash
docker run hello-world
```

## 5. Clone Repository

```bash
git clone https://github.com/RajVadaviya/Docker.git
```

## 6. Navigate to Project

```bash
cd Docker/example/first-docker-file
```

## 7. Build Docker Image

```bash
docker build -t <username>/<docker-hub-repo-name>:latest .
```

## 8. Verify Docker Images

```bash
docker images
```

## 9. Run Docker Container

```bash
docker run -it <username>/<docker-hub-repo-name>:latest
```

Expected Output:

```text
Hello Raj
```

---

# Docker Hub Push Steps

## Login to Docker Hub

```bash
docker login -u <username>
```

Paste Docker Hub Personal Access Token (PAT) as password.

## Push Docker Image

```bash
docker push <username>/<docker-hub-repo-name>:latest
```

---

# Create Docker Hub Personal Access Token

1. Login to Docker Hub
2. Open Security Settings
3. Generate New Token
4. Give permissions:
   - Read
   - Write
   - Delete

Docker Hub:
https://hub.docker.com

PAT Settings:
https://app.docker.com/settings/personal-access-tokens

---

# Pull Image from Docker Hub

```bash
docker pull <username>/<docker-hub-repo-name>:latest

docker run <username>/<docker-hub-repo-name>:latest
```

---

# Commands Summary

## Install Docker

```bash
sudo apt install docker.io -y
```

## Docker Status

```bash
sudo systemctl status docker
```

## Add User to Docker Group

```bash
sudo usermod -aG docker ubuntu
```

## Test Docker

```bash
docker run hello-world
```

## Build Docker Image

```bash
docker build -t <username>/<docker-hub-repo-name>:latest .
```

## Run Docker Container

```bash
docker run -it <username>/<docker-hub-repo-name>:latest
```

## Login Docker Hub

```bash
docker login -u <username>
```

## Push Docker Image

```bash
docker push <username>/<docker-hub-repo-name>:latest
```

---

# Thank You

Thank you for checking out this project.

This project is part of my Cloud and DevOps learning journey 🚀
