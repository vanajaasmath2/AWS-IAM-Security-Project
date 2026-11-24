AWS IAM Security – Access Control and Policy Review

Project Overview

This project focuses on reviewing AWS Identity and Access Management (IAM) policies and understanding how permissions control access to AWS resources.

Objectives

- Understand AWS IAM policies.
- Review AWS-managed ReadOnlyAccess policy.
- Understand Allow and Deny permissions.
- Identify overly broad S3 permissions.
- Apply the Principle of Least Privilege.

Tools and Services

- Amazon Web Services (AWS)
- AWS IAM
- IAM Policies
- JSON policy documents

Practical Activities

1. ReadOnlyAccess Policy Review

Reviewed the AWS-managed ReadOnlyAccess policy and examined its permissions.

Key learning: A policy that grants read-only access does not itself grant permission to delete resources. Other applicable policies can affect the final access decision.

2. Least-Privilege Policy Review

Reviewed this example policy:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-lab-bucket/*"
    }
  ]
}

Key learning: This example grants object-read permission for objects in a specific bucket. "my-lab-bucket" is a placeholder name.

3. Broad Permission Risk Review

Reviewed the following example:

{
  "Effect": "Allow",
  "Action": "s3:*",
  "Resource": "*"
}

Security finding: This permission is overly broad because it can allow many S3 actions, including potentially destructive actions.

Recommendation: Grant only the permissions required for the user's responsibilities.

Key Security Concepts Learned

- IAM policies
- Allow and Deny effects
- Actions and Resources
- S3 bucket and object ARNs
- Least Privilege
- Broad permission risks

Testing Limitation

The AWS IAM Policy Simulator was unavailable in my account. Therefore, this project documents policy inspection and review, not a live permission simulation or enforcement test.

Conclusion

This project helped me understand AWS IAM access control, review JSON-based permissions, identify excessive permissions, and recommend least-privilege access.

Disclaimer

This was a learning project conducted in an AWS account. No custom policy was created or attached to an IAM user or role.
