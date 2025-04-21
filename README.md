<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>


# Deploying Active Directory in Azure

This lab demonstrates how to deploy and configure Active Directory Domain Services (AD DS) on a Windows Server virtual machine (DC-1), create domain users, promote the server as a domain controller, and join a client machine to the new domain.

---

## 🧰 Technologies Used

- Microsoft Azure (Virtual Machines, Networking)
- Windows Server 2022 (Domain Controller)
- Windows 10 Pro (Client)
- Active Directory Domain Services (AD DS)
- Remote Desktop

---

## 🎯 Lab Objectives

- Install and promote AD DS on a domain controller  
- Create Organizational Units (OUs) and administrative users  
- Add a Windows 10 client machine to the domain  
- Verify domain membership via Active Directory Users and Computers (ADUC)

---

## 🖥️ Domain Controller Setup

### 📥 Step 1: Add AD DS Role to DC-1

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/add-role.png?raw=true" width="80%"/>
</p>

Start by adding the **Active Directory Domain Services** role to the DC-1 virtual machine via Server Manager.

---

### 🌐 Step 2: Create a New Forest (mydomain.com)

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/domain.png?raw=true" width="80%"/>
</p>

Promote the server to a Domain Controller by setting up a new forest. In this lab, the domain used was `mydomain.com`.

---

### ⚙️ Step 3: Install and Configure AD DS

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/install.png?raw=true" width="80%"/>
</p>

The installation process completes and the system restarts. Once rebooted, log into DC-1 using the domain format: `mydomain.com\labuser`.

---

## 👤 Creating OUs and Admin Accounts

### 🗂 Step 4: Create _EMPLOYEES and _ADMINS OUs

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/creating-folders.png?raw=true" width="80%"/>
</p>

Using **Active Directory Users and Computers (ADUC)**, create two organizational units (OUs): `_EMPLOYEES` and `_ADMINS`.

---

### 👩‍💼 Step 5: Create a New Admin User (Jane Doe)

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/creating-admin.png?raw=true" width="80%"/>
</p>

Inside the `_ADMINS` OU, create a user named **Jane Doe** with the username `jane_admin` and password `Cyberlab123!`.

---

### 🛡 Step 6: Add Jane to Domain Admins Group

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/domain-admin.png?raw=true" width="80%"/>
</p>

Add `jane_admin` to the **Domain Admins** group to grant her full administrative privileges across the domain.

---

## 🖥️ Client Machine Domain Join

### 🔗 Step 7: Join Client-1 to the Domain

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/client-domain.png?raw=true" width="80%"/>
</p>

From **Client-1**, log in as the local admin (`labuser`) and join the system to `mydomain.com`. The computer will restart after joining.

---

### 📂 Step 8: Organize Client in ADUC

<p align="center">
  <img src="https://github.com/Herkamal/Deploying-Active-Directory/blob/main/Create-client.png?raw=true" width="80%"/>
</p>

Back on DC-1, confirm Client-1 appears in ADUC. Create a new OU called `_CLIENTS` and move the Client-1 object into it for proper organization.

---

## ✅ Lab Complete

At the end of this lab, you will have:

- Installed and configured AD DS  
- Promoted a Windows Server to a domain controller  
- Created domain users and groups  
- Joined a Windows client to the domain  
- Verified domain structure and organization using ADUC

This setup establishes a foundation for managing users, computers, and policies in a real-world Windows domain environment.

---
