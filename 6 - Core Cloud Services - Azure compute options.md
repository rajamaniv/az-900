# Core Cloud Services - Azure compute options

## Introduction

How to create resources, configure them to do the work you need, and pay only for what you use.

Learning objectives:

- Identify compute options in Azure
- Select compute options that are appropriate for your business

## Essential Azure compute concepts

### What is Azure compute?

On-demand computing service for running cloud-based applications. Provides computing resources like multi-cores proessors and superecomputers via virtual machines and containers. Pay only for the resources you use.

4 common techniques:

- Virtual machines
- Containers
- Azure App Service
- Serverless computing

### What are virtual machines?

Software emulation of physical computer. Include virtual processor, memory, storage and networking resources.

### What are containers?

Virtualization environment for running applications. Don't include OS unlike VMs. Instead, bundle libraries and components needed to run the app and use the existing host OS running the container.

### What is Azure App Service?

PaaS offering in Azure, designed to host enterprise-grade web-oriented applications.

### What is Serverless Computing?

Cloud-hosted execution environment that runs your code but completly abstracts the underlying hosting environment.

### Which computing strategy is right for me?

Don't need to take "All or nothing" approach, you can combine them in different ways.

## Explore Azure Virtual Machines

Azure Virtual Machines let you create and use VMs in the cloud. Provide IaaS and can be used in many ways. Ideal choice when you need:

- Total control over the OS
- The ability to run custom software, or
- To use custom hosting configurations

Can create and provision a VM in minutes.

Exemples of when to use VMs:

- During testing and development. Can delete them when no longer needed
- When running applications in the cloud. You can spin up or down VMs when you need them.
- When extending your datacenter to the cloud.
- During disaster recovery

### Moving to the cloud with VMs

Excellent choice when moving from a physical server to the cloud ("lift and shift")

### Scaling VMs in Azure

Can run single VMs for testing, development or minor tasks. Can group VMs together to provide high availability, scalability and redundancy. Azure has several features that help meet your uptime requirements:

- Availability sets
- Virtual Machine Scale Sets
- Azure Batch

#### What are availabilty sets?

Logical grouping of two or more VMs. Help keep your application available during planned or unplanned maintenance.

Planned maintenance: event when the underlying Azure fabric that hosts VMs is updated by Microsoft. Done to patch security vulnerabilities, improve performance, and add or update features.

Unplanned maintenance: hardware failure, power outage, disk failure. Group of VMs that share common hardware are in the same fault domain, which is a rack of servers.

With an availability set, you get:

- Up to three fault domains that each have a server rack with dedicated power and network resources
- Five logical update domains which then can be increased to a maximum of 20

VMs are then sequentially place across the fault and update domain.

#### What are virtual machine scale sets?

Azure Virtual Machine Scale Sets lets you create and manage a group of identical, load balanced VMs. Allows you to centrally manage, configure and update a large number of VMs. Number of VMs instances can automatically increase or decrease in response to demand or a defined schedule.

#### What is Azure Batch?

Enables large-scale job scheduling and compute management with the ability to scale to tens, hundreds or thousands of VMs. When ready to run a job, Batch does the following:

- Start a pool of compute VMs for you
- Install applications and staging data
- Runs jobs with as many tasks as you have
- Identifies failures
- Requeues work
- Scales down the pool as work completes

## Explore Containers in Azure

Excellent choices for multiple instances of an application on a single host machine.

Container: modified runtime environment built on top of a host OS that executes your application. Doesn't use virtualization so doesn't waste resources simulating virtual harware with a redundant OS. Typically more lightweight than VMs. Allows you to quickly respond to change in demand or failure. Can run multiple isolated applications on a single container hosts.

### Containers in Azure

Supports Docker containers, with several ways to manage containers in Azure:

- Azure Container Instances (ACI)
- Azure Kubernetes Service (AKS)

#### Azure Container Instances

Fastest and simplest way to run a container in Azure. Don't have to manage any VM, or configure  additional services. PaaS offering that allows you to upload your containers and execute them directly wth automatic elastic scale.

#### Azure Kubernetes Service

The task of automating, managing and interacting with a large number of containers is known as orchestration. Azure Kubernets Service (AKS) is a complete orchestration service for containers with distributed architectures with multiple containers

### Using containers in your solutions

Containers often used to create solutions using a microservice architecture, when you break solutions into smaller, independant pieces.

### Migrating apps to containers

Can move existing applications to containers and run them with AKS. Control access via integration with Azure Active Directory (Azure AD) and accss SLA-backed Azure services.

## Explore Azure App Service

Azure App Services enables you to build and host web apps, background jobs, mobile backends, RESTful APIs in the programming language of yur choice without managing infrastructure. Offers automatic scaling and high availability. App Service supports both Windows and Linux, and enables automated deployments from GitHub, Azure DevOps, or any Git repo to support a continuous deployment model.

This PaaS allows you to focus on the website and API logic while Azure handles the infra to run and scale your web app.

### App Service costs

Pay as you go, depending on your plan.

### Types of app services

Can host most common app services styles, including:

- Web Apps
- API Apps
- WebJobs
- Mobile Apps

Azure App Service handles most of the infra decisions you deal with hosting web-accesible apps: deployment and managment integrated into the platform, endpoints can be secured, sites can be scaled quickly, built in load balancing.

#### Web apps

App Service includes full support for hosting web apps using ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP or Python. Can choose Windows or Linux.

#### API apps

Like web apps, with full Swagger support and the ability to package and publish your API in the Azure Marketplace

#### Web jobs

Allows you to run a program or script in the same context as a web app, API app or mobile app. Can be scheduled or run by a trigger. Often used to run background tasks as part of your app logic.

#### Mobile app back-ends

Use the Mobile Apps feature of Azure App Service to quickly build a back-end for iOS and Android apps:

- Store mobile app data in the cloud-based SQL database
- Authenticate customers against common social providers
- Send push notifications
- Execute custom back-end logic in C# or Node.js

SDK support for native iOS & Android, Xamarin and React native app.

## Explore Serverless computing in Azure

Serverless computing: abstraction of servers, infrastructure and OSs. Three ideas: 

1. Abstraction of servers: You never explicitly reserve server instances. Each function can run on a different compute instance, and execution context is transparent to the code. Simply deploy code, which then runs with high availability.

2. Event-driven scale: Excellent fit for workloads that respond to incoming events. Events include triggers by timers, HTTP, queues, etc. Instead of writing an entire application, write just the functiuon with contains code and metadata about triggers and bindings. The plateform automatically schedules the function to run and scales the number of compute instances based on the rate of incoming events.

3. Pay only for the time when the code run, per execution and minute of computing.

Two implementations of serverless compute:

- Azure Functions, can execute code in almost any modern language
- Azure Logic Apps, designed in a web-based designer and can execute logic triggered by Azure services without writing any code.

### Azure Functions

Commonly used when you need to perform work in response to an even, often via REST request, timer, or message from another Azure service.

Scale automatically based on demand, solid choice when demand is variable.

Can either be stateless, or stateful ("Durable functions") where a context is passed through the function to track prior activity.

Functions are a key component of serverles computing, but they're also a general compute platform for running any type of code.

### Azure Logic Apps

Execute workflows designated to automate business scenarios and built from predefined logic blocks. Starts with a trigger. Each time the trigger fires, creates a logic app instance that runs the actions in the workflow.

Can create Logic App workflows using avisual designer. Workflows are persisted as a JSON file.

Azure provides over 200 different connectors and processing blocks to intereact with different services - including most popular enterprise apps.
