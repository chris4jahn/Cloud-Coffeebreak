---
layout: post
title: "Turn off if not needed"
date: 2024-11-15
subtitle: "Azure Cost Optimization Part 4"
background: '/img/posts/Rightsizing-azqr-excel-report.png'
---

The cloud is meant to being used in a different way than on premises resources. There is no "we have it, we use it" in Azure. If you want to get the most out of your cloud you need to adopt pay as you go. This also means shutting down services you don't need. Make use of the flexibility Azure offers you.

## Why turning things off matters?

CapEx to OpEx

## How can automation help turning things off?

Tags and automation is a good combination.

AVD and other services offer autoscaling options

- 1000 concurrent sessions on a workday
- 50 sessions over night from 8 pm
- 50 over the weekend

-> RI for sessionhosts for 50 sessions
-> PAYG for the rest (24/7 vs. 12/5 = 65% saving potential)

Turn off the services that you don't need outside core working hours and at weekends, for example. This will quickly save you +60% of your compute costs.

## How to identify candidates for shutting down?

Metrics that show a flatline in usage. Check logfiles and monitoring also for usage over night and on weekends. Talk to the accountables. Make a model like 9to5 a technical option for your resources by automating it and bring it into the company by repeating it again and again. 

## How to actually shut down resources

involve the accountable people.

In case there's no accountable make use of the "cry test".

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

Happy optimization!