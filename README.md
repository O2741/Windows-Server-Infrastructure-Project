# Infrastructure Project: Windows Server Domain Controller Deployment

## Project Overview
This project serves as a foundational implementation of a Windows-based enterprise network environment. The primary objective is to build a centralized management system that allows administrators to control user identities, network resources, and security policies from a single point of authority. This type of infrastructure is the backbone of most corporate IT environments.

## Infrastructure Strategy & Rationale
To build a professional, scalable, and secure environment, we implemented the following core components:

* **Static IP Addressing:** Unlike home networks, servers require a **static** address. 
  * *Purpose:* To ensure that network clients can reliably locate the server at the same address 24/7. Without a static IP, service disruptions would occur if the address changed.
* **Active Directory Domain Services (AD DS):** The central database for user identities.
  * *Purpose:* Establishes a "Single Source of Truth." This allows administrators to manage permissions and access policies across the entire network from one location.
* **DNS (Domain Name System):** The network's phonebook.
  * *Purpose:* AD DS relies entirely on DNS to function. When a client tries to log in, it queries the DNS to find the Domain Controller's location. Without DNS, authentication is impossible.
* **Organizational Units (OU):** Logical containers (e.g., `IT_Service`).
  * *Purpose:* Allows for granular administrative delegation and specific policy (GPO) application to groups of users.

---

## Environment Setup & Installation

### 1. Operating System Installation
We began with a clean installation of Windows Server.
* **Why:** A fresh OS installation ensures a stable, high-performance foundation, free from configuration drift or legacy software conflicts.
![Installing OS](images/InstallingWindowsServer.png)

### 2. Static IP Configuration
The server was assigned a static IP (`192.168.1.10`).
![Static IP Setup](images/staticipconfiguration.png)
![Network Properties](images/networkpropertiesadditional.png)

### 3. Deploying AD DS and DNS
Active Directory and DNS roles were installed to enable centralized management.
* **AD DS Installation:** Establishing the directory service for identity management.
![AD Init](images/isntallingadpart2.png)
![AD Progress](images/adprogressdetails.png)
![AD Finished](images/adfinishednotification.png)
* **DNS Configuration:** Mapping domain names to specific servers.
![DNS Tool](images/settingupdns.png)
![DNS Zone Config](images/dnszonesetup.png)

---

## User Management Workflow
We created a user profile for "John Miller" inside the `IT_Service` Organizational Unit (OU).

### Step 1: Adding a New User
Defining user identity to allow controlled access.
![User Part 1](images/userpart1.png)
![User Account Details](images/userdetailsinput.png)
![User Login Setup](images/userloginsetup.png)

### Step 2: Password Security
We enforced a "Change password at next logon" policy.
* **Why:** This ensures the administrator never knows the user's permanent password, maintaining security accountability.
![Password Policy](images/userpart2.png)
![Password Confirmation](images/passwordconfirmdialog.png)

### Step 3: Object Review & Verification
Reviewing and finalizing the user object within the directory.
![Review Setup](images/userpart3.png)
![Final Object Verification](images/objectreviewfinal.png)

### Step 4: Final Verification
Confirming the user is correctly registered in the `IT_Service` OU.
![User Created](images/useradded.png)
![OU Overview](images/ouitserviceview.png)
![Final Domain State](images/finaldomainstate.png)

---
*This setup provides a centralized, secure, and manageable IT foundation.*
