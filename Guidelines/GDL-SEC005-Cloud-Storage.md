# Cloud Storage

| Document Information |
---|
| Category: Architecture Guidelines |
| Created: 21-02-2023 |
| Domain: Security |
| Author: paul.fitzgibbons@education.gov.uk |
| References: |
| GDL-IDE001-Authentication-principles |
| GDL-SEC005-Cloud-Storage |

>tl;dr use Microsoft Azure for cloud storage services

## Working with Cloud Storage

Cloud storage offers systems and users the ability to create, read, update and delete data, that would have traditionally been held on disk, tape or other formats, using the internet.

This allows data to be accessed without geographical restrictions and takes advantages of the scalability and flexibility cloud service providers offer.

>These guidelines focus on cloud storage used by systems hosted on cloud platforms, cloud storage for unstructured and/or direct end-user access will be covered in separate guidelines and guidance.

>SQL and other database technologies are not in-scope for these guidelines, these will be covered in separate guidelines and guidance.

### Choosing the right tool for the right job

Just because it can be done - doesn't mean it should be done.  DfE provide some flexibility in how environments can be operated, however just because something is possible, doesn't mean that it is advisable. Architecture teams can advise on the selection and appropriate use of approved, supported and secured tools.

## Use of the guidelines

This guideline is intended for Civil Servants, contract/contingent workers and Managed Service Providers (MSPs).

This guideline is non-exhaustive in nature.  The rapid pace of development within the cloud means that new storage mechanisms may become available.  

You should engage with [the architecture team](security.architecture@education.gov.uk) to discuss any novel approaches to storage **BEFORE** you start any use or development activity.

**Aligment and exceptions** to the principles will be reviewed as part of assurance processes with the security and architecture professions to streamline governance, Exceptions will be approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested initially via the Architecture Community of Interest, and in the future with standard updates and iterations via GitHub.

## 1. Use the Department's standard cloud provider by default

*Aligning to standard platforms ensures consistent use of services with integration and security built-in*

### Why
**The Department's strategic platform for storage is Microsoft Azure**. Utilising this platform ensures the Department can:

* Protectively monitor services/systems
* Apply centrally managed controls
* Control costs related to cloud platforms
* Apply suitable retention policies to satisfy legal and regulatory needs
* Provide appropriate business continuity and disaster recovery capability

Use of non-preferred platforms impacts on the Department's ability to achieve these goals and will also drive up costs with duplicated services and data ingress/egress costs

### How

* Follow guidance from architecture and operations team
* Utilise existing and mature services which are already integrated with our security and monitoring systems

## 2. Utilise appropriate storage services

*Microsoft Azure is DfE's preferred platform for services and systems.*

[Microsoft Azure Storage](https://learn.microsoft.com/en-us/azure/storage/common/storage-introduction)

Microsoft have a variety of storage services available:

* Azure Blobs: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake Storage Gen2.

* Azure Files: Managed file shares for cloud or on-premises deployments.

>**remove as in preview** Azure Elastic SAN (preview): A fully integrated solution that simplifies deploying, scaling, managing, and configuring a SAN in Azure.

> * Azure Queues: A messaging store for reliable messaging between application components. **This isn't really a storage solution**

> **Suggest that we keep DB technologies in a seperate set of guidelines** Azure Tables: A NoSQL store for schemaless storage of structured data.

>**is the focus for this guideline PaaS or IaaS? Think we need to stick with one and cover IaaS separately** * Azure Disks: Block-level storage volumes for Azure VMs.

### Azure Blobs

[Follow Security recommendations for blob storage](https://learn.microsoft.com/en-us/azure/storage/blobs/security-recommendations)
[Follow Azure Security Baseline for Storage](https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/storage-security-baseline?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json%3Ftoc%3D%2Fazure%2Fstorage%2Fblobs%2FTOC.json)

#### Azure Blobs - Data Protection

* Use the Azure Resource Manager deployment model
* Enable Microsoft Defender for all of your storage accounts
* Turn on soft delete for blobs
* Turn on soft delete for containers
* Lock storage account to prevent accidental or malicious deletion or configuration changes
* Store business-critical data in immutable blobs
* Require secure transfer (HTTPS) to the storage account
* Limit shared access signature (SAS) tokens to HTTPS connections only

#### Azure Blobs - Identity and Access Management

* Please also refer to [GDL-IDE001-Authentication-Principles](https://github.com/DFE-Digital/Enterprise-Security-Architecture/blob/main/Guidelines/GDL-IDE001-Authentication-principles.md)
* Use Azure Active Directory (Azure AD) to authorize access to blob data
* Keep in mind the principle of least privilege when assigning permissions to an Azure AD security principal via Azure RBAC
* Use a user delegation SAS to grant limited access to blob data to clients
* Secure your account access keys with Azure Key Vault
* Regenerate your account keys periodically
* Disallow Shared Key authorization
* Keep in mind the principle of least privilege when assigning permissions to a SAS
* Have a revocation plan in place for any SAS that you issue to clients
* If a service SAS is not associated with a stored access policy, then set the expiry time to one hour or less
* Disable anonymous public read access to containers and blobs

#### Azure Blobs - Networking

* Configure the minimum required version of Transport Layer Security (TLS) for a storage account.
* Enable the Secure transfer required option on all of your storage accounts
* Enable firewall rules
* Allow trusted Microsoft services to access the storage account
* Use private endpoints
* Use VNet service tags
* Limit network access to specific networks
* Configure network routing preference

#### Azure Blobs - Logging and Monitoring

* Track how requests are authorized
* Set up alerts in Azure Monitor

### Azure Files

Recommendation: Speak to Architecture and Infrastructure team

### Azure Elastic SAN

>suggest remove this as currently in preview

Recommendation: do not use services in preview monitor to see if they become generally available.

>we need a general principle about cloud usage which states that preview features are not to be used, then we don't need to call out here.

### Azure Queues

Out of scope for this guideline document.

### Azure Tables

Out of scope for this guideline document.

### Azure Disks

Recommendation: Speak to Architecture and Infrastructure team

### Onedrive

Out of Scope for this document. Refer to support information on Sharepoint Intranet.

## 2. Amazon Web Services (AWS)

**The Department's preferred platform for storage is Microsoft Azure**, this is where the majority of our data/information should be stored.  Use of non-preferred platforms impacts on the Department's ability to:

* protectively monitor services/systems
* Apply centrally managed controls
* Control costs related to cloud platforms
* Apply suitable retention policies to satisfy legal and regulatory needs
* Provide appropriate business continuity and disaster recovery capability

### Why?

Poorly configured cloud storage can result in:

* Inappropriate access to information
* Unauthorised changes to information
* Loss or deletion of information

**If you are using AWS storage within your service/application, please work with your architecture partner to assess migration or exception.**

Amazon provide a wide range of cloud storage services including:

* Amazon Elastic Block Store
* Amazon Elastic File System
* Amazon FSx for Lustre
* Amazon FSx for NetApp ONTAP
* Amazon FSx for Windows File Server
* Amazon FSx for OpenZFS 
* Amazon S3
* AWS Backup
* AWS DataSync
* AWS Snowball
* AWS Snowcone
* AWS Snowmobile
* AWS Storage Gateway
* AWS Transfer Family
* [AWS Documentation](https://aws.amazon.com/documentation-overview/?nc2=h_ql_doc_do)


### Amazon S3 Object Storage

[Amazon Web Services (AWS) S3 object storage](https://aws.amazon.com/documentation-overview/s3/)

### How

* Follow [Amazon Best Practice](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html)
* Use correct policies
* Block public access
* Implement least privilege access
* Use IAM roles for applications and AWS services that require Amazon S3 access
* Select an appropriate encryption strategy
* Consider encryption of data at rest
* Enforce encryption of data in transit
* Consider S3 Object Lock
* Enable versioning
  * Consider implementing on-going detective controls
* Apply an appropriate retention policy
* Consider Amazon S3 cross-region replication
* Consider VPC endpoints for Amazon S3 access
* Use managed AWS services to receive actionable findings in your AWS accounts
* Identify and audit all your Amazon S3 buckets
* Implement monitoring using AWS monitoring tools
* Enable Amazon S3 server access logging
* Use AWS CloudTrail
* Enable AWS Config
* Consider using Amazon Macie with Amazon S3
* Monitor AWS security advisories
* Still reading, wouldn't it just be easier to use Azure Storage?

## 3. Other Cloud Storage Providers

* Dropbox
* Google Drive
* Google Cloud Storage
* others not listed within this document

Not supported
Contact Architecture team **BEFORE** you start design/development work.