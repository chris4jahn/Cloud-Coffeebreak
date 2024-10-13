---
layout: post
title: "Identify cloud waste!"
date: 2024-10-16
subtitle: "Azure Cost Optimization Part 3"
background: '/img/posts/budget_alert_01.png'
---
In this part of the blog post focussing on Azure cost optimization we will have a look at cloud waste and how to get rid of it. As flexibility and agility is a key driver of cloud, cloud waste is not avoidable. But we don't want to waste our money on it. That's why we need to find and eliminate it.

## What is cloud waste?

When you are having cloud resources that increase your spend but are not useful any more, then we are talking about cloud waste.

> Check for underutilized or idle resources.

A customer reported that they spent thousands of Euros with this story. During a regular recovery before Christmas holidays the operations team tested a desaster recovery plan where they recovered a bigger environment. Testing og the backup went well and everyone went to holidays. Some days later someone realized an anomaly in the cloud spend and informed the lead of the ops team. He realized the error and deleted the non-production environment. Until then this cloud waste generated 15.000 Euro of consumption.

I bet everyone heard of stories like this. Luckily this is not the main topic that we are adressing here. But all these small chunks of cloud waste that are leftovers from resources, forgotten or not used services can add up to increased spenditure.

## How to identify cloud waste?

In Azure we have a service called Azure Advisor that can help us identifiying resources that are not used. Orphaned disks for example can be identified as they are not attached to compute.

![test image](/Cloud-Coffeebreak/img/005.png)

## Take care with deleting cloud waste

- regulatory needs
- other services may relate to it

collaborate with business and technical teams to ensure services can be retired. 
Here you see once again that accountablity is so important for cloud services. Who is to being contacted to find out if the resources can be deleted?
If you don't have an accountable person, make use of the "cry-test". Turn the service off and wait if someone cries. 

## Get a first view on Azure Advisor

## How to identify services on your own?

Take a look at apps and services that have a very constant spend. Usually this means that the services have not been touched for a while. Check these resource groups for unattached disks, check the metrics of the services if there is something happening in the services

Then proceed with tagging and your hierarchy.

## Other posts in the cost optimization series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- Azure Cost Optimization Part 4 - Rightsize your resources
- Azure Cost Optimization Part 5 - Turn off if not needed  
- Azure Cost Optimization Part 6 - Start small with commitments
- Azure Cost Optimization Part 7 - Bring cloud optimization into your organization

## Conclusion
