# CIS Control 8 - Audit Log Management

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |

## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* [NCSC Cyber Assessment Framework (CAF) C1](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/c-1-security-monitoring)
* ISO27001:2022: A8.6, A8.15, A8.20
* NIST 800-53: AU-1, AU-2, AU-4, AU-7, AU-12

## Control 8.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Establish and Maintain an Audit Log Management Process|

### The Control

Establish and maintain an audit log management process that defines the enterprise’s logging requirements. At a minimum, address the collection, review, and retention of audit logs for enterprise assets. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.

### Why it is required

### How it is achieved

>Link to guideline or process goes here if existing or planned

## Control 8.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Detect |Collect Audit Logs|

### The Control

Collect audit logs. Ensure that logging, per the enterprise’s audit log management process, has been enabled across enterprise assets.

### Why it is required

* Logs can be used to determine What, Why, How, Who, Where, When
* Logs can be used to detect suspicious or abnormal activity
* Logs can be used to investigate operational and security incidents

### How it is achieved

* Consult security benchmark documentation, i.e. CIS Benchmarks
* Configure systems and software appropriately

## Control 8.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Ensure Adequate Audit Log Storage|

### The Control

Ensure that logging destinations maintain adequate storage to comply with the enterprise’s audit log management process.

### Why it is required

* If logs do not have sufficient capacity they can wrap around if they are overwhelmed with data
* This can cause problems with incident investigations if log information is not available
* Local systems should have enough log storage available to cope with demand until logs can be transferred to other systems

### How it is achieved

* Configure systems using vendor best practice
* Consult security benchmark documentation, i.e. CIS Benchmarks
