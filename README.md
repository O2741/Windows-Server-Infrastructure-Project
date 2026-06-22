# Infrastructure Project: Windows Server Domain Controller Deployment

## Project Overview
This project serves as a foundational implementation of a Windows-based enterprise network, building a centralized system for user identity and security policy management.

---

## 1. Operating System Installation
**Description:** We began with a clean installation of Windows Server to ensure a stable, high-performance base.
* **What it does:** Sets up the core operating environment and kernel services.
* **Why it is necessary:** A fresh installation eliminates configuration drift, providing a predictable foundation for enterprise services.
![OS Setup](images/InstallingWindowsServer.png)
![OS Installed](images/fullyinstalledandloadedVMwithWindowsserver.png)

## 2. Static IP Configuration
**Description:** The server was manually configured with a static IP address.
* **What it does:** Assigns a fixed network address that does not change upon reboot.
* **Why it is necessary:** Servers must remain reachable at a consistent location; dynamic IPs would cause service disruptions for clients.
![Static IP Setup](images/staticipconfiguration.png)
![Verification](images/checkthesetup.png)

## 3. AD DS and DNS Deployment
**Description:** We installed the Active Directory Domain Services and DNS server roles.
* **What it does:** AD DS centralizes identity management, while DNS maps domain names to server IPs.
* **Why it is necessary:** DNS is the "phonebook" of the network; without it, clients cannot locate the Domain Controller for authentication.
![Installing AD](images/installingAD.png)
![AD Part 2](images/isntallingADpart2.png)
![AD Config](images/ActiveDirectoryDomainServicesConfigurationWizard.png)
![Check Before](images/checkbeforeinstallation.png)
![New Forest](images/addnewforest.png)
![AD in Tools](images/activedirectoryintools.png)
![DNS Setup](images/settingupdns.png)
![DNS Forwarder](images/dnsforward.png)

## 4. User Account Management
**Description:** Structured the directory environment and created a new user profile.
* **What it does:** Provisions organizational units and user identity objects.
* **Why it is necessary:** Enables granular access control and administrative delegation based on organizational roles.
![Adding OU](images/addingorganisationalunit.png)
![Add User](images/addinguser.png)
![User Part 1](images/userpart1.png)
![User Part 2](images/userpart2.png)
![User Part 3](images/userpart3.png)
![User Added](images/useradded.png)

---
*This configuration establishes a secure, centralized, and manageable IT foundation.*
