# Cloud Storage

| Document Information |
---|
| Category: Architecture Guidelines |
| Created: 21-02-2023 |
| Domain: Security |
| Author: paul.fitzgibbons@education.gov.uk |
| References: |
| [GDL-IDE001-Authentication-principles](../Guidelines/GDL-IDE001-Authentication-principles.md) |
| [GDL-SEC005-Cloud-Platforms](../Guidelines/GDL-SEC005-Cloud-Guidelines.md) |
| [PAT-SEC001-Cloud-Storage](../Patterns/PAT-SEC001-Cloud-Storage.md) |

>tl;dr use Microsoft Azure for cloud storage services

## Working with Cloud Storage

Cloud storage offers systems and users the ability to create, read, update and delete data, that would have traditionally been held on disk, tape or other formats, using the internet.

This allows data to be accessed without geographical restrictions and takes advantages of the scalability and flexibility cloud service providers offer.

These guidelines focus on cloud storage used by systems hosted on cloud platforms, cloud storage for unstructured and/or direct end-user access will be covered in separate guidelines and guidance identified in the references.

Storage for SQL and other database technologies are not in-scope for these guidelines, these will be covered in separate guidelines and guidance identified in the references.

## Use of the guidelines

This guideline is **level 2** and part of a hierarchy which inherits the guidelines from its corresponding [**level 1** guideline](../Guidelines/GDL-SEC005-Cloud-Guidelines.md). The information provided within provides  specfic guidelines for the specific technology or capability area underneath the **level 1** guideline.

![Guidelines Hierarchy](../Guidelines/images/ESA-Guideline-Hierarchy.png)

This guideline is intended for Civil Servants, contract/contingent workers and Managed Service Providers (MSPs).

This guideline is non-exhaustive in nature.  The rapid pace of development within the cloud means that new storage mechanisms may become available.  

You should engage with [the architecture team](mailto:security.architecture@education.gov.uk) to discuss any novel approaches to storage **BEFORE** you start any use or development activity.

**Aligment and exceptions** to the principles will be reviewed as part of assurance processes with the security and architecture professions to streamline governance, Exceptions will be approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested initially via the Architecture Community of Interest, and in the future with standard updates and iterations via GitHub.

## 1. Refer to the Level 1 guidance for Cloud Platforms

*The Cloud Platforms guidelines provide the baseline security and best practices*

### Why

Level 1 guidelines have been created to provide broad security guidelines for the correct use of cloud platforms within the Department. These apply across all cloud platforms to provide a secure and consistent baseline.

Applying these guidelines to architecture, design and deployment activities will simplify governance and compliance activities and allow teams to shift-left their assurance activities, reducing the burden on their teams and costs for the Department.

### How

* Follow the level 1 guidelines [here](../Guidelines/GDL-SEC005-Cloud-Guidelines.md)
* Review these guidelines along with the more specific guidelines to ensure your service will meet the standard best practice configuration expected by the Department

## Appendix A - AzureAD built-in roles

| Role| Description | Approval | MFA | Time-limited|
---| ---| ---| ---| --|
| Application Administrator | Can create and manage all aspects of app registrations and enterprise apps. | PIM self-approval | soft-token |
| Application Developer | Can create application registrations independent of the 'Users can register applications' setting |PIM self-approval| soft-token |
|Attack Payload Author|Can create attack payloads that an administrator can initiate later.|tbc| tbc|
|Attack Simulation Administrator|Can create and manage all aspects of attack simulation campaigns.|tbc| tbc|
|Attribute Assignment Administrator|Assign custom security attribute keys and values to supported Azure AD objects.|tbc| tbc|
|Attribute Assignment Reader|Read custom security attribute keys and values for supported Azure AD objects.|tbc| tbc|
|Attribute Definition Administrator|Define and manage the definition of custom security attributes.|tbc| tbc|
|Attribute Definition Reader|Read the definition of custom security attributes |tbc| tbc|
|Authentication Administrator|Can access to view, set and reset authentication method information for any non-admin user.|tbc| tbc|
|Authentication Policy Administrator|Can create and manage the authentication methods policy, tenant-wide MFA settings, password protection policy, and verifiable credentials.|tbc| tbc|
|Azure AD Joined Device Local Administrator|Users assigned to this role are added to the local administrators group on Azure AD-joined devices.|tbc| tbc|
|Azure DevOps Administrator|Can manage Azure DevOps policies and settings.|tbc| tbc|
|Azure Information Protection Administrator|Can manage all aspects of the Azure Information Protection product.|tbc| tbc|
|B2C IEF Keyset Administrator|Can manage secrets for federation and encryption in the Identity Experience Framework (IEF).|tbc| tbc|
|B2C IEF Policy Administrator|Can create and manage trust framework policies in the Identity Experience Framework (IEF).|tbc| tbc|
|Billing Administrator|Can perform common billing related tasks like updating payment information.|tbc| tbc|
|Cloud App Security Administrator|Can manage all aspects of the Defender for Cloud Apps product.|tbc| tbc|
|Cloud Application Administrator|Can create and manage all aspects of app registrations and enterprise apps except App Proxy.|tbc| tbc|
|Cloud Device Administrator|Limited access to manage devices in Azure AD.|tbc| tbc|
|Compliance Administrator|Can read and manage compliance configuration and reports in Azure AD and Microsoft 365.|tbc| tbc|
|Compliance Data Administrator|Creates and manages compliance content.|tbc| tbc|
|Conditional Access Administrator|Can manage Conditional Access capabilities.|tbc| tbc|
|Customer LockBox Access Approver|Can approve Microsoft support requests to access customer organizational data.|tbc| tbc|
|Desktop Analytics Administrator|Can access and manage Desktop management tools and services.|tbc| tbc|
|Directory Readers|Can read basic directory information. Commonly used to grant directory read access to applications and guests.|tbc| tbc|
|Directory Synchronization Accounts|Only used by Azure AD Connect service.|tbc| tbc|
|Directory Writers|Can read and write basic directory information. For granting access to applications, not intended for users.|tbc| tbc| tbc|
|Domain Name Administrator|Can manage domain names in cloud and on-premises.|tbc| tbc|
|Dynamics 365 Administrator|Can manage all aspects of the Dynamics 365 product.|tbc| tbc|
|Edge Administrator|Manage all aspects of Microsoft Edge.|tbc| tbc|
|Exchange Administrator|Can manage all aspects of the Exchange product.|PIM admin approval| physical token|
|Exchange Recipient Administrator|Can create or update Exchange Online recipients within the Exchange Online organization.|tbc| tbc|
|External ID User Flow Administrator|Can create and manage all aspects of user flows.|tbc| tbc|
|External ID User Flow Attribute Administrator|Can create and manage the attribute schema available to all user flows.|tbc| tbc|
|External Identity Provider Administrator|Can configure identity providers for use in direct federation.|tbc| tbc|
|Global Administrator|Can manage all aspects of Azure AD and Microsoft services that use Azure AD identities.|PIM admin approval| physical token|
|Global Reader|Can read everything that a Global Administrator can, but not update anything.|PIM admin approval| physical token|
|Groups Administrator|Members of this role can create/manage groups, create/manage groups settings like naming and expiration policies, and view groups activity and audit reports.|tbc| tbc| tbc|
|Guest Inviter|Can invite guest users independent of the 'members can invite guests' setting.|tbc| tbc| tbc|
|Helpdesk Administrator|Can reset passwords for non-administrators and Helpdesk Administrators.|tbc| tbc| tbc|
|Hybrid Identity Administrator|Can manage AD to Azure AD cloud provisioning, Azure AD Connect, Pass-through Authentication (PTA), Password hash synchronization (PHS), Seamless Single sign-on (Seamless SSO), and federation settings.|tbc| tbc| tbc|
|Identity Governance Administrator|Manage access using Azure AD for identity governance scenarios.|tbc| tbc| tbc|
|Insights Administrator|Has administrative access in the Microsoft 365 Insights app.|tbc| tbc| tbc|
|Insights Analyst|Access the analytical capabilities in Microsoft Viva Insights and run custom queries.|tbc| tbc| tbc|
|Insights Business Leader|Can view and share dashboards and insights via the Microsoft 365 Insights app.|tbc| tbc| tbc|
|Intune Administrator|Can manage all aspects of the Intune product.|tbc| tbc| tbc|
|Kaizala Administrator|Can manage settings for Microsoft Kaizala.|tbc| tbc| tbc|
|Knowledge Administrator|Can configure knowledge, learning, and other intelligent features.|tbc| tbc| tbc||tbc| tbc| tbc|
|Knowledge Manager|Can organize, create, manage, and promote topics and knowledge.|tbc| tbc| tbc|
|License Administrator|Can manage product licenses on users and groups.|tbc| tbc| tbc|
|Lifecycle Workflows Administrator|Create and manage all aspects of workflows and tasks associated with Lifecycle Workflows in Azure AD.|tbc| tbc| tbc|
|Message Center Privacy Reader|Can read security messages and updates in Office 365 Message Center only.|tbc| tbc| tbc|
|Message Center Reader|Can read messages and updates for their organization in Office 365 Message Center only.|tbc| tbc| tbc|
|Microsoft Hardware Warranty Administrator|Create and manage all aspects warranty claims and entitlements for Microsoft manufactured hardware, like Surface and HoloLens.|tbc| tbc| tbc|
|Microsoft Hardware Warranty Specialist|Create and read warranty claims for Microsoft manufactured hardware, like Surface and HoloLens.|tbc| tbc| tbc|
|Modern Commerce User|Can manage commercial purchases for a company, department or team.|tbc| tbc| tbc|
|Network Administrator|Can manage network locations and review enterprise network design insights for Microsoft 365 Software as a Service applications.|tbc| tbc| tbc|
|Office Apps Administrator|Can manage Office apps cloud services, including policy and settings management, and manage the ability to select, unselect and publish 'what's new' feature content to end-user's devices.|tbc| tbc| tbc|
|Organizational Messages Writer|Write, publish, manage, and review the organizational messages for end-users through Microsoft product surfaces.|tbc| tbc| tbc|
|Partner Tier1 Support|Do not use - not intended for general use.|tbc| tbc| tbc|
|Partner Tier2 Support|Do not use - not intended for general use.|tbc| tbc| tbc|
|Password Administrator|Can reset passwords for non-administrators and Password Administrators.|tbc| tbc| tbc|
|Permissions Management Administrator|Manage all aspects of Entra Permissions Management.|tbc| tbc| tbc|
|Power BI Administrator|Can manage all aspects of the Power BI product.|tbc| tbc| tbc|
|Power Platform Administrator|Can create and manage all aspects of Microsoft Dynamics 365, Power Apps and Power Automate.|tbc| tbc| tbc|
|Printer Administrator|Can manage all aspects of printers and printer connectors.|tbc| tbc| tbc|
|Printer Technician|Can register and unregister printers and update printer status.|tbc| tbc| tbc|
|Privileged Authentication Administrator|Can access to view, set and reset authentication method information for any user (admin or non-admin).|tbc| tbc| tbc|
|Privileged Role Administrator|Can manage role assignments in Azure AD, and all aspects of Privileged Identity Management.|tbc| tbc| tbc|
|Reports Reader|Can read sign-in and audit reports.|tbc| tbc| tbc|
|Search Administrator|Can create and manage all aspects of Microsoft Search settings.|tbc| tbc| tbc|
|Search Editor|Can create and manage the editorial content such as bookmarks, Q and As, locations, floorplan.|tbc| tbc| tbc|
|Security Administrator|Can read security information and reports, and manage configuration in Azure AD and Office 365.|tbc| tbc| tbc|
|Security Operator|Creates and manages security events.|tbc| tbc| tbc|
|Security Reader|Can read security information and reports in Azure AD and Office 365.|tbc| tbc| tbc|
|Service Support Administrator|Can read service health information and manage support tickets.|tbc| tbc| tbc|
|SharePoint Administrator|Can manage all aspects of the SharePoint service.|tbc| tbc| tbc|
|Skype for Business Administrator|Can manage all aspects of the Skype for Business product.|tbc| tbc| tbc|
|Teams Administrator|Can manage the Microsoft Teams service.|tbc| tbc| tbc|
|Teams Communications Administrator|Can manage calling and meetings features within the Microsoft Teams service.|tbc| tbc| tbc|
|Teams Communications Support Engineer|Can troubleshoot communications issues within Teams using advanced tools.|tbc| tbc| tbc|
|Teams Communications Support Specialist|Can troubleshoot communications issues within Teams using basic tools.|tbc| tbc| tbc|
|Teams Devices Administrator|Can perform management related tasks on Teams certified devices.|tbc| tbc| tbc|
|Tenant Creator|Create new Azure AD or Azure AD B2C tenants.|tbc| tbc| tbc|
|Usage Summary Reports Reader|Can see only tenant level aggregates in Microsoft 365 Usage Analytics and Productivity Score.|tbc| tbc| tbc|
|User Administrator|Can manage all aspects of users and groups, including resetting passwords for limited admins.|tbc| tbc| tbc|
|Virtual Visits Administrator|Manage and share Virtual Visits information and metrics from admin centers or the Virtual Visits app.|tbc| tbc| tbc|
|Viva Goals Administrator|Manage and configure all aspects of Microsoft Viva Goals.|tbc| tbc| tbc|
|Windows 365 Administrator|Can provision and manage all aspects of Cloud PCs.|tbc| tbc| tbc|
|Windows Update Deployment Administrator|Can create and manage all aspects of Windows Update deployments through the Windows Update for Business deployment service.|tbc| tbc| tbc|
|Yammer Administrator|Manage all aspects of the Yammer service.|tbc| tbc| tbc|