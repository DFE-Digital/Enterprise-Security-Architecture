---
Category: Architecture Principles
Expires: 2021-01-01
Domain: Identity
Author: pete.dingwall@education.gov.uk
References: PRI-SEC001 - Authentication Principles
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

*Standard principles will provide the secure baseline for the service and data being exposed*

#### Why?
The policies outlined within the InfoSec Policy Suite provide the broad guidance, whilst princples outlined in PRI-SEC001 define the best practices to ensure that data is secured and access is managed appropriately
#### How?
-   Review PRI-SEC001 and apply all principles
-   Consciously exclude and log principles which are not relevant
-   Capture any exceptions and review with the assumed InfoSec contact

## 2. Review data architecture for suitability

*Datasets exposed via an API must be suitably structured to support separation and access control requirements*

#### Why?
Datasets used with an API may be significant and contain data which includes personal information and other attributes which need to be protected and access managed. Systems accessing the data will be bound by overarching principles defined within *PRI-SEC001* (specifically least-privilege and role-based access controls), therefore data must be suitably structured to provide the required logical separation.

**An inability to support the required data architecture will deem the dataset(s) unsuitable for exposure via an API**


#### How?

-   Review data architecture and structure with the data owner

-   Request appropriate changes to the data model if appropriate to provide the required logical separation.

## 3. Seek approval from the data owner

*Data should not be made available via an API without the explicit approval from the data and system owner*

#### Why?
#### How?

## 4. Ensure the platform has been approved for API usage

*Platforms used to grant and manage access via an API must hold a valid Authority to Operate*

#### Why?
#### How?

## 5. Confirm suitability for internal or external access

*Specific datasets may not be suitable for access outside of the Department*

#### Why?
#### How?

## 6. Seek approval from the data owner

*Data should not be made available via an API without the explicit approval from the data and system owner*

#### Why?
#### How?

Least privilege

Link to OWASP as over-arching Principles
https://owasp.org/www-project-api-security/
