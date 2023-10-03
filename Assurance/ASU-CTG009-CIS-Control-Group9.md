# CIS Control 9 - Email and Web Browser Protections

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |

## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* ISO27001:2022: A8.1, A8.23
* NIST 800-53: CM-10, SC-18, SI-8

## Control 9.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Applications |Protect |Ensure Use of Only Fully Supported Browsers and Email Clients|

### The Control

Ensure only fully supported browsers and email clients are allowed to execute in the enterprise, only using the latest version of browsers and email clients provided through the vendor.

### Why it is required

* Use of non-supported software increases the attack surface exposed to malicious actors
* Use of non-supported software is unlikely to receive automated patching from central services

### How it is achieved

* Use approved tools
* Request non-standard tools from the service desk so they can undergo assurance and risk assessment

## Control 9.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Network |Protect |Use DNS Filtering Services|

### The Control

Use DNS filtering services on all enterprise assets to block access to known malicious domains.

### Why it is required

* Malicious domains can be used by malicious actors to host malware, illegal material or to carry out malicious activities
* Filtering of known malicious domains reduces the likelihood of security incidents and breaches

### How it is achieved

* Use centrally provided DNS services
    * [Use NCSC Protective DNS services](https://www.ncsc.gov.uk/information/pdns)
* Use centrally provided Network services
