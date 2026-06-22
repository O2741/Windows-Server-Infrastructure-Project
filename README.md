# Infrastructure Project: Windows Server Domain Controller Deployment

## Project Overview
This project serves as a foundational implementation of a Windows-based enterprise network environment. The primary objective is to build a centralized management system that allows administrators to control user identities, network resources, and security policies from a single point of authority. This type of infrastructure is the backbone of most corporate IT environments.

## Service and Configuration Notes
To build a reliable network, we utilized the following core configurations:
* **Domain (`lab.local`):** Acts as the logical "home" for all connected devices and users.
* **Active Directory Domain Services (AD DS):** The central database that stores information about all users and computers.
* **DNS (Domain Name System):** The service that allows computers to find each other by name rather than IP addresses.
* **Static IP Addressing:** Ensures the server is always reachable at a fixed location.

## Environment Setup & Installation

### 1. Operating System Installation
We began with a clean installation of Windows Server.
* **Why:** A fresh installation ensures no pre-existing software conflicts or security loopholes. It creates a stable, high-performance foundation.
![Installing OS](images/Installing_Windows_Server.png)

### 2. Static IP Configuration
The server was assigned a static IP address of `192.168.1.10`.
* **Why:** Services like a Domain Controller must be reliable. If the IP address were dynamic, it could change, causing clients to lose connection. A static IP ensures constant availability.
![Static IP](images/static_ip_configuration.png)

### 3. Deploying AD DS and DNS
Active Directory and DNS roles were installed to enable centralized management.
* **Why (AD DS):** This provides the framework for identity management (users, groups, and permissions).
![Installing AD](images/isntalling_ad_part_2.png)
* **Why (DNS):** AD DS requires DNS to map domain names to specific servers. Without it, clients cannot locate the Domain Controller.
![Setting up DNS](images/setting_up_dns.png)

### 4. User Account Management
We created a user profile for "John Miller" inside the `IT_Service` organizational unit.
* **Why (Organizational Units):** Grouping users into OUs allows for granular administrative delegation and specific policy application.
![User Step 1](images/userpart1.png)
* **Why (Password Security):** Enabling "User must change password at next logon" ensures that the user sets their own private credentials, preventing unauthorized access.
![User Step 2](images/userpart2.png)
![User Step 3](images/userpart3.png)
* **Verification:** The user is now correctly registered in the system.
![User Created](images/useradded.png)

***