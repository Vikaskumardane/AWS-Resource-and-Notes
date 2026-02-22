<!-- AWS Day 1: Reformatted for GitHub -->
# AWS — Day 1: Cloud Basics (Interview Notes)

Concise, interview-oriented notes for quick revision. Use this as a Day‑1 checklist and Q&A reference.

## Table of Contents
- [What is Cloud Computing?](#what-is-cloud-computing)
- [Cloud Deployment Models](#cloud-deployment-models)
- [Why Companies Move to Public Cloud](#why-companies-move-to-public-cloud)
- [Why AWS Matters](#why-aws-matters)
- [Advantages of the Cloud](#advantages-of-the-cloud)
- [AWS Core Building Blocks](#aws-core-building-blocks)
- [Quick-Revision Interview Q&A](#quick-revision-interview-qa)

---

## What is Cloud Computing?

On-demand delivery of IT resources (compute, storage, networking) over the internet with pay-as-you-go pricing.

Key points:
- No need to buy or manage physical servers — the provider operates infrastructure.
- Main traits: self-service, broad network access, resource pooling, rapid elasticity, measured service.

## Cloud Deployment Models

- **Public cloud** — Owned by providers (AWS, Azure, GCP). Multi-tenant, pay-as-you-go, accessed over the internet.
- **Private cloud** — Dedicated to a single organization (on-prem or hosted). More control and compliance, higher cost/management.
- **Hybrid cloud** — Mix of public + private; useful when some data must remain private but other workloads need public scalability.

## Why Companies Move to Public Cloud

- Lower upfront cost (no large CAPEX); pay only for usage.
- Faster time to market: provision infrastructure in minutes.
- Elastic scalability: auto-scale with demand.
- Global reach: deploy in multiple regions close to users.
- Built-in provider services for backup, DR, monitoring, and security.

## Why AWS Matters

- One of the earliest and largest public cloud providers with a global footprint (regions, AZs, edge locations).
- Large ecosystem for DevOps and infra automation: services such as `EC2`, `IAM`, `VPC`, `S3`, `CloudWatch`, `CloudFormation`, `ECR`, `ECS`, `EKS`.
- Strong IaC and automation support (CloudFormation, Terraform) — makes repeatable deployments common in interviews.

## Advantages of the Cloud (General + AWS)

- **Cost:** No hardware purchase; options like spot, on-demand, reserved instances for optimization.
- **Reliability & Performance:** Multi-AZ, managed load balancers, CDN (`CloudFront`).
- **Security:** `IAM`, encryption, VPC isolation, audit services (`CloudTrail`, `Config`).
- **Agility:** Rapid experimentation with managed services (databases, analytics, ML, serverless `Lambda`).

## AWS Core Building Blocks to Know from Day 1

- **Regions & Availability Zones (AZs)** — geographic areas and isolated data centers for HA.
- **Compute:** `EC2`, `Lambda`.
- **Storage:** `S3`, `EBS`, `EFS`, `Glacier`.
- **Networking:** `VPC`, subnets, `Route 53`, Load Balancers.
- **Security & IAM:** users, groups, roles, and policies.

## Quick-Revision Interview Q&A
Use this right before interviews — short Q&A style.

**Q1: What is cloud computing?**

A: Delivery of computing services (servers, storage, databases, networking) over the internet with pay-as-you-go pricing.

**Q2: What are the main cloud deployment models?**

A: Public cloud, private cloud, hybrid cloud.

**Q3: Explain public vs private cloud with an example.**

A: Public — an AWS region shared by many customers (multi-tenant). Private — dedicated infrastructure for a single organization, often on-prem.

**Q4: Why move from on-prem to public cloud?**

A: Reduced CAPEX, faster provisioning, elastic scaling, global reach, managed services, improved DR and agility.

**Q5: What advantages does cloud have over traditional data centers?**

A: No hardware management, pay-as-you-go, elasticity, automation, global availability, and many managed services.

**Q6: What is AWS?**

A: Amazon Web Services — a public cloud platform offering compute, storage, networking, database, analytics, and many managed services.

**Q7: Name three core AWS service categories.**

A: Compute (`EC2`, `Lambda`), Storage (`S3`, `EBS`, `EFS`), Networking (`VPC`, `Route 53`, `CloudFront`).

**Q8: Region vs Availability Zone — what's the difference?**

A: Region = separate geographic area. AZ = one or more isolated data centers inside a region used for high availability.

**Q9: How does cloud enable scalability and high availability?**

A: Autoscaling, load balancers, multi-AZ deployments, and global distribution handle traffic and failures.

**Q10: Why should a DevOps engineer learn AWS?**

A: Many CI/CD and infra automation pipelines rely on AWS services like `EC2`, `VPC`, `IAM`, `S3`, `CloudFormation`, and `CodePipeline`.

---

If you'd like, I can:
- add collapsible Q&A sections for quicker scanning,
- create a printable PDF, or
- split this into separate topic files (compute.md, storage.md, networking.md).
