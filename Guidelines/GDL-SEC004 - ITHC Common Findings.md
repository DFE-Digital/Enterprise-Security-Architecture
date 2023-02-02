# ITHC Common Findings

| Document Information |
---|
| Category: Architecture Guidelines |
| Created: 18-01-2023 |
| Domain: Security |
| Author: paul.fitzgibbons@education.gov.uk |
| References: GDL-SEC004 - ITHC Common Findings |

## Introduction and Background

Systems and Services within DfE need assurance that they have been built and are being maintained securely.

Part of this assurance takes the form of an annual (or more frequent) IT Health Check (ITHC). This is time bound and typically consists of a mix of vulnerability scannning, penetration testing, and configuration review.

Cyber and Information Security Division have identified the top thirteen ITHC findings from previous ITHCs.

These items should be reviewed and remediated **ahead of carrying out an ITHC**.

It should be noted that not all items will apply to all services.

### Procuring ITHC resource

If you are looking for information on how to get an ITHC. 

The Information Security Team within Cyber and Information and Security Division manage a call off contract for ITHC resource - further details [here](https://educationgovuk.sharepoint.com/sites/how-do-i/SitePages/security-it-health-check-services.aspx#external-security-resources).

**Updates or modifications** to the principles can be requested initially via the [Cyber and Information Security Divison](mailto://CIS.DELIVERY@education.gov.uk?subject=Architecture_Guidelines_ITHC), and in the future with standard updates and iterations via GitHub.

# DfE Top Thirteen ITHC Findings (last updated 18/01/2023)
Addressing these issues **AHEAD** of carrying out an ITHC will:
* Allow ITHC test teams to focus on identifying unknown / new vulnerabilities resulting in the production of a more focussed report

* Reduce the burden on support teams

* Provides a level of assurance that your service is operating securely (either to your SRO or to Security Teams within the department) - please note that following this guidance does **NOT** replace the need for an ITHC

tl;dr (more detail below this list!)

1. Insecure TLS/SSL Configuration
2. Verbose Server Headers
3. Missing HTTP Security Headers
4. Concurrent Logins Permitted
5. Outdated or Vulnerable Software
6. Missing Operating System Updates
7. Azure Storage Account Misconfiguration
8. SMB Signing Not Required
9. Windows Security Options Configuration
10. Insecure Cryptographic Configuration
11. Lack of Rate Limiting
12. SQL Server Authentication Configuration
13. Windows Audit Policy Configuration

## 1. Insecure TLS/SSL Configuration

*Data in transit must be protected from interception or modification.*

### Why?

Use of outdated or insecure encryption puts the data flowing over network links at risk.

### How?

* Follow NCSC TLS Best Practice guidance.
[Using Transport Layer Security to protect data - NCSC.GOV.UK](https://www.ncsc.gov.uk/guidance/using-tls-to-protect-data)
* Examples:
  * Disable insecure protocols (TLS 1.0, TLS 1.1 and SSL)
  * Use only TLS 1.2 or above
  * etc
* Use web application firewalls with appropriate configuration

* [Windows IIS Crypto](https://www.nartac.com/Products/IISCrypto/)

* [Linux - hardening TLS](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/sec-hardening_tls_configuration)

## 2. Verbose Server Headers

*The  ability  to  accurately  identify  the  vendor  and  version  number  of  software  running  on  a server is of high importance to an attacker.*

### Why?

Knowing the exact type of server in use allows an attacker  to  determine  any  known  vulnerabilities  that  may  be  used  against  it  and  will significantly aid in the selection of any appropriate exploits. A number of application servers will, by default, respond to a client request with data regarding the software running on the server, in the form of an HTTP response header.

### How? 

* Within the Software Development Lifecycle

* Configuration within your application

* Configuration of web servers

  * Use hardened server builds if using IaaS
  * [Example - Remove Unwanted Response Headers - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/iis-support-blog/remove-unwanted-http-response-headers/ba-p/369710)

## 3. Missing HTTP Security Headers

*HyperText Transfer Protocol (“HTTP”) security headers are directives that can be returned by a web application when  responding to a request from a client.*

*These headers can instruct a client  browser  on  specific  methods  of  handling  application data  which  can  include  such functionality  as  determining  scripts  that  can  be  run,  forcing  encryption  to  be  used  for communications, or enabling browser security functions to prevent against common attacks.*

### Why?

It  should  be  noted  that  enabling  HTTP  security  headers  will  not  provide  absolute  protection against sophisticated attacks. However, adding security headers will provide an additional layer of security against attacks that will only serve to enhance the overall security that is offered by a service.

### How? 

* Strict-Transport-Security:
The Strict Transport Security header provides a security enhancement that forces a client web browser to connect to a site over secure HTTP (“HTTPS”) only. This is known as HTTP Strict Transport Security (or “HSTS”). It further instructs the browser to remember the restriction for a specific period of time. It provides a measure of protection against the interception of data in transit (also known as “Man-in-the-Middle” attacks).

* Content-Security-Policy: The Content Security Policy (“CSP”) header defines content sources that are trusted and approved by the browser to load specific resources such as scripts. The header also defines how loaded resources may behave. The header assists in defending against cross-site scripting (“XSS”) and other code execution attacks.

* X-Frame-Options: The X Frame Options header prevents a site from loading iframes, preventing possible “Clickjacking” attacks. Clickjacking is an attack where seemingly benigncontent is reproduced within the context of a site controlled by a malicious party. Through using transparent or invisible content, a user appears to be interacting with trusted content, yet actually be undertaking completely different actions.

* X-XSS-Protection: The X XSS Protection header is designed to detect and assist in protecting against cross-site scripting (“XSS”) attacks. However, most modern browsers ignore this header now as having it on can introduce additional security issues. The header should therefore be set to off.X-XSS-Protection: 0

* X-Content-Type-Options: The X Content Type Options header is intended to prevent a browser from sniffing a response away from the declared content type of a specified resource. It assists in reducing the possibility of a drive-by download attack. In such an attack, a user may assume that they are downloading a legitimate and trusted resource. An appropriately placedattacker may be able to intercept such a request, and replace the original resource with malicious content.

* HSTS Header:The HSTS header should always have its configuration set to: max-age=31536000; includeSubDomains; preload.  This will ensure that the header is doing its job to provide the endpoint maximum security within its requests.

## 4. Concurrent Logins Permitted

*Permitting the user of an application to login more than once with the same set of credentials increases the risk of account compromise.*

### Why?

If attacker access is gained to a user account, the legitimate user is unlikely to observe that their credentials have been compromised if they are able to continue to work as normal.

Any account compromise occurring in this manner will also impede any investigative efforts due to the difficulty in attributing specific actions to either the owner of the account, or the attacker using the account-owner’s credentials.

A further  risk  arises  from  the  possibility  of  login  concurrency  causing  data  corruption.  If changes are made by the same account, on the same records, at a very similar time then there is the risk of competing actions causing information to be overwritten, or corrupted.

### How? 

* In Web Application Firewall Rulesets

* Configuration within your application

* Configuration of web servers

* [OWASP Session Management Cheat Sheet](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Session_Management_Cheat_Sheet.md)

## 5. Outdated or Vulnerable Software

*Software installed within an enterprise requires regular and timely updates in order to reduce the  risk  of  compromise  from  attack.  A  failure  to  incorporate  third-party  software  into  the patching  cycle  (as  opposed  to  patching  only  host  operating  systems)  greatly  increases  the prospect of a successful attack.*

### Why?

Vulnerabilities arising from outdated or vulnerable software may permit an attacker to deny the use of a platform to legitimate users, steal confidential data from a system, or potentially execute code against a system in order to compromise it in its entirety.

### How? 

* Use DfE approved software/tools

* Ensure that there is a maintenance requirements are documented and ensure there is a plan in place for the service. 

* Use roadmaps provided by services and suppliers to plan for updates and upgrades

* [Microsoft Product Lifecycle Information](https://learn.microsoft.com/en-us/lifecycle/products/)

## 6. Missing Operating System Updates

*Software installed within an enterprise requires regular and timely updates in order to reduce the  risk  of  compromise  from  attack.*

### Why?

A  failure  to  incorporate  third-party  software  into  the patching  cycle  (as  opposed  to  patching  only  host  operating  systems)  greatly  increases  the prospect of a successful attack.

Vulnerabilities arising from outdated or vulnerable software may permit an attacker to deny the use of a platform to legitimate users, steal confidential data from a system, or potentially execute code against a system in order to compromise it in its entirety.

### How? 

* Use managed domains for IaaS

* Use centrally managed server builds

* Ensure your service is covered by enterprise patching policies

## 7. Azure Storage Account Misconfiguration

*Azure storage accounts contain all the Azure Storage data objects: blobs, files, queues, tables, and disks. The storage account provides a unique namespace for your Azure Storage data that is  accessible  from  anywhere  in  the  world  over  HTTP  or  HTTPS.  Data  in  your  Azure  storage account is durable and highly available, secure, and massively scalable.*

### Why?

Misconfiguration of Azure Storage Security can increase the attack surface of the service/system.

### How? 

* Encrypt blob storage

* Disable public access

* Require Secure Transfer

* Restrict network access using firewalls, network rules or private endpoints

* [Review Microsoft guidance](https://learn.microsoft.com/en-us/azure/storage/blobs/security-recommendations)

## 8. SMB Signing Not Required

*The Server Message Block (SMB) protocol is a client-server communication protocol typically utilised  within  Microsoft  Windows  environments,  but  also  found  in  other  forms  (such  as Samba) elsewhere. The protocol is typically used for providing access to files, printers and other  network  resources.*

### Why?

Signing  of  SMB  traffic  allows  for  the  recipient  of  any  SMB communication to verify the origin of the data. Where SMB signing is not required, a suitably positioned attacker can perform attacks on the data in transit. Within Windows environments, this is typically exploited with the aim of intercepting user password hashes.

### How? 

* Use hardened server builds

* Ensure servers are domain joined and that servers have appropriate group policies applied

* SMB signing should be required for all communications between networked hosts. This can be configured through Windows group policy under the setting “Digitally sign communications (always)” and setting it to “Enabled” for both Microsoft network client and Microsoft network server communications. 

  * This setting can be located within the group policy editor under the following location: 

  * Computer Configuration–>Windows Settings–>Security Settings–>Local Policies–>Security Options

## 9. Windows Security Options Configuration

*Windows security options are configured within Windows group policy.*

### Why?

The security options contain  groupings  of  security  policy  settings  that  can  be  applied  to  hosts  within  the environment  in  order  to  provide  specific  security  functionality,  or  to  provide  additional hardening against attack.

### How? 

* Use hardened server builds

* Ensure servers are domain joined and that servers have appropriate group policies applied

* [Microsoft Security Options](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/security-options)

## 10. Insecure Cryptographic Configuration

*Host operating  systems  typically  provide  support  for  a  number  of  different  cryptographic protocols,  ciphers  and  hashing  types.  This  is  in  order  to  provide  support  for  a  variety  of different  communication  types  whilst  also  providing  support  for  backwards  compatibility.*

### Why?

Whilst supporting a more generic configuration allows compatibility for a greater number of applications, it also renders a host more vulnerable to attack in the instance that a deprecated, or known vulnerable, method of secured transfer is used.

### How? 

* Domain join IaaS servers to a domain under active management

* Ensure appropriate and up to date Windows Group Policies are applied

* Configure standalone or non-domain joined servers appropriately

* [Windows IIS Crypto](https://www.nartac.com/Products/IISCrypto/)

* [Linux - hardening TLS](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/sec-hardening_tls_configuration)

## 11. Lack of Rate Limiting

*Rate-limiting is used in APIs to limit the number of requests that can be made to the endpoint, once this limit is reached,servicesshould be denied to the user.*

### Why?

With a lack of rate-limiting,an attacker is able to repeat requests an unlimited numberof times leading to an associated drain on the resources of the server, potentially resulting in a denial-of-service ("DoS") attack.
### How? 

* In Web Application Firewall Rulesets

* Configuration within your application

* Configuration of web servers

* Use of one time tokens

## 12. SQL Server Authentication Configuration

*SQL Server should use Windows Authentication (Active Directory Credentials)*

### Why?

SQL Server Authentication credentials are not centrally managed. Windows/AD Credentials can be managed through the DfE's Joiners, Movers, Leavers process which ensures that accounts that are no longer required are disabled or removed.

### How? 

* Ensure server is domain joined to a DfE approved and managed domain

* Ensure 'ServerAuthentication' Property is set to 'Windows Authentication Mode'

* Ensure 'CHECK_EXPIRATION' Option is set to 'ON' for All SQL Authenticated Logins Within the Sysadmin Role 

* Ensure 'SQLServerAudit' is set to capture both 'failed' and 'successfullogins' - AUDIT_CHANGE_GROUP 

* Ensure 'SQLServerAudit' is set to capture both 'failed' and 'successfullogins' - FAILED_LOGIN_GROUP 

* Ensure 'SQLServerAudit' is set to capture both 'failed' and 'successfullogins' - SUCCESSFUL_LOGIN_GROUP 

* Ensure 'MUST_CHANGE' Option is set to 'ON' for All SQL Authenticated Logins

see also: [Authentication Principles](GDL-IDE001%20-%20Authentication%20principles.md)

## 13. Windows Audit Policy Configuration

*The  audit  policy  applied  within  a  Microsoft  Windows  environment  allows  system administrators to collect important information about system and network events.*

### Why?

Not only can this information assist in troubleshooting day-to-day issues, but audit information is also of particular importance following an attack. Audit and log data can provide the means to identify attackers, their techniques, and the mechanism by which they are able to compromise a host. Such information is critical for attribution and evidence gathering in the event of a successful attack.

### How? 

* Ensure IaaS servers are domain joined to an approved, managed DfE domain

* [Microsoft - Audit Policy Recommendations](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/audit-policy-recommendations)

* [Github - Audit Policy Recommendations](https://github.com/MicrosoftDocs/windowsserverdocs/blob/master/WindowsServerDocs/identity/ad-ds/plan/security-best-practices/Audit-Policy-Recommendations.md)

