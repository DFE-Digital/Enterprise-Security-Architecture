# CIS Control 6 - Access Control Management

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| Edits: paul.fitzgibbons@education.gov.uk |

## Related Controls 
This is covered in various other Security/Management/Assessment Frameworks such as:
* [NCSC Cyber Assessment Framework (CAF) B2](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance/b-2-identity-and-access-control)
* ISO27001:2022: A5.15, A5.16, A5.18, A5.16, A5.18, A6.5, A5.15, A6.7, A8.2
* NIST 800-53: IA-2, IA-4, IA-5, AC-1, AC-2, AC-19

## Control 6.1

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Establish an Access Granting Process|

### The Control

Establish and follow a process, preferably automated, for granting access to enterprise assets upon new hire, rights grant, or role change of a user.

### Why it is required

* If access is not granted in a timely basis this can:
*     be frustrating for users
*     be wasteful of public money

### How it is achieved

* Leverage APIs and automation in enterprise products to join up systems and integrate processes

## Control 6.2

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Establish an Access Revoking Process|

### The Control

Establish and follow a process, preferably automated, for revoking access to enterprise assets, through disabling accounts immediately upon termination, rights revocation, or role change of a user. Disabling accounts, instead of deleting accounts, may be necessary to preserve audit trails.

### Why it is required

* If access is not revoked  in a timely basis this can:
*     lead to unauthorised access of information (Information Disclosure)
*     lead to unauthorised modification of information (Tampering)
*     be wasteful of public money

### How it is achieved

* Leverage APIs and automation in enterprise products to join up systems and integrate processes

## Control 6.3

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Require MFA for Externally-Exposed Applications|

### The Control

Require all externally-exposed enterprise or third-party applications to enforce MFA, where supported. Enforcing MFA through a directory service or SSO provider is a satisfactory implementation of this Safeguard.

### Why it is required

* Externally exposed assets are more likely to be targetted by threat actors

### How it is achieved

* Use common components which meet the requirements of the Department

## Control 6.4

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Require MFA for Remote Network Access|

### The Control

Require MFA for remote network access.

### Why it is required

* Makes it more difficult for an attacker to gain unauthorized access to the network

### How it is achieved

>Link to guideline or process goes here if existing or planned

## Control 6.5

| Asset Type | Security Function | Title| 
---| ---| ---|
|Users |Protect |Require MFA for Administrative Access|

### The Control

Require MFA for all administrative access accounts, where supported, on all enterprise assets, whether managed on-site or through a third-party provider.

### Why it is required

* Administrator, root, super-user, privileged accounts have enhanced privileges allowing them more access to the underlying software or hardware.  These can be abused by threat actors if they can gain access.  MFA can prevent password spraying attacks or dictionary attacks as it requires additional layers of authentication.

### How it is achieved

* [Identity Guidelines](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-IDE001-Authentication-principles.md#identity-guidelines)
* [MFA Guidance - Suppliers/External](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-IDE003-MFA-Guidance-External.md#multi-factor-authentication---suppliersexternal)
* Use DfE identity architecture standards (see intranet)
