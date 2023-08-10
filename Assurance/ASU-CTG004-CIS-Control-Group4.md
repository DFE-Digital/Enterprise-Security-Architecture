# CIS Control 4

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |

## Control 4.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Establish and Maintain a Secure Configuration Process|

Establish and maintain a secure configuration process for enterprise assets (end-user devices, including portable and mobile, non-computing/IoT devices, and servers) and software (operating systems and applications). Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

## Control 4.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |EEstablish and Maintain a Secure Configuration Process for Network Infrastructure|

Establish and maintain a secure configuration process for network devices. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

## Control 4.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Configure Automatic Session Locking on Enterprise Assets|

Configure automatic session locking on enterprise assets after a defined period of inactivity. For general purpose operating systems, the period must not exceed 15 minutes. For mobile end-user devices, the period must not exceed 2 minutes.

## Control 4.4

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Implement and Manage a Firewall on Servers|

Implement and manage a firewall on servers, where supported. Example implementations include a virtual firewall, operating system firewall, or a third-party firewall agent.

## Control 4.5

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Implement and Manage a Firewall on End-User Devices|

Implement and manage a host-based firewall or port-filtering tool on end-user devices, with a default-deny rule that drops all traffic except those services and ports that are explicitly allowed.

## Control 4.6

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Securely Manage Enterprise Assets and Software|

Securely manage enterprise assets and software. Example implementations include managing configuration through version-controlled-infrastructure-as-code and accessing administrative interfaces over secure network protocols, such as Secure Shell (SSH) and Hypertext Transfer Protocol Secure (HTTPS). Do not use insecure management protocols, such as Telnet (Teletype Network) and HTTP, unless operationally essential.

## Control 4.7

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Manage Default Accounts on Enterprise Assets and Software|

Manage default accounts on enterprise assets and software, such as root, administrator, and other pre-configured vendor accounts. Example implementations can include: disabling default accounts or making them unusable.