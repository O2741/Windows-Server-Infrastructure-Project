# Infrastructure Project: Windows Server Domain Controller Deployment

## Project Overview
This project serves as a foundational implementation of a Windows-based enterprise network, building a centralized system for user identity and security policy management.

---

## 1. Operating System Installation
**Description:** We began with a clean installation of Windows Server to ensure a stable, high-performance base.
* **What it does:** Sets up the core operating environment and kernel services.
* **Why it is necessary:** A fresh installation eliminates configuration drift and security loopholes, providing a predictable foundation for enterprise services.
![Installing OS](images/InstallingWindowsServer.png)

## 2. Static IP Configuration
**Description:** The server was manually configured with a static IP address of `192.168.1.10`.
* **What it does:** Assigns a fixed network address that does not change upon reboot.
* **Why it is necessary:** Servers must remain reachable at a consistent location; dynamic IPs would cause service disruptions for clients relying on the Domain Controller.
![Static IP Setup](images/staticipconfiguration.png)
![Network Properties](images/network_properties_additional.png)

## 3. AD DS and DNS Deployment
**Description:** We installed the Active Directory Domain Services and DNS server roles.
* **What it does:** AD DS centralizes identity management, while DNS maps domain names to server IPs.
* **Why it is necessary:** DNS is the "phonebook" of the network; without it, clients cannot locate the Domain Controller for authentication.
![AD Init](images/isntallingadpart2.png)
![AD Progress](images/ad_progress_details.png)
![AD Finished](images/ad_finished_notification.png)
![DNS Tool](images/settingupdns.png)
![DNS Zone Config](images/dns_zone_setup.png)

## 4. Firewall and Security Logging
**Description:** Adjusted firewall policies to permit network traffic for auditing purposes.
* **What it does:** Opens necessary ports to allow network probes and Nmap scans to reach the host.
* **Why it is necessary:** Allows Sysmon to capture and generate Event ID 3 (Network Connection) logs, which are vital for security monitoring.
![Firewall Config](images/firewall_adjustment.png)

## 5. User Account Creation
**Description:** Created a new user profile for "John Miller" within the `IT_Service` Organizational Unit.
* **What it does:** Provisions a new identity object in the directory database.
* **Why it is necessary:** Enables granular access control and administrative delegation based on organizational roles.
![User Part 1](images/userpart1.png)
![User Account Details](images/user_details_input.png)
![User Login Setup](images/user_login_setup.png)

## 6. Password Security Policy
**Description:** Enforced the "User must change password at next logon" setting.
* **What it does:** Requires the user to define their own private credentials upon first access.
* **Why it is necessary:** Ensures the administrator never knows the user's password, maintaining account integrity and individual accountability.
![Password Policy](images/userpart2.png)
![Password Confirmation](images/password_confirm_dialog.png)

## 7. Verification and Final Review
**Description:** Final check of the user object and Organizational Unit structure.
* **What it does:** Validates that the user is correctly registered and subject to group policies.
* **Why it is necessary:** Confirms the infrastructure is correctly configured and ready for production use.
![Review Setup](images/userpart3.png)
![Final Object Verification](images/object_review_final.png)
![User Created](images/useradded.png)
![OU Overview](images/ou_it_service_view.png)
![Final Domain State](images/final_domain_state.png)

---
*This configuration establishes a secure, centralized, and manageable IT foundation.*
