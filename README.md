# 🚴 Bicycle Rental Website Deployment using Docker, Nginx & AWS

This project demonstrates how to deploy a static website using **Docker**, **Nginx**, and an **AWS EC2 instance**.

---

## 📌 Prerequisites

* AWS EC2 instance (Ubuntu recommended)
* Basic knowledge of Linux commands
* Security Group configured for web traffic

---

## ⚙️ Step 1: Install Docker

Update your system and install Docker:

```bash
sudo apt update -y
sudo apt install docker.io -y
docker --version
```

---

## ⚠️ Common Beginner Mistake

After installing Docker, many users forget to:

* Start the Docker daemon
* Grant user permissions to run Docker commands

---

## 🚀 Step 2: Verify Docker Installation

Run:

```bash
docker run hello-world
```

### ❌ If you see this error:

```bash
permission denied while trying to connect to the Docker daemon socket
```

It means:

* Docker daemon is NOT running OR
* Your user does NOT have permission

---

## 🔧 Step 3: Start Docker Service

Check Docker status:

```bash
sudo systemctl status docker
```

Start Docker if it's not running:

```bash
sudo systemctl start docker
```

---

## 👤 Step 4: Grant User Permissions

Add your user to the Docker group:

```bash
sudo usermod -aG docker ubuntu
```

> Replace `ubuntu` with your username if different.

⚠️ **Important:** Logout and login again for changes to take effect.

---

## ✅ Step 5: Verify Again

```bash
docker run hello-world
```

Expected output:

```
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

---

## 📂 Step 6: Clone the Project

```bash
git clone https://github.com/nagendradot2/A-Bicycle-rental-website-.git
cd A-Bicycle-rental-website-/
```

---

## 🌐 Step 7: Run Website using Docker & Nginx

```bash
docker run -d \
  -p 8080:80 \
  -v $(pwd):/usr/share/nginx/html \
  nginx
```

### 🔍 Explanation:

* `-d` → Run container in background
* `-p 8080:80` → Map port 8080 (host) to 80 (container)
* `-v $(pwd):/usr/share/nginx/html` → Mount website files
* `nginx` → Use official Nginx image

---

## 🌍 Step 8: Access Website

Open your browser:

```
http://<EC2-Public-IP>:8080
```

---

## 🚫 If Website is Not Accessible



You may need to configure **Security Groups**.<img width="1874" height="738" alt="Screenshot 2026-04-03 001518" src="https://github.com/user-attachments/assets/f5ecda27-9991-403b-8720-756b3817fb0d" />


### 🔓 Fix: Open Required Ports

Go to:

**AWS Console → EC2 → Security Groups → Inbound Rules**

Add:

| Type        | Port |
| ----------- | ---- |
| HTTP        | 80   |
| HTTPS       | 443  |
| Custom      | 8080 |
| All Traffic | All  |

---

## 🎉 Success!

Your website should now be live on AWS using Docker and Nginx 🚀

<img width="1883" height="943" alt="Screenshot 2026-04-03 001619" src="https://github.com/user-attachments/assets/59bb3900-054a-4767-87af-1d45804048da" />

---

## 📁 Project Structure

```
A-Bicycle-rental-website-/
│── index.html
│── assets/
│── css/
│── js/
```

---

## 💡 Tips

* Always ensure Docker service is running
* Use `docker ps` to check running containers
* Use `docker logs <container_id>` for debugging

---

## 📜 License

This project is open-source and available under the MIT License.

---

## 🙌 Author

**Nagendra BS**

---
=======
# A-Bicycle-rental-website-
A responsive bicycle rental website built with HTML, CSS, and JavaScript, designed for university students to easily rent bikes on campus. Features a clean UI, smooth navigation, and interactive elements for an intuitive user experience. 🚀
>>>>>>> 3a44bda (Initial commit)
