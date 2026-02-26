<!-- AWS Day 3: EC2 (Elastic Compute Cloud) -->
# AWS — Day 3: EC2 (Elastic Compute Cloud)

Core compute service for running applications in the cloud. Essential for DevOps and cloud architecture interviews.

## Table of Contents
- [What is EC2?](#what-is-ec2)
- [Why EC2 Matters](#why-ec2-matters)
- [EC2 Use Cases](#ec2-use-cases)
- [EC2 Instance Types](#ec2-instance-types)
- [Instance Families](#instance-families)
- [Instance Capabilities](#instance-capabilities)
- [EC2 Instance Basics](#ec2-instance-basics)
- [Launching an EC2 Instance](#launching-an-ec2-instance)
- [Managing EC2 Instances](#managing-ec2-instances)
- [Quick-Revision Interview Q&A](#quick-revision-interview-qa)

---

## What is EC2?

Amazon Elastic Compute Cloud (EC2) is a web service that provides secure, resizable compute capacity in the cloud.

Key points:
- On-demand infrastructure for running applications.
- Scale capacity within minutes with 99.99% availability SLA.
- Secure compute foundation with AWS Nitro System.
- Flexible pricing options (On-Demand, Reserved, Spot, Savings Plans).

---

## Why EC2 Matters

EC2 is the backbone of AWS compute services:
- Most widely used AWS service in production environments.
- Foundation for web applications, databases, batch processing, and more.
- Essential for understanding cloud architecture and DevOps practices.
- Heavily tested in AWS certification and job interviews.

---

## EC2 Use Cases

### General Business Applications
- Web servers and application hosting.
- Development and test environments.
- Small to medium databases.

### High-Performance Computing (HPC)
- Scientific modeling and simulations.
- Financial modeling and risk analysis.
- Media rendering and transcoding.

### Machine Learning & AI
- Training and inference workloads.
- Deep learning model deployment.
- Data processing pipelines.

### Cost Optimization
- AWS Spot instances for fault-tolerant workloads.
- Reserved instances for predictable workloads.
- Savings Plans for long-term commitments.

---

## EC2 Instance Types

### General Purpose
- Balance of compute, memory, and network resources.
- Suitable for web servers, small databases, development environments.
- Examples: T3, M5, M6g (Graviton2).

### Compute Optimized
- Higher compute-to-memory ratio.
- Ideal for batch processing, gaming servers, high-performance web servers.
- Examples: C5, C6g (Graviton2).

### Memory Optimized
- Large amounts of RAM for memory-intensive workloads.
- Perfect for in-memory databases, real-time analytics, high-performance computing.
- Examples: R5, R6g (Graviton2).

### Storage Optimized
- High sequential read/write access to large datasets.
- Ideal for data warehousing, log processing, distributed file systems.
- Examples: I3, D2, H1.

### Accelerated Computing
- GPUs, FPGAs, or custom ASICs for offloading intensive tasks.
- Used for machine learning, 3D rendering, scientific simulations.
- Examples: P3, G4, F1.

---

## Instance Families

### Compute-Focused
- **C** – Compute optimized (C5, C6g)
- **P** – GPU instances (P3, P4)
- **F** – FPGA instances (F1)

### Storage-Focused
- **D** – Dense storage (D2, D3)
- **I** – I/O optimized (I3, I4)

### Memory-Focused
- **R** – Random access memory (R5, R6g)
- **X** – Extra-large memory (X1, X2)
- **U** – Ultra-high memory (U-12tb1, U-18tb1)

### General Purpose
- **M** – Most scenarios (M5, M6g)
- **T** – Turbo (burstable instances like T3, T4g)

### Specialized
- **Hpc** – High performance computing
- **Inf** – AWS Inferentia (machine learning inference)
- **Trn** – AWS Tranium (machine learning training)
- **VT** – Video transcoding

---

## Instance Capabilities

### Processor Types
- **a** – AMD processors
- **g** – AWS Graviton processors (ARM-based, cost-effective)
- **i** – Intel processors

### Storage Options
- **d** – Instance store volumes (high-speed local storage)
- **e** – Extra storage or memory

### Network Optimization
- **n** – Network and EBS optimized

### Performance
- **z** – High performance

---

## EC2 Instance Basics

### Virtual Servers and Instances
- EC2 instances are virtual servers running in AWS data centers.
- Each instance runs its own operating system and applications.
- Instances can be started, stopped, and terminated independently.

### Key Components

#### AMI (Amazon Machine Image)
- Template containing the operating system, applications, and configurations.
- Types: AWS-provided, AWS Marketplace, custom AMIs.
- Choose AMI based on OS, application requirements, and licensing.

#### Instance Types
- Define CPU, memory, storage, and networking capacity.
- Choose based on workload requirements and cost optimization.

#### Instance States
- **Running:** Instance is active and running applications.
- **Stopped:** Instance is off but configuration is preserved.
- **Terminated:** Instance is permanently deleted.

### Instance Pricing Models

#### On-Demand
- Pay by the hour with no upfront commitment.
- Most flexible but highest cost.
- Best for unpredictable workloads.

#### Reserved Instances
- Up to 75% discount compared to On-Demand.
- Commit to 1 or 3 years with upfront payment options.
- Ideal for steady-state workloads.

#### Spot Instances
- Up to 90% discount compared to On-Demand.
- Bid on unused capacity; instances can be interrupted.
- Perfect for fault-tolerant, flexible workloads.

---

## Launching an EC2 Instance

### Step-by-Step Process

1. **Choose AMI** – Select operating system and application stack.
2. **Select Instance Type** – Match compute requirements to instance family.
3. **Configure Instance Details** – Network settings, IAM roles, user data.
4. **Add Storage** – Root volume and additional EBS volumes.
5. **Configure Security Group** – Firewall rules for inbound/outbound traffic.
6. **Review and Launch** – Verify settings and launch instance.

### Key Configuration Options

#### Network Settings
- **VPC:** Virtual network for your instance.
- **Subnet:** Availability Zone placement.
- **Public IP:** Internet accessibility.
- **IAM Role:** Permissions for AWS services.

#### Storage Options
- **EBS Volumes:** Persistent block storage.
- **Instance Store:** High-speed local storage (ephemeral).
- **Root Volume:** Operating system and boot volume.

#### Security Groups
- Virtual firewall controlling traffic.
- Define inbound and outbound rules.
- Can reference other security groups for internal access.

#### Key Pairs
- SSH key pair for secure instance access.
- Public key stored in AWS, private key kept by user.
- Required for initial SSH connection.

---

## Managing EC2 Instances

### Instance Lifecycle

#### Starting
- Instance moves from stopped to running state.
- Public IP may change (unless using Elastic IP).
- Applications restart automatically.

#### Stopping
- Instance moves from running to stopped state.
- No charges for instance usage (but EBS storage still billed).
- Public IP is released.

#### Terminating
- Instance is permanently deleted.
- All data on instance store volumes is lost.
- EBS volumes can be preserved or deleted.

### Monitoring and Performance

#### CloudWatch Metrics
- CPU utilization, network traffic, disk I/O.
- Memory utilization (requires custom monitoring).
- Status checks (system and instance).

#### Performance Optimization
- Right-sizing instances based on workload.
- Using CloudWatch alarms for automated actions.
- Implementing auto-scaling for dynamic workloads.

### Troubleshooting

#### Common Issues
- SSH connection failures (security group, key pair, network).
- Instance status checks failing (hardware issues, OS problems).
- High CPU or memory utilization.

#### Access Methods
- **SSH:** Secure Shell for Linux instances.
- **RDP:** Remote Desktop for Windows instances.
- **AWS Systems Manager:** Session Manager for secure access without SSH/RDP.

---

## Quick-Revision Interview Q&A

**Q1: What is EC2 and why is it important?**

A: EC2 is AWS's compute service providing resizable virtual servers. It's fundamental because it's the foundation for running applications in the cloud and most widely used AWS service.

**Q2: What are the main EC2 instance types and when would you use each?**

A: General Purpose (balanced workloads), Compute Optimized (high-performance processing), Memory Optimized (large datasets), Storage Optimized (sequential I/O), Accelerated Computing (GPU/FPGA workloads).

**Q3: Explain the difference between On-Demand, Reserved, and Spot instances.**

A: On-Demand (pay hourly, no commitment), Reserved (up to 75% discount with 1-3 year commitment), Spot (up to 90% discount, bid on unused capacity, can be interrupted).

**Q4: What is an AMI and why is it important?**

A: AMI is a template containing OS, applications, and configurations. It's essential because it defines what runs on your instance and enables consistent deployments.

**Q5: What's the difference between EBS and instance store volumes?**

A: EBS is persistent block storage (data survives instance stop/termination). Instance store is high-speed local storage (data lost on instance stop/termination).

**Q6: How do you secure an EC2 instance?**

A: Use security groups (firewall rules), key pairs (SSH access), IAM roles (permissions), and follow least privilege principle. Enable monitoring and regular patching.

**Q7: What is the AWS Nitro System?**

A: AWS's foundational technology providing enhanced security, performance, and isolation for EC2 instances. It offloads virtualization functions to dedicated hardware.

**Q8: How would you handle a Spot instance interruption?**

A: Implement Spot Instance interruption notices (2-minute warning), use Spot Fleets for diversification, or design applications to be fault-tolerant and restartable.

**Q9: What are the different ways to access an EC2 instance?**

A: SSH (Linux), RDP (Windows), AWS Systems Manager Session Manager (secure access without SSH/RDP), AWS CLI/SDK.

**Q10: How do you monitor EC2 instance performance?**

A: Use CloudWatch for CPU, network, disk metrics. Set up alarms for automated actions. Use AWS Systems Manager for detailed monitoring and management.

**Q11: What is auto-scaling and how does it work with EC2?**

A: Auto-scaling automatically adjusts EC2 capacity based on demand. Uses CloudWatch alarms to trigger scaling actions (add/remove instances) to maintain performance and cost efficiency.

**Q12: What's the difference between stopping and terminating an EC2 instance?**

A: Stopping preserves the instance state and configuration (can restart later). Terminating permanently deletes the instance and all instance store data.

**Q13: How do you choose the right EC2 instance type for your workload?**

A: Analyze workload requirements (CPU, memory, storage, network), consider cost optimization (Reserved/Spot), and use AWS Cost Explorer or Compute Optimizer for recommendations.

**Q14: What is Elastic IP and when would you use it?**

A: Elastic IP is a static public IP address that you can attach to EC2 instances. Use it when you need a fixed IP for DNS, whitelisting, or failover scenarios.

**Q15: How do you handle EC2 instance failures?**

A: Use CloudWatch alarms for monitoring, implement auto-scaling for redundancy, use Elastic Load Balancing for distribution, and have backup/restore procedures.

---

**Study Tips:**
- Practice launching instances with different configurations in the AWS console.
- Understand when to use each instance type and pricing model.
- Know the difference between EBS and instance store storage.
- Be familiar with security group rules and key pair management.
- Practice troubleshooting common SSH and instance issues.
- Understand auto-scaling concepts and CloudWatch monitoring.
