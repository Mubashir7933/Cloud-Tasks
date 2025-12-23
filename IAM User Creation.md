# AWS IAM User Creation – Nautilus Lab

## Overview
This task demonstrates how to create a basic IAM (Identity and Access Management) user in AWS. IAM is a foundational security service that controls who can access AWS resources and what actions they are allowed to perform. Creating IAM users is one of the first steps in setting up secure cloud infrastructure.

---

## Objective
Create an IAM user with the following requirement:
- **IAM User Name:** `iamuser_javed`

No permissions, groups, or access keys are required for this task.

---

## Target Resource
- **Service:** AWS Identity and Access Management (IAM)
- **IAM User Name:** `iamuser_javed`

---

## Key Concept: IAM User

### What It Is
An IAM user is an AWS identity that represents a person or service that needs to interact with AWS resources. Each IAM user has unique credentials and can be assigned permissions.

### Why It Is Used
IAM users are used to:
- Avoid using the root AWS account for daily operations
- Provide individual identities for users
- Apply the principle of least privilege
- Track and audit actions performed in AWS

### How It Works
By default, a newly created IAM user has **no permissions**. Permissions are later granted by attaching policies directly or through IAM groups.

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Navigate to the **IAM** service.
3. In the left navigation pane, click **Users**.
4. Click **Create user**.
5. Enter the user name:  
   - `iamuser_javed`
6. Click **Next**.
7. Skip permission assignment (no permissions required for this task).
8. Review the configuration.
9. Click **Create user**.

---

## Verification

- Confirm that the IAM user **`iamuser_javed`** appears in the Users list.
- Ensure the user is created successfully with no permissions attached.

---

## Outcome
The IAM user `iamuser_javed` is successfully created and is ready for permission assignment or group membership in future tasks.

---

## Learning Outcome
This task reinforces:
- The role of IAM in AWS security
- The purpose of IAM users
- Safe identity creation without unnecessary permissions
