# EC2 Instance Type Optimization (t2.micro → t2.nano)

## Overview
This task focuses on optimizing AWS EC2 resource usage by identifying an underutilized instance and resizing it to a more cost-effective instance type. The goal was to reduce unnecessary resource consumption while ensuring the instance remains operational.

The EC2 instance `devops-ec2` was resized from `t2.micro` to `t2.nano` after confirming that all system status checks were complete.

---

## Task Requirements
- Change the EC2 instance type from **t2.micro** to **t2.nano**
- Ensure the instance status checks are completed before making changes
- Confirm the instance is in **Running** state after the modification

---

## Implementation Steps

### 1. Verify Instance Status Checks
- Navigated to **EC2 → Instances**
- Selected the instance **devops-ec2**
- Confirmed **Status Checks: 2/2 passed**

> Instance type changes must not be performed while the instance is initializing.

---

### 2. Stop the EC2 Instance
- Selected **devops-ec2**
- Action: **Instance state → Stop**
- Waited until the instance state changed to **Stopped**

---

### 3. Change Instance Type
- With the instance stopped:
  - Navigated to **Actions → Instance settings → Change instance type**
  - Updated instance type to:
    ```
    t2.nano
    ```
- Applied the changes

---

### 4. Start the EC2 Instance
- Selected **Instance state → Start**
- Verified the instance state returned to **Running**

---

## Final Verification
- **Instance Name:** devops-ec2  
- **Instance Type:** t2.nano  
- **Instance State:** Running  

All task requirements were successfully met.

---

## Key Learnings
- EC2 instance types can only be modified when the instance is stopped
- Waiting for system status checks ensures safe configuration changes
- Downsizing underutilized instances is an effective cost-optimization strategy
- This approach is commonly used in development and testing environments to reduce cloud costs

---

## Tools & Technologies
- AWS EC2
- AWS Management Console
