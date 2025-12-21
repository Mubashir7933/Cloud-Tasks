# AWS EC2 Instance Termination – Nautilus Lab

## Overview
This task demonstrates how to permanently delete an Amazon EC2 instance that is no longer required. Terminating unused resources is an important part of cloud operations, as it helps reduce costs, minimize security risks, and keep the environment clean during and after a migration.

---

## Objective
Terminate the EC2 instance named `nautilus-ec2` and verify that its final state is **terminated**.

---

## Target Resource
- **EC2 Instance Name:** `nautilus-ec2`
- **Service:** Amazon EC2
- **Region:** `us-east-1`

---

## Key Concept: EC2 Termination

### What It Is
Terminating an EC2 instance means permanently deleting the virtual server. Once terminated, the instance cannot be restarted or recovered.

### Why It Is Used
EC2 instances that are no longer needed should be terminated to:
- Avoid unnecessary AWS charges
- Reduce operational clutter
- Eliminate unused or obsolete infrastructure
- Improve overall security posture

### What Happens on Termination
- The EC2 instance is destroyed
- The root EBS volume is deleted by default
- The instance ID is permanently removed
- Any attached Elastic IP is detached (but not automatically released)

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the selected region is **us-east-1**.
3. Navigate to **EC2** → **Instances**.
4. Locate and select the instance **`nautilus-ec2`**.
5. Click **Instance state** → **Terminate instance**.
6. Confirm the termination action.

---

## Verification

1. Remain on the **Instances** page.
2. Observe the instance state transition:
   - `shutting-down`
   - **`terminated`**
3. Confirm the final state shows **terminated** before submitting the task.

---

## Outcome
The EC2 instance `nautilus-ec2` is successfully terminated and permanently removed from the AWS environment.

---

## Learning Outcome
This task reinforces:
- The difference between stopping and terminating an EC2 instance
- The irreversible nature of instance termination
- The importance of resource cleanup during cloud migrations
