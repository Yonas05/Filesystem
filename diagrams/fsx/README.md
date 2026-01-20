# Amazon FSx Architecture Diagram

## Diagram File
`fsx-architecture.png`

---

## Overview

This diagram represents **Amazon FSx**, a set of high-performance,
fully managed file systems designed for specific workloads.

---

## Architecture Description

- Clients connect to FSx using **SMB or NFS**
- The filesystem type determines performance and protocol
- FSx is optimized for throughput, latency, and IOPS
- Optional Active Directory integration (Windows FSx)

---

## Supported FSx Types

- FSx for Windows File Server (SMB)
- FSx for Lustre (HPC / ML)
- FSx for NetApp ONTAP (Enterprise NAS)
- FSx for OpenZFS (Low-latency workloads)

---

## Access Flow

1. Clients (EC2, HPC nodes, or applications) are launched
2. FSx filesystem is provisioned in a VPC
3. Network rules allow SMB or NFS access
4. Clients mount FSx based on filesystem type

---

## Key Characteristics

- High throughput and low latency
- Windows and Linux support
- Workload-optimized storage
- Enterprise-grade features

---

## Typical Use Cases

- Windows enterprise applications
- High-performance computing
- Machine learning training
- Media processing and rendering

---

## Design Considerations

- Choose FSx type based on workload
- Use dedicated subnets for performance
- Monitor throughput and IOPS carefully
