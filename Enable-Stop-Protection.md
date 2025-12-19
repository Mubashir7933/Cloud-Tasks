# AWS EC2 Stop Protection Configuration – Nautilus Lab

## Overview
This task focuses on applying a safety configuration to an existing Amazon EC2 instance as part of an incremental cloud migration. The objective is to prevent accidental service disruption by enabling stop protection on a critical compute resource.

---

## Objective
Enable **Stop Protection** on an existing EC2 instance to ensure it cannot be stopped unintentionally through the AWS Console, CLI, or API.

---

## Target Resource
- **Instance Name:** `datacenter-ec2`
- **Service:** Amazon EC2
- **Region:** `us-east-1`

---

## Key Concept: Stop Protection

### What It Is
Stop protection is an EC2 instance-level safeguard that blocks any attempt to stop the instance.

### Why It Is Used
In production environments, stopping certain instances can cause service outages. Stop protection acts as a guardrail to prevent accidental downtime caused by human error or automation.

### What It Does Not Protect Against
- Instance termination
- Instance reboot
- Operating system shutdown from inside the instance

---

## Implementation Steps

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the selected region is **us-east-1**.
3. Navigate to **EC2** → **Instances**.
4. Select the instance named **`datacenter-ec2`**.
5. Click **Actions** → **Instance settings** → **Change stop protection**.
6. Enable **Stop Protection**.
7. Save the configuration.

No reboot or downtime occurs when enabling this setting.

---

## Verification

- Attempting to stop the instance after enabling stop protection results in an AWS error.
- This confirms that stop protection is active and functioning as intended.

---

## Outcome
The EC2 instance `datacenter-ec2` is now protected from accidental stop operations, reducing the risk of unplanned service disruption during ongoing infrastructure migration.

---

## Learning Outcome
This task reinforces:
- Safe operational practices in AWS
- The difference between stop protection and termination protection
- The importance of guardrails in production environments
