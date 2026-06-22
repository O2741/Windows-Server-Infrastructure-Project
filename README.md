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

* **DNS Delegation Note:** During the DNS setup, you may encounter a warning regarding "DNS delegation." 
  * **What it does:** It informs you that the parent zone cannot be automatically found or delegated.
  * **Why it is not an issue:** In an isolated virtual machine environment (a lab), this is expected behavior. It only matters if you were integrating this DNS server with an existing, large-scale enterprise DNS infrastructure. For our `lab.local` domain, no further action is required, and this warning does not affect the functionality of the domain controller.
![Check Before](images/checkbeforeinstallation.png)

* **Deployment Configuration:** We selected "Add a new forest" and defined the root domain as `lab.local`.
    * **What it does:** Creates the primary container (forest) and defines the DNS namespace for the entire network.
    * **Why it is necessary:** This establishes the root of the identity hierarchy, ensuring all network resources can be uniquely identified via FQDN.
![New Forest](images/addnewforest.png)

* **Verification of Installation:** After successfully installing AD DS, the Active Directory tools become available in the Server Manager "Tools" menu.
![AD in Tools](images/activedirectoryintools.png)

* **DNS Management & Zone Configuration:**
    * **What it does:** DNS Manager handles "Forward Lookup Zones" to resolve device names to IP addresses.
    * **Why it is necessary:** DNS acts as the "phonebook" for AD DS. Without it, clients cannot locate the Domain Controller for authentication.
![DNS Setup](images/settingupdns.png)
![DNS Forwarder](images/dnsforward.png)

## 4. User Account Management
**Description:** We created an `IT_Service` Organizational Unit (OU) and provisioned a new user profile for "John Miller" within it.
* **What it does:** Organizes the directory structure and assigns a specific user identity to the IT department group.
* **Why it is necessary:** Enables granular access control and ensures that specific security policies are applied directly to the IT administrative group.
![Adding OU](images/addingorganisationalunit.png)
![Add User](images/addinguser.png)
![User Part 1](images/userpart1.png)
![User Part 2](images/userpart2.png)
![User Part 3](images/userpart3.png)
![User Added](images/useradded.png)

---
*This configuration establishes a secure, centralized, and manageable IT foundation.*
