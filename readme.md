# 🚀 DevOps Technical Challenge

## 📦 Project Structure
- `CI-Frontend/`: Vue.js frontend
- `CI-Backend/`: Node.js backend API
- `nginx/`: NGINX reverse proxy config

## 🐳 Docker
- Frontend: Built and served with NGINX
- Backend: Node.js API on port 3000

## 🌐 Deployment
- Frontend on EC2 Server 1 (`port 5000`)
- Backend on EC2 Server 2 (`port 3000`)
- NGINX routes `/api` → Backend

## 🔄 CI/CD
- GitHub Actions triggers deployment on push
- Auto-build + deploy to EC2 over SSH

## 🔐 GitHub Secrets
- `SSH_PRIVATE_KEY`: EC2 private key
- `FRONTEND_SERVER_IP`: Public IP of frontend server
- `BACKEND_SERVER_IP`: Public IP of backend server

## 📎 How to Run Locally
```bash
cd CI-Frontend
docker build -t frontend-app .
docker run -d -p 5000:5000 frontend-app

cd CI-Backend
docker build -t backend-app .
docker run -d -p 3000:3000 backend-app
