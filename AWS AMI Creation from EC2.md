# AWS AMI Creation from EC2 – Nautilus Lab

## Overview
This task demonstrates how to create an Amazon Machine Image (AMI) from an existing EC2 instance. An AMI acts as a reusable server image that can be used to launch new EC2 instances with the same operating system, installed software, and baseline configuration captured at a specific point in time.

---

## Objective
Create an AMI from the existing EC2 instance `devops-ec2` with the following requirements:
- **AMI Name:** `devops-ec2-ami`
- Ensure the AMI reaches the **Available** state before submitting the task.

---

## Target Resources
- **EC2 Instance Name:** `devops-ec2`
- **AMI Name:** `devops-ec2-ami`
- **Service:** Amazon EC2 (AMI / Images)
- **Region:** As provided by the lab (select the correct region in the console)

---

## Key Concept: AMI (Amazon Machine Image)

### What It Is
An AMI is a reusable image/template of an EC2 instance. It captures the instance’s system state, including:
- Operating system
- Installed packages and software
- Configuration files
- Disk contents (via EBS snapshots)

### Why It Is Used
AMIs are commonly used for:
- Creating backups of server configuration and disk state
- Rapidly cloning servers for scaling or testing
- Building “golden images” for consistent deployments
- Disaster recovery (quick replacement of failed instances)

### How It Works
When an AMI is created from an EC2 instance, AWS automatically creates one or more EBS snapshots of the instance’s attached volumes and then registers an AMI that references those snapshots. The AMI becomes usable once its state changes to **Available**.

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the correct **region** is selected.
3. Navigate to **EC2** → **Instances**.
4. Select the instance **`devops-ec2`**.
5. Click **Actions** → **Image and templates** → **Create image**.
6. Enter the following:
   - **Image name:** `devops-ec2-ami`
   - (Optional) Description: `AMI created from devops-ec2`
7. Keep remaining settings as default unless the lab specifies otherwise.
8. Click **Create image**.

---

## Verification

1. In the EC2 left navigation pane, go to **AMIs** (under **Images**).
2. Locate **`devops-ec2-ami`**.
3. Confirm the **State** progresses from `pending` to **`available`**.

The task is complete only when the AMI state is **Available**.

---

## Outcome
A new AMI named `devops-ec2-ami` is successfully created from the EC2 instance `devops-ec2` and is ready to be used for launching new EC2 instances with the same baseline configuration.

---

## Learning Outcome
This task reinforces:
- The difference between an EC2 instance (running server) and an AMI (server image/template)
- How AWS uses EBS snapshots to build AMIs
- Why AMIs are important for backups, consistency, and fast recovery
