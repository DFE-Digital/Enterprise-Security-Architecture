---
Category: Architecture Principles
Expires: 2021-01-01
Domain: Identity
Author: pete.dingwall@education.gov.uk
---

# AzureAD B2B principles

#### Introduction to AzureAD B2B
AzureAD B2B refers to a guest account which is provided as part of the wider Microsoft Azure Active Directory (AzureAD) service. AzureAD B2B provides a 'Bring Your Own Identity' service where users who are invited into an AzureAD directory as guests and are trusted for authentication only. The DfE will not impose password standards or housekeeping for the authentication of the user, but will maintain control over the authorisation of the B2B user into any services which are provided.

*Microsoft also offer an **Azure AD B2C** service, which is targeted at consumers and utilises a separate AzureAD identity directory, this service is not covered within these principles and will be covered separately.*

The use of B2B is synonymous with the concept of a house with many rooms which are all individually locked and protected. B2B provides the ability for the user to enter the front door of the house (Authentication) but not to access any of the locked rooms (Authorisation) without this access being explicitly granted.

It is essential that the concept of B2B is well understood, and the level of assurance it offers. With B2B, there is no concept of some B2B users being more 'trusted' than others due to the identity they use as part of B2B. A B2B account formed via a Google account could not be considered as any more or less trusted than from a managed corporate identity provided by an organisation providing services to the DfE. If the corporate identity is poorly managed by the supplier it would be less secure than a consumer identity from Google and Microsoft, both of which provide levels of multi-factor authentication as standard.

Suppliers are also often a route of exploit for malicious activity against the Department, as they can be seen as a 'weak link'. A compromise for an account from a poorly-managed tenant could lead to an exploit of a critical Department system, or access to sensitive data.

**Due to this, there is no plan or intention to tier or categorise B2B accounts into trusted or non-trusted domains or organisations**. Instead, all B2B accounts will be considered to provide the same level of assurance from an authentication perspective, and the additional assurance required will be provided by the authorisation into the relevant application(s) and with the use of additional policies (Conditional Access) and multi-factor authentication where required.

## Principles for appropriate use of AzureAD B2B
The following principles are provided to guide projects and teams when creating or procuring solutions for use by DfE users or consumers. The principles will be used to create a framework for projects to operate within and to demonstrate alignment with best practice.

**Exceptions** to the principles will be reviewed with the security and architecture governance teams and approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested via the owning architect, and will be reviewed against the roadmap and strategy and within the Architecture profession.

**Escalations** will be dealt with within the immediate leadership within the relevant architecture domain (up to DD level) and to the SMT by exception.

## <a href="#P1"> 1. Apply consistent assurance consideration for all B2B accounts </a>

*B2B accounts are all created equal, there is no concept of trusted or untrusted accounts*

#### Why?

We won’t have a concept of ‘trusted’ domains/tenants for guest accounts as it’s not sustainable to maintain this and would require the Department to impose and validate ways of working. It is simpler and more consistent to apply a single level of assurance across all B2B accounts and ensure that these are used appropriately by following the principles captured within this guidance.

A B2B account sourced from a strategic provider does not guarantee any levels of assurance or security as this is wholly dependant on the provider's internal processes and governance. Increased levels of assurance assumed for a provider, resulting in the provision of privileged roles or access, could result in a significant compromise into the Department if the provider's environment is compromised or poorly managed.

#### How?

-   Follow the guidance provided within the B2B Principles
-   Do not provide significant levels of access or privilege via B2B accounts

## 2. Distinguish between consumer and provider B2B and use appropriately

*Consumer and provider B2B identity sources are permitted but must be aligned to the appropriate use-case *

#### Why?

B2B invites only require an email address to be validated in order to be created. Whilst it may be preferable to use consumer email addresses (@gmail, @outlook etc) for some use-cases, the permitted use of these consumer emails will be dependent on the intended use-case. Ensuring that provider engagement via B2B uses the provider's email address provides the ability to easily identify groups of users from suppliers and manage appropriately, and will also align to that provider's working practices with joiner/mover/leaver governance and device management.

The use of consumer email for providers moves the responsibility of account management to the end-user and removes the clarity between B2B user and provider. This would also provide the ability for the B2B user to move between providers and still retain the same level of access provided by a previous provider, or retain access to Department services beyond their employment with a provider.

Consumer email is suitable for limited collaboration use-cases where it is necessary for the Department to have a 1-2-1 relationship with a consumer, as part of a review process or other specific engagement. However, this B2B account must be appropriately managed and only enabled for access for the duration of the 1-2-1 relationship.

#### How?

-   Ensure that email usage for B2B invites is aligned to the use-cases identified below
-   Do not use consumer email addresses for convenience when working with a provider, even on a short-term basis

| Use-case      | Appropriate email type |
| ----------- | ----------- |
| Provider working for DfE to deliver services      | Provider's email address |
| Sector user working with DfE for specific activity   | Education establishment email address |
| Sector user collaborating with the DfE for co-authoring etc| Education establishment email address |
| Cross-Government activity for collaboration, co-authoriing etc| Government Department email address |
| Individual/personal engagement for specific review | Consumer email address |


## 3. Only use B2B accounts for appropriate services

*Inappropriate use of B2B accounts could lead to data exfiltration to 3rd parties or individual, or compromise of systems in the Department and beyond*

#### Why?

The use of B2B accounts allows the use of 3rd party devices to access Department services and data, and (as per principle 1) it is not possible to reliably assure the source accounts and devices being used. Due to this the type of access will be tailored appropriately to align with the level of assurance and potential risks from the use of B2B accounts.

#### How?

-   Ensure that B2B usage is aligned with the use-cases identified below
-   Any use-cases not identified below are not permitted by default
-   Check with your Information Security contact to review any uses-cases which are not identified

| Use-case      | Compliance with B2B|
| ----------- | ----------- |
| Provider accessing collaboration platforms      | Yes |
| Provider accessing SaaS applications provided by the Department | Yes |
| Provider accessing code repositories as part of development engagement | Yes |
| Provider managing applications  on behalf of Department| Partial (*see principle 4*)|
| Provider managing enterprise systems on behalf of Department |Partial (*see principle 4*)|
| Provider managing cloud platforms on behalf of Department| Partial (*see principle 4*)|
| DfE user managing cloud platforms | Yes|
| DfE user accessing xGov collaboration platforms |Yes |
| Individual accessing collaboration platforms to support review/hearing | Yes |



##### *Note-* May need to refer to external source if this list gets too long


## 4. Use B2B accounts appropriately for privileged access and privileged roles

*Administrative access must be controlled appropriately via well-managed accounts and managed devices*

#### Why?

As stated in **Principle 1**, B2B accounts issued to 3rd parties only provide a limited level of assurance and must not be used to provide administrative-level access to DfE services, applications or resources. The lack of visibility of devices used to access or control over locations, or the knowledge of joiner/mover/leaver processes creates a significant risk with the use of of administrative-level access.

Refer to **Principle 3** for appropriate services and usage.

DfE users who have responsibility for management of specific services, applications or resources can use B2B with administrative privileges where the B2B account is sourced from the main AzureAD tenant. This identity is managed, controlled and governed at the required trusted level to allow it to be used safely with administrative privileges, however privileges must only be applied on a least privilege and just-in-time basis to protect against inappropriate or malicious use.

#### How?

-   Review the requirement for privileged access within your service and use B2B appropriately
-   Providers requiring administrative access will utilise a DfE-provided identity which is managed and controlled appropriately
-   Check with your Information Security contact to review roles and confirm whether B2B is appropriate

## 5. Enforce standard account lifecycle policies

*B2B accounts will be subject to baseline controls for expiry and renewal to provide a coarse-grain level of management*

#### Why?

As stated in **Principles 1 and 2**, B2B accounts for providers or consumers will not have consistent or reliable joiner/mover/leaver processes applied. Coarse controls will therefore be applied by default to all B2B accounts to ensure that they are reviewed and re-certified on a regular basis. This coarse-grained control will be in addition to the finer-grained reviews and controls mandated in **Principle 6**.

#### How?

-   Standard baselines will be applied to all B2B accounts to ensure appropriate use
-   Baselines will be applied to all B2B accounts regardless of their use and owner
-   Rules

**Baseline controls for accounts**

| B2B Type |Condition | Control    | When applied |
| ----------- | ----------- | ----------- | ----------- |
|Provider/DfE user | B2B invite not accepted | Account Removed | 7 days |
|Provider/DfE user | B2B account not used | Account Disabled | 30 days |
|Individual | B2B account not used | Account Disabled | 7 days |
|All | Disabled B2B account not enabled | Account Removed | 30 days |

*Different baseline controls are applied to individual accounts as they are only used for a specific purpose and are short-lived*

**Baseline controls for account and role validation**

| B2B Type |Condition | Control    | When applied |
| ----------- | ----------- | ----------- | ----------- |
|Provider/DfE user | Privileged access recertification | Roles evaluated and updated | 3 Months*|
|Provider/DfE user | Data/system access recertification | Roles evaluated and updated | 3 Months|
|Provider/DfE user | B2B recertification | B2B account requirement validated | 6 Months |

* Note - maybe want to make the privileged access recertification more regular?


## 6. Carry out regular access reviews for B2B access

*B2B accounts must be reviewed regularly to ensure that access is valid and appropriate*

#### Why?

As stated in **Principles 1 and 2**, B2B accounts for providers or consumers will not have consistent or reliable joiner/mover/leaver processes applied. The onus is therefore on the resource owner to ensure that regular reviews are carried out for B2B accounts to ensure that access is still required and at the appropriate level. The reviews should be carried out by an appropriate system or data owner who has the responsibility and accountability for the service.

Access reviews will be subject to audit and will be used as part of any investigation into inappropriate access or data leakage so it is key that the process is followed correctly and is respected.


#### How?

-    Access reviews will be triggered at the agreed intervals as outlined in **Principle 5**
-    3 monthly access reviews will be carried out by the system or data owner
-    6 monthly access reviews and recertification will be carried out by the B2B account owner
-    System owners will be expected to review the B2B accounts and ensure that only those requiring to retain access are approved


## 7. Utilise coarse and fine-grained controls to manage access

*Policy-based access control will provide a broad control for access from appropriate networks, devices and locations*

#### Why?

Security controls are layered to provide a defence-in-depth approach to securing access to the Department's systems and data. Policy-based access controls will be used as coarse and fine-grained methods to ensure that access via a B2B account fits an accepted criteria and a standard pattern of behaviour. This provides a level of assurance that the B2B access is as expected and is not being used inappropriately.

Types of coarse-grained policy (for all or a wide range of B2B users) which will be applied are:
- Location
- Device
- Time window

Types of fine-grained policy (apps and/or role-specific) which will be applied are:
- Account type (Department issued vs B2B)
- Requirement for multi-factor authentication (MFA)
- ???


#### How?

Most/all of the implementation will be carried out via the central support teams to apply consistent controls.

-   Baseline controls will be applied as standard for B2B usage
-   Additional baseline controls will be applied depending on the level of access provided to the B2B account
-   Specific controls will be identified as part of assurance processes and applied
-   Additional controls will be added or existing controls amended depending on emerging threats

## 8. Monitor B2B accounts for inappropriate use

*B2B accounts must be monitored to protect against misuse and inappropriate activities*

#### Why?

As per **Principle 1**, we cannot guarantee assurance or security best practices for B2B accounts. Additional oversight is therefore required to ensure that we protect access to the Department's data and applications. The Department's identity protection solution will detect common inappropriate use patterns and identify compromised accounts and passwords.

The triggering of these alerts may result in an additional verification request (MFA, call, email) or the account being blocked, depending on the severity of the alert.

**Note** - *Some issues identified will require intervention either from the B2B user or from the user's support teams. The Department's IT teams will not be able to assist with this, and the account will remain restricted or blocked until this issue is resolved.*

#### How?

The implementation will be carried out via the central support teams to apply consistent controls.

-   Baseline identity protection will be provided for all B2B accounts
-   Controls invoked in the event of an event trigger will be applied depending on the level of access provided to the B2B account

## 9. B2B accounts will be bound by a Terms of Use agreement

*B2B account users will bound by a Terms of Use to ensure consistent behaviour and working practices*

#### Why?

Providing a Terms of Use is common practice within the Department when end-users are accessing their device or specific systems provided by the Department. The ToU provides a base set of best practice behaviour and expected working practices, and links to any policies which are relevant to the system or service being accessed.

This will extend to B2B guest users to ensure that they have a clear understanding of expectations from the Department and can align their behaviour and working practices as required when working for the Department. It will be necessary for B2B users to accept the Department's ToU, as this then provides an audited record for the acceptance of the working practices and also awareness of any monitoring and auditing activities whilst using data and systems provided by the Department.

#### How?

The implementation will be carried out via the central support team so no direct action is required. Project teams may want to share details of the ToU in advance of engagement with 3rd parties to ensure that they are aware of the terms and are able to adhere to them.


## 10. Limit access to Guest Inviter role and manage on a time-limited basis

*The ability to invite guests will be managed appropriately and only used when required*

#### Why?

A specific role has been created to enable users to invite 3rd party users into the Department's AzureAD tenant. The Guest Inviter role provides the ability to invite *any 3rd party user* into the Department's AzureAD directory, and once invited the 3rd party is able to access any system or data store which is managed via AZureAD. The Guest Inviter provides access via the "front-door" and whilst further authorisation is required to access data and systems it remains essential that the control of inviting guests is carefully managed and aligns to the principles outlined within this guide.

The Guest Inviter role will be held by the central operational teams responsible for Identity Management within the Department, providing a central service to manage 3rd party access to the Departments systems and data. It may also be appropriate for the role to be delegated to delivery teams who require the ability to manage 3rd party access into their solution due to the rate of change and/or the volume of 3rd party users requiring access to their system(s).

Users provided with the Guest Inviter role will be made aware of their responsibilities and accountability with this role, and all use will be audited to review appropriate use. The use of time-limited access is a further control which ensures that any use of the guest invite role is a conscious 'step-up' for the user and a useful reminder of the power this role provides. The role will also be subject to regular recertification as per the Department's standard operating procedures to ensure that the role is still required and is appropriate.

#### How?

-   Ensure that 3rd party access requirements are raised as part of the standard assurance processes
-   Aim to use the central support teams for managing 3rd party access wherever possible
-   Consider the support model for systems requiring 3rd party access and whether delegated access is required for delivery teams
-   If delegated access to invite guests is required, ensure that suitable dedicated resources are identified
-   Ensure that operational processes are defined within the relevant service which adhere to the principles within this guide

## 11. Consider licensing implications for the use of B2B accounts

*Costs can escalate if usage and licensing models are not well understood*

#### Why?

The cost models for the use of Guest accounts and their supporting services (MFA, Identity Protection etc) is designed to provide the optimal financial return for the vendor, and can be unclear and confusing. There are different tiers of service provided (Basic, Premium), the authentication service cost is charged based upon Monthly Active Users (MAU), with an initial volume provided as free, and costs generated for active users above this free allocation. Additional costs are also generated with the use of MFA, which is billed for each authentication attempt as 3rd party users access the Department's systems.

These costs are duplicated across different instances of the Department's AzureAD environments, meaning guest users who exist in two separate instances are billed as two individual costs for the Department. Whilst the costs for these additional uses appear small, the costs will quickly escalate when extrapolated across different environments and systems.

#### How?

-   Review the vendor's pricing plans for B2B usage and ensure that ongoing costs are included for the system
-   Consult with the Department's financial and contracts teams to review licensing implications
-   Consider re-use of existing central identity platforms wherever possible to avoid duplication of costs
-   Ensure that additional costs such as MFA are considered as part of ongoing costs, and the use of MFA is appropriate


## 12. Utilise the main AzureAD tenant for 3rd party accounts

*Centralise B2B usage to reduce costs and simplify management and assurance*

#### Why?
Management and monitoring of guest users, and enabling users to re-use their identity to access multiple services provided by the Department, is enabled by utilising the main Department AzureAD instance. This ensures that users are only invited once and provides a more consistent experience when accessing systems provided by the Department. This also provides the ability to share content and collaborate via the Department's standard collaboration and sharing platform via the same guest identity.

Monitoring and providing account lifecycle governance is more straightforward via a single instance as assurance and operational teams manage a single environment to gain oversight of all guest accounts. Joiner/mover/leaver processes can be managed via a single instance, enabling access to be managed or removed as required from a single location.

Licensing costs are also managed effectively via a single instance, as highlighted in **Principle 11**, as the single guest user account is part of the MAU allocation rather than being duplicated across multiple tenants and charged for several times.


#### How?

-   Ensure that services align to the standard AzureAD instance as the Identity Provider
-   Do not plan or design separate identity environments or platforms


## 14. Only permit internal use of B2B accounts from the primary AzureAD tenant

*A hub/spoke model for internal access simplifies management and reduces cost*

#### Why?
The Department has historically separated cloud environments using separate AzureAD instances, resulting in users managing numerous identities to access the different environments. This approach can be significantly simplified by utilising the main AzureAD instance as the hub, which contains the primary identity for users to access other environments. B2B will be utilised to enable access into the separate AzureAD instances, treating these as spoke 'resource' directories.

Benefits for this are similar to those identified within **Principle 11**, with improvements to end-user experience and enhanced security with a reduced number of accounts to manage. Alignment to this principle also supports and simplifies future consolidation of the numerous environments in the future.


#### How?

-   Align to the cloud instances which re-use the main AzureAD tenant, utilising separate tenants by exception only
-   Plan to remove existing tenant-specific identities and replace with B2B identities
-   Plan to re-use B2B identities in any new systems which are deployed outside of the main AzureAD instance
-   Do not create additional Identity directories without approval from the Cyber and InfoSec division
