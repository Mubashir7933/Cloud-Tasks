# Task 1 – Create an RSA Key Pair (`nautilus-kp`) in AWS

This task is part of my **100 Days of Cloud / DevOps Hands-On Practice**, where I complete real AWS infrastructure tasks and document each one for learning and portfolio-building.

---

## 🚀 Scenario

The Nautilus DevOps team is migrating part of their infrastructure to AWS.  
To keep the migration controlled and low-risk, the team breaks the process into small, manageable tasks.

My first task is to create a secure **SSH key pair** that will later allow access to EC2 instances.

---

## 🎯 Task Objective

Create a key pair in AWS with the following:

- **Key Pair Name:** `nautilus-kp`
- **Key Type:** RSA
- **Region:** `us-east-1`

---

## 🧠 What is a Key Pair?

A key pair is used for secure SSH authentication.

- **Private key (.pem):** downloaded to my system  
- **Public key:** injected by AWS into the EC2 instance during launch  

SSH access works by verifying cryptographic keys instead of passwords, making it more secure.

---

## 🛠️ Steps Performed

### 1. Log in to AWS Console
Used lab credentials and opened:  
`https://197630153581.signin.aws.amazon.com/console?region=us-east-1`

### 2. Select Region
Set the region to: **N. Virginia (us-east-1)**.

### 3. Navigate to EC2 → Key Pairs

### 4. Create Key Pair
Clicked **Create key pair** and entered:

| Setting | Value |
|--------|--------|
| Name | `nautilus-kp` |
| Key pair type | RSA |
| Private key format | .pem |

The `.pem` file downloaded automatically:
