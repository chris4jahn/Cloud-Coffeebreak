---
layout: post
title: "Identify cloud waste!"
date: 2024-10-16
subtitle: "Azure Cost Optimization Part 3"
background: '/img/header.png'
---
In this part of the blog series focussing on Azure cost optimization we will have a look at cloud waste and how to get rid of it. As flexibility and agility is a key driver of cloud, cloud waste is not avoidable. But we don't want to waste our money on it, that's why we need to find and eliminate it.

## What is cloud waste?

When you are having cloud resources that increase your spend but are not useful any more, then we are talking about cloud waste.

> Check for underutilized or idle resources.

Here is an example of a customer who reported, that he spent thousands of Euros with this.  
During a regular recovery before Christmas holidays the operations team tested a desaster recovery plan, where they recovered a bigger environment. Testing of the backup went well, was documented properly and after that everyone went to holidays. Some days later an alarm was thrown because an anomaly in the cloud spend was detected. This informed the Teamlead of the ops team who also was in holidays. After coming back he realized the error and deleted the non-production environment. Until then this cloud waste generated more than 15.000 Euro.

I bet everyone heard of stories like this. This is an example of a higher cloud waste which in most environments are not happening on a regular basis. But all these small chunks of cloud waste, that are leftovers from resources, forgotten or unused services can add up to increased spenditure.

## How to identify cloud waste?

In Azure we have a service called Azure Advisor that can help us identifiying resources that are not or hardly used. One resource that is often left over is VM disks or storage in general. Orphaned disks can be identified by Azure Advisor easily, as they are not attached to compute. I prefer working with the [Azure Orphaned Resources v2.0](https://github.com/dolevshor/azure-orphan-resources?tab=readme-ov-file) as the workbook takes a look on a lot of unused services in a nice overview. (see below)

## Take care with deleting cloud waste

Be careful with deleting cloud waste. There can be reasons for not deleting these resources like regulatory requirements or other services that relate to it. Collaborate with business and technical teams to ensure services can be retired. If the environment is deployed using infrastructure as code be sure not to create code drift by manually deleting things.  
As you can see see once again, accountablity is the key for optimization. The decision of what services can be deleted must be taken from the accountable team or user.

If you don't have an accountable person, make use of the "cry-test". Turn the service off and wait for some weeks if someone cries. Unsused services can then be deleted or costs at least can being reduced.  
To reduce storage costs you can move the data to cold or archieve tier, or reduce the size of disks. 

## Find orphaned resources with an Azure workbook

The Azure Workbook [Azure Orphaned Resources v2.0](https://github.com/dolevshor/azure-orphan-resources?tab=readme-ov-file) gives you an overwiew of where to realize cost savings by reducing waste in your Azure subscriptions.  
Hint: Before taking care on the orphaned resources talk to the accountable teams.

<img src="/img/posts/Orphaned_Resources_Workbook.png" class="img-fluid"/>
Here you can see an overview of orphaned services from the workbook.

Here is a [grafana dashboard](https://github.com/Azure-Samples/azure-orphan-resources-grafana-dashboard) for identifiying cloud waste like orphaned resources.

## How to identify services on your own?

When you want to advance finding unused services there are several ways to do that. One option is to take a look at apps and services that have a very constant spend. Usually this means that the services have not been touched for a while. Check these resource groups for unattached disks, check the metrics of the services. Check who accessed the services. If there have been requests to the resources, ... This gives you a first hint. Then contact the accountable team and/or users and ask them to evaluate if the services are need or not. 

## Other posts in the cost optimization series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- [Azure Cost Optimization Part 4 - Rightsize your resources](2024-10-24-azure-cost-optimization-part-4-rightsize-your-resources.md)
- [Azure Cost Optimization Part 5 - Turn off if not needed](2024-11-15-azure-cost-optimization-part-5-turn-off-if-not-needed.md)
- [Azure Cost Optimization Part 6 - Start small with commitments](2024-12-30-azure-cost-optimization-part-6-start-small-with-commitments.md)
- Azure Cost Optimization Part 7 - Bring cloud optimization into your organization

## Conclusion

Small chunks of waste resources can quickly sum up to a reasonable amount of cloud spend. Take care of cloud waste and identify unused or orphaned resources. Involve business and technical teams to evaluate if resources can being deleted. By eliminating cloud costs you can easily reduce cloud costs. This is a repeatable task as flexibility and agility leads to having cloud waste over time.

Happy optimization!
