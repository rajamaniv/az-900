# Core Cloud Services - Azure networking options

## Introduction

### Learning objectives

- How an Azure virtual network provides secure network communication among resources such as virtual machines and other networks
- What high availability and resiliency mean and how Azure Load Balancer can increase resiliency within a single geographic region
- What latency is and how Traffic Manager helps reduce network latency and provides resiliency across geographic locations

## Deploy your site to Azure

### Your e-commerce site at a glance

Two ways of doing things:

- losely coupled architecture
- N-tier architecture

### Your e-commerce site running on Azure

#### What's an Azure region?

One or more Azure data centers within a specific geographic location. East US, West US, North Europe are exemple of regions.

#### What's a virtual network?

Logically isolated network on Azure. Like networks on Hyper-V, VMware, or public cloud. Scoped to a single region. Can be connected to other virtual network of other regions through virtual network peering.

#### What's a network security group?

Allows or denies inbound network traffic to your Azure resources.

## Scale with Azure Load Balancer

### What are availability and high availability?

Availability: how long your service is up and running without interruption.

### What is resiliency?

A system's ability to stay operational during abnormal conditions like:

- natural disasters
- system maintenance, both planned and unplanned
- spikes in traffic to your site
- threats made by malicious parties like DDoS, attacks

### What is a load balancer?

A load balancer distributes traffic evenly among each system in a pool. Can help achieve both high avaialability and resiliency.

### Azure Application Gateway

If all traffic is HTTP, There's Azure Application Gateway. Application Gateway is a load balancer designed for web app. Uses Azure Load Balancer at the transport level (TCP) and applies URL based routing. Here are some benefits:

- Cookie affinity: Useful when you want to keep a user session on the same backend server
- SSL termination: Can manage SSL certificates and pass unencrypted traffic to the backend servers to avoid encryption/decryption overhead. Also supports full end to end encryption
- Web application firewall (WAF): firewall with detailed monitoring and logging to detect malicious attacks against your network infrastructure
- URL rule-based routes: Allows you to route traffic based on URL patterns, source IP address and port to destination IP and port. Helpful when setting up CDN
- Rewrite HTTP headers: add or remove info from inbound and outbound HTTP headers

#### What is a Content Delivery Network?

Distributed network of servers than can efficiently deliver web content to users. Can be hosted in Azure or any other location.

### What about DNS

Azure DNS

## Reduce latency with Azure Traffic Manager

### What is network latency?

Times it takes for data to travel over the network. Typically measured in milliseconds.

The closer you are to the data center, the less latency there is.

### Scale out to different regions

Making copies of your website into different regions helps reduce latency

### Use Traffic Manager to route users to the closest endpoint

Azure Traffic Manager uses the DNS server that's the closest to the user to direct user traffic to a globally distributed endpoint.

### Compare Load Balancer to Traffic Manager

Azure Load Balancer distributes traffic within the same region to make your services more highly available and resilient. Traffic Manager works at the DNS level, and directs the client to a preferred endpoint. This endpoint can be to the region that's closest to your user.

Load Balancer and Traffic Manager both help make your services more resilient, but in slightly different ways. When Load Balancer detects an unresponsive VM, it directs traffic to other VMs in the pool. Traffic Manager monitors the health of your endpoints. When Traffic Manager finds an unresponsive endpoint, it directs traffic to the next closest endpoint that is responsive.