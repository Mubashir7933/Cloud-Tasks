# AWS EC2 Instance Launch – Nautilus Lab

## Overview
This task demonstrates how to launch a basic Amazon EC2 instance in AWS as part of an incremental cloud migration strategy. The goal is to provision a lightweight virtual server using standard AWS defaults while understanding the core components involved in compute provisioning.

---

## Objective
Create an EC2 instance with predefined specifications to simulate a real-world infrastructure migration step.

---

## Requirements
The EC2 instance must meet the following criteria:

- Instance Name: `nautilus-ec2`
- Amazon Machine Image (AMI): Amazon Linux
- Instance Type: `t2.micro`
- Key Pair: New RSA key pair named `nautilus-kp`
- Security Group: Default security group
- Region: As provided in the lab credentials

---

## Key Concepts Explained

### EC2 (Elastic Compute Cloud)
EC2 is a virtual server provided by AWS that allows users to run applications without managing physical hardware.

### AMI (Amazon Machine Image)
An AMI defines the operating system and initial software configuration of the EC2 instance. Amazon Linux is optimized for AWS and commonly used for training and production workloads.

### Instance Type
The instance type determines the CPU, memory, and networking capacity. `t2.micro` is a low-cost, entry-level instance suitable for labs and testing.

### Key Pair
A key pair is used for secure authentication when connecting to the instance via SSH. AWS does not support password-based login for EC2.

### Security Group
A security group acts as a virtual firewall controlling inbound and outbound traffic to the instance. The default security group is sufficient for this basic setup.

---

## Implementation Steps

1. Log in to the AWS Management Console using the provided credentials.
2. Navigate to **EC2** from the AWS services menu.
3. Click **Launch Instance**.
4. Set the instance name to `nautilus-ec2`.
5. Select **Amazon Linux AMI**.
6. Choose **t2.micro** as the instance type.
7. Create a new key pair:
   - Name: `nautilus-kp`
   - Type: RSA
   - Download and securely store the private key file.
8. Select the **default security group**.
9. Review the configuration and launch the instance.

---

## Result
A running EC2 instance named `nautilus-ec2` is successfully provisioned using Amazon Linux, secured with an RSA key pair, and attached to the default security group.

---

## Learning Outcome
By completing this task, you gain hands-on experience with:
- Launching EC2 instances
- Understanding AMIs and instance types
- Using key pairs for secure access
- Applying default security configurations in AWS

This forms the foundation for more advanced topics such as networking, storage attachment, and application deployment on AWS.
