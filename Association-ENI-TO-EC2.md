# AWS ENI Attachment to EC2 – Nautilus Lab

## Overview
This task demonstrates how to attach an existing Elastic Network Interface (ENI) to an existing Amazon EC2 instance in AWS. ENIs act as virtual network cards for EC2 instances and carry key networking attributes such as private IP addresses and security groups. Attaching an ENI is a common operational action during migrations, failover scenarios, and network reconfiguration.

---

## Objective
Attach the existing network interface `datacenter-eni` to the EC2 instance `datacenter-ec2` and confirm that the ENI status shows **attached** before submission.

---

## Target Resources
- **EC2 Instance Name:** `datacenter-ec2`
- **Elastic Network Interface (ENI) Name:** `datacenter-eni`
- **Service:** Amazon EC2
- **Region:** `us-east-1`

---

## Key Concept: Elastic Network Interface (ENI)

### What It Is
An Elastic Network Interface (ENI) is a virtual network card used by an EC2 instance to connect to a VPC network. It can be attached and detached independently from the instance.

### Why It Is Used
ENIs allow AWS to separate compute (EC2) from networking (interface identity). This enables:
- Stable networking identity even if an instance is replaced
- Failover by moving an ENI to another instance
- Multiple network interfaces on a single instance for advanced networking setups

### How It Works
The ENI contains networking configuration such as private IP address(es), security groups, subnet membership, and a MAC address. When attached, the EC2 instance can send and receive traffic through that ENI.

---

## Preconditions
Before attaching the ENI:
- Ensure the instance `datacenter-ec2` has completed initialization (status checks passed).
- Ensure you are working in the correct region: `us-east-1`.

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Confirm the region is set to **us-east-1**.
3. Navigate to **EC2** → **Instances**.
4. Select the instance **`datacenter-ec2`** and confirm:
   - Instance state is **Running**
   - Status checks show **2/2 passed**
5. In the EC2 left navigation pane, click **Network Interfaces**.
6. Select the network interface **`datacenter-eni`**.
7. Click **Actions** → **Attach** (or **Attach network interface**, depending on console view).
8. Select the instance **`datacenter-ec2`** as the attachment target.
9. (If prompted) Choose an available device index (AWS will often auto-pick).
10. Click **Attach** to complete the operation.

---

## Verification

1. Go to **EC2** → **Network Interfaces**.
2. Select **`datacenter-eni`**.
3. Confirm:
   - **Status:** `in-use`
   - **Attachment:** shows the EC2 instance `datacenter-ec2`
   - The interface is marked as **attached**

This verification must be completed before submitting the task.

---

## Outcome
The ENI `datacenter-eni` is successfully attached to the EC2 instance `datacenter-ec2`, and its status confirms the attachment is active.

---

## Learning Outcome
By completing this task, you learn:
- What an ENI is and why AWS uses it
- How EC2 networking is managed through ENIs
- How to verify correct network attachment status in AWS
