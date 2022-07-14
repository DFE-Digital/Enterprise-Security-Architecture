
# Web Filtering Briefing Note

| Document Information |
------------------------|
| Category: Briefing Note |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| References: BRF-SEC002 - Web Filtering |

## Guidelines for the use of external identities

The following briefing note is provided to guide Department's operational and service teams when working with external identities accessing the Department's systems and services. 

External identities refers to 3rd parties who require access to the Department's systems or services but who are not directly employed by the Department and/or do not have a Department-issued identity.

**Exceptions** to the guidelines will be reviewed with the security and architecture governance teams and approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested via the owning architect, and will be reviewed against the roadmap and strategy and within the Architecture profession.

**Escalations** will be dealt with within the immediate leadership within the relevant architecture domain (up to DD level) and to the SLT by exception.

## Introduction

The guidelines are provided to define a consistent approach when working with 3rd party identities and to enable our future strategy for the management of 3rd party identities by removing dependencies on legacy identity platforms.

## 3rd party identity use within the Department

Historically, the Department has hosted servicces on traditional platforms and enabled access to these via our standard on-premise Active Directory identity platform. This method of authentication is well suited to on-premise and traditional services, but does add complexities when providing services to 3rd parties. Standard solutions to enable access for 3rd parties would involve using thin-client solutions or providing the 3rd party with a Department-issued device.

Services provided by the Department are almost exclusively provided via cloud-first platforms and as-a-service, and authentication for modern services is now provided via Microsoft's AzureAD identity platform. Identities which are created in Active Directory are automatically synchronised into AzureAD, but this synchronisation is no longer required and adds further complexity and cost for the management of identities.

Microsoft are also signalling the deprecation and retirement of traditional Active Directory platforms as it continues its focus on cloud-first solutions, therefore it is important that the Department prepares for this by reducing our dependencies on traditional Active Directory identities.

## Standard approach for 3rd party identities

To ease administrative burdens and improve security, 3rd party identites must now only be managed within AzureAD and not Active Directory, and services which are reliant upon 3rd party identities stored in Active Directory must start to plan to move these identities so they are only mastered and managed in AzureAD.

There are two main types of AzureAD identities which can be used for 3rd party identities. Details for these, with recommendations and (where aplicable) positives and negatives are described below.

*Note - this does not include AzureAD B2C identities. These are not intended for use within the Department and are primarily designed for use in a B2C (Citizen) use-case*

### AzureAD accounts

AzureAD accounts are identities which are created directly within our AzureAD identity platform. Whilst these types of accounts meet the security requirement and remove the need for Active Directory accounts, they do not reduce or remove the administrative burden as they are still managed and maintained by our internal support teams.

**Our support teams are responsible for:**

- Account management (creation/modification/removal)
- Password management (create/unlock/change)
- Group management (adding/removing/changing group membership)
- Multi-factor authentication management (providing and managing MFA devices)
- Conditional Access management (policy-based access controls)

### AzureAD B2B accounts

AzureAD B2B accounts are identities which are created by the 3rd party and invited into our AzureAD identity platform. Once they are invited they behave like standard AzureAD accounts and have the same features. These accounts meet the security requirement, remove the need for Active Directory accounts and also reduce the administrative burden for our internal support teams.

**Our support teams are responsible for:**

- Group management (adding/removing/changing group membership)
- Conditional Access management (policy-based access controls)

**The 3rd party support teams are responsible for:**

- Account management (creation/modification/removal)
- Password management (create/unlock/change)
- Multi-factor authentication management (providing and managing MFA devices)
- Conditional Access management (policy-based access controls)
