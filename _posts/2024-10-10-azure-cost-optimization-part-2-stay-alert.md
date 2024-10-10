---
layout: post
title: "Define your budgets and stay alert!"
date: 2024-10-10
subtitle: "Azure Cost Optimization Part 2"
background: '/img/posts/budget_alert_01.png'
---
In this part of the blog series we are focussing on budgets and alerts. They are crucialfor your optimization journey, as they are the fundamental basis. You need to know what is expecting you in the upcoming months or years to being able to plan your spending in the cloud. Remember it's not CapEx, it's OpEx! 

## Know your budget!

Do you know someone that was suprised by a skyrockting cloud bill? At least I think you heard of that topic.  
A developer created a test environment to test things out and became sick the next day. The resources remained running and as he returns, he didn't think at the stil-running Kubernetes cluster. Within weeks these forgotten resources grew to a big surprise, that was revealed with the monthly cloud bill. 

It does not have to be like this. What if you define budgets for your hierarchy? Start with an overall budget for your total cloud spend and add several budgets for teams, apps, environments, etc. Create budget alerts to being informed when you are getting close or hit the budget. Like this you stay in the driver's seat and are able to derive actions.  

## Howto getting started with realistic budgets

It is pretty common that noone is budgeting at all. A lot of organizations don't know how to start, but the same orgs also realize that they are spending more than expected. Often the finance department then starts with budgets over years which are not communicated. And if they are, budgets created by finance only tend to being exceeded. At the end this leads to ignoring the budget. 

So how can you do it better? One first apporach can be to use the historical data for your budgets. As a starting point try to stay in the amount you spent in the same period last year. Be aware that this is not based on an analysis and that the amount is not verified, but it's a beginning.   

## Advancing with budgets

In the next phase you can go into rolling forecasting at least month over month. Better are shorter periods as you want to identify when new solutions or test environments are going live, which has an impact on your forecast.  
The ultimate discipline is to tie cloud spentd to business outcome. Go for unit economics performance metrics and measure spend according to business outcome.  

> My Advice: Start in small steps with your budget and mature over time.

## Use Azure Budget Alerts to stay on top of your budget

After creating budgets an important step is to monitor those budgets. With Azure Budget alerts you can define thresholds for an amount and when reaching a certain percentage being notified in order to take actions or adjust budgets.  
With transparent budgets and their monitoring you are able to define and achieve your spending goals and ensure staying in budget. 

Define Budget Alerts for Subscriptions, Resource Groups, Resources. Use your hierarchy I mentioned in [Part 1](/Cloud-Coffeebreak/_posts/2024-10-01-azure-cost-optimization-part-1-know-your-costs.md) to define your environments, apps, teams, etc. and create budget alerts on top pf them.

Here is an example on how to create Budget Alerst in Azure.

<img src="/img/posts/budget_alert_01.png" class="img-fluid"/>
Select the scope. In my case I chose a newly created Resource Group with an AKS test environment.

<img src="/img/posts/budget_alert_02.png" class="img-fluid"/>
You can apply filters like Tags or whatever to go into details. Select a recognizable name and the period and the amount of the budget.

<img src="/img/posts/budget_alert_03.png" class="img-fluid"/>
Select the conditions. In my case I created two conditions for this alert. One, inform me when we actually reached 100% of the amount and two inform me when the forecast is going to reach 100%. Use an action group and/or email address that should be used. Be aware that the alert has an enddate. You can use that for adjusting budgets regularly. 
Hit *create* and you are done.

<img src="/img/posts/budget_alert_04.png" class="img-fluid"/>
This is an example of another budget alert. There is additional information in the email like the subscription and tenant id (not in the screenshot).

You can find a Terraform module for creating budget alerts in my git repo [Terraform for Azure FinOps](https://github.com/chris4jahn/terraform-for-azure-finops/tree/main/modules/azurerm-budget-alert-for-resource-group) 

## Use Azure Anomaly Alerts to get informed when unforseen things happen

With Azure Anomaly Alerts you no longer have to fear surprises when getting your cloud bill. Microsoft offers automated and intelligent detection of anomalies to inform you on unusual spending trends. In case of an anomaly you are equipped with the information you need to adress the root cause of the spike (e.g. Subscription, Resource Group, Resource).  
Be aware that there will be false positives when using anomaly alerts. Nevertheless you should always check alerts for not becoming the next victim of skyrocketing cloud bills.

Creating an Anomaly Alert is straight forward.

<img src="/img/posts/anomaly_alert_01.png" class="img-fluid"/>
Select the scope for the anomaly alert. This must be a subscription. Management Groups, or Resource Groups are not supported.

<img src="/img/posts/anomaly_alert_02.png" class="img-fluid"/>
Select the type *anomaly* and change settings if you want to. Be aware that the alert has an enddate. 
Hit *create* and you are done.

<img src="/img/posts/anomaly_alert_03.png" class="img-fluid"/>
Here is an example of an anomaly alert. If you click on *Details* you are forwarded into Azure Cost Management Analysis. There is additional information in the email like the subscription name and id (not in the screenshot).

You can find a Terraform module for creating anomaly alerts in my git repo [Terraform for Azure FinOps](https://github.com/chris4jahn/terraform-for-azure-finops/tree/main/modules/azurerm-cost-anomaly-alert)

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

Defining and monitoring your budgets is crucial for your cost optimization. You need transperancy on where you stay in your budgets and where you are exeeding your budgets in order to take actions. Azure Budget and Anomaly Alerts help you staying on top of your budgets. Use them wherever useful and adjust them on a regular basis.  

Happy optimization!
