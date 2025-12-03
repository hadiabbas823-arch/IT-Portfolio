# 💻 IT & Cybersecurity Labs Portfolio

Hands-on IT and Cybersecurity labs for portfolio and resume.  
This repository demonstrates virtualization, Windows Server deployment, Active Directory, networking, and automation skills.

---
## 📌 Quick Overview

| Lab / Topic | Description |
|------------|-------------|
| Windows 10 VM Setup | Create a client VM for Active Directory, ticketing, and networking labs. |
| Kali Linux VM Setup | Deploy Kali Linux for penetration testing and cybersecurity exercises. |
| Windows Server 2025 Setup | Install Server 2025 as Domain Controller, DNS, DHCP, AD DS, and GPO labs. |
| Active Directory Full Deployment | Step-by-step AD lab: rename server, set static IP, install AD DS, create users, join clients, verify DHCP/DNS. |
| **Help Desk Ticketing System (Peppermint)** | **Cloud-hosted ticketing system using Docker; user roles, ticket lifecycle (open → in progress → resolved), and incident handling (phishing).** |

---

## 🛠️ Technologies / Tools Used

- VirtualBox 7.x (VM virtualization)  
- Windows 10 & Windows Server 2025  
- Kali Linux (prebuilt VM)  
- Active Directory, DNS, DHCP  
- PowerShell for bulk user automation  
- Networking: internal IPs, domain join, DHCP/DNS verification  
- **Linux (Ubuntu), Docker & Docker Compose**  
- **Peppermint Ticket System (Help Desk)**  
- **Cloud Hosting (Linode)**  
- Git & GitHub for version control  

---

## 📂 Table of Contents

- [Week 1: Windows 10 VM Setup](#week-1-windows-10-vm-setup-on-virtualbox)  
- [Week 1: Kali Linux VM Setup](#week-1-kali-linux-vm-setup-on-virtualbox)  
- [Week 1: Windows Server 2025 Setup](#week-1-windows-server-2025-setup-on-virtualbox)  
- [Active Directory Lab - Windows Server 2025 Full Deployment](#active-directory-lab---windows-server-2025-full-deployment)  
- [Week 2: Help Desk Ticketing System (Peppermint)](#week-2-help-desk-ticketing-system-peppermint)

---

## 🏆 Status / Badges

| Lab | Status |
|-----|--------|
| Windows 10 VM Setup | ✅ Completed |
| Kali Linux VM Setup | ✅ Completed |
| Windows Server 2025 Setup | ✅ Completed |
| Active Directory Full Deployment | ✅ Completed |
| **Help Desk Ticketing System (Peppermint)** | **✅ Completed** |


## ⚡ Notes

- Screenshots included for all major steps.  
- Use VirtualBox snapshots for safe rollbacks.  
- All filenames and folders are standardized for consistency.  
- Labs are reproducible with minimal setup (see each lab section for details).  

---

## 📎 Contact / Links

- GitHub: [hadiabbas823-arch](https://github.com/hadiabbas823-arch/IT-Portfolio)  
- Portfolio file (uploaded): `/mnt/data/README (1).md`  

---

## Week 1: Windows 10 VM Setup on VirtualBox

**Objective**  
Create a Windows 10 client VM for Active Directory, ticketing, and networking labs.

**System Configuration**

| Component       | Configuration |
|-----------------|---------------|
| Host OS         | Windows 11, 64-bit |
| Processor       | AMD Ryzen 7 8845HS (8 cores, 3.8 GHz) |
| RAM             | 16 GB (Allocated 4 GB to VM) |
| Disk            | 50 GB VDI (dynamic) |
| Virtualization  | VirtualBox 7.x |
| ISO             | Windows 10 64-bit Evaluation |

### Steps Completed

1. **Installed VirtualBox**  
   Verified installation using the dashboard.  
   ![VirtualBox Installed](Week1_Screenshots/VirtualBox_Installed.png)

2. **Created New VM**  
   - Name: `Win10-Lab`  
   - OS Type: Windows 10 (64-bit)  
   - RAM: 4 GB  
   - Disk: 50 GB  
   ![VM Config](Week1_Screenshots/Win10_VM_Config.png)

3. **Attached Windows 10 ISO**  
   Configured optical drive → mounted ISO file.

4. **Completed Installation**  
   Followed standard setup → Installed Windows 10 Pro.  
   ![Windows Setup](Week1_Screenshots/Win10_Setup_Screen.png)

**Observations**
- VM installation successful  
- 4 GB RAM is enough for client labs  
- Snapshots recommended for rollback points

**Next Steps**
- Install Windows updates  
- Create clean snapshot  
- Connect to Domain Controller in AD labs

**Files / Screenshots Included**
- `VirtualBox_Installed.png`  
- `Win10_VM_Config.png`  
- `Win10_ISO_Attached.png`  
- `Win10_Setup_Screen.png`  
- `Snapshot_CleanInstall.png`

---

## Week 1: Kali Linux VM Setup on VirtualBox

**Objective**  
Deploy a Kali Linux VM for penetration testing, network analysis, and cybersecurity labs.

**System Configuration**

| Component       | Configuration |
|-----------------|---------------|
| Host OS         | Windows 11 |
| RAM             | 16 GB (Allocated 8 GB) |
| Disk            | ~14 GB dynamic |
| Image           | Kali Linux VirtualBox Prebuilt VM |
| Virtualization  | VirtualBox 7.x |

### Steps Completed

1. **Downloaded Kali VM Image**  
   Downloaded pre-installed VirtualBox image from kali.org.  
   ![Kali VM Download](Week1_Screenshots/Kali_VM_Download.png)

2. **Imported VM**  
   Double-clicked OVA → VirtualBox imported automatically.  
   ![Kali VM Imported](Week1_Screenshots/Kali_VM_Imported.png)

3. **Updated Settings**  
   Increased memory to 8 GB for smoother performance.

4. **Booted VM**  
   Logged in using default credentials (`kali / kali`).  
   ![Kali Home Screen](Week1_Screenshots/Kali_Home_Screen.png)

**Observations**
- Fast installation due to prebuilt image  
- RAM upgrade improves tools performance  
- Ready for Nmap, Wireshark, password attacks, etc.

**Files / Screenshots Included**
- `Kali_VM_Download.png`  
- `Kali_VM_Imported.png`  
- `Kali_Home_Screen.png`

---

## Week 1: Windows Server 2025 Setup on VirtualBox

**Objective**  
Install Windows Server 2025 as a Domain Controller for Active Directory + GPO labs.

**System Configuration**

| Component       | Configuration |
|-----------------|---------------|
| Host OS         | Windows 11 |
| Processor       | AMD Ryzen 7 8845HS |
| RAM             | 4–6 GB allocated |
| Disk            | 60 GB dynamic |
| ISO             | Windows Server 2025 Standard Evaluation (Desktop Experience) |
| Virtualization  | VirtualBox 7.x |

### Steps Completed

1. **Created Server VM**  
   - Name: `WinServer-DC`  
   - OS Type: Windows 2022 (64-bit)  
   - RAM: 4–6 GB  
   - Disk: 60 GB  
 ![WinServer VM Config](WinServer_VM_Config.png)

2. **Attached Server ISO**  
   Mounted Server 2025 ISO via Storage settings.

3. **Installed Server 2025**  
   Selected Standard Evaluation (Desktop Experience) and completed install.  
![WinServer Setup Screen](WinServer_Setup_Screen.png)

**Snapshot**
![Snapshot Clean Install](Week1_Screenshots/Snapshot_CleanInstall_WinServer.png)

**Observations**
- Server boots and Server Manager loads successfully.  
- Desktop Experience simplifies AD/GPO admin.  
- 4–6 GB RAM adequate for lab usage.

**Next Steps**
- Rename server → `DC01`  
- Set static IP and DNS (127.0.0.1)  
- Install Active Directory Domain Services (AD DS)  
- Promote to Domain Controller (domain: `lab.local`)  
- Create OUs, Users, Groups  
- Apply GPOs: Disable USB, enforce password policy, set wallpaper

**Files / Screenshots Included**
- `WinServer_VM_Config.png`  
- `WinServer_Setup_Screen.png`  
- `Snapshot_CleanInstall_WinServer.png`

---

## Notes & Tips
- Use VirtualBox snapshots before major changes.  
- Keep filenames consistent and use subfolders per week (e.g., `Week1_Screenshots/`).  
- Crop & annotate screenshots for clarity when possible.

---

## Active Directory Lab - Windows Server 2025 Full Deployment


## Network Diagram

       ┌───────────────────────────┐
       │     Windows Server 2025    │
       │            DC01            │
       │  AD DS / DNS / DHCP        │
       │  Static IP: 10.0.0.10       │
       └──────────────┬────────────┘
                      │ Internal Network
       ┌──────────────┴────────────┐
       │      Windows 10 Client     │
       │          CLIENT1           │
       │  DHCP IP from DC           │
       │  Domain: MYDOMAIN.COM      │
       └────────────────────────────┘
**

---


---

---

## 1️⃣ Rename Server → DC  
![DC](Week1_Screenshots/DC.png)

---

## 2️⃣ Configure Static Internal IP  
![Internal IPv4](Week1_Screenshots/Internal%20ipv4.png)

---

## 3️⃣ Install Active Directory Domain Services (AD DS)
![AD DS](AD%20DS/AD_DS.png)

---

## 4️⃣ AD DS Installation Completed
![AD DS INSTALLED](Week1_Screenshots/AD%20DS%20INSTALLED.png) 

---

## 5️⃣ Domain Login (MYDOMAIN\Administrator)  
![mydomain](Week1_Screenshots/mydomain.png)

---

## 6️⃣ Create New Domain Admin Account  
![new domain account](Week1_Screenshots/new%20domain%20account.png)

---

## 7️⃣ Install DHCP Server  
![dhcp server installing](Week1_Screenshots/dhcp%20server%20installing.png)

---

## 8️⃣ DNS Server Installed  
![DNS SERVER](Week1_Screenshots/DNS%20SERVER.png)

---

## 9️⃣ Bulk User Creation (1000 Users via PowerShell ISE)  
![USER CREATION](Week1_Screenshots/USER%20CREATION.png)

---

## 🔟 Windows 10 Client Setup (CLIENT1 Installed)  
![client 1 win 10](Week1_Screenshots/client%201%20win%2010.png)

---

## 1️⃣1️⃣ Client Welcome Screen (After Domain Join)  
![Welcome](Week1_Screenshots/wELCOME%20TO%20MY%20DOMAIN.png)

---

## 1️⃣2️⃣ DHCP + DNS Verification  

### Check IP Configuration  
![ipconfig](Week1_Screenshots/I%20config.png)

### Ping Domain  
![ping domain](Week1_Screenshots/ping%20mydomain%20.com.png)

---

## 1️⃣3️⃣ Join CLIENT1 to MYDOMAIN.COM  
![CLIENT1](Week1_Screenshots/CLIENT1.png)

---

## 1️⃣4️⃣ DHCP Detects CLIENT1  
![dhcp server c1](Week1_Screenshots/dhcp%20server%20c1.png)

---

## 1️⃣5️⃣ AD Confirms CLIENT1 + User Login Success  
![ad c1](Week1_Screenshots/ad%20c1.png)  
![login using created user](Week1_Screenshots/logging%20in%20using%20created%20user.png)

---

# 🎉 Lab Completed — Skills Demonstrated

- Installed & configured **Windows Server 2025**
- Deployed **AD DS, DNS, DHCP**
- Created enterprise domain **MYDOMAIN.COM**
- Automated **1000 user accounts** (PowerShell)
- Joined Windows 10 client to domain
- Verified DHCP leases, DNS resolution, domain login
- Full enterprise-grade virtual environment

---

## Week 2: Help Desk Ticketing System (Peppermint)


## Overview
This lab demonstrates hands-on **Help Desk / MSP-style ticketing experience** using **Peppermint Ticket System** deployed on a **cloud-hosted Ubuntu server**.  
The project covers installation, configuration, user roles, and resolving real-world IT support tickets.

Key skills demonstrated:
- Linux system administration
- Docker & Docker Compose
- Cloud hosting (Linode)
- Help Desk ticket lifecycle (Open → In Progress → Resolved)
- Role-based access control
- Incident response (phishing)

---

## 🛠️ Technologies Used
- Ubuntu (Cloud VM)
- Docker & Docker Compose
- Peppermint Ticket System
- PostgreSQL
- Windows Subsystem for Linux (WSL)
- Web-based admin & technician workflows

---

## 1️⃣ Environment Setup (WSL + Linux)

### Install WSL and Ubuntu on Windows
Used WSL to manage Linux commands locally before deploying to the cloud.

📸 Screenshot: WSL Installation  
![WSL Install](Week2_Screenshots/WSL_Install.png)

---

## 2️⃣ Cloud Server Deployment (Linode)

### Create Ubuntu Server
Provisioned an Ubuntu VM using Linode Marketplace.

📸 Linode Ubuntu Selection  
![Linode Image](Week2_Screenshots/Linode_Ubuntu_Image_Plan_Selection.png)

📸 Linode App Installation  
![Linode Install](Week2_Screenshots/Linode_Installing.png)

📸 Weblish Console Login  
![Weblish Login](Week2_Screenshots/Weblish_Login.png)

---

## 3️⃣ Deploy Peppermint with Docker

### Docker Compose Configuration
Configured Peppermint and PostgreSQL containers.

📸 Docker Compose File  
![Docker Compose](Week2_Screenshots/Docker_Compose-d.png)

📸 Pasting Peppermint Code  
![Peppermint Install](Week2_Screenshots/Pasting_Peppermint_Code.png)

✅ Containers running successfully.


---

## 4️⃣ Access Peppermint Web Interface

Accessed Peppermint through the public IP.

- URL: `http://<SERVER-IP>:3000`

📸 Login Page  
![Peppermint Login](Week2_Screenshots/Peppermint_Login_Page.png)

📸 Admin Logged In  
![Peppermint Logged In](Week2_Screenshots/Peppermint_Logged_in.png)

---

## 5️⃣ User & Role Management

### Internal Users Created
Created Admin and Tier 1 technician users.

📸 User List  
![Users](Week2_Screenshots/Peppermint_User_Role_Assignments.png)

Users:
- Admin
- Michael Tech (Tier 1)
- Sara Helpdesk
- John Smith
- Alex Martinez

---

### Custom Technician Role
Created **TECHNICIAN (Help Desk Tier 1)** role with scoped permissions.

📸 Role Permissions  
![Technician Role](Week2_Screenshots/TECHNICIAN_Role.png)

---

## 6️⃣ Ticket Lifecycle Demonstrations

Each ticket follows:
**Open → In Progress → Resolved**

---

### 🎫 Ticket 1 – Printer Not Connecting (Michael Tech)

📸 Ticket Created  
![Ticket1](Week2_Screenshots/Ticket1.png)

📸 In Progress  
![Ticket1 In Progress](Week2_Screenshots/Ticket1_InProgress.png)

✅ Resolution:
- Restarted print spooler
- Cleared queue
- Reinstalled printer driver

📸 Resolved  
![Ticket1 Resolved](Week2_Screenshots/Ticket1_Resolved.png)

---

### 🎫 Ticket 2 – Cannot Login to Domain (Sara Helpdesk)

📸 Ticket Created  
![Ticket2](Week2_Screenshots/Ticket2.png)

📸 In Progress  
![Ticket2 In Progress](Week2_Screenshots/Ticket2_InProgress.png)

✅ Resolution:
- Verified user identity
- Found account lockout
- Reset password and issued temporary credentials

📸 Resolved  
![Ticket2 Resolved](Week2_Screenshots/Ticket2_Resolved.png)

---

### 🎫 Ticket 3 – Outlook Not Syncing (John Smith)

📸 Ticket Created  
![Ticket3](Week2_Screenshots/Ticket3.png)

📸 In Progress  
![Ticket3 In Progress](Week2_Screenshots/Ticket3_InProgress.png)

✅ Resolution:
- Repaired Outlook profile
- Restarted Cached Exchange Mode
- Verified Send/Receive

📸 Resolved  
![Ticket3 Resolved](Week2_Screenshots/Ticket3_Resolved.png)

---

### 🎫 Ticket 4 – Network Connectivity Issue (Alex Martinez)

📸 Ticket Created  
![Ticket4](Week2_Screenshots/Ticket4.png)

📸 In Progress  
![Ticket4 In Progress](Week2_Screenshots/Ticket4_InProgress.png)

✅ Resolution:
- Identified DHCP issue
- Renewed IP configuration
- Reset network adapter

📸 Resolved  
![Ticket4 Resolved](Week2_Screenshots/Ticket4_Resolved.png)

---

### 🎫 Ticket 5 – Phishing Email Report (Michael Tech)

📸 Ticket Created  
![Ticket5](Week2_Screenshots/Ticket5.png)

📸 In Progress  
![Ticket5 In Progress](Week2_Screenshots/Ticket5_InProgress.png)

✅ Resolution:
- Reviewed headers and URL
- Confirmed phishing attempt
- Blocked sender domain
- Reported to security team
- Educated user

📸 Resolved  
![Ticket5 Resolved](Week2_Screenshots/Ticket5_Resolved.png)

---

## ✅ Final Status

📸 All Issues Resolved  
![All Resolved](Week2_Screenshots/All_Issues_Succesfully_Closed.png)

📸 Dashboard Overview  
![Dashboard](Week2_Screenshots/dashboard.png)

---

## 📌 Skills Demonstrated
- Tier 1 Help Desk workflows
- Ticket escalation and resolution
- Cloud-hosted ticketing systems
- Linux + Docker administration
- Security incident handling (phishing)

---

## 🏁 Conclusion
This lab simulates a **real MSP / IT Help Desk environment**, demonstrating technical troubleshooting, ticket ownership, and professional documentation.  
All actions are supported with screenshots and role-based workflows.


## Contact / Links
- GitHub: `https://github.com/hadiabbas823-arch/IT-Portfolio`  
- Portfolio file (uploaded): `/mnt/data/README (1).md`
