# Project Web-1

This project demonstrates a **Dockerized Node.js (backend) and ReactJS (frontend) application** running behind an **Nginx reverse proxy** using `docker-compose`.  
It was built as part of a DevOps technical task.

---

## 🚀 Features
- **Backend**: Node.js + Express API (runs on port `5000`)
- **Frontend**: ReactJS (served via Nginx, runs on port `3000` inside container)
- **Reverse Proxy**: Nginx routes traffic:
  - `/api` → Node.js backend
  - `/` → React frontend
- **Multi-stage Docker builds** for lightweight images
- **Docker Compose** to orchestrate services

---

## 📂 Project Structure
        Project-Web-1/
        │── backend/ # Node.js API service
        │ ├── Dockerfile
        │ ├── package.json
        │ └── server.js
        │
        │── frontend/ # ReactJS frontend
        │ ├── Dockerfile
        │ ├── package.json
        │ ├── public/index.html
        │ └── src/
        │ ├── App.js
        │ └── index.js
        │
        │── nginx/ # Reverse proxy config
        │ └── nginx.conf
        │
        │── docker-compose.yml
        │── README.md



---

## ⚙️ Prerequisites
- Docker installed
- Docker Compose installed
- Git (for cloning the repo)
Build YOUR EC2 ubuntu with will script 

```
    #!/bin/bash
    # Update & upgrade
    apt update && apt upgrade -y
    
    # Install dependencies
    apt install -y apt-transport-https ca-certificates curl software-properties-common
    
    # Install Docker
    apt install -y docker.io
    
    # Install docker-compose (v1.29.2)
    curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" \
      -o /usr/local/bin/docker-compose
    chmod +x /usr/local/bin/docker-compose
    
    # Add default 'ubuntu' user to docker group
    usermod -aG docker ubuntu
    
    # Enable and start Docker
    systemctl enable docker
    systemctl start docker
```
---

## ▶️ How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/project-web-1.git
   cd project-web-1



docker-compose build
docker-compose up -d



Access the app:

Frontend (React): http://localhost

Backend (Node.js): http://localhost/api


🛠️ Useful Commands

Stop services:

docker-compose down


View logs:

docker-compose logs -f


Rebuild images:

docker-compose build --no-cache





