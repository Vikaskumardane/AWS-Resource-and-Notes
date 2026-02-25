<!-- AWS Day 2: IAM (Identity and Access Management) -->
# AWS — Day 2: IAM (Identity and Access Management)

Essential security service for managing access to AWS resources. Master this for interviews — it's fundamental to AWS security architecture.

## Table of Contents
- [What is IAM?](#what-is-iam)
- [Core IAM Components](#core-iam-components)
- [IAM Policies](#iam-policies)
- [Key Principles & Best Practices](#key-principles--best-practices)
- [IAM Features](#iam-features)
- [Quick-Revision Interview Q&A](#quick-revision-interview-qa)

---

## What is IAM?

Identity and Access Management (IAM) is AWS's service for managing access to AWS resources. Think of it as a security checkpoint for your entire AWS account.

Key points:
- Centralized control over who can access what resources.
- Granular permission management at scale.
- No additional cost — included with AWS account.
- Works across all AWS services.

---

## Core IAM Components

### Users
- Represent individual people or entities (applications, services).
- Each user has a unique name and security credentials (password or access keys).
- Used for human or application-level access.
- Access keys consist of Access Key ID and Secret Access Key.

### Groups
- Collections of users with similar access requirements.
- Simplify permission management (assign permissions once, apply to many users).
- Users can belong to multiple groups.
- Permissions are inherited from group policies.

### Roles
- Temporary access mechanism for AWS services or external entities.
- Do not have permanent credentials like users.
- Have associated policies that define permissions.
- Used for cross-account access, EC2 instances, Lambda, and third-party integrations.
- AssumeRole trust relationship defines who can use the role.

### Policies
JSON documents that define permissions — the heart of access control.

Structure:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:DescribeInstances",
      "Resource": "*"
    }
  ]
}
```

Types:
- **AWS Managed Policies:** Predefined by AWS, maintained and updated automatically.
- **Customer Managed Policies:** Created and updated by you for custom needs.
- **Inline Policies:** Directly embedded in a single user, group, or role (not recommended at scale).

---

## IAM Policies

### Policy Components

- **Effect:** `Allow` or `Deny` — explicitly grant or restrict access.
- **Action:** Specific API calls (e.g., `ec2:DescribeInstances`, `s3:GetObject`).
- **Resource:** ARN (Amazon Resource Name) of the resource the action applies to (e.g., `arn:aws:s3:::bucket-name/*`).
- **Condition:** Optional — restrict based on time, IP, MFA, etc.

### Example Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:RunInstances",
        "ec2:TerminateInstances",
        "ec2:DescribeInstances"
      ],
      "Resource": "arn:aws:ec2:us-east-1:123456789012:instance/*"
    }
  ]
}
```

---

## Key Principles & Best Practices

### Principle of Least Privilege
- Grant only the minimum permissions needed for the task.
- Reduces security risk of compromised accounts.
- Regularly audit and remove unused permissions.

### Best Practices
- Never use AWS root account for daily tasks.
- Enable MFA on all users (especially root).
- Use roles instead of sharing access keys.
- Rotate access keys regularly (every 90 days).
- Use temporary credentials via STS (Security Token Service) when possible.
- Monitor IAM activity with CloudTrail.
- Avoid inline policies — use managed policies.

---

## IAM Features

- **Multi-Factor Authentication (MFA):** Adds second layer of security (password + device code).
- **Access Advisor:** Shows which services a user/role accessed and when.
- **Credential Report:** Lists all credentials and password age for compliance.
- **IAM Policy Simulator:** Test policies before applying them.
- **CloudTrail Integration:** Audit all IAM actions and changes.
- **Temporary Security Credentials:** Time-limited access via AssumeRole.

---

## Quick-Revision Interview Q&A

**Q1: What is IAM and why is it important?**

A: IAM is AWS's service for securely controlling access to resources. It's critical because it enables least-privilege access, audit trails, and centralized permission management across the entire AWS account.

**Q2: What are the main IAM components?**

A: Users (individual access), Groups (collections of users), Roles (temporary access for services), and Policies (permission definitions in JSON).

**Q3: What's the difference between IAM users and IAM roles?**

A: Users have permanent credentials (passwords, access keys) for human/application access. Roles have temporary credentials and are assumed by AWS services or external entities.

**Q4: Explain the principle of least privilege.**

A: Grant only the minimum permissions needed for a task. This reduces security risk — if an account is compromised, the attacker has limited access.

**Q5: What is an IAM policy and how is it structured?**

A: A JSON document defining permissions. Structure includes Effect (Allow/Deny), Action (API calls), Resource (target ARN), and optional Condition (restrictions).

**Q6: What's the difference between AWS managed and customer managed policies?**

A: AWS managed policies are predefined and maintained by AWS. Customer managed policies are created by you for custom requirements and give you more control.

**Q7: Should you use the root account for daily tasks? Why?**

A: No. Root has unrestricted access. Best practice is to create IAM users with limited permissions and keep root for account recovery only.

**Q8: What is MFA and why should you enable it?**

A: Multi-Factor Authentication adds a second layer — something you know (password) + something you have (device code). Dramatically improves security.

**Q9: How would you grant an EC2 instance access to an S3 bucket?**

A: Attach an IAM role to the EC2 instance. The role has a policy allowing S3 actions. The instance automatically receives temporary credentials to access S3.

**Q10: How do you audit IAM activity and changes?**

A: Use CloudTrail to log all API calls and IAM changes. Use IAM Access Advisor to see what services a user accessed and when. Generate credential reports for compliance.

**Q11: What is an ARN (Amazon Resource Name)?**

A: A unique identifier for AWS resources. Format: `arn:partition:service:region:account-id:resource`. Example: `arn:aws:ec2:us-east-1:123456789012:instance/i-1234567890abcdef0`.

**Q12: Can you use IAM policies with S3 bucket policies? What's the difference?**

A: Yes. IAM policies control access FROM identities (users, roles). S3 bucket policies control access TO a bucket (can grant cross-account access). Both can coexist; the most restrictive applies.

**Q13: What is AssumeRole and when would you use it?**

A: AssumeRole allows a principal (user, service, external account) to temporarily assume a role's permissions. Used for cross-account access, service delegation, and temporary elevated permissions.

**Q14: How do you handle temporary credentials and why are they better than long-term access keys?**

A: STS (Security Token Service) issues temporary credentials (valid 15 min–36 hours). Better than long-term keys because they expire automatically, reducing exposure if compromised.

**Q15: What's the difference between Allow and Deny in IAM policies?**

A: Allow grants permissions (explicit). Deny explicitly blocks (overrides Allow). Always evaluate Deny first — one Deny blocks an action even if Allow exists elsewhere.

---

**Study Tips:**
- Practice reading and writing IAM policies in the AWS console.
- Simulate policies before applying them using IAM Policy Simulator.
- Understand ARN format — commonly tested in interviews.
- Know the difference between user and role scenarios; interviewers ask "when would you use each?"
- Memorize the principle of least privilege — it's the foundation of IAM design.
