---
layout: post
title: "Azure Cost Optimization Part 2"
date: 2024-10-01
subtitle: "Stay Alert!"
background: '/img/posts/006.png'
---
In the first part of this blog series we discussed knowing your costs. If you don't know your costs, how can you optimize them. In this part we are focussing on budgets and alerts as they are the fundamental basis for your optimization journey. 

## Know your budget!

Do you know someone that was suprised by a skyrockting cloud bill? At least I think you heard of that topic. A developer created a test environment to test things out and became sick the next day. The resources remained running and as he returns he never thought about the forgotten Kubernetes cluster. Within the weeks these forgotten resources grew to big surprise when the monthly cloud bill arrived. 

It does not have to be like this. What if you define budgets for your hierarchy? on overall budget if you want to and several budgets for teams, apps, environments, etc. If you are getting close or hit the budget you are getting informed and are able to derive actions.  

## How do you get to realistic budgets?

It is pretty common that noone is budgeting at all. A lot of organizations don't know how to start, but the same orgs also realize that they are spending more than expected. Often the finance department then starts with budgets over years which are not communicated. This leads to ignoring the budget. 
One first apporach can be to use the historical data for your budgets. As a starting point try to stay in the amount you spent last year. Be aware that this is not based on an analysis and that the amount is not verified as if it is the right amount.  
Later you can go into rolling forecasting at least month over month. Better are shorter periods as you want to identify when new solutions or test environments are going live.  
The ultimate discipline is to tie cloud spentd to business outcome. Go for unit economics performance metrics and measure spend according to business outcome. 

But let's start in small steps and mature over time.

## Use Azure Budget Alerts to stay on top of your budget



## Use Azure Anomaly Alerts to get informed when unforseen things happen

## Other posts in the cost optimization series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](2024-10-14-azure-cost-optimization-part-2-stay-alert.md)
- Azure Cost Optimization Part 3 - Identify cloud waste 
- Azure Cost Optimization Part 4 - Rightsize your resources
- Azure Cost Optimization Part 5 - Turn off if not needed  
- Azure Cost Optimization Part 6 - Start small with commitments
- Azure Cost Optimization Part 7 - Bring cloud optimization into your organization 

## Conclusion

