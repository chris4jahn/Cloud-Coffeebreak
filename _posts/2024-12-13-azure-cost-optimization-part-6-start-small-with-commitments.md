---
layout: post
title: "Start Small with Commitments"
date: 2024-12-13
subtitle: "Azure Cost Optimization Part 6"
background: '/img/header.png'
---

One of the first things most people think about when it comes to **Azure cost optimization** is **reservations**. By committing to a specific plan, like a VM family for 1 or 3 years, you can receive significant discounts. However, this is just one form of commitment. To truly optimize your cloud investments, it’s essential to understand the different types of commitments and how to use them effectively. In this guide, we’ll explore the options and strategies to save money while maintaining flexibility.

## How to Start with Commitments?

Starting with commitments can feel overwhelming, but taking small steps is the key to success. Many customers begin their journey with just a handful of services. This allows them to get familiar with how commitments are booked and managed within their Azure subscriptions.

Learning the basics first will help you avoid common mistakes and prepare you for scaling commitments in the future. Create a clear plan for your commitments - understand your usage patterns, explore available options, and align them with your organizational goals before diving into larger purchases.

## Why Should I Start Small with Commitments?

Starting small allows you to minimize risks and avoid costly mistakes. Jumping into large commitments without proper preparation can lead to serious issues. For example, I’ve seen cases where customers committed to a large number of VMs in the wrong region. This resulted in months of negotiations with Microsoft and an expensive learning experience.

By starting with smaller commitments, you can test the waters, refine your strategy, and confidently scale your approach over time. Consulting with experts and thoroughly researching your options ensures you make informed decisions.

<img src="/img/posts/saving-plan-or-reservation.png" class="img-fluid" alt="Slide with the Heading 'Saving Plan or Resrvation'. You can see two images showing the amount you could save either with Saving Plans or Reserved Instances in Azure. In the middle is a man with curley hair that looks confused and overwhelmed by the possibilities." />

## Types of Commitments

Azure offers various commitment options, each suited to different workloads and needs. Understanding these options is critical for optimizing costs effectively. Commitments shouldn’t be seen as a one-time purchase - they should be part of a regular, evolving strategy that grows with your business.

### Azure Reserved Instances

**Azure Reserved Instances (RI)** are a popular cost-saving tool, offering discounts of up to **72%** compared to pay-as-you-go pricing. By prepaying for virtual machines and other services you can significantly reduce your costs. However, RIs come with some limitations:

- **Region-Specific and Family-Specific**: RIs are tied to specific regions and VM families, so planning is essential to avoid over- or under-committing.  
- **Cancellation and Exchange Options**: Microsoft allows you to exchange or cancel RIs, but these come with restrictions such as prorated refunds and annual limits on changes.  
- **Ideal for Predictable Workloads**: RIs are best suited for long-running or stable workloads, such as production environments.

Careful planning and staying within a consistent VM family can help you maximize flexibility and repurpose RIs for evolving workloads.

**Azure Reserved Capacity** is a commitment-based option specifically for storage, databases and other services. It allows you to reserve a certain amount of storage capacity or throughput for a period of 1 or 3 years in exchange for discounts.

- **Predictable Storage Needs**: If you have workloads with predictable storage requirements, such as data archives or analytics pipelines, reserved capacity is an excellent option.  
- **Discounts on Storage Services**: Reserved Capacity applies to storage types like Azure Blob Storage, Azure Data Lake Storage, and more, offering substantial savings over pay-as-you-go rates.  
- **Flexible Scope**: You can apply reserved capacity across subscriptions or specific storage accounts, giving you control over how it’s utilized.  

Reserved Capacity is ideal for businesses managing large-scale data operations where storage costs are a significant portion of their Azure bill. Proper planning ensures you align your storage commitments with long-term data strategies.

### Azure Saving Plans

**Azure Saving Plans (SP)** provide a more flexible approach to cost management. Instead of committing to specific resources, SPs allow you to commit to a **fixed monetary amount** for a period of 1 or 3 years.

- **Flexibility Across Regions and Resource Types**: SPs cover multiple Azure services and aren’t tied to specific regions or VM families.  
- **Moderate Discounts**: While the savings are lower than RIs, SPs offer greater adaptability, making them ideal for businesses with diverse or changing workloads.  
- **No Cancellation Option**: Unlike RIs, Saving Plans cannot be canceled, so careful planning is crucial before committing.

SPs are perfect for organizations that prioritize flexibility and want to optimize costs across a wide range of Azure services.

## When to Choose Reservations vs. Saving Plans?

Choosing between **Azure Reserved Instances** and **Azure Saving Plans** depends on your workload patterns, business requirements, and flexibility needs. Here’s a quick guide to help you decide:

### When to Choose Reserved Instances

- **Predictable Workloads**: Ideal for workloads with consistent resource usage over time, such as production servers or databases.  
- **Region-Specific Needs**: If your resources are tied to a specific region and VM family, RIs provide the highest savings.  
- **Deep Discounts Needed**: If maximizing cost savings is your top priority, RIs are the better choice, offering up to 72% off pay-as-you-go pricing.  
- **Flexibility in Exchange and Cancellation**: If there’s a chance you may need to adjust your commitments (e.g., switching VM families), RIs allow for limited exchanges or prorated cancellations.  

### When to Choose Saving Plans

- **Dynamic Workloads**: Ideal for businesses with fluctuating or unpredictable workloads across multiple regions and resource types.  
- **Greater Flexibility**: If you want the ability to shift resources between regions, VM families, or other services, SPs are the better choice.  
- **Broad Coverage**: Saving Plans cover more Azure services, such as app services and container instances, making them suitable for organizations with diverse resource needs.  
- **Ease of Use**: If managing detailed reservations feels overwhelming, Saving Plans offer a simpler commitment model tied to a monetary value.  

By understanding the strengths of each option, you can decide whether Reserved Instances or Saving Plans - or a combination of both - align best with your organization’s goals.

### Azure Hybrid Benefit

**Azure Hybrid Benefit (AHB)** isn’t a traditional commitment, but it’s a powerful licensing strategy for saving costs. AHB allows organizations with **Software Assurance** to use existing on-premises licenses in Azure at no additional cost. Alternatively, you can purchase licenses specifically for Azure usage, which is often significantly cheaper than subscription-based pricing.

Microsoft estimates that AHB can reduce costs by up to **85%**, making it a valuable tool for businesses transitioning to the cloud or running long-term workloads. If you have eligible licenses, leveraging AHB is an easy way to unlock substantial savings.

## Monitor the Usage of Your Commitments

After committing to a plan, it’s crucial to regularly monitor its usage to ensure you’re maximizing its value. Are your Reserved Instances, Saving Plans, Reserved Capacities, or Hybrid Benefits fully utilized? If not, adjust your workloads or resource configurations to align with your commitments.

For example, if a reserved resource is no longer needed, consider repurposing it for other workloads within the same VM family. Staying within a limited number of VM families enhances flexibility and reduces the risk of underutilized commitments.

Additionally, take advantage of Microsoft’s free cancellation or exchange options where applicable to optimize your strategy over time. Regularly reviewing your commitments helps you stay aligned with your actual needs and avoid waste.

## Other Posts in the Cost Optimization Series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- [Azure Cost Optimization Part 4 - Rightsize your resources](2024-10-24-azure-cost-optimization-part-4-rightsize-your-resources.md)
- [Azure Cost Optimization Part 5 - Turn off if not needed](2024-11-15-azure-cost-optimization-part-5-turn-off-if-not-needed.md)
- [Azure Cost Optimization Part 6 - Start small with commitments](2024-12-30-azure-cost-optimization-part-6-start-small-with-commitments.md)
- Azure Cost Optimization Part 7 - Bring cloud optimization into your organization

## Conclusion

Commitments are a powerful tool for reducing Azure costs, but they require careful planning and ongoing management to realize their full potential. By starting small, understanding the different types of commitments, and monitoring their usage, you can build a sustainable strategy that saves money while keeping your cloud environment flexible and responsive. Combine Reserved Instances, Saving Plans, and Azure Hybrid Benefit strategically to tailor a cost-optimization approach that aligns with your organization’s needs.

Happy Optimization!
