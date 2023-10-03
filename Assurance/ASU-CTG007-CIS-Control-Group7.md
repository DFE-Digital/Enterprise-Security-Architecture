# CIS Control 7 - Continuous Vulnerability Management

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
* ISO27001:2022: A8.8
* NIST 800-53: RA-5, RA-7, SI-2

## Control 7.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Establish and Maintain a Vulnerability Management Process|

### The Control

Establish and maintain a documented vulnerability management process for enterprise assets. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

### Why it is required

* [NCSC Guidance - 10 Steps to Cyber Security - Vulnerability Management](https://www.ncsc.gov.uk/collection/10-steps/vulnerability-management)
* Vulnerabilities in software, hardware and/or configuration can put systems at risk of exploit from malicious actors
* Good management of vulnerabilities will help the Department to maintain a strong security posture

### How it is achieved

* Build security into the design of your system or service
* Know your assets
    * [CIS Control 1 - Inventory and Control of Enterprise Assets](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG001-CIS-Control-Group1.md)
    * [CIS Control 2 - Inventory and Control of Software Assets](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Assurance/ASU-CTG002-CIS-Control-Group2.md)
* Scan assets regularly for vulnerabilities preferably using automated tools
* Prioritise addressing vulnerabilities based on severity and impact to the Department's mission/objectives

## Control 7.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Respond |Establish and Maintain a Remediation Process|

### The Control

Establish and maintain a risk-based remediation strategy documented in a remediation process, with monthly, or more frequent, reviews.

### Why it is required

* New vulnerabilities can be discovered anywhere and at any time within the lifecycle of a project, programme or service
* Without a regular process to address vulnerabilities the Department can become exposed to increased risk

### How it is achieved

* Follow the Department's assurance model
* [Intranet - Assurance Remediation Plan](https://educationgovuk.sharepoint.com/sites/security/SitePages/assurance.aspx#a-standardised-remediation-action-plan-(rap))

## Control 7.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Perform Automated Operating System Patch Management|

### The Control

Perform operating system updates on enterprise assets through automated patch management on a monthly, or more frequent, basis.

### Why it is required

* Ensures that systems remain protected from known vulnerabilities
* Reduces the time that systems remain vulnerable from patch release to installation

### How it is achieved

* Configure systems to apply updates using automated tooling
* Use devices that are managed centrally
* Use devices that are managed with MDM
* If using IaaS, join a managed domain

## Control 7.4

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Perform Automated Application Patch Management|

### The Control

Perform application updates on enterprise assets through automated patch management on a monthly, or more frequent, basis.

### Why it is required

* Ensures that applications remain protected from known vulnerabilities
* Reduces the time that applications remain vulnerable from patch release to installation

### How it is achieved

* Configure applications appropriately
* Configure platform management appropriately
