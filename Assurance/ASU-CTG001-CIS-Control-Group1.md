# CIS Control 1 - Inventory and Control of Enterprise Assets

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |


## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* [NCSC Cyber Assessment Framework (CAF) A3](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/a-3-asset-management)
* ISO27001:2022: A5.9, A8.8
* NIST 800-53 CA-7: Continuous Monitoring, CM-8: Information System Component Inventory, IA-3: Device Identification and Authentication, SA-4: Acquisition Process, SC-17: Public Key Infrastructure Certificates, SI-4: Information System Monitoring, PM-5: Information System Inventory
* ITIL 2011 KPIs: Information Security Management
* ICO Protecting Data: Inappropriate locations for processing data

## Control 1.1

| Asset Type | Security Function | Title| 
---| ---| ---|
| Devices | Identify | Establish and Maintain Detailed Enterprise Asset Inventory

### The Control

Establish and maintain an accurate, detailed, and up-to-date inventory of all enterprise assets with the potential to store or process data, to include: end-user devices (including portable and mobile), network devices, non-computing/IoT devices, and servers.

Ensure the inventory records the network address (if static), hardware address, machine name, enterprise asset owner, department for each asset, and whether the asset has been approved to connect to the network. For mobile end-user devices, MDM type tools can support this process, where appropriate.

This inventory includes assets connected to the infrastructure physically, virtually, remotely, and those within cloud environments. Additionally, it includes assets that are regularly connected to the enterprise’s network infrastructure, even if they are not under control of the enterprise. Review and update the inventory of all enterprise assets bi-annually, or more frequently.

### Why it is required

This is the key control which must be implemented fully to ensure that assets on the IT estate are known and well managed. 

The Department's level of risk will be increased if assets are not known (This is sometimes known as 'shadow IT' or 'grey IT').

Operations and security teams cannot support and secure the full estate if they do not have visibility of all assets.

A service cannot properly plan for Business Continuity and Disaster Recovery (BC/DR) if it does not know its assets.

Please also see: [NCSC Asset Management Guidance](https://www.ncsc.gov.uk/guidance/asset-management)

### How it is achieved

The outcome required is for all devices to be captured and maintained within a central repository. The method of achieving this is different depending on the type of device and should be aligned with processes and ways of working to ensure that it is easily achieved and managed. 

Service owners and delivery teams will be expected to select the optimal method to update and maintain their devices and demonstrate evidence of this.

* The Configuration Management Database (CMDB) is the master repository for all devices wihtin the Department.
* Software Bill Of Materials (SBOM) can be created and maintained as part of standard CI/CD processes to maintain the up-to-date view of software components and configuration for a service
* CMDB can be updated programatically within a CI/CD pipeline to update and manage components as they're deployed and updated
* Device information can be gathered directly from the master source for the relevant information
  * Network Management
  * Device Management
  * Cloud platforms

![CMDB hierarchy and integration](../Assurance/Images/ASU-CTG001-CMDB-Hierarchy.png)

*Compliance for this control is met when 100% of a services' assets are captured and maintained. Less than 100% of all assets will result in non-compliance with this control*

### Who will do this activity

* Accountability within the department ultimately rests with the Permanent Secretary 
* Accountable role: Service Owner (Senior Responsible Owner if not Service Owner)
* Responsible roles: Business Analyst, Technical Architects, Security Architect, Security Risk Management
* Other supporting roles: Delivery Manager, Product Manager, DevOps, Security Architect

## Control 1.2

| Asset Type | Security Function | Title| 
---| ---| ---|
| Devices |Respond |Address Unauthorized Assets |

### The Control
Ensure that a process exists to address unauthorized assets on a weekly basis. The enterprise may choose to remove the asset from the network, deny the asset from connecting remotely to the network, or quarantine the asset.

### Why it is required

Keep an updated record of what's on the estate and remove stuff which shouldn't be there. Helps to highlight unauthorised stuff etc.

This helps to reduce the attack surface presented to malicious actors.  If something is switched off, it can't be attacked.

### How it is achieved

*TBC at present for an enterprise-wide approach, no consistent way of doing this, onus on the services keeping their records up to date*
