# AWS IAM Policy Attachment – iampolicy_ammar to iamuser_ammar

This document records the attachment of an existing IAM policy to an existing IAM user. The purpose of this task is to activate permissions by explicitly linking a customer-managed IAM policy to a user identity. In AWS IAM, policies do not take effect until they are attached, which makes this step critical for enforcing access control.

The task requirement was to attach the IAM policy named `iampolicy_ammar` to the IAM user named `iamuser_ammar`. Both the user and the policy already existed prior to this task. No new users or policies were created as part of this activity.

In AWS Identity and Access Management, permissions are applied only through explicit attachments. Creating a policy merely defines a set of rules, while attaching the policy determines who those rules apply to. By attaching `iampolicy_ammar` directly to `iamuser_ammar`, the permissions defined in the policy become effective for that user.

To complete this task using the AWS Management Console, IAM was opened from the AWS Console, the existing user `iamuser_ammar` was selected, and permissions were added by attaching the customer-managed policy `iampolicy_ammar` directly to the user. After reviewing the attachment, the policy was successfully applied.

Once attached, the user `iamuser_ammar` immediately inherits all permissions defined in `iampolicy_ammar`. Any allowed actions in the policy can now be performed by the user, while all other actions remain denied by default due to IAM’s implicit deny behavior.

The result of this task is a correctly configured IAM user with active permissions enforced through a customer-managed policy. This step demonstrates how AWS IAM separates permission definition from permission assignment, allowing secure, deliberate, and auditable access control.

Key takeaway: in AWS IAM, policies have no effect until they are explicitly attached to a user, group, or role. The attachment is the action that activates permissions.
