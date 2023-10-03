# CIS Control 10 - Malware Defenses

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |

## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* [NCSC Cyber Assessment Framework (CAF) B4](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-4-system-security)
* [NCSC Cyber Assessment Framework (CAF) C1](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/c-1-security-monitoring)
* ISO27001:2022: A8.1, A8.7
* NIST 800-53: SI-3, MP-7
 
## Control 10.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Deploy and Maintain Anti-Malware Software|

### The Control

Deploy and maintain anti-malware software on all enterprise assets.

### Why it is required

* To block the delivery of malware whether via email, the web or other distribution channels

### How it is achieved

* Use centrally provided tooling and software
* Configure devices appropriately

## Control 10.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Configure Automatic Anti-Malware Signature Updates|

### The Control

Configure automatic updates for anti-malware signature files on all enterprise assets.

### Why it is required

* New malware is released regularly
* Updated signatures are required to detect newer malware variants

### How it is achieved

* Configure systems and software appropriately
* Use supported hardware and software

## Control 10.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Devices |Protect |Disable Autorun and Autoplay for Removable Media|

### The Control

Disable autorun and autoplay auto-execute functionality for removable media.

### Why it is required

* [Reduces the exposure to cyber attack](https://www.ncsc.gov.uk/information/reducing-your-exposure-to-cyber-attack)

### How it is achieved

* Configure systems appropriately using security baselines i.e. CIS Benchmarks
