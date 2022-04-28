
# Firewall Rules Guidelines

| Document Information |
------------------------
| Category: Architecture Guidelines |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| References: PRI-SEC004 - Firewall Guidelines |

## Baseline guidelines for firewall rulesets and access

The following guidelines are provided to guide Department operational teams when creating and maintaining firewall policies, and managing requests for access from the Department's delivery and operational teams

**Exceptions** to the guidelines will be reviewed with the security and architecture governance teams and approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested via the owning architect, and will be reviewed against the roadmap and strategy and within the Architecture profession.

**Escalations** will be dealt with within the immediate leadership within the relevant architecture domain (up to DD level) and to the SLT by exception.

## Introduction

The guidelines are provided for baseline guidance for the definition of firewall policies and management of firewalls, and to provide an understanding of the common and non-standard ports and protocols used within the Department,

## 1. Enable logging into the appropriate platform
*Centralised and consistent logging ensures that we can identify any issues and monitor for alignment to our guidelines*

### Why?

Logs captured by the firewalls help central support teams to both capture details of how the firewalls are being administered, how systems are accessing them and identify potential attempts for malicious or inappropriate access.

It is important that these logs are captured into the appropriate platforms so that they can be analysed and rules and alerts can be defined to quickly identify issues.

### How?

- Capture administrative access logs into the SIEM platform so these can be analysed proactively and retrospectively
- Define alerting as required for changes made to firewalls aligned to production workloads
- Capture firewall logs to the appropriate firewall-monitoring platform for aggregation
- Configure critical alerts and important messages to be forwarded into the Department's SIEM platform

## 2. Manage admin access appropriately

*Incorrect or inappropriate access leads to poor practices increases risk*

### Why?

Firewalls need to be managed and controlled appropriately, as changes made could expose vital DfE services and data to inappropriate access. Standard best practices need to be followed to ensure that access is only granted when required and at the approriate level, to ensure that only specific teams are making changes to the firewalls.

Separation of Duties ensures that teams are conscsiously making changes to the relevant environment and device, and maintaining this separation also ensures that a compromise of an account or inappropriate access is limited within a specific environment rather than across all devices.

Just-in-time access, ensures that access is only provided for the specific time period requried to carry out the change, and also protects against inappropriate or malicious access as the permissions are only available for a short period of time.

### How?

- Review **PRI-SEC001** (Authentication principles) and follow guidelines to secure administrative access
- Follow a **least privilege** approach at all times ensures that any changes are made consciously and appropriately
- Use a well-defined **role-based access control (RBAC)** method provided by the firewall vendor to ensure that permissions required to manage the device are appropriate
- Use a **Just-In-Time access model**, complemented with the least-privilege model to ensure that access is only provided when required for the specific task
- Apply **Separation of Duties** when assigning permissions to ensure that teams managing multiple environments only have access to the specific environment and service (Dev/UAT/Prod etc)
- Restrict access for firewall administration (at all levels) to DfE-provided devices only (not from BYO or 3rd party) to ensure that access is protected and secured appropriately

## 3. Block inappropriate traffic

*Baseline rules block common exploits and provide a last line of defence*

### Why?

General best practices are applied to block specific traffic or IP ranges which should not have access or which could be signals of malicious activities. These baseline controls and rules provide the basic lines of defence for a firewall ruleset and should always be applied.

### How?

- Block rfc 6761 1918 4913 for inbound or Internet access. These address ranges are designated for internal access and should be dropped by default from any inbound rules
- Restrict internet access from networks hosting servers or platforms which are not located in a designated DMZ network. These servers should not require direct access Internet sites as standard
- Restric access to servers in DMZ other than the ports/protocols required specifically for their service
- Block and do not log broadcast traffic. Many devices use broadcast to locate devices on their local network segment as standard, but this does not add any value beyond the segment and can create significant noise. This traffic should be blocked by default between networks, and not logged.
- Use a drop-all rule as per best practice to ensure that any traffic which does not meet a specified rule is dropped

## 4. Enable access consciously and limit to least-access

*Less is more with firewall rules and open ports*

### Why?
Any port open from a firewall can provide the potential for inappropriate or malicious access, so access must be limited to the specific requirements only. 

If a system is requesting broad access across a range of firewalls this should be challenged as otherwise it could lead to a compromise if it is poorly architected.

### How?

- Open up consciously based on the specific requirements for the service
- Ensure access is limited to only what's required
- Avoid generic and broad rules, other than for standard and agreed services
- Be wary of and challenge poorly architected services
- Use risk management processes to highlight problematic and poorly-architected solutions

## 5. Restrict access to services which could enable direct Internet access

*Access to the Internet should be managed appropriately*

### Why?

Many internet sites contain inappropriate content or exploits which can be used to gain access to the Department's data or exploit its users. Web filtering solutions are provided by the Department to ensure that we protect our users and data appropriately.

The web filtering solutions also log and monitor access to Internet sites and track inappropriate use or identify potential indicators of compromise.

>**Note for BYOD, explaining how we can't control these devices when operating outside of the DfE network, and how this is mitigated**

### How?

- Ensure network restrictions are in-place to ensure that users cannot circumvent web filtering solutions by disabling VPNs or altering proxy settings
- Baseline firewall policies must be created from all exit points from the Department's networks to block direct access to the Internet
- Permit access to web-filtering solutions which can be used as the control point for all Internet access
- Restrict DNS traffic from from our networks to the Internet. DNS resolution should only be via our Department-managed DNS service



## 6. Use automation and intelligence feeds if available

*Internet services change regularly, make use of supplier automation options to keep up*

### Why?
Most of the Department's systems take advantage of as-a-service platforms and software as part of their overall service provision. These platforms and services are constantly evolving and expanding, with services changes and adding additional nodes and endpoints.

Using IP as a control point can be challenging in these environments, requiring constant oversight to keep ahead of the changes and ensure that services are not inadvaertently blocked. Most/all suppliers provide automated feeds for their services as they grow and change which can be used to fully or partially automate firewall updates.

Firewall vendors also provide intelligence and threat feeds for potential and known malicious sites, IP ranges and endpoints. These feeds can be used to update firewall rules so that these are blocked automatically to protect our users and services.

### How?

- Design processes to make use of the automation provided, with focus on taking the automation as-is and not as a bespoke service
- Do not rely upon human intervention or validation of feeds and automation unless strictly required
- Use automated feeds for cloud services to manage dynamic IP ranges such as Microsoft's RSS feeds for Azure services
- Review firewall vendor capability to take live threat feeds for perimeter firewalls
- Ensure processes are implemented to manage any false positives quickly to ensure  services are not impacted

## 7. Only permit access for a service on its standard port

*Because security through obscurity isn't enough*

### Why?

Most services and protocols use common standard IP ports to enable access from other systems. These ports are well known and often targeted for specific types of malicious activity.

A service running on **TCP 1433** is well known as **MSSQL**, and a service running on **TCP 3389** is well known as **Remote Desktop**, so malicious users will search for these ports and target systems which are advertising them.

Attempts to 'secure' these services by using non-standard ports only provide a basic level of security, as the service will still be identified in a port scan and respond in a consistent way to advertise itself to a malicious user. Services which are attractive to malicious access should be secured via other methods, or not advertised externally.

The use of non-secure ports can also be used as a method for users to attempt to evade scrutiny of security, or to evade a firewall block for the service on its standard port.

>Any attempted use to hide services behind non-standard ports should be flagged as a security violation and captured in the risk log so it can be identified and tracked.

### How?

- Validate well-known services are using their standard ports or port ranges
- Application-specific services should be validated with the specific vendor to ensure that they are aligned with their standards
- Challenge Department-specific services which require numerous ports (as per Principle 3) and track exceptions as risks

## 8. Only permit access to valid endpoints

*The use of consumer or dynamic services could lead to spoofing and malicious access*

### Why?
Many of our systems will connect outwards to other xGov systems or 3rd party providers as part of the architecture solution. These outbound connections will facilitate sharing of data and information, and also carry credentials to access these systems.

It is key to ensure that we understand what these endpoints are, what they are being used for and who is providing and supporting the endpoints we're connecting to. Due to this, the use of services which could be used to mask services will not be permitted. 

The systems being accessed should also be provided from an appropriate 'enterprise grade' provider to ensure that the security of the remote system is maintained and the provider has been suitably assured.


### How

- Only permit remote endpoints which are using registered and valid domains
- Do not allow remote endpoints using URL shorteners (ow.ly, bit.ly etc) as these can easily be updated to point to other endpoints or URLs without the Department's visibility
- Do not allow remote endpoints using dynamic DNS domains as these can easily be updated and changed to point to other endpoints without the Department's visibility
- Do not allow remote endpoints hosted on consumer-level services, as the assurance provided on these platforms will not be suitable or sufficient, and may lead to compromise of a system hosted by the Department
- Do not allow remote endpoints hosted on consumer hosting platforms (GoDaddy, SquareSpace, Wordpress etc) as the assurance provided on these platforms will not be suitable or sufficient, and may lead to compromise of a system hosted by the Department

## 9. Track exceptions with Risk Management

### Why?

Systems which are not able to follow the guidelines within this document may be exposing the Department to additional risk for data exfiltration or other malicious access to other systems and networks. The use of risk management will enable the tracking of exceptions and also the aggregation of risk for specific systems or service lines.

### How

- Ensure that risks are logged for systems which are not able to meet the guidelines
- Ensure that the risk owner is correct and assigned to the system owner and not the security or operational team who have identified the exception
- Ensure that the risk severity is commensurate with the exception and the system
- Ensure that risks are aggregated to highlight the cumulative risks being carried by a system or a service line, to ensure that visibility is achieved at the appropriate level

## 10. Delivery/Operations teams are responsible for systems and their access

### Why?

Delivery/Operations teams are responsible for systems (either developed by the Department or COTS) and the access required by that service. Any risks or exceptions are managed and owned by the respective team, and ongoing responsibility for the maintenance and management of this access remains the responsibility of the Delivery team for the lifetime of the respective system(s).

### How?

- The Delivery/Operations team must document and validate any outbound or inbound requirements within the system document
- The team retains ownership and responsibility for any further updates and changes to the system, and must ensure documentation is kept updated
- The team must consider their attack surface and only open what's required for their system
- Recertification of inbound and external access and any related risks will be required every 6 months, with supporting evidence in the systems documentation
- Recertification will be tracked and audited

# Appendix - Standards for outbound and inbound access

A limited number of services and ports have been identified as common for all services and agreed by default. Other services and ports have been agreed for specific central and operational services.

## Outbound access

### Defaults

The following services and protocols are allowed outbound by default for public-facing services within DMZs:

| Service | Protocol & Port |
-----------|------|
| http | TCP 80 |
| https | TCP 443 |

### On-request

The following services and protocols are allowed outbound with conscious approval and demonstrated business need:

| Service | Protocol & Port | Caveats |
---|---|---|
|DNS | TCP/UDP 53 |Authorised internal DNS servers requiring external lookup|
|SMTP | TCP 587 | Authorised internal  mail servers requiring outbound relay |
|IMAPS | TCP 993 | Authorised internal mail servers requiring inbound mail |
|NTP   | TCP 123 | Authorised NTP servers within the Stratum hierarchy |
|SSH | TCP 22 | Permitted to agreed endpoints and services |
|MSSQL | TCP 1433 | Permitted to agreed endpoints and services |

## Inbound access

### Defaults

The following services and protocols are allowed outbound by default for public-facing services within DMZs:

| Service | Protocol & Port |
-----------|------|
| http | TCP 80 |
| https | TCP 443 |


### On-request

The following services and protocols are allowed outbound with conscious approval and demonstrated business need:

| Service | Protocol & Port | Caveats |
---|---|---|
|VPN  | UDP 1194 | Permitted for the Department's main remote access solution
|SFTP | TCP 22 |For specific endpoints which need to securely and programatically exchange data
|FTPS | TCP 900 | For specific endpoints which need to securely and programatically exchange data
|DNS | TCP 53 |Pending review, may not be required if we do not host externally-accessible DNS zones

### Not Permitted

Any protocols and services which are not listed in the Inbound and Outbound Access sections are not permitted. Services will be updated and iterated for other approved services following approved demand from delivery and operations areas.

Common *not permitted* services are outlined below, with rationale and guidance for services which provide a suitable alternative.

| Not-permitted service | Rationale | Equivalent service |
---|---|---
|FTP| Unsecure service | SSH
|Telnet | Unesecure, legacy service | SSH
|Telnets | Legacy service | SSH
|RDP | RDP sevices are a regularly exploited and a security risk |(jump box strategy)
|File services protocols SMB, NFS etc| Unsecure, regularly exploited service | SFTP
|Legacy auth traffic (Kerberos, NTLM) | Not designed for WAN/Internet use | OIDC, SAML 2.0
|LDAP/LDAPS | Potential for exposure if poorly implementated | No business need
|Remote access and tunelling protocols | Could be used to circumvent standard protective controls | No Business Need
|Legacy name lookup services (WINS) | Not designed for WAN/Internet use |DNS
|IP6to4 protocols? | Could be used to circumvent standard protective controls | No Business Need
