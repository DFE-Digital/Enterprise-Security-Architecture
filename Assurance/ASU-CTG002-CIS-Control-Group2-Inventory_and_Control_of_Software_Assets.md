# CIS Control 2 - Inventory and Control of Software Assets

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
* ISO27001:2022: A5.9
* NIST 800-53: CM-8, CM-7(1), MA-3, SA-22, CM-7(2), CM-8(3), CM-10, CM-11
* ITIL 2011 KPIs: Information Security Management
* ICO Protecting Data: Decommissioning of software or services

## Control 2.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications	|Identify	|Establish and Maintain a Software Inventory

### The Control

Establish and maintain a detailed inventory of all licensed software installed on enterprise assets. The software inventory must document the title, publisher, initial install/use date, and business purpose for each entry; where appropriate, include the Uniform Resource Locator (URL), app store(s), version(s), deployment mechanism, and decommission date. Review and update the software inventory bi-annually, or more frequently.

### Why it is required

Establishing and maintaining a software asset inventory is a fundamental cybersecurity practice that enhances security, compliance, efficiency, and incident response capabilities.

* Security: Helps to identify and manage vulnerabilities.  Enables tracking of security patches and updates. Reduces risk of security breaches.
* Compliance: Helps to comply with legal or regulatory requirements.
* License Management: Helps prevent over or under licensing ensuring DfE only pays for the software it needs to carry out its business objectives.  Reduces likelihood of vendor fines for non-compliance.
* Efficiency: Enables DfE to optimise software deployment, streamline maintenance and make informed decisions about purchases
* Incident Response: Enables quick identification of affected systems in the event of a security incident or breach. 

### How it is achieved

>Link to guideline or process goes here if existing or planned

## Control 2.2

| Asset Type | Security Function | Title|
---| ---| ---|
|Applications |Identify |Ensure Authorized Software is Currently Supported

### The Control

Ensure that only currently supported software is designated as authorized in the software inventory for enterprise assets.

If software is unsupported, yet necessary for the fulfillment of the enterprise’s mission, document an exception detailing mitigating controls and residual risk acceptance.

For any unsupported software without an exception documentation, designate as unauthorized. Review the software list to verify software support at least monthly, or more frequently.

### Why it is required

Vulnerabilities may exist in unsupported software that can be exploited by malicious actors.

* The May 2017 Wannacry attacks on the NHS exploited vulnerabilities in unsupported versions of Microsoft software.  The attacks are estimated to have cost the NHS in excess of £90m [DHSC Wannacry Report](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/747464/securing-cyber-resilience-in-health-and-care-september-2018-update.pdf)*

### How it is achieved

Service Portal has process to request software.

* Asset Discovery - see also [CIS Control Group 1](./ASU-CTG001-CIS-Control-Group1.md)
* Software Discovery
* Continuous Monitoring
* Asset Lifecycle Management: Need to track the lifecycle from pre-procurement (requirements), purchase (business case), installation, patching and maintenance, to retirement
* Automation: Can be utilised to streamline the process and help maintain accuracy
* Regular Audits: Can discover discrepencies and ensure compliance
* Integration: Integrate with other security and IT tools, i.e. SIEM, Vulnerability Management, Network Management, Firewalls
* Policy Enforcement
* User Training: Ensure users understand the importance of software asset management and their role in it.
* Response Plan: Plan to address unauthorized or unmanaged software. Include procedures for mitigating risk.

## Control 2.3

| Asset Type | Security Function | Title| 
---| ---| ---|
Applications | Respond |Address Unauthorized Software

### The Control

Ensure that unauthorized software is either removed from use on enterprise assets or receives a documented exception. Review monthly, or more frequently.

### Why it is required

Unauthorized software can expose the Department to unknown levels of risk.

### How it is achieved

* Asset Lifecycle Management
* Automation: Can be utilised to streamline the process and help maintain accuracy
* Regular Audits: Can discover discrepencies and ensure compliance
* Integration: Integrate with other security and IT tools, i.e. SIEM, Vulnerability Management, Network Management, Firewalls
* Response Plan: Plan to address unauthorised or unmanaged software. Include procedures for mitigating risk.
