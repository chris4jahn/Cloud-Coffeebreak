---
layout: post
title: "Are you paying too much for your cloud?"
date: 2024-09-25
subtitle: "7 steps to start your cloud optimization"
background: '/img/posts/004.png'
---
I bet you are paying too much for your cloud services. Why I think I know that? Because I guess everyone does. The only person that is not paying too much, is the person not using cloud services. What do you think?

Do you know someone that was suprised by his cloud bill? I guess everyone knows a story. 
I had a customer that used a lot of SQL databases in Azure. As he had a multi-client service and separated data in databases this lead to increasing cloud bills as more customers were onboarded to their solution. As I saw the metrics for the databases we discussed possible solutions and finally threw the databases into an Elastic Pool which shares performance over multiple databases. Saving ~80%. 
That's just one small example of an optimized service which is a little bit more advanced. But there are easy steps to follow for identifiying low hanging fruits. 

## How to getting started with cost optimization
When it comes to optimizing cloud costs almoste everyone thinks about commitments like reserved instances or saving plans. But that's only a small part of the story. Optmizing costs does not necessarily mean reducing costs but to lower costs for a specific business outcome. For example the cost to find and onboard a new customer.
When you are at the beginning of your cloud optimization journey you are good not do everything at the once, but to start in small steps. Here is an example of 7 steps you can take to start with your cost optimization.

<img src="/img/posts/004.png" class="img-fluid"/>

## Take 7 steps to optimize your cloud in Azure
1. The first and most important step is to getting to know your costs. Start using the Azure Cost Management and dive into your costs over the last months or years. Use the same tool to get a daily or at least weekly view on your costs. Identify cost drivers and dig into your data. 
Looking at costs only once a month is not the best choice as months differ from each other. On the other hand a month is a very long time in cloud usage. This could lead to being too late if anomalies like forgotten test deployments lead to a big surprise in the upcoming bill. 
2. Create Alerts for budgets and anomalies
Getting alerts for budgets will make you better in forecasting your cloud spent. This will be important when you mature with your cloud optimization. 
Begin with creating an overall budget for the upcoming week. Over time you can adjust the budgets so that you are beginning to get a feeling for a forecast of your cloud costs. From there you can start creating budgets for teams, applications and so on. 
Create Anomaly Alerts. These alerts will help you finding services that lead to unusual cost increases. Having them in place will warn you and your teams to having a look at spikes coming from test environments that have been deoloyed and forgotten etc. Anomalies will lead to false positives but you should stay alert and not ignore them as they could prevent you from having exploding cloud spent.
3. Identify cloud waste. One of the main cost driver in grown environments are resources that are not used and at the same time not deprovisioned. This leads to increasing costs without outcome.
Over time there are more and more services in your environment and it can quickly get confusing. Sometimes after testing services they are not deprovisioed or for example during deleting a VM their discs could be left over. You can use Azure Advisor for getting a quick view on resources not in use. But be careful this will not identify all your unused resources and there can be a reason for unused ressources. Don't delete them without talking to the responsible.
4. Rightsize your resources. Cloud is not on premises. This means there is no "we always sized VMs like this". You don't have to take care of usage in the future as you can adjust the SKU whenever needed.
Often resources are deployed thinking the usage will be much higher or less than it turns out in reality. Use monitoring to identify the actual needs regarding CPU, Memory usage, etc. and adjust the SKU as needed. Azure Advisor and Azure Monitor can find over- or underutilized resources. Use the data and rightsize your resources regularly.
5. Turn services off if they are not used. That's kind of the same story as rightsizing your resources. A lot of services are not needed over night. So why not turning them off. Perhaps that you are not used to it, but that's the way pay-as-you-go is meant to being used. In classic environments it does not make big differences if a VM is running or not. But in the cloud it makes big differences. Pay as you go means you only pay for what you are using.
If you are running a service 12 hours for 5 days a week compared to 24/7 you could save ~65%! 
6. Start small with commitments. There are several ways of making commitments. Reserved Instances, Saving Plans or buying licenses for the Hybrid Benefit. All of them can safe a lot of money if they are really needed. 
Talk to the product owners and ensure that services are running 24/7 for the upcoming time before purchasing any commitment based plans. You cannot or almost not cancel your commitments after purchasing. 
7. Last but not least bring cloud optimization into your organization by providing teams and departments with the relevant data. Don't do one Dashboard to rule them all but find the individual information the receiver needs.
Create dashboards and make costs a performance metric for your teams. Involve tech, business and finance and give each of them only the relevant data. It does not help them if they have an overview of the total costs if they are not accountable for the overall spent. But if they can see their application's business outcome and costs alligned to each other they can optimize cost per business outcome.

## Cost optimization is no one-stop-shop, it's a process
You do not optimize your costs once and it's done. It is an ongoing process. You are good to go with the steps above. Start over from the beginning and optimize every part in just small steps. Start over when you are at the end. Over time this will make you better in every disciplin and mature. Embrace cloud and use the flexibility and agility, scale up and down and get used to pay-as-you-go. 

## Conclusion
You could prevent paying too much for your cloud if you are following the steps above. Start your cost optimization in small steps and try out one thing after the other. Iterate over every step again and again for becoming the expert in the relevant areas. Take care not to doing too much at a time as this could overextend your organization. Happy optimization!