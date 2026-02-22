Day 1 – AWS & Cloud Basics (Notebook‑style notes)
Use this as your DAY-1.md and for quick revision.

1. What is Cloud Computing?
On‑demand delivery of IT resources (compute, storage, networking) over the internet, pay‑as‑you‑go.
​

No need to buy/manage physical servers or data centers; provider manages infrastructure.
​

Key traits: on‑demand self‑service, broad network access, resource pooling, rapid elasticity, measured service.
​

2. Public vs Private Cloud
Public cloud:

Owned and operated by cloud providers (AWS, Azure, GCP).

Resources shared across many customers (multi‑tenant).

Accessed over the public internet; pay‑as‑you‑go.

Private cloud:

Cloud infrastructure dedicated to a single organization (on‑prem or hosted).

More control, customization, and strict security/compliance, but higher cost and management overhead.

Hybrid:

Mix of public + private, used when some workloads/data must stay private, others benefit from public scalability.
​

3. Why Companies Move to Public Cloud
Lower upfront cost (no big capex on hardware); pay only for what you use.

Faster time to market: provision servers in minutes instead of weeks.

Elastic scalability: scale up/down automatically with demand (autoscaling).

Global reach: deploy apps in multiple regions near users.
​

Built‑in security, backup, disaster recovery features from the provider.

4. Why AWS Is Important in Public Cloud
One of the largest and earliest public cloud providers with global presence (regions, AZs, edge locations).

Rich ecosystem for DevOps: EC2, IAM, VPC, S3, CloudWatch, CloudFormation, CodeCommit/CodeBuild/CodeDeploy/CodePipeline, ECR/ECS/EKS, etc.

Strong integration between services, good automation and IaC support (CloudFormation, Terraform).

Widely used in industry → high demand for AWS + DevOps skills in interviews and jobs.

5. Advantages of Moving to Cloud (General + AWS)
Cost: no hardware purchase, reduced maintenance, right‑size resources, spot/on‑demand/reserved pricing options.

Performance & reliability: multiple AZs, managed load balancing, automatic failover, CDN (CloudFront).

Security: IAM, encryption, network isolation (VPC), monitoring/audit (CloudTrail, Config, CloudWatch).

Agility & innovation: experiment quickly, use managed services for databases, analytics, AI/ML, serverless (Lambda).

6. AWS Core Building Blocks to Know from Day 1
Regions & Availability Zones (AZs) – geographic locations and isolated data centers.
​

Compute: EC2, Lambda.

Storage: S3, EBS, EFS, Glacier.

Networking: VPC, subnets, Route 53, Load Balancers.

Security & IAM: IAM users/groups/roles/policies.

Quick‑Revision Interview Q&A (Most Asked on Day‑1 Topics)
Use this section right before interviews.

Conceptual Questions
Q1. What is cloud computing?
A. Delivery of computing services (servers, storage, databases, networking, etc.) over the internet with pay‑as‑you‑go pricing.
​

Q2. What are the main cloud deployment models?
A. Public cloud, private cloud, hybrid cloud.

Q3. Explain public vs private cloud with an example.
A. Public: AWS region where many customers share infrastructure; private: dedicated environment for one organization, often on‑prem or hosted.

Q4. Why do companies move from on‑prem to public cloud?
A. Reduced capex, faster provisioning, elastic scaling, global reach, managed services, improved DR and agility.

Q5. What are the advantages of cloud over traditional data centers?
A. No hardware management, pay‑as‑you‑go, elasticity, automation, global availability, rich managed services.

Q6. What is AWS?
A. Amazon Web Services, a comprehensive public cloud platform providing compute, storage, networking, database, analytics, and more on a pay‑as‑you‑go model.

Q7. Name three core service categories in AWS.
A. Compute (EC2, Lambda), Storage (S3, EBS, EFS), Networking (VPC, Route 53, CloudFront).

Q8. What is the difference between region and availability zone in AWS?
A. Region = separate geographic area; AZ = one or more isolated data centers inside a region, used for high availability.

Q9. How does cloud help with scalability and high availability?
A. Use autoscaling, load balancers, multi‑AZ deployments, and global distribution to handle traffic and failures.

Q10. As a DevOps engineer, why should you learn AWS?
A. Most CI/CD, infra automation, and modern deployments are built on AWS services like EC2, VPC, IAM, S3, CloudFormation, and CodePipeline.