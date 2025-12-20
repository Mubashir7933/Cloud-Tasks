# AWS Elastic IP Association with EC2 – Nautilus Lab

## Overview
This task demonstrates how to associate an Elastic IP address with an existing Amazon EC2 instance. Elastic IPs provide a stable public endpoint, which is essential during cloud migrations and for production workloads where consistent external access is required.

---

## Objective
Attach an existing Elastic IP address to an existing EC2 instance to ensure the instance can be accessed using a static public IP.

---

## Target Resources
- **EC2 Instance Name:** `nautilus-ec2`
- **Elastic IP Name:** `nautilus-ec2-eip`
- **Service:** Amazon EC2
- **Region:** `us-east-1`

---

## Key Concept: Elastic IP

### What It Is
An Elastic IP is a static public IPv4 address allocated to an AWS account. It can be attached to or detached from EC2 instances as needed.

### Why It Is Used
By default, EC2 instances receive temporary public IP addresses that change when the instance is stopped or restarted. Elastic IPs solve this problem by providing a permanent public address that remains constant regardless of instance lifecycle events.

### How It Works
The Elastic IP is associated with an EC2 instance. Incoming traffic to the Elastic IP is routed by AWS to the instance’s private IP inside the VPC.

---

## Implementation Steps

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the selected region is **us-east-1**.
3. Navigate to **EC2** from the AWS services menu.
4. In the left navigation pane, click **Elastic IPs**.
5. If the Elastic IP does not exist, allocate a new Elastic IP and name it `nautilus-ec2-eip`.
6. Select the Elastic IP `nautilus-ec2-eip`.
7. Click **Actions** → **Associate Elastic IP address**.
8. Set **Resource type** to **Instance**.
9. Select the EC2 instance **`nautilus-ec2`**.
10. Click **Associate**.

The association is immediate and does not require a reboot.

---

## Verification

- Navigate to **EC2** → **Instances**.
- Select **`nautilus-ec2`**.
- Confirm that the **Public IPv4 address** matches the Elastic IP.

---

## Outcome
The EC2 instance `nautilus-ec2` is now accessible via a static Elastic IP address, ensuring stable public connectivity even if the instance is stopped, started, or replaced.

---

## Learning Outcome
This task reinforces:
- The difference between public IPs and Elastic IPs
- Why Elastic IPs are used in cloud migrations
- How AWS separates compute resources from networking
- Best practices for maintaining stable external access
