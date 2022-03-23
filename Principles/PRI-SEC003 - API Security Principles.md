---
Category: Architecture Principles
Created: 2021-11-01
Domain: Security
Author: pete.dingwall@education.gov.uk
References: PRI-SEC003 - API Security Principles
---

# API security principles

## Principles for the use of APIs
The following principles are provided to guide projects and teams when using APIs to exchange data securely between applications and systems . The principles will be used to create a framework for projects to operate within and to demonstrate alignment with best practice.

**Exceptions** to the principles will be reviewed with the security and architecture governance teams and approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested via the owning architect, and will be reviewed against the roadmap and strategy and within the Architecture profession.

**Escalations** will be dealt with within the immediate leadership within the relevant architecture domain (up to DD level) and to the SLT by exception.

## Introduction
APIs are used within the Department as a common standard to exchange data between systems and to make the Department's data publicly accessible when relevant or desirable. The intended use is for applications and systems to access or exchange required data on a transactional, scheduled and on-demand basis.

## 1. Ensure adherence to Department policies and relevant principles

*Standard Department principles will provide the secure baseline for the service and data being exposed*

#### Why?
The policies outlined within the InfoSec Policy Suite provide the broad guidance, whilst princples outlined in PRI-SEC001 define the best practices to ensure that data is secured and access is managed appropriately
#### How?
-   Review PRI-SEC001 and apply all principles
-   Where appropriate, consciously exclude and log principles which are not relevant
-   Capture any exceptions and review with the assigned Information Security lead

## 2. Review and apply guidance and considerations from the OWASP principles

*Industry standard principles will provide the best-practice secure baselines for the Department's API usage*

#### Why?
The [Open Web Application Security Project (OWASP)](https://owasp.org/) foundation create standard guidance to secure web and API services. The guidance and principles are sourced through community-led global resources to provide a consistent baseline of best practice and advice.

Adherence to these standards within the Department ensures that we follow consistent and standard guidance and secure our API services appropriately.

#### How?

-  Refer to the [OWASP API Top 10](https://owasp.org/www-project-api-security/) and review guidance
-  Ensure system documentation refers to the OWASP API Top 10 and explains how each area has been reviewed and addressed as appropriate
-  Document and agree any non-compliance with the Top 10 and how any non-compliance risks are mitigated
-  Track ongoing change to the OWASP Top 10 and ensure that funding is available to apply any future changes or updates

## 3. Review data architecture for suitability

*Datasets exposed via an API must be suitably structured to support separation and access control requirements*

#### Why?
Datasets used with an API may be significant and contain data which includes personal information and other attributes which need to be protected and access managed. Systems accessing the data will be bound by overarching principles defined within *PRI-SEC001* (specifically least-privilege and role-based access controls), therefore data must be suitably structured to provide the required logical separation.

**An inability to support the required data architecture will deem the dataset(s) unsuitable for exposure via an API**


#### How?

-   Review data architecture and structure with the data owner
-   Request appropriate changes to the data model if appropriate to provide the required logical separation
-  Ensure that project funds include sufficient financial cover to support changes to the data model and structure
-  Ensure that mitigation options are available if the data owner is not able to make changes to their data model or data architecture

## 4. Seek approval from the data owner

*Data should not be made available via an API without the explicit approval from the data and system owner*

#### Why?
Any data which is exposed via an API for specific systems or wider usage should be suitable for the relevant usage, and the data owner who is responsible for the data must be aware of the usage and the context of the usage. The context should include (at least) the following:

1. Whether the API will be accessible for DfE systems or external systems or both
2. The permissions granted via the API to the data (read/modify/delete etc)
3. Whether data accessed via the API will be stored on other system(s)
4. Whether data will be processed or aggregated further

#### How?
-  Engage with the data owner(s) as early as possible (during the discovery phase) to ensure that sufficient time is available to discuss the use and address any concerns
-  Ensure that full details of the planned API usage are fully documented
-  Ensure that project funds include sufficient financial cover to amend or update designs and technical approaches following feedback from the data owner
-  Ensure that mitigation options are available if the data owner is not willing to permit API access to their data

## 5. Ensure the platform has been approved for API usage

*Platforms used to grant and manage access via an API must hold a valid Authority to Operate*

#### Why?
The system which is in-scope for access via an API must hold a valid AtO to ensure that it is secure and suitable for exposure to other systems and users via an API. The AtO process provides a baseline check of security controls and best practices based upon the system's categorisation and provides appropriate assurance.

The use of an API may change the security position for the specific system being accessed, which may in-turn require the AtO to be re-visited and re-assured for the specific area(s) of the system affected by the API access.

#### How?

-  Engage with the assigned Information Security lead for your project to review the AtO status of all in-scope Systems
-  Seek guidance from Information Security for any updates required to ensure that AtO approval is granted for all in-scope services
-  Ensure that project funds include sufficient financial cover to amend AtO process artefacts to gain approval and re-approval

## 6. Confirm suitability for internal or external access

*Specific datasets may not be suitable for access outside of the Department*

#### Why?
Information held in data sets can range from widely-available public knowledge to sensitive information relating to specific individuals and institutions. Due to this it is essential that any changes to how data is accessed or processed are carefully reviewed to ensure that this use is appropriate.

The access and processing of specific data may be acceptable if this is retained within internal systems which are only accessible from trusted Department personnel, but not acceptable if accessed from an external system or made available to wider public use.

The re-use or expansion of the use of data must be a conscious and considered decision, with stakeholders including (but not limited to):
1. The Data owner(s)
2. Information Security
3. Data Privacy

#### How?
(*The approach is consistent with Principle 4, but stakeholders are different*)

-  Engage with the stakeholders as early as possible (during the discovery phase) to ensure that sufficient time is available to discuss the use and address any concerns
-  Ensure that full details of the planned API usage are fully documented
-  Ensure that project funds include sufficient financial cover to amend or update designs and technical approaches following feedback from the data owner
-  Ensure that mitigation options are available if stakeholder(s) are not willing to permit API access to their data or cannot allow external access

## 7. Review any systems risks and update as necessary

*Exposing system data may change or increase the risk profile of the dataset or service*

#### Why?
Changes made to a system or service can affect the risk posture of either the system being exposed via an API or the system accessing the API or both.

The change to the system may require an update to the risk statement, and either agreement to accept the risk by the current risk owner, or escalation to a higher risk owner if the risk impact change is significant.

#### How?
-  Engage with the assigned Information Security lead and risk owners to review any risks assigned to the in-scope service(s) or system(s)
-  Seek guidance from Information Security and risk owner for any updates required to ensure that risk statements are appropriate for all in-scope services
-  Ensure that project funds include sufficient financial cover to amend risk statements and to gain approval and re-approval for existing and new risks
-  Ensure that mitigation options are available to manage and reduce risks if approval cannot be granted by the risk owner.
