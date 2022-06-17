
# Access controls and security considerations for SaaS and PaaS

| Category: Architecture principles
------------------------|
| Expires: 2022-07-01
| Domain: Security
| References: Authentication Principles **(PRI-SEC001)**
---

# Briefing Notes - Access controls and security considerations for SaaS and PaaS

Briefing notes are provided as general guidance and background to support a strategic future direction or to provide information about strategic intent for emerging technologies and capabilities.

Information within a Briefing Note can also act as a strategic placeholder whilst a formal strategy is being developed, providing sufficient information to inform colleagues and signpost strategic alignment.

## Introduction

This briefing note provides guidance for the use of Platform-a-a-Service (PaaS) and Software-as-a-Service (SaaS) platforms with appropriate controls to govern access and protect the Department's data from inappropriate access or removal. These services are provided by 3rd parties as a complete end-to-end solution with little or no customisation available for the consumers of the solution. This provides the ability for the provider to offer a low-cost and scalable service for consumer due to it being provided as-is and without the need for customer-specific changes.

The provider dictates the pace of change for the solution, providing a roadmap for the evolution of the service which can both add *and remove* capabilities from the service. Sufficient notice is provided for any changes to allow for consumers to plan to adopt, and whilst channels for feedback are available (customer voice etc) the timescale is rigid and rarely changes. This approach drives a need to take the service as-is and not amend or augment with self-developed solutions which may be impacted in the future by a change to the platform.

### Standard approaches to manage access

PaaS and SaaS mark a change from physical servers and Infrastructure-as-a-service (IaaS) platforms, where full control is available for the configuration of the operating system, application and network endpoints. IaaS provided the ability to use traditional border-based controls with firewalls to manage access, and IP whitelisting where necessary to restrict access to the service from specific locations or organisations.

These controls provide broad controls to manage access and secure services, but do not provide full protection against modern and evolving malicious activity. Restricting access via firewalls to specific network ports still provides the ability to exploit any vulnerability on the platform if it is exposed via a standard port, and IP whitelists are easily circumvented with the use of IP spoofing or VPN routing.

Cloud platforms do provide additional insights and protections against brute-force attacks, and the use of modern Endpoint Detection and Response (EDR) tools provide oversights into malicious patterns of activity, but the need to manage, monitor and respond to these activities is the responsibility of the service owner (the Department) rather than the service provider.

### Moving to PaaS/SaaS

The use of IaaS enables physical servers to be moved into cloud platforms via a 'lift-and-shift' approach, with the same controls being implemented post-migration. This is typically the first phase of an organisation's cloud migration approach, followed by a transition away from these traditional brittle services to the more flexible and service-managed platforms. This approach is suggested and recommended by the cloud providers, but the complexity of the change is overlooked or not clearly stated, which invariably leads to a mixed estate of IaaS, PaaS and SaaS platforms.

*It is important to recognise that this mixed estate needs a range of options to control access which are aligned to the platform being utilised. The outcomes remain the same but the method to achieve the outcome will differ as appropriate.*

## Access Controls

The most significant change for PaaS and SaaS is the implicit understanding that the service is open to the Internet and not restricted to specific IP ranges or locations. In most cases this is acceptable as our externally-facing services are accessible for all consumers regardless of their location. However, in some cases it is necessary to restrict access to specific groups of users, and for system-to-system access (APIs etc) there may be a requirement to control the endpoints which can connect to a service depending on what data or services are exposed.

### IP and port-based access controls

The controls used to secure access to IaaS platforms can be applied to PaaS, but with limited degrees of success and usefulness. The use of firewalls to restrict access and the tiered model (presentation/app/database) for systems is still utilised as part of the service provided, with recommendations and guidance provided automatically to ensure that services have the basic levels of security applied.

However, IP whitelisting controls are less useful and challenging or impossible to manage for PaaS and SaaS. If a system is utilising a SaaS platform for example it would be necessary to whitelist all endpoints used by the service provider, which is often an extensive list which will expand as the service grows. This becomes a more significant challenge when attempting to whitelist PaaS platforms as these are often elastic in scale and the range of IP endpoints could extend to most of the IP ranges used by a specific cloud region.

It is possible to automatically update access lists and firewall rules using rss feeds from the cloud providers, but this is unlikely to add value given the wide number of endpoints included. If the access list contains most/all of the endpoints used within a cloud platform the resultant control would be so broad that it would prove to add limited value.

**This control is not recommended for PaaS and SaaS systems due to the limited value it provides and the complexity to manage**

### Augmenting existing solutions

It is possible to create a front-end service for a PaaS platform which is controlled by the Department and can therefore provide a single point of access and control which can then be used with traditional controls such as IP whitelisting and application firewalls. However, this is impacting the overall managed service benefit of using PaaS and SaaS platforms by implementing a separate capability which must be managed and maintained separately, and which could become a vulnerability if not properly maintained and updated.

This front-end service would also be considered a brittle and static service which would be impacted by the ongoing evolution of the PaaS/SaaS service it is augmenting. A change made to the PaaS/SaaS platform (removal of a specific integration method, increased security etc) could break the integration and cause the service to fail.

**This control can be used as a short-term method of control (up to 12 months) whilst the solution aligns with criteria required for policy-based access controls**

### Policy-based access control

Policy-based access controls are the preferred and recommended method of managing access to PaaS and SaaS systems, as they are designed for cloud-first platforms, provide continuous evaluation of the access into a system and provide access based upon least-privilege principles. Many SaaS applications provide support for policy-based access controls by default, but should be evaluated to ensure that they meet the criteria below. Systems built upon PaaS platforms provide the foundations for policy-based access controls but require specific considerations and design decisions to ensure that they meet the required criteria.

Key tenets of policy-based access control and modern security practices are data and identity controls, which are used in place of traditional border controls to meet the same outcomes of protecting access to the system and data within. The ability to utilise data and identity as controls requires specfiic design and architecture considerations.

**Data design** - Fundamental to the alignment to policy-based access controls is secure and well-structured data. Alignment to principles such as least privilege within **PRI-SEC001** will not be possible if the database is not suitably structured to logically separate and secure data. This separation ensures that a functional account which is granted access to data can only access what is appropriate, and the risk of account compromise is mitigated by the access controls within the database.

**Robust permissions model** - Systems planning to utilise policy-based access controls must be able to demonstrate a mature access model which separates roles appropriately and assigns permissions based upon a least-privilege model. Alignment to the principles within **PRI-SEC001** allows access to internet endpoints without traditional access controls (IP whitelisting etc) as the access provided is constrained accordingly and only provides access to the data specific to the service exposed.

**Integration with strategic authentication provider** - Systems which integrate with strategic authentication providers can leverage capabilities provided by the platform to manage access appropriately. Conditions can be applied for access to a specific system which are tailored to the requirements, and can also adapt based on risk or other signals. This integration also ensures that monitoring of the authentication, authorisation and access is logged and integrated with strategic SIEM tooling.

### Inability to meet the requirements for policy-based controls may require a review of the architecture and decision regarding whether PaaS/SaaS is the most appropriate platform.
