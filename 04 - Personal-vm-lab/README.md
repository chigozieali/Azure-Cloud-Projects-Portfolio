# Project 4: Azure Blob Storage + File Upload Solution

**Goal**: Build a cost-optimized file storage and sharing solution using Azure Blob Storage with automatic tiering.

## Technologies Used
- Azure Storage Account
- Blob Containers (Hot, Cool, Archive)
- Lifecycle Management
- Blob Versioning & Soft Delete
- AzCopy

## Architecture Diagram
<img width="620" height="720" alt="Azure Load Balancer-2026-04-17-122514" src="https://github.com/user-attachments/assets/f577b575-6c3c-476d-9379-3f99c596b6f2" />

# Deployment Steps (How I Built It)

### 1. Created Storage Account
* Name: chigoziestorage2026
* Region: Canada Central
* Redundancy: LRS

### 2. Created Containers
* uploads, hot-files, archive

### 3. Uploaded Files
* Via Azure Portal
* Via AzCopy tool

### 4. Enabled Data Protection
* Blob Versioning
* Soft Delete (30 days)

### 5. Configured Lifecycle Management
* Auto-move files older than 30 days to Cool tier
* Auto-move files older than 90 days to Archive tier

# Challenges Encountered & Resolutions
**Issue:** Could not create Storage Account in some regions

**Resolution:** Switched to **Canada Central** region (same as App Service).

**Issue:** Lifecycle rule not applying immediately
**Resolution:** Understood that lifecycle rules run once per day (not real-time).

**Key Learning:** Storage tiers help significantly reduce long-term costs.

**Screenshots**

* Storage Account Overview
* Containers list
* Lifecycle Management rules
* AzCopy command execution
* Versioning & Soft Delete settings

**Key Learnings**

* Difference between Hot, Cool, and Archive tiers
* Importance of Lifecycle Management for cost optimization
* Data protection features (Versioning & Soft Delete)
* Using command-line tools (AzCopy)

**AZ-900 Skills Demonstrated**

* Azure Storage Services
* Storage Tiers & Lifecycle Policies
* Data Protection & Redundancy
* Cost Management & Governance


