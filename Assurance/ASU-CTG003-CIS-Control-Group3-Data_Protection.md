# CIS Control 3 - Data Protection

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
* [NCSC Cyber Assessment Framework (CAF) B2](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-2-identity-and-access-control)
* [NCSC Cyber Assessment Framework (CAF) B3](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-3-data-security)
* ISO27001:2022: A5.9, A5.10, A5.15, A5.33, A6.7, A8.1, A8.3, A8.4
* NIST 800-53: AC-3, AC-5, AC-6, AU-11, CM-12, MP-2, MP-6, PM-5, RA-2, SC-28, SI-12, SR-12

## Control 3.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Establish and Maintain a Data Management Process|

### The Control

Establish and maintain a data management process. In the process, address data sensitivity, data owner, handling of data, data retention limits, and disposal requirements, based on sensitivity and retention standards for the enterprise. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

### Why it is required

Mitigates risks associated with data misuse or mishandling.

### How it is achieved

* Assign an Information Asset Owner
* Assign an Information Asset Manager
* Register Information Assets on Information Asset Register (Managed by KIM team)
* Register Risks to Information Assets on Informantion Asset Risk Register
* Document your process(es) for Data Management

## Control 3.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Establish and Maintain a Data Inventory|

### The Control

Establish and maintain a data inventory, based on the enterprise’s data management process. Inventory sensitive data, at a minimum. Review and update inventory annually, at a minimum, with a priority on sensitive data.

### Why it is required

If assets are not inventorised, they cannot be properly managed.

### How it is achieved

* Review your documented process(es) for Data Management
* Check Information Asset Owner information
* Check Information Asset Manager information
* Verify data held on Register Information Assets on Information Asset Register (Managed by KIM team)
* Verify data held on Check Register Risks to Information Assets on Informantion Asset Risk Register


## Control 3.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Configure Data Access Control Lists|

### The Control

Configure data access control lists based on a user’s need to know. Apply data access control lists, also known as access permissions, to local and remote file systems, databases, and applications.

### Why it is required

Access should be granted on a least privilege/need to know basis.  Permissions should be the minimum required by the user or role carrying out the function.

Without appropriate access control, data mishandling or security breaches are more likely to occur.

### How it is achieved

* Use an appropriate role or identity for the information being accessed - see also identity guidelines and principles [link??](??)
* Review guidance and common standards for common components within the department
* Follow vendor best practice

## Control 3.4

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Enforce Data Retention|

### The Control

Retain data according to the enterprise’s data management process. Data retention must include both minimum and maximum timelines.

### Why it is required

The department has legal and regulatory responsibility to manage data assets appropriately.

### How it is achieved

>Link to guideline or process goes here if existing or planned
* Engagement with KIM team
* Engagement with DPO team
* Applying appropriate technical controls (i.e. retention policies within Sharepoint)

## Control 3.5

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Securely Dispose of Data|

### The Control

Securely dispose of data as outlined in the enterprise’s data management process. Ensure the disposal process and method are commensurate with the data sensitivity.

### Why it is required

To reduce the risk to the Department from data breaches.
[[NCSC Guidance on Secure Sanitisation of Storage Media](https://www.ncsc.gov.uk/guidance/secure-sanitisation-storage-media)

### How it is achieved

* Follow the Department's decommissioning process

## Control 3.6

| Asset Type | Security Function | Title| 
---| ---| ---|
|Data |Identify |Encrypt Data on End-User Devices|

### The Control

Encrypt data on end-user devices containing sensitive data. Example implementations can include: Windows BitLocker®, Apple FileVault®, Linux® dm-crypt.

### Why it is required

To reduce the risk to the Department from data breaches.  If a device is lost or stolen, sensitive data on end user devices can be recovered.

### How it is achieved

* Use approved, authorised end user devices using approved, secure encryption methods
* End-User Devices (EUD) (including BYOD) need to comply with acceptable use policies
