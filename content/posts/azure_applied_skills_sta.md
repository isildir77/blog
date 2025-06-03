---
title: "Azure Applied Skills - Storage Account"
categories: ["Azure Learning"]
date: 2025-05-07
---

This article resume the content of [Microsoft Applied Skills : Secure storage for Azure Files and Azure Blob Storage](https://learn.microsoft.com/en-us/training/paths/implement-storage-azure-files-azure-blob-storage/)

# I. Configure Azure Storage Account

Azure Storage groups one ore more of the following services:
- Blob | Files | Queues | Tables

ex: sta-test-1 can have 2 blob, 1 file and 1 table

## Storage account settings

1. Name (must be globally unique)
2. Subscription
3. Location
4. Performance : Standard v2, Premium/Page Blobs, Premium/Block Blobs, Premium/File shares
5. Replication : LRS/ZRS/GRS/GZRS
6. Access tier : Hot or Cool
7. Secure transfer with HTTPS
8. Virtual networks

Data diversity, cost sensitivity and fault tolerance determines the number of storage accounts.

Storage creation tools :
- Azure CLI | Azure Portal | Azure Powershell | SDK

# II. Configure Azure Blob Storage

BLOB stands for **B**inary **L**arge **OB**ject

Sta-test-1:
- Blob1
  - test.txt
- Blob2
  - video.mov
  - picture.png
 
Data migration tools:
- AzCopy, Azure Storage Explorer, Azure Powershell
- No Cut/Paste option when using 
 
## Containers (folders) access level

Public access level:
- Private = Prohibit anonymous access to containers and blob
- Blob = Allow anonymous public read access for the blobs only
- Container = Allow anonymous public read **AND LIST** access to the entire container, including blobs

## Blob access tiers

| Hot | Cool | Cold | Archive |
|----| ----| ---- | ---- |
| Immediate access | 30 days backup | 90 days backup | 180 days backup |
| milliseconds | milliseconds | milliseconds | hours in latency |

## Blob lifecycle management rules

Used to transition data to the appropriate access tier or to delete the blob after a certain period of time.

Ex: If blob created 6 months ago, then move blob to cold storage

## Blob object replication

Asynchronously replicate blobs in another STA. Target STA can be in another region. 
- Object replication applies to all tier
- Blob versioning must be enabled in both STA
- Replication does not support snapshots

## Manage blobs

- Block blobs (classic)
- Append blobs (append operations like logging)
- Page blobs  (max 8TB in size, used for VM disks read/write operations)

Blob upload tools:
- | Azure Portal | Azure Storage Explorer | AzCopy | Azure Data Box Disk (transfer data from on-premise to Blob storage)

## Blob storage pricing

Following parameters impact STA pricing:
- Performance (Standard / Premium)
- Data access (Hot / Cool tier)
- Transaction costs
- Geo-replication
- Outbound data transfer
- Access tier modification (Cool to Hot tier)

# III. Configure Azure Files

# IV. Configure Azure Storage Security

# V. NSG and service endpoints applied to Storage Accounts (*TO BE COMPLETED*)

Network Security Group
: network ip firewall rules

Service tags
: Alias to identify Azure services in NSG (ex: Virtual network or Storage account). Service tag represents Azure Storage services IP range

App Security Group
: Resources rejoining in a virtual network no matter the IP addresses used in NSG

Exercise:
- PaaS service endpoints
- Create NSG & ASG using Azure CLI

