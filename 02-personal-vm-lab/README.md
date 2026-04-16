# Project 2: Secure Ubuntu VM Lab Environment

**Goal**: Deploy a secure Ubuntu Virtual Machine with proper networking and cost control.

## Technologies Used
- Azure Virtual Machine (Ubuntu 22.04)
- Network Security Group (NSG)
- SSH (port 22)
- Auto-shutdown
- Nginx Web Server

## What I Built
- Deployed Ubuntu VM (B2s size)
- Go to portal.azure.com
-In the search bar, type Virtual machines → Click + Create → Azure virtual machine
-Fill in the Basics tab:
-Resource group: Select your existing one (Azure-Projects-RG)
-Virtual machine name: chigozie-lab-vm (or my-cloud-lab)
-Region: Choose West Europe or North Europe (good speed from Nigeria)
-Availability options: No infrastructure redundancy (cheapest)
-Image: Choose one of these:
-Windows Server 2022 Datacenter (easier if you like Windows)
-or Ubuntu Server 22.04 LTS (recommended for cloud learning)

-Size: Choose a free-tier eligible size:
-Standard_B2s or Standard_B1s (2 vCPU, 4GB RAM is good)

-Administrator account:
-Username: azureuser (or your name)
-Password: Create a strong password (save it somewhere safe)

- Configured NSG to allow SSH only from my IP
- In the first screenshot, you are creating a new rule. Change it like this:
    
    Source: My IP (much safer than "Any")
    Source port ranges: *
    Destination: Any
    Service: Custom
    Destination port ranges: 22 ← Change from 8080 to 22
    Protocol: Any or TCP
    Action: Allow
    Priority: 110 (lower number = higher priority, put it before 1000 if possible)
    Name: Allow-SSH-MyIP
    Description: Allow SSH from my location only
    Then click Add.
- Installed Nginx web server
- Enabled Auto-shutdown to save costs

## Live Access
- Website: http://20.54.7.214 (Nginx default page)
- Connection: SSH on port 22

- ## Challenges Encountered & Resolutions

**Issue**: Nginx Welcome Page Not Loading on Public IP  
**Description**: Nginx was running correctly locally (`curl http://localhost` worked), but the site was not accessible from the browser.  

**Root Cause**: Port 80 (HTTP) was blocked by Azure Network Security Group.  

**Resolution**:
- Added Inbound NSG Rule for port 80 (Source: My IP, Action: Allow)
- Updated Ubuntu firewall with `sudo ufw allow 'Nginx Full'`

**Outcome**: Website became accessible successfully.

**Key Learning**: Always verify both Azure NSG rules and VM internal firewall when deploying internet-facing services.

## Screenshots
- VM Overview
- <img width="1072" height="763" alt="image" src="https://github.com/user-attachments/assets/a3771bd2-547c-4b45-9572-b792d4dd1ce3" />

- NSG Inbound Rules (showing Allow-SSH-MyIP)
- <img width="1383" height="877" alt="image" src="https://github.com/user-attachments/assets/0bf6a492-5617-448b-90f9-ddbcfd16b2ac" />

- Browser showing Nginx page
- <img width="1635" height="756" alt="image" src="https://github.com/user-attachments/assets/23261264-15e5-49be-80d6-af42e853a451" />

- Terminal screenshot after SSH login
- <img width="758" height="263" alt="image" src="https://github.com/user-attachments/assets/a165e405-f63a-448a-a284-213b43477bbb" />

### Alternative: Simple Text / ASCII Diagram (if Mermaid doesn't work)

<img width="1634" height="3322" alt="Azure Load Balancer-2026-04-16-143043" src="https://github.com/user-attachments/assets/e078313a-d431-438e-9d15-83a1d8299522" />

## Key Learnings
- Difference between Windows (RDP) and Linux (SSH)
- Importance of restricting NSG rules to "My IP"
- Cost management in IaaS resources
- Basic Linux server administration

## AZ-900 / AZ-104 Skills
- Compute (Virtual Machines)
- Networking & Security (NSG)
- Governance & Cost Control



**Status**: Completed ✅ - April 2026
