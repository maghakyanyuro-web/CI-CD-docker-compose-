# 🚀 Full Stack DevOps Practice: Docker Compose & CI/CD Pipeline

This project demonstrates a complete DevOps workflow, including containerization, local orchestration, and automated deployment to a Cloud environment (AWS).

## 🛠 Tech Stack
- **Application:** Python (Flask)
- **Database:** Redis (for session/hit counting)
- **Containerization:** Docker & Docker Compose
- **CI/CD:** GitHub Actions
- **Cloud:** AWS EC2 (Ubuntu)
- **OS:** Linux

## 🏗 System Architecture
1. **Flask App:** A simple web application that tracks the number of visits.
2. **Redis:** A fast in-memory data store used for incrementing the hit counter.
3. **Docker Compose:** Manages both services and ensures they are in the same network.
4. **Volumes:** Implemented data persistence for Redis to prevent data loss on container restart.

## 🤖 CI/CD Workflow
The project uses **GitHub Actions** to automate the deployment process:
- **Trigger:** On every `push` to the `main` branch.
- **Process:** 
    - Connects to AWS EC2 via **SSH**.
    - Pulls the latest code from the repository.
    - Rebuilds and restarts containers using `docker compose up -d --build`.

## 🚀 How to Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/maghakyanyuro-web/CI-CD-docker-compose-

Run the application:
bash
docker-compose up -d

Access the app at http://localhost:5000.
🔍 Engineering Highlights (Troubleshooting)
During the development of this project, several real-world DevOps challenges were solved:
Service Discovery: Configured communication between Flask and Redis using Docker internal DNS.
Data Persistence: Implemented Docker Volumes to ensure hit counts are preserved after container removal.
Permission Management: Configured non-root Docker execution on the AWS server.
Network Security: Managed AWS Security Groups to allow specific traffic on port 5000 and 22.
