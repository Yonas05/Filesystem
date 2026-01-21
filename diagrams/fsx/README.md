# Amazon FSx Architecture Diagram

## Architecture Diagram

![Amazon FSx Architecture](fsx-architecture.png)

---

## Overview

This diagram illustrates **Amazon FSx**, a collection of high-performance,
fully managed file systems designed for specific workloads and access patterns.

---

## Architecture Description

- Clients connect to Amazon FSx using **SMB or NFS**, depending on the file system
- The selected FSx type determines protocol support, performance, and features
- FSx is optimized for **throughput, latency, and IOPS**
- Optional **Active Directory integration** is available for Windows-based FSx deployments

---

## Supported Amazon FSx Types

- **FSx for Windows File Server** – SMB-based Windows workloads
- **FSx for Lustre** – High-performance computing (HPC) and machine learning
- **FSx for NetApp ONTAP** – Enterprise NAS with snapshots and replication
- **FSx for OpenZFS** – Low-latency and high-IOPS workloads

---

## Access Flow

1. Clients (EC2 instances, HPC nodes, or applications) are launched in a VPC
2. An Amazon FSx filesystem is provisioned within the VPC
3. Security groups and network rules allow SMB or NFS traffic
4. Clients mount the FSx filesystem based on the selected FSx type

---

## Key Characteristics

- High throughput and low latency
- Supports both Windows and Linux workloads
- Workload-optimized file systems
- Enterprise-grade features and integrations

---

## Typical Use Cases

- Windows enterprise applications
- High-performance computing (HPC)
- Machine learning training and analytics
- Media processing and rendering pipelines

---

## Design Considerations

- Select the FSx type based on workload requirements
- Use dedicated subnets to ensure predictable performance
- Monitor throughput, IOPS, and latency metrics
- Plan network and security configurations carefully
