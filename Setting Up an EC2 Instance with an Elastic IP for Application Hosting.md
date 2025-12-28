# EC2 Instance with Elastic IP Configuration (AWS)

## Overview
This task documents the creation of an Amazon EC2 instance with a **static public IP address** using an Elastic IP. The objective is to provide a **reliable and consistent access point** for an application hosted on EC2, ensuring uninterrupted client connectivity even if the instance is restarted or replaced.

---

## Task Requirements
- Create an EC2 instance named **`xfusion-ec2`**
- Use any Linux-based AMI (Ubuntu selected)
- Instance type must be **`t2.micro`**
- Allocate and associate an Elastic IP
- Name the Elastic IP **`xfusion-eip`**

---

## Why Elastic IP Is Required
By default, EC2 instances receive a **temporary public IP address**. This IP can change when the instance is stopped, started, or recreated. Such behavior is unsuitable for applications that require a fixed endpoint.

An **Elastic IP (EIP)** solves this problem by providing:
- A **static public IPv4 address**
- Ownership at the AWS account level
- The ability to reattach the same IP to a different instance if needed

This ensures clients can always reach the application using the same IP address.

---

## Architecture Concept

Client
|
v
Elastic IP (Static Public IP)
|
v
EC2 Instance (xfusion-ec2)
|
v
Application

---

The client communicates only with the Elastic IP. The underlying EC2 instance can change without affecting client access.

---

## Implementation Steps

### 1. Launch EC2 Instance
- Service: Amazon EC2
- Instance Name: `xfusion-ec2`
- AMI: Linux (Ubuntu)
- Instance Type: `t2.micro`
- Network settings left as default
- Instance launched successfully

### 2. Allocate Elastic IP
- Navigated to **EC2 → Elastic IPs**
- Allocated a new Elastic IP address
- Added tag:
  - Key: `Name`
  - Value: `xfusion-eip`

### 3. Associate Elastic IP
- Associated `xfusion-eip` with `xfusion-ec2`
- Verified the Elastic IP is attached to the running instance

---

## Result
- EC2 instance `xfusion-ec2` is running
- Elastic IP `xfusion-eip` is permanently associated
- Application is accessible via a **stable public IP**
- Instance restarts or replacements will not affect client connectivity

---

## Best Practices Highlighted
- Avoid relying on default EC2 public IPs in production
- Use Elastic IPs for stable access points
- Release unused Elastic IPs to avoid unnecessary costs
- For large-scale systems, prefer Load Balancers and DNS, but understand Elastic IP fundamentals

---

## Key Takeaway
Clients access applications on EC2 through a public IP address.  
Attaching an Elastic IP ensures that this address **remains constant**, providing reliability, stability, and production-grade accessibility.

---
*Documented as part of hands-on AWS Cloud and DevOps learning.*
