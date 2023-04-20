# Secure Development

| Document Information |
---|
| Created: 23-03-2023 |
| Domain: Security |
| Author: paul.fitzgibbons@education.gov.uk
| References: |
| [GDL-??-??](../Guidelines/GDL-??-??.md) |
| ?? |
| ??

## Developing Secure Services

The Department is following a cloud-first strategy to host and run its digital services. Cloud enables the Department to take  of its digital services by consuming cloud services on-demand and scaling horizontally and vertically as required.

The use of cloud also provides benefits for the operational teams by reducing the need to manage traditional hosting and low-value activities and providing the ability to deploy and manage service at pace and scale.

## Use of the guidelines

This guideline is **level 1** and part of a hierarchy which will include use of  technologies, platforms and services which are related to this level 1 guideline. The information provided within will provide the broad guidelines which will apply to all corresponding guidelines within the hierarchy.

![Guidelines Hierarchy](../Guidelines/images/ESA-Guideline-Hierarchy.png)

This guideline is non-exhaustive in nature.  The rapid pace of development within the cloud means that new development practices may become available.

You should engage with [the architecture team](security.architecture@education.gov.uk) to discuss any novel approaches to development **BEFORE** you start any use or development activity.

**Alignment and exceptions** to the principles will be reviewed as part of assurance processes with the security and architecture professions to streamline governance, Exceptions will be approved or declined as relevant, with all decisions tracked with rationale for future reference.


## 1. Adhere to NCSC's Secure Development Principles

*Standard principles will provide the best-practice secure baselines for the Department's use of cloud platforms and services*

### Why?

The [NCSC](https://www.ncsc.gov.uk) have created principles for secure development.

Adherence to these principles within the Department ensures that we follow consistent and standard guidance and secure our code and pipelines appropriately.

### How?

* Refer to the [principles](https://www.ncsc.gov.uk/collection/developers-collection/principles) and review the principles against your service, platform or application
* Ensure system documentation refers to the NCSC development principles and explains how each area has been reviewed and addressed as appropriate
* Document and agree any non-compliance with the principles and how any non-compliance risks are mitigated
* Track ongoing change to the principles and ensure that funding is available to apply any future changes or updates

## 2. Use the Department's standard platforms and tools

*Aligning to standard platforms ensures consistent use of services with integration, operational oversight and security built-in*

### Why?

**The Department's strategic platform is Azure**. Utilising strategic platforms and tools ensures the Department:

* Protectively monitors services/systems
* Applies centrally managed controls
* Controls costs related to cloud platforms
* Applies suitable retention policies to satisfy legal and regulatory needs
* Provides appropriate business continuity and disaster recovery capability

Use of non-preferred platforms impacts on the Department's ability to achieve these goals and will also drive up costs with duplicated services and data ingress/egress costs

The use of non-standard cloud platforms will require delivery teams to provide their own operational services and ensure that all monitoring and security needs are met, which will increase operational costs for the Department by duplicating effort and capability.

### How?

* Always use the Department's standard cloud platform
* Follow guidance from architecture and operations team to identify existing standard technologies and patterns
* Utilise existing and mature services which are already integrated with our security and monitoring systems
* Engage with architecture and operational teams where required to request additional standard platforms and services are added

### Relates to the following DfE EA principles:

* [1 - Re-use services and components](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#1-re-use-services-and-components)

* [4 - Evaluate Total Cost of Ownership](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#4-evaluate-total-cost-of-ownership)

* [7 - Deliver a secure service](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#7-deliver-a-secure-service)

## 3. ??Register your source code repositories as Information Assets.

* Source code is:
  * Vital to business outcomes
  * Critical for the organisation to deliver its services
  * Not easily replaceable

Registering source code repositories on the [Information Asset Register](https://educationgovuk.sharepoint.com/sites/iac/SitePages/Information-Asset-Register.aspx) ensures that ownership and responsibility for the code continues to be managed even when staff change roles or leave the organisation.

## 4. Seek out vendor best practices and re-use

*Vendors typically invest heavily in security research and typically provide comprehensive documentation on best practices, we can leverage this to the departments advantage.*

### Why?
Adherence to best practice helps to reduce risk by following standard approaches.

### How?
Microsoft provide [guidance](https://learn.microsoft.com/en-us/azure/security/develop/secure-dev-overview) on how to develop and deploy secure applications on Azure.


## 5. Choose the right tool for the right job

*Just because you can, doesn't mean you should*

### Why?

DfE provide some flexibility in how environments can be operated, however just because something is possible, doesn't mean that it is advisable.

Utilising new and novel technologies might seem as an attractive option but can add further complexity to our environment with multiple ways for achieving the same outcome.

There may also be preferences to use services and capabilities which architects are more familiar with rather than existing standards, but whilst this meets a personal/local need it adds further complexity and cost for the Department due to duplicated and competing technologies which all need to be integrated into operational and security tooling, and which may need specialist skills to manage and maintain.

### How?

* Always review existing standards and patterns for re-use opportunities

* Engage with architecture teams who can advise on the selection and appropriate use of approved, supported and secured tools

* Review new capabilities with the architecture profession and the security architecture community for suitability and alignment with the Department's strategy

* When introducing new capabilities, ensure that opportunities to consolidate existing capabilities is part of this review to manage and minimise technical debt.

### Relates to the following DfE EA principles:

* [1 - Re-use services and components](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#1-re-use-services-and-components)

* [4 - Evaluate Total Cost of Ownership](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#4-evaluate-total-cost-of-ownership)

* [13 - Minimise technical debt](https://github.com/DFE-Digital/architecture/blob/master/principles/enterprise-architecture-principles.md#13-minimise-technical-debt)

## 6. Do not use preview features

*Preview features are still being tested and may be removed by the cloud provider*

### Why?

Cloud providers provide access to 'preview' features which are under development by a product group. The provider may choose to allow access to test the service and gain feedback (either directly or via service telemetry) so they can continue to iterate the service prior to it reaching General Availability (GA).

Some preview features may be pulled by the vendor in the future due to feedback or a change in strategy, they may also be provided free-of-charge during the preview period but then subject to an additional license charge when reaching GA, generating unplanned costs for the Department.

It is also key to note that the vendor does not provide any suppport for preview features, so any service which uses a preview feature will be impacted if a preview feature is used and subsequently fails.

### How?

* Review the guidance from Microsoft for the managemnt of [Preview Features in Azure](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/preview-features?tabs=azure-portal)

* Evaluate preview features in development or test environments to safely review features and benefits as part of a future strategyic activity to adopt the service or feature once it reaches GA

* Do not use preview features for any workloads in pre-prod/prod or environments which have access to production data

* Ensure that you understand any future pricing model for the preview feature and ensure that these costs are included in the budget plans for your service

* Prepare for changes to or removal of preview features and ensure that you have a 'plan B' to ensure that services are not completely dependent on a specific preview feature

## 7. Use Infrastructure as code for deployment 
*Infrastructure as Code ensures repeatable builds and deterministic deployments*

### Why?
Use of standardised configuration tools, reduces costs to the department, improves the efficiency of training and reduces costs for security testing

### How?
* Review level 2 guidance.
* Review level 3 guidance (patterns)
* Review vendor guidance.
Review vendor guidance: https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/syntax


## 8. Plan for migration from non-standard CI/CD pipelines
*Use of non standard tools/pipelines increases risk to the Department*

### Why?
Standard pipelines benefit from central management and visibility of security controls.

### How?
Engage with the architecture team who will be able to advise.



