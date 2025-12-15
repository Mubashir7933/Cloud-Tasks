# AWS EBS Volume Creation (gp3)

## Overview

This document describes the creation of an **Amazon Elastic Block Store (EBS)** volume as part of an incremental AWS cloud migration exercise.  
The objective is to provision **persistent block storage** independently of compute resources, following cloud best practices for scalability, reliability, and data safety.

The volume created in this task will later be attached to an EC2 instance and used as durable storage during phased migration activities.

---

## Why This Task Matters

In real-world cloud environments, **compute resources are ephemeral** while **data must persist**.  
By creating an EBS volume separately from an EC2 instance, we decouple storage from compute, allowing:

- Safe instance replacement without data loss
- Incremental migration and testing
- Better cost and lifecycle control
- Reduced operational risk during infrastructure changes

This task establishes the foundation for production-grade storage management in AWS.

---

## Resource Specifications

| Attribute        | Value               |
|------------------|---------------------|
| Resource Type    | EBS Volume          |
| Volume Name      | `datacenter-volume`|
| Volume Type      | `gp3` (General Purpose SSD) |
| Volume Size      | `2 GiB`             |
| State            | `Available`         |
| Region           | As specified in task (e.g. `us-east-1`) |
| Availability Zone| Single AZ           |

---

## Implementation Steps

### Step 1: Access AWS EC2 Dashboard

- Log in to the AWS Management Console using the provided credentials
- Confirm the correct AWS Region in the top-right corner
- Navigate to **EC2** from the AWS services menu

---

### Step 2: Navigate to EBS Volumes

- In the EC2 dashboard, open **Elastic Block Store**
- Select **Volumes**
- Click **Create volume**

---

### Step 3: Configure Volume Settings

Apply the following configuration:

- **Volume type:** `gp3`
- **Size:** `2 GiB`
- **Availability Zone:** Select any available AZ
- **Tags:**
  - Key: `Name`
  - Value: `datacenter-volume`

All other settings are left as default.

---

### Step 4: Create and Verify

- Click **Create volume**
- Confirm the volume appears in the volumes list
- Verify:
  - Name tag is correctly applied
  - Volume type is `gp3`
  - Size is `2 GiB`
  - State is `Available`

---

## Key Technical Notes

- EBS volumes are **Availability Zone–specific**
- A volume can only be attached to EC2 instances in the **same AZ**
- The volume is created independently and is **not attached** to any instance at this stage
- Data stored on this volume will persist even if EC2 instances are terminated

---

## Outcome

A standalone, cost-efficient, and high-performance EBS volume has been successfully provisioned.  
This volume is now ready to be attached to EC2 instances in subsequent steps of the migration process.

---

## Next Steps

- Attach the EBS volume to an EC2 instance
- Create a filesystem and mount the volume
- Validate data persistence across instance lifecycle events

---

## Author

Documented as part of AWS Cloud hands-on learning and DevOps infrastructure practice.
