# CIS Control 1

| Document Information |
------------------------|
| Category: Assurance Guidance |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |

## Control 1.1

| Asset Type | Security Function | Title| 
---| ---| ---|
| Devices | Identify | Establish and Maintain Detailed Enterprise Asset Inventory

### The Control

Establish and maintain an accurate, detailed, and up-to-date inventory of all enterprise assets with the potential to store or process data, to include: end-user devices (including portable and mobile), network devices, non-computing/IoT devices, and servers.

Ensure the inventory records the network address (if static), hardware address, machine name, enterprise asset owner, department for each asset, and whether the asset has been approved to connect to the network. For mobile end-user devices, MDM type tools can support this process, where appropriate.

This inventory includes assets connected to the infrastructure physically, virtually, remotely, and those within cloud environments. Additionally, it includes assets that are regularly connected to the enterprise’s network infrastructure, even if they are not under control of the enterprise. Review and update the inventory of all enterprise assets bi-annually, or more frequently.

### Why it is required

Inventory is important, gives us a full view of the estate etc.

Link to NCSC's guidance, ISO27001 etc - know your estate, if you don't know your assets how can you secure etc.

### How it is achieved

* CMDB
* SBOMs
* Integration via CI/CD
* Pulling info from tooling
  * SolarWinds
  * Palo Alto
  * Azure

>Link to guideline goes here

## Control 1.2

| Asset Type | Security Function | Title| 
---| ---| ---|
| Devices |Respond |Address Unauthorized Assets |

### The Control
Ensure that a process exists to address unauthorized assets on a weekly basis. The enterprise may choose to remove the asset from the network, deny the asset from connecting remotely to the network, or quarantine the asset.

### Why it is required

Keep an updated record of what's on the estate and remove stuff which shouldn't be there. Helps to highlight unauthorised stuff etc.

### How it is achieved

*TBC at present for an enterprise-wide approach, no consistent way of doing this, onus on the servers keeping their records up to date*
