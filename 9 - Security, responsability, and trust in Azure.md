# Security, responsability, and trust in Azure

## Introduction

### Learning objectives

In this module, you will learn how:

- Security resonsibility is shared with Azure
- Identity management provides protection, even outside your network
- Encryption capabilities built into Azure can protect your data
- To protect your network and virtual network

## Cloud security is a shared responsibility

Responsibility for security shared by the customer and the cloud provider.

### Security is a shared responsability

First shift: on-premises to IaaS. Still responsible to patch and secure the OS and software, as well as configure your network to be secure.

Moving to PaaS: Azure takes care of the OS and most foundational software like DBMS. Everything updated with the latest security patches.

Moving to SaaS: outsource almost everything. SaaS is software that runs with an internet infrastructure. Ex: Office 365

Regardless of the deployment type, you always retain responsibility for the following items:

- Data
- Endpoints
- Accounts
- Access managment

### A layered approach to security

Defense in depth: series of mechanisms to slow the advance of an attack aimed at acquiring unauthorized access to information. Each layer provides protection so that if one layer is breached, a subsequent layer is already in place.

#### Data

In almost all cases, attackers are after data:

- Stored in a database
- Stored on disk inside virtual machines
- Stored on a SaaS application such as Office 365
- Stored in cloud storage

#### Application

- ensure applications are secure and free of vulnerabilities
- store sensisitive application secrets in a secure storage medium
- make security a design requirement for all application development

#### Compute

- secure access to virtual machines
- implement endpoint protection and keep systems patched and current

#### Networking

- limit communication between resources
- deny by default
- restrict inbound internet access and limit outbound, where appropriate
- implement secure connectivity to on-premises network

#### Perimeter

- use DDoS protection to filter large-scale attacks before they can cause a denial of service for end users
- use perimeter firewalls to identify and alert on malicious attacks against your network

#### Identity and access

- control access to infrastructure and change control
- use single sign-on and multi-factor authentication
- audit events and changes

#### Physical security

- physical building security and controlling access to computing hardware within the data center is the first line of defense

## Get tips from Azure Security Center

Security Center: monitoring service that provides threat protection across all of your services both in Azure and on-premises. Security Center can:

- Provide security recommandations based on your configurations, resources, and networks
- Monitor security settings across on-premises and cloud workloads, and automatically apply required security to new services as they come online
- Continuously monitor all your services, and perform automatic security assessments to identify potential vulnerabilities before they can be exploited
- Use machine learning to detect and block malware from being installed on your virtual machines and services. You can also define a list of allowed applications to ensure that only the apps you validate are allowed to execute
- Analyze and identify potential inbound attacks, and help investigate threates and any post-breach activity that might have occured
- Provide just-in-time access control for ports, reducing your attack surface by ensuring the network only allows traffic that you require

### Available tiers

Azure Security Center is available in two tiers:

1. Free: Available as part of your Azure subscription, limited to assessments and recommendations of Azure resources only
2. Standard: This tier provides a full suite of security-related services including continuous monitoring, threat detection, just-in-time access control for ports, and more. 15$ per node per month

### Usage scenarios

You can integrate Security Center into your workflows and use it in many ways

1. Use Security Center for incident response
2. Use Security Center recommandations to enhance security

## Identity and access

Before: network perimeters, firewalls, physical acces control as primary protection for corporate data. With Bring Your Own Device (BYOD), mobile apps and cloud applications -> network becomes porous.

### Authentication and authorization

- Authentication is the process of establishing the identity of a person or service looking to access a resource. It involves the act of challenging a party for legitimate credentials, and provides the basis for creating a security principal for identity and access control use. It establishes if they are who they say they are
- Authorization is the process of establishing what level of access an authenticated person or service has. It specifies what data they're allowed to access and what they can do with it

- Authentication -> AuthN
- Authorization -> AuthZ

### What is Azure Active Directory?

Azure AD is a cloud-based identity service. Has built in support for synchronizing with your existing on-premises Active Directory or can be used stand-alone. Means all applications, wether on-prem or in the cloud, can share the same credentials.

Azure AD provides services such as:

- Authentication: includes verifying identity to access applications and resources, and providing functionality such as self-service password reset, multi-factor authentication (MFA), a custom banned password list, and smart lockout services
- Single-Sign-On (SSO): enables user to remember only one ID and one password to access multiple applications. A single identity is tied to a user, simplifying the security model. As user change roles or leave an organization, access modifications are tied to that identity, greatly reducing the effort needed to change or disable accounts
- Application management: You can manage your cloud and on-premises apps using Azure AD Application Proxy, SSO, the My app portal (also referred to as Access panel), and SaaS apps
- Business to business (B2B) identity services: Manage your guest users and external partners while maintaining control over your own corporate data
- Business to customer (B2C) identity services: Customize and control how users sign up, sign in, and manage their profiles when using your apps with services
- Device Management: Manage how your cloud or on-premises devices access your corporate data

### Multi-factor authentication

MFA provides additional security for your identities by requireding two or more elements for full authentication. Three categories:

- Something you know: password, answer to security question
- Something you are: mobile app with notification or token
- Something you possess: biometric property, like fingerprint or face scan

### Providing identities to services

#### Services principals

An identity is a thing that can be authenticated. This includes users with a user name and password, but can also include applications or servers, which might authenticate with secret keys or certificates.

A principal is an identity acting with certain roles or claims. Usually, it is not useful to consider identity and principal separately, but think of using "sudo" on a Bash prompt in Linux or on Windows using "run as Administrator". In both cases, you are still logged in as the same identity as before, but you've changed the role under which you are executing. Groups are often considered principles because they can have rights assigned.

A service principal is an identity that is used by a service or application. And like other identities, it can be assigned roles.

#### Managed identities for Azure services

Managed identities for Azure makes creating service principal easier.

### Role-based access control

Roles are sets of permissions like "Read-only" or "Contributor" that users can be granted to access an Azure service instance. Identitites are mapped to roles directly or through group membership.

#### Privileged Identity Management

Azure AD Privileged Identity Management (PIM) is an additional, paid-for offering that provides oversight of role assignments, self-service, and just-in-time role activation and Azure AD and Azure resources access reviews.

## Encryption

Encryption serves as the last and strongest line of defense in a layered security strategy.

### What is encryption?

Process of making data unreadable and unusable to unauthorized viewers. Two top-level of encryption: symmetric and asymmetric

- Symmetric encryption uses the same key to encrypt and decrypt the data
- Asymmetric encryption uses a public key and private key. Used for TLS in HTTPS and data signing

Encryption is approached in two ways:

1. Encryption at rest
2. Encryption in transit

### Encryption at rest

Data at rest is data stored on a physical medium. Encryption at rest ensures that stored data is unreadable without the keys and secrets needed to decrypt it.

### Encryption in transit

Data in transit is data actively moving from one location to another.

### Encryption on Azure

#### Encrypt raw storage

Azure Storage Service Encryption for data at rest helps protect your data to meet your organizational security and compliance commitments. With this, the Azure storage platform automatically encrypts your data before persisting it to Azure Managed Disks, Azure Files or Azure Queue storage, and decrypts data before retrieval.

#### Encrypt virtual machine disks

Azure Disk Encryption helps encrypt your Windows and Linux IaaS virtual disks. Azure Disk Encryption leverages the industry standard BitLocker feature of Windows and the dm-crypt feature of Linux to provide volume encryption for the OS and data disks. Integrated with Azure Key Vault to help you control and maange the disk encryption keys and secrets

#### Encrypt databases

Transparent Data Encryption (TDE) helps protect Azure SQL Database and Azure Data Warehouse. Performs real time encryption and decrytption of the database, associated backups, and transaction log files at rest without requiring changes to the application. By default, TDE enabled for all newly deployed Azure SQL Database instances.

#### Encrypt secrets

Azure Key Vault is a centralized cloud service for storing your application secrets. Key Vault helps you control your applications' secrets by keeping them in a single, central location and by providing access, permissions control, and access logging capabilities. It is useful for a variety of scenarios:

- secrets management: You can use Key Vault to securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets
- key management: You can also use Key Vault as a key management solution. Key Vault makes it easier to create and control the encryption keys to encrypt your data
- certificate management: Key Vault lets you provision, manage, and deploy your public and private SSL/TLS certificates for your Azure, and internally connected, resources more easily
- store secrets backed by hardware security moduls (HSMs). The secrets and keys can be protected by either software, of by FIPS 140-2 Level 2 validated HSMs

The benefits of using Key Vault includes:

- Centralized application secrets. Centralizing storage for application secrets allows you to control their distribution, and reduces the chances that secrets may be accidently leaked
- Securely stored secrets and keys. Azure uses industry-standard algorithms, key length, and HSMs, and access requires proper authentication and authorization
- Monitor access and usage. Using Vault Key, you can monitor and control access to company secrets
- Simplified administration of application secrets. Key Vault makes it easier to enroll and renew certificates from public Certificate Authorities (CAs). You can also scale up and replicate content within regions, and use standard certificate management tools
- Integrate with other Azure services. You can integrate Key Vault with storage accounts, contrainers registries, event hubs, and many more Azure services

## Overview of Azure certificates

Certificates used in Azure are x.509 v3, and can be signed by a trusted certificate authority, or they can be self-signed. Self-signed are not trusted by default.

### Types of certificates

1. Services certificates are used for cloud services
2. Management certificates are used for authenticating with the management API

#### Service certificates

Services certificates are attached to cloud services and enable secure communication to and from the service. You can upload service certificates to Azure either using the Azure portal or by using the classic deployment model. Service certificates are associated with a specific cloud service.

#### Management certificates

Management certificates allow you to authenticate with the classic deployment model. Many programs and tools (such as Visual Studio or Azure SDK) use these certificates to automate configuration and deployment of various Azure services. However, these types of certificates are not related to cloud services.

### Using Azure Key Vault with certificates

You can store certificates in Azure Key Vault - much like any other secret. However, Key Vault provides additional features above and beyond the typical certificate management:

- You can create certificates in Key Vault, or import existing certificates
- You can securely store and manage certificates without interaction with private key material
- You can create a policity that directs Key Vault to manage the life cycle of a certificate
- You can provide contact information for notification about life-cycle events of expiration and renewal of certificate
- You can automatically renew certificates with selected issuers - Key Vault partner x509 certificates providers / certificate authorities

## Protect your network

### A layered approach to network security

#### Internet protection

Only allow inbound and outbound communication where necessary. Azure Security Center is a great place to look for this information, because it will identify internet-facing resources that don't have network security groups associated with them, as well as resources that are not secured behind a firewall

#### What's a firewall?

A firewall is a service that grants server access based on the originated IP address of each request. You create firewall rules that specify ranges of IP addresses. Only clients from these granted IP addresses will be allowed to access the server. Firewall rules, generally speaking, also include specific network protocol and port information. To provide inbound protection at the perimete, you have several choices:

- Azure Firewall is a managed, cloud-based, network security service that protects your Azure Virtual Network resources. It is a fully stateful firewall as a service with built-in high availability and unrestricted cloud scalability. Azure Firewall provides inbound protection from non-HTTP/S protocols. Examples of non-HTTP/S protocols include: Remote Desktop Protocol (RDP), Secure Shell (SSH), File Transfer Protocol (FTP). Also provides outbound, network-level protection for all ports and protocols and application-level protection for outbound HTTP/S
- Azure Application Gateway is a load balancer that includes a Web Application Firewall (WAF) that provides protection from common, known vulnerabilities in websites. It is designed to protect HTTP traffic
- Network virtual appliances (NVAs) are ideal options for non-HTTP services or advanced configurations, and are similar to hardware firewall appliances

#### Stopping Distributed Denial of Service (DDoS) attacks

Azure DDoS Protection leverages the scale and elasticity of Microsoft's global network to bring DDoS mitigation capacity to every Azure region. Azure DDoS protection provides the following service tiers:

- Basic: Automatically enabled as part of the Azure platform. Always-on traffic monitoring and real-time mitigation of common network-level attacks provide the same defenses that Microsoft's online services use. Azure's global network is used to distribute and mitigate attack traffic across regions.
- Standard: The Standard service tier provides additional mitigation capabilties that are tuned specifically to Microsoft Azure Virtual Network resources. DDoS Protection Standard is simple to enable and requires no application changes. Protection policies are tuned through dedicated traffic monitoring and machine learning algorithms. Policies are applied to public IP addresses associated with resources deployed in virtual networks, such as Azure Load Balancer and Application Gateway. DDoS standard protection can mitigate the following types of attack:

- Volumetric attacks: the attackers goal is to flood the network layer with a substantial amount of seemingly legitimate traffic
- Protocol attacks: these attacks render a target inacessible, by exploiting a weakness in the layer 3 and layer 4 protocol stack
- Resource (application) layer attacks: these attacks target web application packets to disrupt the transmission of data between hosts

### Controlling the traffic inside your virtual network

#### Virtual network security

Once inside a virtual network (VNet), crucial that you limit communcation betwen resources to only what is required. For communication between VMs, Network Security Groups (NSGs) are a critical piece to restrict unnecessary communication

NSGs allow you to filter network traffic to and from Azure resources in an Azure virtual network. An NSG can contain multiple inbound and outbound security rules that enable you to filter traffic to and from resources by source and destination IP address, port and protocal. They provide a list of allowed and denied communication to and from network interfaces and subnets, and are fully customizable.

You can completely remove public internet access to your services by restricting access to service endpoints. With service endpoints, Azure service access can be limited to your virtual network.

#### Network integration

Azure ExpressRoute: provide a dedicated, private connection between your network and Azure, you can use it. Lets your extend your on-premises networks into the Microsoft cloud over a private connection facilitated by a connectivity provider.

## Protect your shared documents

Microsoft Azure Information Protection (AIP) is a cloud-based solution that helps organizations classify and otionally protect documents and emails by applying labels.

## Azure Advanced Threat Protection (Azure ATP)

Cloud-based security solution that identifies, detects, and helps you investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.

### Azure ATP components

#### Azure ATP portal

Has its own portal, where you can monitor and respond to suspicious activity.

#### Azure ATP sensor

Installed directly on your domain controllers. Monitors domain controller traffic without requiring a dedicated server or configuring port mirroring.

#### Azure ATP cloud service

Runs on Azure infrastructure. Connected to Microsoft's intelligent security graph.

### Purchasing Azure Advanced Threat Protection

Azure ATP available as part of the Enterprise Mobility + Security E5 suite (EMS E5) and as a standalone license. Not available to purchase via the Azure portal.

## Understand Security Considerations for Applications Lifecycle Management Solutions

The Microsoft Security Development Lifecycle (SDL) introduces security and privacy considerations throughout all phases of the development processes.

### Provide training

Security is everyone's job. Not everyone needs to be a security experts but everyone must keep the goal in mind.

### Define security requirements

- Legal and industry requirements
- Internal standards and coding practices
- Review of previous incidents
- Known threats

### Defines metrics and compliance reporting

Define the minimum acceptable levels of security quality, and hold engineering teams accountable to meeting that criteria.

### Perform threat modeling

Should be used in environments where there is a meaningful security risk.

### Establish design requirements

### Manage security risks from using third-party components

### Use approved tools

### Perform Static Analysis Security Testing

### Perform Dynamic Security Testing

### Perform penetration testing

### Establish a standard incident response process
