# AWS IAM Role Creation – iamrole_john

This document describes the creation of an IAM Role in AWS that is intended to be assumed by an AWS service rather than a human user. The role enables an Amazon EC2 instance to securely access other AWS services based on permissions defined in an attached IAM policy. This task demonstrates service-to-service authentication using IAM roles, which is a core security concept in AWS.

The requirement for this task was to create an IAM role named `iamrole_john`, configure it for an AWS Service as the trusted entity, select Amazon EC2 as the use case, and attach an existing IAM policy named `iampolicy_john` to the role.

Unlike IAM users, IAM roles do not represent people and do not have passwords or long-term access keys. Instead, roles are assumed by AWS services and provide temporary, automatically rotated credentials. In this case, the role allows EC2 instances to securely perform actions defined in `iampolicy_john` without embedding credentials in code or configuration files.

To complete this task, the IAM service was opened from the AWS Management Console. A new role was created by selecting AWS Service as the trusted entity type and choosing EC2 as the service use case. This configuration establishes a trust relationship that allows EC2 instances to assume the role. During role creation, the customer-managed policy `iampolicy_john` was attached to define what actions the EC2 instance is permitted to perform. The role was then named `iamrole_john` and created.

After creation, the role was verified to ensure that Amazon EC2 is listed as the trusted entity and that `iampolicy_john` is attached under permissions. Once this role is associated with an EC2 instance, the instance will automatically receive temporary credentials and will be able to perform only the actions allowed by the attached policy.

The result of this task is a correctly configured IAM role that enables secure, policy-driven access for EC2 instances. This approach follows AWS best practices by eliminating hardcoded credentials and enforcing least-privilege access at the service level.

Key takeaway: IAM roles are used by AWS services, such as EC2, to securely access other AWS resources using temporary credentials defined by attached policies.
