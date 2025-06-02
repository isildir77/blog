---
title: "Azure Applied Skills - Storage Account"
categories: ["Azure Learning"]
date: 2025-05-07
---

This article resume the content of [Microsoft Applied Skills : Secure storage for Azure Files and Azure Blob Storage](https://learn.microsoft.com/en-us/training/paths/implement-storage-azure-files-azure-blob-storage/)

# Configure Azure Storage Account

Azure Storage groups one ore more of the following services:
- | Blob | Files | Queues | Tables |

ex: sta-test-1 can have 2 blob, 1 files and 1 table

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
- | Azure CLI | Azure Portal | Azure Powershell | SDK |

# Configure Azure Blob Storage

# Configure Azure Files

# Configure Azure Storage Security

# NSG and service endpoints applied to Storage Accounts
