# Amazon EFS Architecture Diagram

## Diagram File
`efs-architecture.png`

---

## Overview

This diagram illustrates how **Amazon Elastic File System (EFS)** provides
shared file storage to multiple Linux-based compute resources across
Availability Zones.

---

## Architecture Description

- Multiple **EC2 instances** run in different Availability Zones
- Each instance mounts the same EFS filesystem
- Communication uses **NFS v4.1 (port 2049)**
- EFS is managed and replicated automatically by AWS

---

## Access Flow

1. EC2 instances are launched inside a VPC
2. Security groups allow NFS traffic (TCP 2049)
3. Instances mount EFS using a DNS endpoint
4. All instances read and write to the same filesystem

---

## Key Characteristics

- Linux-only file system
- Fully managed by AWS
- Automatically scales storage
- Multi-AZ availability by default

---

## Typical Use Cases

- Shared application content
- Containers (EKS / ECS)
- CI/CD pipelines
- Configuration and asset storage

---

## Design Considerations

- Place EFS and EC2 in the same VPC
- Use private subnets for security
- Enable encryption in transit and at rest
