# 🚀 AWS EC2 Web Server Deployment (Nginx)

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazon-aws)
![Linux](https://img.shields.io/badge/Linux-Amazon%20Linux-2C3E50?style=for-the-badge&logo=linux)
![Nginx](https://img.shields.io/badge/Web%20Server-Nginx-009639?style=for-the-badge&logo=nginx)
![SSH](https://img.shields.io/badge/Access-SSH-blue?style=for-the-badge&logo=openssh)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

This project demonstrates how to manually deploy a **web server on AWS EC2** and make it publicly accessible via the internet.

It covers the full workflow of:
- Cloud compute provisioning (EC2)
- Secure remote access (SSH)
- Web server installation (Nginx)
- Network configuration (Security Groups)
- Public internet access via IP address

---

## 🏗️ Architecture

User Browser
↓

Public Internet
↓

AWS EC2 Public IP
↓

Security Group (Port 80 allowed)
↓

EC2 Instance (Amazon Linux 2023)
↓

Nginx Web Server
↓

HTML Response (Welcome Page)


---

## ⚙️ Tech Stack

- AWS EC2 (Compute)
- Amazon Linux 2023 (OS)
- Nginx (Web Server)
- SSH (Remote Access)
- AWS Security Groups (Firewall)

---

## 🚀 Deployment Steps

### 1. Launch EC2 Instance
- Amazon Linux 2023 AMI
- t2.micro instance type
- Enabled public IP
- Created key pair (.pem)

---

### 2. Configure Security Group
Inbound rules:

| Type | Port | Source |
|------|------|--------|
| SSH  | 22   | My IP  |
| HTTP | 80   | 0.0.0.0/0 |

---

### 3. Connect via SSH

```bash
ssh -i "etiku.pem" ec2-user@13.59.11.213

sudo yum update -y
sudo yum install nginx -y

sudo systemctl start nginx
sudo systemctl enable nginx

http://13.59.11.213
