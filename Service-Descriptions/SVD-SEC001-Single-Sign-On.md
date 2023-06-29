# Security Service Definitions - Single Sign-on

| Document Information |
---|
| Category: Service Definition |
| Created: 18-01-2023 |
| Domain: Security |
| Author: <pete.dingwall@education.gov.uk> |
| References: None |

## Introduction and background

Service definitions are provided by the Cyber and Information Security Division (C&IS) and used by service teams to understand:

1. Which standard services are provided
2. What is the scope of the service offering
3. How they're requested
4. What information is required by the team providing the service
5. Expertise required by the requesting team
6. What the C&IS team will provide back to the service

---

### Single Sign-on (SSO)

#### **Service Definition**

The SSO service enables service teams to integrate an application into the Department's standard identity provider for civil servants and contractors working on behalf of the Department. This is also described as a Business-To-Enterprise (B2E) identity.

#### **Scope**

The SSO service can be used for any web-based application which is used within the B2E identity segment, including internally-developed services and 3rd-party SaaS applications.

Services seeking to integrate into the SSO service must support either SAML2.0 or OIDC protocols.

#### **How to request the service**

The service can be requested via ServiceNow for the attention of the IDAM team. Standard response times for requests are X working days.

The time to complete the work will depend on the complexity of the request, the IDAM team will discuss this with you once they have all of the required information.

*There are no escalation routes to expedite requests, so please ensure that you plan appropriately within yor project.*

#### **Information required**

The following information must be provided to support the service team to fulfill the request. All information is mandatory unless otherwise stated.

- Name of the service being integrated for SSO
- Design for the service
- Evidence of assurance oversight from:
  - Security
  - Data Protection Office
- A data flow diagram showing at least the following:
  - Where the service is hosted
  - Trust boundaries
  - Connectivity between the service and other services and/or data stores as relevant
  - Data being exchanged by the service
  - Protocols used by the service
- Authentication protocol used by the service
- Relevant URLs for the SSO integration
- Access to the application SME to configure the service
- Identity claims required to be exchanged by the service
- Users of the service:
  - Internal users
  - 3rd party users
- Authorisation information:
  - How is authorisation handled?
  - Will groups be required to manage access?

#### **Expertise required**

The requesting team will be expected to provide the following expertise to support the request:

- Technical architecture to provide the design and overview of the service
- SME support to provide the in-depth knowledge of the service. This could be an internal resource or the vendor providing the service


#### **Output provided**

The IDAM team will work with the service to configure and test the service to confirm that SSO is working as expected.

Once the SSO integration work is completed, it is expected that there will be no further involvement from the IDAM team for ongoing management of the service, unless there is a signficant change which would require a change to the SSO integration.
