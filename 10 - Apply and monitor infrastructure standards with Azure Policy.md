# Apply and monitor infrastructure standards with Azure Policy

## Introduction

Good IT governance involves planning your initiatives and setting priorities on a strategic level to help manage and prevent issues. You need good governance when:

- You have multiple engineering teams working in Azure
- You have multiple subscriptions in your tenant
- You have regulatory requirements that must be enforced
- You want ot ensure standards are followed for all IT allocated resources

In this module, you will:

- Apply policies to control and audit resource creation
- Learn how role-based security can fine-tune access to your resources
- Understand Microsoft's policies and privacy guarantees
- Learn how to monitor your resources

## Define IT compliance with Azure Policy

Azure Policy is an Azure service you use to create, assign and manage policies. For example, to control cost, you can forbid the creation of CMs with more than 4 CPUs.

### Creating a policy

1. Create a policy definition
2. Assign a definition to a scope of resources
3. View policy evaluation results

#### What is a policy definition?

Express what to evaluate and what action to take. Policies are represented as JSON files.

#### Applying Azure policy

To apply a policy, use the Azure portal or one of the CLI tools by adfding `Microsoft.PolicyInsights` extension.

## Organize policity with initiatives

Initiatives work alongside policies in Azure Policy. An initiative definition is a set or group of policy definitions to help track your compliance state for a larger goal.

## Enterprise governance management

Azure Management Groups are containers for managing access, policies, and compliance across multiple AZure subscriptions. Management groups allow you to order your Azure resources hierarchically  into collections, which provide further level of classification that is above the level of subscriptions. All subscriptions within a management group automatically inherit the conditions applied to the management group. Management groups give you enterprise-grade management at a large scale no matter what type of subscription you might have.

## Define standard resources with Azure Blueprints

Blueprints for cloud deployment. Declarative way to orchestrate the deployment of various resources templates and other artifacts, such as:

- Role assignments
- Policy assignments
- Azure Resource Manager templates
- Resources groups

The process of implementing Azure Blueprint consists of the following high-level steps:

1. Create an Azure Blueprint
2. Assign the blueprint
3. Track the blueprint assignments

Backed un in Azure Cosmos.

### How is it different from Resource Manager templates?

Designed to help with environment setup. You can use them together.

### How it's different from Azure Policy

You can include policies in blueprints.

## Explore your service compliance with Compliance Manager

Four sources:

1. Microsoft Privacy Statement
2. Microsoft Trust Center
3. Service Trust Portal
4. Compliance Manager

### Microsoft Privacy Statement

Explains what personal data Microsoft processes, how Microsoft processes it, and for what purpose.

### What is the Microsoft Trust Center?

Trust Center is a website resource containing information and details about how Microsoft implements and supports security, privacy, compliance, and transparency in all Microsoft cloud products and services. Provides support and resources for the legal and compliance community including:

- In-depth information about security, privacy, compliance offerings, policies, features, and practices across Microsoft cloud products
- Recommanded resources in the form of a curated list of the most applicable and widely used resources for each topic
- Information specific to key organizational roles, including business managers, tenant admins or data security teams, risk assessment and privacy officers, and legal compliance teams
- Cross-company document search, which is coming soon and will enable existing cloud service customers to search the Service Trust Portal
- Direct guidance and support for when you can't find what you're looking for

### What is the Service Trust Portal?

The Service Trust Portal (STP) hosts the Compliance Manager service, and is the Microsoft public site for publishing audit reports and other compliance-related information relevant to Microsoft's cloud services. Also includes informations about how Microsoft online services can help your organization maintain and track compliance with standards, laws, and regulations, such as:

- ISO
- SOC
- NIST
- FedRAMP
- GDPR

Service Trust Portal is a companion feature to the Trust Center, and allows you to:

- Access audit reports across Microsoft cloud services on a single page
- Access compliance guides to help you understand how you can use Microsoft cloud service features to manage compliance with various regulations
- Access trust documents to help you understand how Microsoft cloud services help protect your data

### Compliance Manager

Workflow-based risk assessment dashboard within the Service Trust Portal that enables you to track, assign, and verify your organization's regulatory compliance activities related to Microsoft professional services and Microsoft cloud services such as Office 365, Dynamics 365 and Azure. Provides the following features:

- Combines the following three items:
  1. Detailed information provided by Microsoft to auditors and regulators, as part of various third-party audits of Microsoft's cloud services against various standards (for example, ISO 27001, ISO 27018 and NIST)
  2. Information that Microsoft compiles internally for its own compliance with regulations (such as HIPAA and the EU GDPR)
  3. An organization's self-assessment of their own compliance with these standards and regulations
- Enables you to assign, track, and record compliance and assessment-related activities, which can help your organization cross team barriers to achieve your organization's compliance goals
- Provides a Compliance Score to help you track your progress and prioritize auditing controls that will help reduce your organization's exposure to risk
- Provides a secure repository in which to upload and manage evidence and other artifacts related to compliance activities

## Monitor your service health

### Azure Monitor

Maximizes the availability and performance of your applications by delivering a comprehensive solution for collecting, analyzing and acting on telemetry from your cloud and on-premises environment. It helps you understand how your applications are performing and proactively identifies issues affecting them and the resources they depend on.

#### Diagnostic settings

- Enable guest-level monitoring
- Performance counters: collect performance data
- Event Logs: enable various event logs
- Crash Dumps: enable or disable
- Sinks: send your diagnostic data to other services for more analysis
- Agent: configure agent settings

#### Getting more data from your apps

##### Application Insights

Service that monitors the availability, performance, and usage of your web apps. Includes connection points to a variety of development tools, and integrates with Microsoft Visual Studio to support your DevOps process.

##### Azure Monitor for containers

Service designed to monitor the performance of container workloads, deployed on AKS. Containers logs are also 

##### Azure Monitor for VMs

Service that monitors Azure VMs at scale, analyzing performanc and health.

#### Responding to alert conditions

##### Alerts

Azure Monitor proactively notifies you of critical conditions using alerts.

##### Autoscale

Azure Monitor uses Autoscale to ensure that you have the right amount of resources running.

#### Visualize monitoring data

- Dashboards
- Views
- Power BI

#### Integrate with other services

Other Azure services can work with Azure Monitor to provide this integration

### Azure Service Health

Suite of experiences that provide personalized guidance and support when issues with Azure services affect you. Composed of the following views:

#### Azure Status

Provides a global view of the health state of Azure services.

#### Service Health

Customizable dashboard that tracks the state of your Azure services in the regions where you use them.

#### Resources Health

Helps you diagnose and obtain support when an Azure service issue affects your resources.
