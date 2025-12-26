# AWS IAM Custom Policy – `iampolicy_rose`

## Overview
This task documents the creation of a **custom IAM policy** in AWS that provides **read-only access to the Amazon EC2 console**.  
The policy is designed following least-privilege principles and allows users to **view EC2 resources without the ability to create, modify, or delete anything**.

This is a foundational IAM skill and a critical step in building secure, production-ready AWS environments.

---

## What This Task Actually Is
Create a **customer-managed IAM policy** named:

The policy must allow users to:
- View EC2 instances
- View AMIs
- View snapshots
- View related EC2 metadata

The policy must **not** allow any write, modify, or delete actions.

---

## Why This Policy Exists (Real-World Reasoning)
In real production environments, not every user needs full access to cloud resources.

Common scenarios:
- Auditors need visibility
- Managers want infrastructure insight
- Junior engineers need learning access
- Support teams need read-only diagnostics

Granting full EC2 access in these cases is dangerous and irresponsible.

This policy enforces:
- Visibility without risk
- Security through least privilege
- Clear separation between read and write access

---

## How Read-Only Access Works in IAM
AWS IAM does **not** have a “read-only” flag.

Read-only access is achieved by:
- Allowing only `Describe`, `List`, and `Get` actions
- Relying on AWS’s **implicit deny** for everything else

If an action is not explicitly allowed, AWS automatically blocks it.

---

## Policy Definition (JSON)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances",
        "ec2:DescribeImages",
        "ec2:DescribeSnapshots",
        "ec2:DescribeVolumes",
        "ec2:DescribeSecurityGroups",
        "ec2:DescribeKeyPairs",
        "ec2:DescribeNetworkInterfaces",
        "ec2:DescribeAvailabilityZones",
        "ec2:DescribeRegions"
      ],
      "Resource": "*"
    }
  ]
}
```json
