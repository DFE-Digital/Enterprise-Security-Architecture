# CIS Control 4 - Secure Configuration of Enterprise Assets and Software

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |

## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* [NCSC Cyber Assessment Framework (CAF) B1](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-1-service-protection-policies-and-processes)
* [NCSC Cyber Assessment Framework (CAF) B4](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-4-system-security)
* ISO27001:2022: A6.7, A8.1, A8.2, A8.5, A8.9
* NIST 800-53: CM-1, CM-2, CM-6, CM-7, CM-9, SA-3, SA-8, SA-10, AC-18, AC-2, AC-11, AC-12, CA-9, SC-7, MA-4, IA-5


## Control 4.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Establish and Maintain a Secure Configuration Process|

### The Control

Establish and maintain a secure configuration process for enterprise assets (end-user devices, including portable and mobile, non-computing/IoT devices, and servers) and software (operating systems and applications). Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

### Why it is required

* Reduces the attack surface presented to mailcious users or attackers
* Makes it more difficult for malicious actors to exploit vulnerabilities

### How it is achieved

* [Identify all enterprise assets](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG001-CIS-Control-Group1.md#cis-control-1---inventory-and-control-of-enterprise-assets)
* [Identify all enterprise software](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG002-CIS-Control-Group2.md#cis-control-2---inventory-and-control-of-software-assets)
* Establish baseline configuration for assets
*    Center for Internet Security provides suitable baselines that can be used or adapted
*    Vendor Security baselines may be used or adapted
*    Scan Infrastructure as code templates for vulnerabilities or bad practices
* Apply controls based on baselines
* Regularly review baselines and controls to ensure they remain effective
* Follow change management process to ensure CMDB is kept up to date

## Control 4.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Establish and Maintain a Secure Configuration Process for Network Infrastructure|

### The Control

Establish and maintain a secure configuration process for network devices. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

### Why it is required

* Reduces the attack surface presented to mailcious users or attackers
* Makes it more difficult for malicious actors to exploit vulnerabilities

### How it is achieved

* [Identify all enterprise assets](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG001-CIS-Control-Group1.md#cis-control-1---inventory-and-control-of-enterprise-assets)
* [Identify all enterprise software](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG002-CIS-Control-Group2.md#cis-control-2---inventory-and-control-of-software-assets)
* Establish baseline configuration for assets
*    Center for Internet Security provides suitable baselines that can be used or adapted
*    Vendor Security baselines may be used or adapted
*    Scan Infrastructure as code templates for vulnerabilities or bad practices
* Apply controls based on baselines
* Regularly review baselines and controls to ensure they remain effective
* Follow change management process to ensure CMDB is kept up to date

## Control 4.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Configure Automatic Session Locking on Enterprise Assets|

### The Control

Configure automatic session locking on enterprise assets after a defined period of inactivity. For general purpose operating systems, the period must not exceed 15 minutes. For mobile end-user devices, the period must not exceed 2 minutes.

### Why it is required

* Helps to prevent unauthorised access to information assets

### How it is achieved

* Configuration of Operating Systems, Mobile device or application to enable automatic session locking
* Set an appropriate timeout
* Configure the system to require authentication before unlocking
* Test the automatic session locking to ensure it is working correctly
* Educate users on the importance of locking sessions when devices are left unattended

## Control 4.4

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Implement and Manage a Firewall on Servers|

### The Control

Implement and manage a firewall on servers, where supported. Example implementations include a virtual firewall, operating system firewall, or a third-party firewall agent.

### Why it is required

* Reduces the attack surface presented to mailcious users or attackers
* Makes it more difficult for malicious actors to exploit vulnerabilities
* Makes it easier to monitor for malicious activity

### How it is achieved

* [Firewall Rules Guidelines](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-SEC002-Firewall-Policies-and-

## Control 4.5

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Implement and Manage a Firewall on End-User Devices|

### The Control

Implement and manage a host-based firewall or port-filtering tool on end-user devices, with a default-deny rule that drops all traffic except those services and ports that are explicitly allowed.

### Why it is required

* Reduces the attack surface presented to mailcious users or attackers
* Makes it more difficult for malicious actors to exploit vulnerabilities
* Makes it easier to monitor for malicious activity

### How it is achieved

* [Firewall Rules Guidelines](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-SEC002-Firewall-Policies-and-Access.md#firewall-rules-guidelines)

## Control 4.6

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Securely Manage Enterprise Assets and Software|

### The Control

Securely manage enterprise assets and software. Example implementations include managing configuration through version-controlled-infrastructure-as-code and accessing administrative interfaces over secure network protocols, such as Secure Shell (SSH) and Hypertext Transfer Protocol Secure (HTTPS). Do not use insecure management protocols, such as Telnet (Teletype Network) and HTTP, unless operationally essential.

### Why it is required

* Use of insecure management protocols may be intercepted or modified by malicious actors

### How it is achieved

>Link to guideline or process goes here if existing or planned

## Control 4.7

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Manage Default Accounts on Enterprise Assets and Software|

### The Control

Manage default accounts on enterprise assets and software, such as root, administrator, and other pre-configured vendor accounts. Example implementations can include: disabling default accounts or making them unusable.

### Why it is required

* Well known accounts are typically targetted by malicious actors
* Default accounts may be configured with well-known default passwords

### How it is achieved

* Disable, Change or rename default accounts
* Change default passwords to strong passwords
* Scan Infrastructure and Code configurations for known weaknesses or vulnerabilities
* [Identity Guidleine](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-IDE001-Authentication-principles.md#identity-guidelines)
