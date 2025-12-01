# IT-Portfolio
Hands-on IT & Cybersecurity labs for portfolio and resume.



---

## Table of Contents
- [Week 1: Windows 10 VM Setup on VirtualBox](#week-1-windows-10-vm-setup-on-virtualbox)
- [Week 1: Kali Linux VM Setup on VirtualBox](#week-1-kali-linux-vm-setup-on-virtualbox)
- [Week 1: Windows Server 2025 Setup on VirtualBox](#week-1-windows-server-2025-setup-on-virtualbox)
- [Active Directory Lab — Windows Server 2025 (Full Deployment)](#active-directory-lab-windows-server-2025-full-deployment)



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

# Active Directory Lab — Windows Server 2025 (Full Deployment)

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



## Contact / Links
- GitHub: `https://github.com/hadiabbas823-arch/IT-Portfolio`  
- Portfolio file (uploaded): `/mnt/data/README (1).md`
