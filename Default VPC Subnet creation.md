# AWS VPC Subnet Creation – Default VPC (us-east-1)

## Overview
This repository documents a hands-on AWS networking task completed as part of a cloud infrastructure lab.  
The objective was to create a new subnet inside the **default VPC** in the **us-east-1 (N. Virginia)** region, following AWS networking constraints and best practices.

---

## Objective
- Create **one subnet** named **`xfusion-subnet`**
- Use the **default VPC**
- Ensure the subnet CIDR:
  - Lies within the VPC CIDR range
  - Does not overlap with existing subnets
- Perform all actions in **us-east-1**

---

## Environment
- **Cloud Provider:** Amazon Web Services (AWS)
- **Region:** us-east-1 (N. Virginia)
- **VPC:** Default VPC
- **VPC CIDR:** `172.31.0.0/16`

---

## Key Constraint Identified
The default VPC already contained multiple pre-created subnets (`/20` CIDRs) covering the address space.  
Since AWS does **not allow overlapping or nested subnets**, a new subnet could not be created until CIDR space was freed.

---

## Solution Approach
1. Inspected existing subnets in the default VPC.
2. Deleted one unused default subnet to free its CIDR block.
3. Created a new subnet using the released CIDR.
4. Assigned the required name and verified successful creation.

---

## Subnet Configuration
| Property | Value |
|--------|------|
| Subnet Name | `xfusion-subnet` |
| VPC | Default VPC |
| Region | us-east-1 |
| Availability Zone | us-east-1a |
| IPv4 CIDR | `172.31.32.0/20` |
| State | Available |

---

## Verification
- Subnet successfully created under the default VPC
- CIDR block lies within `172.31.0.0/16`
- No overlap with existing subnets
- AWS Console validation passed

---

## Key Learnings
- Default VPCs come with pre-allocated subnets that may fully consume the CIDR range.
- AWS does **not** support subnet nesting.
- Creating new subnets in a default VPC may require deleting unused default subnets.
- CIDR planning is critical to avoid address exhaustion.

---

## Next Steps
- Attach route tables to distinguish public vs private subnets
- Launch EC2 instances inside the subnet
- Explore internet gateway and NAT gateway behavior

---
