# 🖥️ Active Directory Lab in Oracle VirtualBox

This lab was built using **Oracle VirtualBox**, simulating a basic Windows domain with **Active Directory**. This has been great for me for practicing Windows Server administration, domain control, and PowerShell automation. This setup is a simplified version of what you would find in your work or school, where you can take your one username and password and log into multiple desktops with it.

Coming soon...
📺 - [Showcase of an Active Directory Lab in Oracle VirtualBox](https://www.youtube.com)
---

### 💡 Components:

- **DC (Server19):**  
  - Windows Server 2019  
  - Roles: Active Directory Domain Services (AD DS), DNS, DHCP, and NAT (RRAS)  
  - Dual NICs:  
    - NIC 1: Connected to home network via NAT (DHCP from router)  
    - NIC 2: Internal Network (static IP: `172.16.0.1`)

- **Client1 (Win10):**  
  - Windows 10 VM  
  - Single NIC on Internal Network  
  - Gets IP and DNS from Server via DHCP

---

## 🌐 Network Configuration

| Component         | IP Address       | Role                         | Notes                      |
|------------------|------------------|------------------------------|----------------------------|
| DC (Internal NIC) | `172.16.0.1`     | DHCP, DNS, AD DS             | Gateway for Client         |
| DC (Internet NIC) | DHCP from router | External internet access     | Uses NAT via RRAS          |
| Client1           | `172.16.0.x`     | Domain-joined client (DHCP)  | Receives IP from DC        |

### 🧾 DHCP Scope (configured on DC):

- **Range:** `172.16.0.100` – `172.16.0.200`  
- **Subnet Mask:** `255.255.255.0`  
- **Gateway:** `172.16.0.1`  
- **DNS:** `172.16.0.1`

---

## 🔧 Technologies Used

- Oracle VirtualBox
- Windows Server 2019
- Windows 10
- PowerShell
- Active Directory Domain Services (AD DS)
- DNS, DHCP
- Routing and Remote Access Service (RRAS)

---

## 📷 Screenshots

| Description            | Preview |
|------------------------|---------|
| Domain Join Success    | ![](screenshots/login_success.png) |
| GPO Applied to Client  | ![](screenshots/group_policy_example.png) |

---
