# AWS EC2 Termination Protection Configuration – Nautilus Lab

## Overview
As part of an incremental AWS cloud migration, this task focuses on safeguarding an existing EC2 instance by enabling termination protection. This configuration prevents accidental deletion of critical compute resources during operational changes or automation.

---

## Objective
Enable **Termination Protection** on an existing Amazon EC2 instance to ensure it cannot be permanently deleted through the AWS Console, CLI, or API.

---

## Target Resource
- **Instance Name:** `nautilus-ec2`
- **Service:** Amazon EC2
- **Region:** `us-east-1`

---

## Key Concept: Termination Protection

### What It Is
Termination protection is an EC2 instance-level safety feature that blocks any attempt to terminate (delete) an instance.

### Why It Is Used
Terminating an EC2 instance is irreversible and can result in permanent data loss and service outages. Termination protection is used to prevent accidental or unauthorized deletion of critical infrastructure components.

### What It Does Not Protect Against
- Stopping the instance
- Rebooting the instance
- Operating system shutdown initiated from within the instance

---

## Implementation Steps

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the selected region is **us-east-1**.
3. Navigate to **EC2** → **Instances**.
4. Select the instance named **`nautilus-ec2`**.
5. Click **Actions** → **Instance settings** → **Change termination protection**.
6. Enable **Termination Protection**.
7. Save the configuration.

This change does not cause any downtime or require a reboot.

---

## Verification

- Attempting to terminate the instance after enabling termination protection results in an AWS error.
- This confirms that termination protection is active and functioning correctly.

---

## Outcome
The EC2 instance `nautilus-ec2` is now protected from accidental termination, reducing the risk of permanent data loss or service disruption during migration activities.

---

## Learning Outcome
This task reinforces:
- The difference between stopping and terminating EC2 instances
- The importance of termination protection in production environments
- Safe operational practices when managing cloud infrastructure
