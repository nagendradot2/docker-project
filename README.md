# 🚴 Bicycle Rental Website Deployment using Docker, Nginx & AWS

![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![Nginx](https://img.shields.io/badge/Nginx-WebServer-green)
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Overview

This project demonstrates how to deploy a **static website** using:

* Docker 🐳
* Nginx 🌐
* AWS EC2 ☁️
* Docker Compose ⚙️

It follows a **real-world DevOps workflow** used in production environments.

---

## 🧱 Architecture Diagram

```
        ┌──────────────┐
        │   Browser    │
        └──────┬───────┘
               │ HTTP (5000)
        ┌──────▼───────┐
        │    AWS EC2   │
        └──────┬───────┘
               │
        ┌──────▼────────┐
        │   Docker      │
        └──────┬────────┘
               │
        ┌──────▼────────┐
        │   Nginx       │
        └──────┬────────┘
               │
        ┌──────▼────────┐
        │ Static Files  │
        └───────────────┘
```

---

## 📁 Project Structure

```
A-Bicycle-rental-website-/
│── docker-compose.yml
│── index.html
│── assets/
│── css/
│── js/
```

---

## ⚙️ Setup Instructions

### 1️⃣ Install Docker

```bash
sudo apt update -y
sudo apt install docker.io -y
```

---

### 2️⃣ Start Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

---

### 3️⃣ Add User to Docker Group

```bash
sudo usermod -aG docker ubuntu
newgrp docker
```

---

### 4️⃣ Install Docker Compose

```bash
sudo apt install docker-compose-plugin -y
```

---

## 🐳 Docker Compose Configuration

```yaml
services:
  nginx:
    image: nginx
    ports:
      - "5000:80"
    volumes:
      - .:/usr/share/nginx/html
```

---

## 🚀 Run Application

```bash
docker compose up -d
```

---

## 🌐 Access Website

```
http://<EC2-PUBLIC-IP>:5000
```

---

## 🔓 AWS Security Group Configuration

| Type   | Port |
| ------ | ---- |
| HTTP   | 80   |
| Custom | 5000 |

---

## 🔍 Useful Commands

```bash
docker ps
docker compose logs
docker compose down
```

---

## ⚠️ Common Issues & Fixes

### ❌ Docker daemon not running

```bash
sudo systemctl start docker
```

### ❌ Permission denied

```bash
sudo usermod -aG docker ubuntu
newgrp docker
```

### ❌ Port not accessible

✔ Check AWS Security Group

---


## 🎉 Result

Your static website is now deployed using:

✔ Docker
✔ Nginx
✔ AWS EC2
✔ Docker Compose

---

## 📜 License

MIT License

---

## 🙌 Author

**Nagendra BS**

---

## 🌟 About Project

A responsive bicycle rental website built with:

* HTML
* CSS
* JavaScript

Designed for students to easily rent bicycles on campus 🚴
