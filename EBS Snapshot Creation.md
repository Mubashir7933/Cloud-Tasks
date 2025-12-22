# AWS EBS Snapshot Creation – Nautilus Lab

## Overview
This task demonstrates how to create an Amazon EBS (Elastic Block Store) snapshot from an existing EBS volume. Snapshots are point-in-time backups of storage volumes and are a critical component of backup, recovery, and migration strategies in AWS.

---

## Objective
Create a snapshot of the existing EBS volume `xfusion-vol` with the following requirements:
- **Snapshot Name:** `xfusion-vol-ss`
- **Description:** `xfusion Snapshot`
- Ensure the snapshot status reaches **completed** before submission.

---

## Target Resource
- **EBS Volume Name:** `xfusion-vol`
- **Snapshot Name:** `xfusion-vol-ss`
- **Service:** Amazon EC2 / Elastic Block Store (EBS)
- **Region:** `us-east-1`

---

## Key Concept: EBS Snapshot

### What It Is
An EBS snapshot is a point-in-time backup of an EBS volume. It captures the data stored on the volume at the moment the snapshot is created.

### Why It Is Used
Snapshots are used to:
- Back up critical data
- Restore volumes after failure or deletion
- Create new EBS volumes from existing data
- Serve as the foundation for creating AMIs

### How It Works
When a snapshot is created, AWS copies the data blocks from the EBS volume and stores them securely in Amazon-managed storage. The first snapshot is a full copy, while subsequent snapshots are incremental.

---

## Preconditions
Before creating the snapshot:
- Ensure you are working in the **us-east-1** region.
- Confirm that the EBS volume `xfusion-vol` exists.

---

## Implementation Steps (AWS Console)

1. Log in to the AWS Management Console using the provided credentials.
2. Ensure the selected region is **us-east-1**.
3. Navigate to **EC2** from the AWS services menu.
4. In the left navigation pane, under **Elastic Block Store**, click **Volumes**.
5. Select the volume **`xfusion-vol`**.
6. Click **Actions** → **Create snapshot**.
7. Enter the following details:
   - **Snapshot name:** `xfusion-vol-ss`
   - **Description:** `xfusion Snapshot`
8. Click **Create snapshot**.

---

## Verification

1. In the EC2 left navigation pane, click **Snapshots**.
2. Locate the snapshot **`xfusion-vol-ss`**.
3. Confirm the **Status** transitions from `pending` to **`completed`**.

The task is considered complete only when the snapshot status is **completed**.

---

## Outcome
A snapshot named `xfusion-vol-ss` is successfully created from the EBS volume `xfusion-vol` and is ready for use in recovery, cloning, or AMI creation.

---

## Learning Outcome
This task reinforces:
- The role of EBS snapshots in data protection
- The difference between volumes, snapshots, and AMIs
- Proper verification of snapshot completion before relying on backups
