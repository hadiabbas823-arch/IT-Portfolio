# IT-Portfolio
Hands-on IT/cybersecurity labs for portfolio and resume.
# Week 1: Windows 10 VM Setup on VirtualBox

## Objective
Set up a Windows 10 virtual machine on Oracle VirtualBox to serve as a client machine for hands-on IT labs, including Active Directory and ticketing simulations. This environment allows practicing core IT skills safely without affecting the host system.

---

## System Configuration (Host & VM)

| Component       | Configuration                       |
|-----------------|------------------------------------|
| Host OS         | Windows 11, 64-bit                 |
| Processor       | AMD Ryzen 7 8845HS (3.8 GHz, 8 cores) |
| RAM             | 16 GB (Allocated 4 GB for VM)      |
| Disk            | 50 GB dynamically allocated        |
| Virtualization  | Oracle VirtualBox 7.x              |
| ISO             | Windows 10 64-bit Evaluation       |

---

## Steps Completed

1. **Installed VirtualBox**
   - Verified installation by opening the VirtualBox dashboard
   - **Screenshot:** `VirtualBox_Installed.png`

2. **Created New VM**
   - Name: `Win10-Lab`
   - Type: Microsoft Windows → Version: Windows 10 (64-bit)
   - RAM: 4096 MB
   - Virtual Hard Disk: 50 GB, VDI, dynamically allocated
   - **Screenshot:** `Win10_VM_Config.png`

3. **Attached Windows 10 ISO**
   - Storage → Optical Drive → Selected ISO
   - **Screenshot:** `Win10_ISO_Attached.png`

4. **Started VM and Began Installation**
   - Followed Windows setup prompts (language, region, keyboard, etc.)
   - Installed Windows Pro for lab compatibility
   - **Screenshot:** `Win10_Setup_Screen.png`

---

## Observations
- VM boots successfully; installation runs without errors.
- 4 GB RAM and 50 GB disk sufficient for lab exercises.
- VirtualBox snapshots can be created to preserve clean baseline.

---

## Next Steps
1. Complete Windows installation and updates.
2. Take a snapshot of the clean install (`Snapshot_CleanInstall.png`).
3. Begin Week 1 lab exercises:
   - Active Directory client simulation
   - Ticketing system setup

---

## Files / Screenshots Included
- `VirtualBox_Installed.png`
- `Win10_VM_Config.png`
- `Win10_ISO_Attached.png`
- `Win10_Setup_Screen.png`
- `Snapshot_CleanInstall.png` (after installation)

---


