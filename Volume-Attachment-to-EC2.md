# AWS EBS Volume Attachment to EC2 – Nautilus Lab

## Overview
This task demonstrates how to attach an existing Amazon EBS (Elastic Block Store) volume to an existing EC2 instance using the AWS Management Console. EBS volumes provide persistent block-level storage that can be attached to EC2 instances as virtual disks.

---

## Objective
Attach the existing EBS volume `nautilus-volume` to the EC2 instance `nautilus-ec2` and ensure the device name is set to `/dev/sdb`.

---

## Target Resources
- **EC2 Instance Name:** `nautilus-ec2`
- **EBS Volume Name:** `nautilus-volume`
- **Service:** Amazon EC2 / Elastic Block Store (EBS)
- **Region:** `us-east-1`
- **Device Name:** `/dev/sdb`

---

## Key Concept: EBS Volume

### What It Is
An EBS volume is a persistent virtual hard disk that provides block-level storage for EC2 instances. Data stored on an EBS volume remains intact even if the instance is stopped or restarted.

### Why It Is Used
EBS volumes allow storage to be separated from compute, enabling:
- Data persistence beyond the lifecycle of an EC2 instance
- Easy attachment and detachment between instances
- Scalable and flexible storage for applications, databases, and logs

### How It Works
When an EBS volume is attached to an EC2 instance, the operating system detects it as a new disk device (for example, `/dev/sdb`). The volume can then be formatted and mounted inside the instance if required.

---

## Preconditions
Before attaching the volume:
- The EC2 instance `nautilus-ec2` must be in **Running** state.
- Instance status checks must show **2/2 passed** (initialization completed).
- The EBS volume `nautilus-volume` must be in **Available** state.
- The region must be set to **us-east-1**.

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Confirm the selected region is **us-east-1**.
3. Navigate to **EC2** → **Instances** and verify that `nautilus-ec2` is running and fully initialized.
4. In the EC2 left navigation pane, under **Elastic Block Store**, click **Volumes**.
5. Select the volume **`nautilus-volume`**.
6. Ensure the volume state is **Available**.
7. Click **Actions** → **Attach volume**.
8. Select the instance **`nautilus-ec2`**.
9. Set the **Device name** to **`/dev/sdb`**.
10. Click **Attach volume**.

---

## Verification

1. Navigate back to **EC2** → **Volumes**.
2. Select **`nautilus-volume`**.
3. Confirm:
   - **State:** `In-use`
   - **Attached instance:** `nautilus-ec2`
   - **Device:** `/dev/sdb`

---

## Outcome
The EBS volume `nautilus-volume` is successfully attached to the EC2 instance `nautilus-ec2` as device `/dev/sdb`, making it available for use by the instance.

---

## Learning Outcome
This task reinforces:
- The concept of persistent storage in AWS using EBS
- How storage is attached independently of compute resources
- Proper verification of volume attachment in the AWS Console
