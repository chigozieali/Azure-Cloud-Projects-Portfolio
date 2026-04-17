# Project 5: Azure SQL Database – Managed Database Setup

**Goal**: Create a fully managed Azure SQL Database (PaaS), populate it with data, and connect securely from my laptop.

## Technologies Used
- Azure SQL Database (Serverless)
- SQL Server Firewall Rules
- Query Editor
- Azure Data Studio

## Architecture Diagram
<img width="620" height="720" alt="image" src="https://github.com/user-attachments/assets/9999f366-634b-4271-82d2-336ac3da8455" />

# Deployment Steps (How I Built It)

### 1. Created Azure SQL Database
* Server: chigozie-sqlserver2026
* Database: chigozie-sampledb
* Compute: Serverless (Free tier eligible)
* Region: Canada Central

### 2. Configured Firewall
* Added rule to allow my IP address
* Enabled "Allow Azure services"

### 3. Added Sample Data
* Used Query Editor in Azure Portal
* Created Employees table + inserted 3 records

### 4. Connected from Laptop
* Installed Azure Data Studio
* Connected using SQL authentication


## Challenges Encountered & Resolutions
**Issue:** Could not connect from Azure Data Studio

**Resolution:** Added my public IP in Firewall rules + enabled "Allow Azure services".

**Issue:** "Login failed" error
**Resolution:** Double-checked password and used correct server name (.database.windows.net).

**Key Learning:** Azure SQL Database is PaaS — Azure handles patching, backups, and high availability.

### Screenshots
* SQL Server + Database creation
  <img width="1398" height="985" alt="image" src="https://github.com/user-attachments/assets/05c6955e-7c29-4e2b-ac84-559a6e895e90" />
  <img width="1133" height="816" alt="image" src="https://github.com/user-attachments/assets/669e88e8-4190-427c-acd4-4fe7ae8c045a" />
* Firewall rules (with my IP)
  <img width="1141" height="750" alt="image" src="https://github.com/user-attachments/assets/99447cdc-942f-4521-aacd-8bc9f23ea6bc" />
* Query Editor showing Employees table
  <img width="1108" height="909" alt="image" src="https://github.com/user-attachments/assets/42e7110e-152b-4e33-9a5d-110e69e0a25e" />
* Azure Data Studio connected
* <img width="1289" height="966" alt="image" src="https://github.com/user-attachments/assets/0975a839-4e40-48ba-8ff2-871cd9e0ee96" />
* Successful query result
  <img width="1271" height="951" alt="image" src="https://github.com/user-attachments/assets/76892427-575b-40ea-a035-c9bf530b9006" />

### Key Learnings

* How PaaS databases work (less management than on-prem SQL)
* Importance of firewall rules for security
* Connecting external tools to cloud databases

### AZ-900 Skills Demonstrated

* Azure Databases (PaaS)
* Security (Firewall Rules)
* Data Management & Querying
* Connectivity & Troubleshooting
