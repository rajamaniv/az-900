# Cloud Concepts - Principles of cloud computing

## Intro

Cloud computing: like when turning on a light switch and you don't have to care about where or how the electricity is produced, delivered, etc

### Learning objectives

- Explore common cloud computing services
- Explore the benefits of cloud computing
- Decide which cloud deployment model is best for you

## What is cloud computing?

Renting resources on another company's computer. Only pay for what you use. Can add and remove resources as you need.

Basic services:

- compute power
- storage
- networking
- analytics

### Compute power

Compute power: No need to buy the hardware or install the OS, you can use a VM on a datacenter. Also, containers and serverless.

Containers: consistent, isolated execution environment for applications. Don't require guest OS.

Serverless: let you run application code without creating, configuring or maintaining a server. Application broken into separate functions, that runs when triggered. You only pay for the processing time used when they're running.

### Storage

Data read/write, which scales.

### Summary

Cloud computing is flexible and cost-efficient.

## Benefits of cloud computing

Not all or nothing, can use some parts only.

### Cost-effective

- Pay for what you need and only what you need
- No upfront costs
- No need to purchase and manage infra

### Scalable

Support both horizontal and vertical scaling

- Vertical scaling: "scaling up", adding resources to increase the power of an existing server, like more CPUs or RAM
- Horizontal scaling: "scaling out", adding more servers that function together as one unit

Can be automatic or manual following specific triggers.

### Elastic

Can automatically add more or less resources if and when needed.

### Current

Eliminates burden like maintaining software patch, hardware, etc.

### Reliable

Redundency is built in, great fault tolerence.

### Global

Datacenters in various region for better latency.

### Secure

- physical security: who can access the datacenter
- digital security: access control

### Summary

You spend more time building what matters, and less time managing.

## Compliance terms and requirements

When selecting a cloud provider to host your solution, understand that the provider can help you comply with regulations and standards. Ex:

- How compliant is the cloud provider when it comes to handling sensitive data?
- How compliant are the services offered by the cloud provider?
- How can I deploy my own cloud-based solutions to scenarios that have accreditation or compliance requirements?
- What terms are part of the privacy statement for the provider?

### Compliance offerings

Some of all that are available:

- Criminal Justice Information Service (CJIS)
- Cloud Security Alliance (CSA) STAR Certification
- General Data Protection Regulation (GDPR)
- EU Model Clauses
- Health Insurance Portability and Accountability Act (HIPAA)
- International Organization for Standarization (ISO) and International Electrotechnical Commission (IEC) 27018
- Multi-Tier Cloud Security (MTCS) Singapore
- Service Organization Controls (SOC) 1, 2 and 3
- National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)
- UK Government G-Cloud

## Economies of scale

Do thing more efficiently or at a lower-cost per unit when operating at a larger scale

## Capital expenditure (CapEx) vs operational expenditure (OpEx)

- CapEx: spending of money on physical infrastructure up front, and then deducting that expense from your tax bill over time. Upfront cost, value that reduces over time
- OpEx: spending of money on services or products now and being billed for them now

### CapEx computing costs

- Server costs
- Storage costs
- Network costs
- Backup and archive costs
- Organization continuity and disaster recovery costs
- Datacenter infrastructure costs
- Technical personnel

### OpEx cloud computing costs

- Leasing software and customized features
- Scaling charges based on usage/demand instead of fixed hardware or capcity
- Billing at the user or organization level

### Benefits of CapEx

Fixed costs, planned at the beginning of the project

### Benefits of OpEx

Pay as you go, more agile/elastic

## Cloud deployement models

3 models: public, private, hybrid

### Public cloud

#### Advantages

- high scalability/agility
- pay-as-you-go pricing
- You're not responsible for maintenance or updates of the hardware
- Minimal technical knowedge to set up and use

#### Disadvantages

- Specific security requirements that cannot be met using public cloud
- Governement policies, industry standards, or legal requirements which public clouds cannot meet
- YOu don't own the hardware or services and you cannot manage them as you want to
- Unique business requirements, such as having to maintain a legacy application might be hard to meet

### Private cloud

Made with Azure Stack

#### Advantages

- You can ensure the configuration can support any scenario or legacy application
- You have control (and responsability) over security
- Private cloud can meet strict security, compliance or legal requirements

#### Disadvantages

- Initial CapEx and must purchase the hardware
- Limited agility: to scale you must buy, install and setup new hardware
- Private clouds require IT skills and expertise that's hard to come by

### Hybrid cloud

For exemple website in public cloud connected to database in private cloud

#### Advantages

- Keep any systems running and accessible that use out-of-date hardware or out-of-date operating system
- You have flexibility with what you run locally versus in the cloud
- You can take advantage of the economies of scale from public cloud providers for services and resources where it's cheaper, and supplement with your own equipment when it's not
- You can use your own equipment to meet security, compliance or legacy scenarios where you need to completly control your environment

#### Disadvantages

- Can be more expensive that one deployment model since involves CapEx up front
- Can be more complicated to set up and manage

## Types of cloud services

Three major categories: IaaS, SaaS, PaaS

### Exploring the three categories of cloud computing

#### Infrastructure as a Services (IaaS)

Instead of buying hardware, you rent it. Ensuring that the service is up and running is a shared responsability.

Used in the following scenarios:

- migrating workloads: managed like on-premises infra, provide easy migration path
- test and development: can quickly set up and dismantle test and dev environment, bringing new app to market faster
- storage, backup and recovery: useful for managing unpredictable demand and steadily growing storage need. Also simplify the planning and management of backup and recovery system

#### Platform as a Service (PaaS)

Environment for building, testing and deploying software applications. Goal of PaaS is creating app quickly without managing infra.

Used in following scenarios:

- Development framework: provides framework that developers can build upon to develop or customize cloud-based applications. Cloud features such as scalability, high-availability, and multi-tenant capability are included.
- Analytics or BI: tools provided aaS with PaaS allow organizations to analyze and mine their data

#### Software as a Service (SaaS)

Software like Office 365, Skype, etc