# Control and oranize Azure resources with Azure Resource Manager

## Introduction

### Learning objetives

- Use resources group to organize Azure resources
- Use tags to organize resources
- Apply policies to enforce standards in your Azure environments
- Use resource locks to protect critical Azure resources from accidental deletion

## Principles of resources groups

### What are resource groups?

A logical container for resources deployed on Azure. These resources are anything you create in Azure subscription like VMs, Application Gateways, and CosmosDB instances. All resources must be in a resource group and a resource can only be a member of a single resource group.

#### Local grouping

Can create order and organization by grouping resource of similar usage, type and location into the same resources groups.

#### Life cycle

If you delete a resource group, all resources inside are also deleted.

#### Authorization

Resource groups are also a scope for applying role-based access control (RBAC) permissions.

### Use resource groups for organization

Some guidelines and best practices that can help with the organization:

#### Consistent naming convention

What it's used for, what it is, the type of resource itself

#### Organizing principles

- Group resources by type (DB, app, gateway)
- Group resources by environment (dev, prod, qa)
- Group resources by domain (marketing, finance, hr)
- Group resources by authorization
- Group resources by life cycle
- Group resources by biling

Can be combined

## Use tagging to organize resources

### What are tags?

Tags are name/value pairs of text data that you can apply to resources and resources groups. Resources can have up to 50 tags, with a 512 character limit for all types except storage accounts, which are limited to 128. The tag value is limited to 256 characters.

### Use tags for organization

Tagging resources can help grouping them, ex: grouping them by billing.

Can also be used in automation, ex: start or shutdown all resources that have a tags.

## Use policies to enforce standards

### What is Azure Policy?

Service you can use to create, assign or manage policies. These policies can apply and enforce rules that your resources need to follow.

### Use policies to enforce standards

Can use policies to restrict which Azure region you can deploy resources to, restrict which types of virtual machine sizes can be deployed, enforce naming conventions.

## Secure resources with role-based access control

Fine-rained acccess management for Azure resources, enabling you to grant users the specific rights they need to perform their jobs. RBAC is considered a core servicce and is included with all subscriptions levels at no cost. Using it, you can:

- Allow one user to manage VMs in a subscription, and another user to manage virtual networks
- Allow a database admninistrator (DBA) group to manage SQL databases in subscription
- Allow a user to manage all resources in a resource group, such as VMs, websites, and virtual subnets
- Allow an application to access all resources in a resource group

### How RBAC defines access

Uses an allow model.

### Best practices for RBAC

- Segregate duties within your team and grant only the amount of access to users that they need to perform their jobs. Instead of giving everybody unrestricted permissions in your Azure subscription or resource, allow only specific actions at a particular scope
- When planning your access control strategy, grant users the lowest privilege level that they need to do their work
- Use Resource Locks to ensure critical resource aren't modified or deleted

## Use Resource Locks to protect resources

### What are resource locks?

Setting that can be applied to any resource to block modification or deletion. Can be set to either Delete or Read-only. Delete will allow all operations against the resource but block the ability to delete it. Read-only only allow read. When a resource lock is in place, you must first remove the lock in order to perform the action. Applied regardless of RBAC permissions
