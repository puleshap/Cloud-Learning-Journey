# Cloud Security with AWS IAM

## Problem

I wanted to understand how AWS IAM controls access to AWS resources and how permissions can be safely managed for different users.

---

## Architecture

IAM User → IAM Group → IAM Policy → EC2 Access

---

## Implementation

- Launched EC2 instances
- Created a custom IAM policy
- Created an AWS account alias
- Created IAM users and groups
- Assigned policies to groups
- Tested user permissions
- Used IAM Policy Simulator to validate access

---

## Challenges Faced

- Understanding IAM policy JSON structure
- Differentiating users, groups, and policies
- Troubleshooting permission denied errors
- Understanding how inherited permissions work

---

## Solutions

- Used IAM groups instead of assigning permissions directly to users
- Tested permissions using separate IAM accounts
- Used IAM Policy Simulator to verify effective permissions
- Applied least-privilege access principles

---

## Key Learnings

- IAM is the core security layer of AWS
- Policies define permissions using JSON
- Groups simplify permission management
- Least privilege improves security
- Permission testing is important before production use

---

## Additional Observations

- IAM policies can allow or deny very specific actions on AWS resources
- Multiple policies combine to create effective permissions
- Explicit deny overrides allow permissions
