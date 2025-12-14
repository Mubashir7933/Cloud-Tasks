# AWS Elastic IP Allocation – Nautilus DevOps Task

## Overview

As part of an incremental cloud migration strategy, the Nautilus DevOps team is migrating infrastructure components to AWS in small, controlled phases. One of the foundational networking steps in this process is allocating a **static public IP address** that remains stable regardless of resource restarts or replacements.

This document explains what an **Elastic IP (EIP)** is, why it is used, and how it was allocated in AWS as part of this task.

---

## What is an Elastic IP?

An **Elastic IP (EIP)** is a **static, public IPv4 address** provided by AWS. Unlike automatically assigned public IPs, an Elastic IP does not change when an EC2 instance is stopped or restarted. The IP is owned by the AWS account and can be attached or moved between supported resources.

Elastic IPs are commonly used for:
- Production EC2 instances
- Bastion hosts
- VPN gateways
- Systems requiring IP whitelisting
- Failover and recovery scenarios

---

## Why Elastic IPs are Required

By default, AWS assigns **dynamic public IPs** to EC2 instances. These IPs can change on instance stop/start, which can break:
- DNS records
- Firewall and security rules
- External system integrations
- Client access configurations

An Elastic IP solves this by separating the **network identity (public IP)** from the **compute resource (EC2)**, ensuring consistent external access.

---

## Task Objective

The objective of this task was to allocate an Elastic IP address in AWS and name it appropriately for identification and future association.

- **Elastic IP Name:** `nautilus-eip`
- **AWS Region:** `us-east-1`

---

## Prerequisites

- Valid AWS Management Console access
- Correct region selected (`us-east-1`)
- Permission to manage EC2 networking resources

---

## Implementation Steps

### Step 1: Access Elastic IP Management

Navigate to the following path in the AWS Management Console:


---

### Step 2: Allocate a New Elastic IP

1. Click **Allocate Elastic IP address**
2. Configure the allocation:
   - **IPv4 address pool:** Amazon’s pool
   - **Network border group:** us-east-1
3. Click **Allocate**

This action reserves a static public IPv4 address under the AWS account.

---

### Step 3: Tag the Elastic IP

To follow professional cloud resource management practices, the Elastic IP was tagged as follows:

| Key  | Value         |
|-----|---------------|
| Name | nautilus-eip |

Tagging ensures clarity, traceability, and easier cost management in shared environments.

---

## Result

- A static Elastic IP address was successfully allocated
- The IP is owned by the AWS account and remains reserved
- The resource is clearly identified as `nautilus-eip`
- The Elastic IP is ready for future association with an EC2 instance or other supported services

---

## Best Practices

- Avoid leaving Elastic IPs unassociated, as AWS charges for unused EIPs
- Use Elastic IPs only when a stable public IP is required
- Prefer Load Balancers or DNS-based solutions for scalable architectures
- Always apply meaningful tags to cloud resources

---

## Summary

This task demonstrates a core AWS networking concept: maintaining a **stable public network identity** during cloud migrations. Elastic IPs are essential when consistency, reliability, and controlled external access are required in real-world cloud architectures.
