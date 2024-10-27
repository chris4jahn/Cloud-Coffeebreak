---
layout: post
title: "Rightsize your resources"
date: 2024-10-28
subtitle: "Azure Cost Optimization Part 4"
background: '/img/posts/Rightsizing-azqr-excel-report.png'
---

With Part 4 of our series on Azure cost optimization, we dive into rightsizing your resources. This process plays a crucial role in minimizing costs in your cloud environment. But what is rightsizing? How do you identify overprovisioned resources? And what's the best way to mitigate these inefficiencies?

## What is Rightsizing?

Rightsizing is the process of identifying overprovisioned services and adjusting their size to match actual needs. This process doesn't stop with compute resources alone but extends to databases, storage, and other cloud resources.

Imagine a customer who started deploying new services in the cloud regularly. During setup, IT teams may choose larger instances to ensure smooth user experiences when setting up applications. However, when these services are handed over to the business, they often stay oversized. Over time, the number of overprovisioned services grows, increasing costs without adding value.

## Why Do Resources Become Overprovisioned?

There are several reasons for overprovisioning. Here are three examples:

Initial Over-Allocation: As mentioned, services are often deployed in "t-shirt sizes," where oversized instances are chosen. Many forget that resource size is flexible and can be adjusted as needed.
Changing Requirements: During an application's lifecycle, requirements may change. You may initially expect high demand and allocate resources accordingly, only to find lower demand. Always reassess and adjust workloads over time.

Data Storage for Compliance: Some applications write substantial amounts of data, which must be stored for compliance reasons but may not require immediate access. In such cases, consider moving the data to cheaper storage tiers, like cold or archive storage.

These reasons highlight the importance of identifying and adjusting overprovisioned services to control costs effectively.

## How to Identify Resources That Need Rightsizing

To locate overprovisioned resources, leverage Azure’s built-in tools:

Azure Advisor offers insights across various services.
Azure Quick Review (azqr), a command-line tool, scans your subscription for optimization opportunities like compliance, security, and cost.

These tools rely on ongoing monitoring of resource metrics (e.g., CPU, memory, storage, and network usage) to highlight potential optimizations. Regular monitoring empowers teams to spot both over- and under-provisioned resources.

Pro Tip: Regular monitoring is essential for effective rightsizing!

## Using Azure Quick Review (azqr) to Identify Overprovisioned Resources

The azqr command-line tool can help identify overprovisioned resources, among other checks. It’s designed to highlight non-compliant resources that don’t align with Microsoft’s best practices. Additionally, azqr pulls data from Azure Advisor and outputs a convenient Excel file summarizing optimization opportunities.

### How to Use azqr for Rightsizing

<img src="/img/posts/Rightsizing-using-azqr.png" class="img-fluid" alt="Azure Quick Review Command"/>
Start by logging in with az login. Choose the subscription you want to scan. Run the command azqr scan.

<img src="/img/posts/Rightsizing-azqr-excel-report.png" class="img-fluid" alt="Azure Quick Review Excel Report"/>
After scanning, an Excel report is generated in the directory where you ran the command, providing a structured list of rightsizing recommendations.

## Implementing Rightsizing Recommendations

Once you have a list of rightsizing recommendations, collaborate with accountable teams before making changes. Resizing resources without coordination can lead to issues, especially if resources are managed through Infrastructure as Code (IaC). In such cases, resizing directly in the Azure portal may result in "code drift," where the IaC-defined size conflicts with manual changes. This can lead to resources reverting to the original size or, worse, deployment failures.

Tip: Always inform relevant teams or users about findings and available rightsizing options.

## Other posts in the cost optimization series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- [Azure Cost Optimization Part 4 - Rightsize your resources](2024-10-24-azure-cost-optimization-part-4-rightsize-your-resources.md)
- Azure Cost Optimization Part 5 - Turn off if not needed  
- Azure Cost Optimization Part 6 - Start small with commitments
- Azure Cost Optimization Part 7 - Bring cloud optimization into your organization

## Conclusion

Rightsizing enables you to adjust overprovisioned services to match actual needs, saving costs and optimizing resources. Lifecycle changes, storage requirements, and initial over-provisioning are common reasons for oversized resources. Leverage Azure’s monitoring tools to identify and adjust overprovisioned assets, and always communicate rightsizing options with relevant teams.

Happy optimizing!