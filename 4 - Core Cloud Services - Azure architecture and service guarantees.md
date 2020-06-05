# Core Cloud Services - Azure architecture and service guarantees

## Introduction

Situation: small business owner with great set of web based services. Clients are experiencing network lag accessing from distant location. Azure allows you to gain globl reach with local presence.

Learning objectives:

- Explore the physical structure of Azure infrastructure
- Understand the service level agreements (SLA) provided by Azure
- Learn how to provide SLA for your apps

## Understand Datacenters and Regions in Azure

Azure is made up of datacenters around the globe. Datacenters aren't exposed to end user directly, Azure organizes them into regions.

### What is a region?

Geographical area on the planet containing one to multiple datacenters that are nearby and networked together.

Regions helps you bring applications closer to your users. Also provides better scalability, redundancy, and preserves data residency.

### Special Azure regions

- US DoD Central, US Gov Virginia, US Gov Iowa and more: special network-isolated instances for US governement agencies and partners
- China East, China North and more: available through unique partnership between Microsoft and 21Vianet, whereby Microsoft does not directly maintain the datacenters

## Understand Geographies in Azure

Azure divides the world into geographies that are defined by geopolitical boundaries or country borders. An Azure geography is a discrete market typically containing two or more regions that preserve data residency and compliance boundaries. Several benefits:

- Geographies allow customers with specific data residency and compliance needs to keep their data and application close
- Geographies ensure that data residency, sovereignty, compliance and resiliency requirements are honored within geographical boundaries
- Geographies are fault-tolerant to ithstand complete region failure through their connection to dedicated high-capacity networking infrastructure

Geographies are broken up into the following areas:

- Americas
- Europe
- Asia Pacific
- Middle East and Africa

## Understand Availability Zones in Azure

### What is an Availability Zone?

Availability Zones are physically separate datacenters within an Azure region. Each made up of one or more datacenter with independant power, cooling and networking. Connected through high-speed, private fiber-optic networks.

### Using Availability Zones in your apps

Primarly for VMs, managed disks, load balancers and SQL databases. Two categories of Azure services that support Availability Zones:

- Zonal services: you pin the resource to a specific zone
- Zone-redundant services: platform replicates automatically across zones (ex: zone-redundant storage, SQL Database)

## Understand Region Pairs in Azure

### What is a region pair?

Each region always paired with another region in the same geography at least 300 miles away. Allows for replication of resources and reduces the likelihood of interruptions.

## Understand Service-Level Agreements for Azure

- SLAs describe Microsoft's commitment to providing Azure customers with specific performance standards
- There are SLAs for individual Azure products and services
- SLA also specify what happens if a service or product fails to perform to a governing SLA's specification

### SLA for Azure products and services

Three key characteristics:

- Performance Targets
- Uptime and Connectivity Guarantees
- Service credits

#### Performance targets

Uptime guarantees, connectivity rate. Specific to each product or service

#### Uptime and connectivity guarantees

From "three nines" (99.9%) to "five nines" (99.999%)

#### Service credits

If performs under uptime, Azure applies a discount to the bill.

### Compose SLAs across services.

Mutliply between layers, calculate layers with possibility of simultaneous failure.

## Improve your app reliability in Azure

### Understand your app requirements

Need to know the workload requirements.

### Resiliency

Recovering from failures when they happen.

### Cost and complexity vs high availability

The more availability you want, the more complex and costly the system becomes

### Consideration for defining application SLAs

- If your app SLA has 4 nines, recovery from failure by manual intervention may not be enough
