# Task 2 – Create a Security Group in AWS (100 Days of Cloud)

## 📌 Overview
In this task, I created a Security Group in AWS to control inbound traffic to my EC2 instances.  
A Security Group acts as a **virtual firewall**, deciding which types of traffic are allowed to reach the server and which are blocked.

---

## 🛡️ What is a Security Group?
A **Security Group (SG)** is a stateful virtual firewall that protects AWS resources such as EC2 instances.

- All inbound traffic is blocked by default.
- Outbound traffic is allowed by default.
- Only the traffic we explicitly allow can reach our server.

Security Groups are essential for protecting cloud infrastructure from unauthorized access and attacks.

---

## 🎯 Task Requirements

Create a Security Group with the following configuration:

| Setting | Value |
|--------|--------|
| **Name** | `devops-sg` |
| **Description** | `Security group for Nautilus App Servers` |
| **VPC** | Default VPC |
| **Inbound Rule 1** | HTTP (Port 80) from `0.0.0.0/0` |
| **Inbound Rule 2** | SSH (Port 22) from `0.0.0.0/0` |
| **Outbound Rules** | Default (Allow All) |

---

## 🔍 Purpose of the Two Inbound Rules

### 1️⃣ HTTP (Port 80) — For Users
Allows **public users** to access the application running on the EC2 instance.  
If this rule is missing, the website/application will not load for anyone.

### 2️⃣ SSH (Port 22) — For Administrators
Allows engineers/administrators to connect to the instance via SSH for management and configuration.  
Without this rule, you cannot log into your EC2 instance.

> ⚠️ Note: In production environments, SSH should never be open to `0.0.0.0/0`.  
> For training labs, this is acceptable.

---

## 📝 Steps to Create the Security Group

1. Log in to the AWS Console.
2. Navigate to **EC2 Dashboard** → **Security Groups**.
3. Click **Create Security Group**.
4. Enter:
   - Security Group Name: `devops-sg`
   - Description: `Security group for Nautilus App Servers`
   - VPC: Select the **default VPC**
5. Add Inbound Rules:
   - **HTTP (80)** → Source: `0.0.0.0/0`
   - **SSH (22)** → Source: `0.0.0.0/0`
6. Leave outbound rules as default (Allow All).
7. Click **Create Security Group**.

---

## ✅ Outcome
A functional, properly configured Security Group (`devops-sg`) is created under the default VPC.  
It allows:
- Public access to the application (HTTP)
- Administrative access to the server (SSH)


---
