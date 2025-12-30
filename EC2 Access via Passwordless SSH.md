# Secure EC2 Access via Passwordless SSH (aws-client → xfusion-ec2)

## Overview
This task documents the setup of a secure, passwordless SSH connection from a trusted landing host (`aws-client`) to an Amazon EC2 instance. The goal is to allow administrative access to the EC2 instance without using passwords or AWS key pairs, relying instead on SSH key-based authentication. This approach reflects real-world DevOps practices for controlled server-to-server access.

---

## Task Requirements
- Create an EC2 instance named **`xfusion-ec2`**
- Use a Linux-based AMI
- Instance type must be **`t2.micro`**
- Create an SSH key pair on the landing host (`aws-client`) under `/root/.ssh/` if it does not already exist
- Add the public key from `aws-client` to the **root user’s** `authorized_keys` file on the EC2 instance
- Enable passwordless SSH access from `aws-client` to `xfusion-ec2`

---

## Architecture Concept
aws-client (landing host)
└── Private SSH Key (/root/.ssh/id_rsa)
|
v
xfusion-ec2 (EC2 instance)
└── Trusted Public Key (/root/.ssh/authorized_keys)

The EC2 instance explicitly trusts the `aws-client` host, allowing secure SSH access without passwords.

---

## Implementation Summary

### 1. EC2 Instance Creation
An EC2 instance was launched with the following configuration:
- Name: `xfusion-ec2`
- AMI: Linux (Amazon Linux / Ubuntu)
- Instance type: `t2.micro`
- Key pair: **None** (EC2 Instance Connect used for bootstrap access)
- Security group: SSH (port 22) allowed from the landing host network

---

### 2. SSH Key Setup on aws-client
On the landing host (`aws-client`), an SSH key pair was verified or created under `/root/.ssh/`. If the key did not exist, it was generated using standard SSH tooling. The public key represents the identity of `aws-client` and is later trusted by the EC2 instance.

---

### 3. Bootstrap Access to EC2
Since the instance was created without an AWS key pair, **EC2 Instance Connect** was used to access the instance one time via the AWS Console. This temporary access allows initial configuration without permanent credentials.

---

### 4. Configuring Trust on EC2
After connecting to the instance via EC2 Instance Connect, root access was obtained. The public key from `aws-client` was added to the following file on the EC2 instance:

root/.ssh/authorized_keys

Correct permissions were applied to ensure secure SSH operation:
- `/root/.ssh` → `700`
- `/root/.ssh/authorized_keys` → `600`

This step explicitly tells the EC2 instance to trust the `aws-client` host.

---

### 5. Verification
From `aws-client`, an SSH connection was initiated using the EC2 instance’s IP address:

```bash
ssh root@<EC2-IP>

The connection succeeded without a password prompt, confirming that passwordless SSH access was correctly configured.

⸻

Result
	•	EC2 instance xfusion-ec2 is accessible securely from aws-client
	•	SSH access is passwordless and key-based
	•	No AWS key pairs or passwords are used
	•	Access control is explicit, auditable, and production-aligned
