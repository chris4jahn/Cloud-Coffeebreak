---
layout: post
title: "Start Small with Commitments"
date: 2024-12-13
subtitle: "Azure Cost Optimization Part 6"
background: '/img/header.webp'
---

One of the first things that come to mind when talking about **Azure cost optimization** is **reservations**. By committing to a plan, like a VM family for 1 or 3 years, you can save a lot of money. But reservations aren’t the only way to commit. To get the most out of your cloud spend, you need to know the different types of commitments and how to use them. Let’s dive into the options and figure out when to use what.

## How to Start with Commitments?

Start small. I’ve seen many customers go big with commitments right from the start, and it didn’t always end well. Some didn’t fully understand how commitments work and ended up buying the wrong resources in the wrong region. This led to a lot of back and forth with Microsoft and turned into an expensive lesson.

Take it step by step. Start with just a few services, learn how commitments are booked and managed in your subscription, and get familiar with the process. Once you’ve got the basics, you can scale it up and make bigger commitments with confidence.

## Why Should I Start Small with Commitments?

Starting small helps you avoid mistakes and fine-tune your strategy. Jumping in without preparation can lead to missteps, like committing to resources you don’t fully understand or can’t use effectively. It’s better to test the waters, learn how commitments align with your workloads, and build your strategy from there. Talk to people who’ve been through this process, and make sure you understand the commitment types and their pros and cons.

![Slide with the Heading 'Saving Plan or Resrvation'. You can see two images showing the amount you could save either with Saving Plans or Reserved Instances in Azure. In the middle is a man with curley hair that looks confused and overwhelmed by the possibilities.](/img/posts/saving-plan-or-reservation.png){: .img-fluid}

## Types of Commitments

Azure offers a few different types of commitments, and each has its strengths. Knowing when to use them is key to saving money while staying flexible. And remember, commitments aren’t a one-and-done thing - you’ll want to revisit and update them regularly as your needs evolve.

### Azure Reservations

**Azure Reserved Instances (RI)** are great for predictable workloads. You prepay for resources like virtual machines or databases, and in return, you can save up to **72%** compared to pay-as-you-go prices. But RIs come with a few limitations:

- They’re tied to specific **regions** and **VM families**, so planning is essential.  
- Microsoft allows you to **exchange or cancel** RIs, but there are restrictions, such as prorated refunds and limits on the number of changes allowed per year.  
- RIs are best for workloads that run consistently, like production environments or long-running applications.  

If your workloads are stable and you know what you need, RIs can be a game-changer for cost savings.

Services covered by reservations:
Reserved Virtual Machine Instance, Azure Blob storage reserved capacity, Azure Files reserved capacity, Azure Cosmos DB reserved capacity, Azure Data Factory data flows, SQL Database reserved vCore, SQL Managed Instance reserved vCore, Azure Synapse Analytics, Azure Databricks, App Service stamp fee, Azure Database for MySQL, Azure Database for PostgreSQL, Azure Data Explorer, Azure Cache for Redis, Azure Dedicated Host, Azure Disk Storage reservations, Azure Backup Storage reserved capacity, Azure NetApp Files, SUSE Linux, Red Hat Plans, Azure Red Hat OpenShift

### Azure Saving Plans

If your workloads are less predictable or more dynamic, **Azure Saving Plans (SP)** might be a better fit. Instead of committing to specific resources, SPs let you commit to a monetary amount for 1 or 3 years. Here’s why SPs might work for you:

- They’re more **flexible** since they aren’t tied to specific regions or VM families.  
- They cover a broader range of **Azure services**, including VMs, app services, and container instances.  
- While the savings aren’t as high as RIs, SPs are perfect for businesses that need the ability to shift workloads around.  

One thing to watch out for: unlike RIs, SPs **can’t be canceled**. Make sure you’re confident about your spending commitment before you dive in.

Services covered by Saving Plans:
Azure Virtual Machines, Azure App Service, Azure Functions Premium Plan, Azure Container Instances, Azure Dedicated Hosts, Azure Container Apps, Azure Spring Apps Entreprise

### Azure Hybrid Benefit

**Azure Hybrid Benefit (AHB)** isn’t technically a commitment, but it’s worth mentioning here because it can save you a lot of money. If you already have on-premises licenses with Software Assurance, you can use them in Azure at no extra cost. Or you can buy licenses upfront for much less than what Azure’s pay-as-you-go rates would cost.

Microsoft says AHB can reduce costs by up to **85%** for certain workloads. It’s especially useful for businesses moving from on-premises infrastructure to the cloud or running long-term workloads.

Coverable Services:
Windows Virtual Machines, SQL Databases

## When to Choose Reservations vs. Saving Plans?

Now that you know the basics, let’s figure out when to use **Reserved Instances** and when to go with **Saving Plans**:

### Choose Reserved Instances if

- Your workloads are **predictable**, like production servers or databases that run 24/7.  
- You want **maximum savings**—RIs offer the biggest discounts, up to 72%.  
- You don’t need flexibility across regions or VM families.  
- You like having the option to **exchange or cancel** if your needs change.  

### Choose Saving Plans if

- Your workloads are **dynamic** or spread across multiple regions and services.  
- You want the **freedom** to shift resources between VM families, regions, or even other Azure services.  
- You need **broad coverage**—Saving Plans can cover services like app services and containers.  
- You’re okay with a bit less savings for the flexibility you get.  

Sometimes, the best approach is to use a mix of both, depending on your workloads.

## Monitor the Usage of Your Commitments

Once you’ve made commitments, don’t just set them and forget them. Keep an eye on how they’re being used. Are your RIs or SPs fully utilized? If not, adjust your workloads or resource configurations to get the most out of them.

For example, if you have unused reservations, check if they can be repurposed for other workloads within the same VM family. Staying within a limited number of VM families gives you more flexibility. And don’t forget to use any free cancellation or exchange options if things change.

Regularly reviewing your commitments ensures you’re always aligned with your actual needs and not leaving money on the table.

## Other Posts in the Cost Optimization Series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- [Azure Cost Optimization Part 4 - Rightsize your resources](2024-10-24-azure-cost-optimization-part-4-rightsize-your-resources.md)
- [Azure Cost Optimization Part 5 - Turn off if not needed](2024-11-15-azure-cost-optimization-part-5-turn-off-if-not-needed.md)
- [Azure Cost Optimization Part 6 - Start small with commitments](2024-12-30-azure-cost-optimization-part-6-start-small-with-commitments.md)
- [Azure Cost Optimization Part 7 - Bring cloud cost optimization into your organization](2024-12-23-azure-cost-opmization-part-7-bring-cloud-cost-optimization-to-your-organization.md)

## Conclusion

Commitments are one of the best ways to save money in **Azure**, but they aren’t a one-size-fits-all solution. By starting small, understanding your options, and monitoring usage, you can create a strategy that fits your needs and saves you money. Whether it’s Reserved Instances, Saving Plans, or the Azure Hybrid Benefit, knowing when and how to use each one will help you optimize your cloud costs without sacrificing flexibility.

**Happy Optimization!**
