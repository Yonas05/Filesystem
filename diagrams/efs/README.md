# Amazon EFS Architecture Diagram

## Architecture Diagram

![Amazon EFS Architecture](efs-architecture.png)

---

## Overview

This diagram illustrates how **Amazon Elastic File System (EFS)** provides
shared file storage to multiple Linux-based compute resources across
multiple Availability Zones.

---

## Architecture Description

- Multiple **EC2 instances** run in different Availability Zones
- Each instance mounts the same EFS filesystem
- Communication uses **NFS v4.1 (TCP port 2049)**
- EFS is fully managed and automatically replicated by AWS

---

## Access Flow

1. EC2 instances are launched inside a VPC
2. Security groups allow NFS traffic (TCP 2049)
3. Instances mount EFS using an AWS-provided DNS endpoint
4. All instances read from and write to the same shared filesystem

---

## Key Characteristics

- Linux-based file system
- Fully managed by AWS
- Automatically scales storage capacity
- Highly available with Multi-AZ replication by default

---

## Typical Use Cases

- Shared application content
- Container workloads (EKS / ECS)
- CI/CD pipelines
- Configuration and asset storage
- Web servers requiring shared file access

---

## Design Considerations

- Deploy EC2 instances and EFS in the same VPC
- Use private subnets for improved security
- Configure security groups carefully for NFS access
- Enable encryption at rest and in transit
