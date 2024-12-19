---
layout: post
title: "How to create Service Health Alerts"
date: 2024-09-17
subtitle: "Hands on Azure"
background: '/img/header.webp'
---
In this Hands on Azure I'll show you how you can create your Azure Service Health Alert. In this first step we are using the Azure portal for that. In one of the next posts we are gonna be using terraform, using infrastructure as code (IaC) to manage this.

## What is Azure Service Health?

Service Health gives you the possibility to get a personalized view on the availability of Azure services and regions. With Service Health Alerts you stay informed about service disruptions in a certain region, e.g. "Germany West Central". On top of that you will be informed abouot planned maintenance including the possiblity to choose a time slot that fits your needs. Last but not least you will be informed about upcoming service changes or retirements. With Service Health Alerts you stay informed about your services and regions.

## Why not using Azure Monitor?

Azure monitor works on another level. It monitors your resources on the virtualization and OS level, where Service Health is watching the availability at the plattform level. Azure Monitor checks the metrics like CPU usage, network traffic and much more. For monitoring yoour cloud infrastructure it's important to have a look at this performance level and at the same time it is crucial to have an eye on the platfrom itself. Azure Service Health and it's alerts is your choice for that.

## Step by step to your Service Health Alert

Do you want to create your Service Health Alerts now? You can achieve this in multiple ways. You can use the Azure portal, CLI, PowerShell, Bicep, Terraform, etc. We will focus on the deployment via Azure Portal for now.

### Create your Service Health Alert using the Azure portal

![Service Health Search](/img/posts/ServiceHealth01.PNG){: .img-fluid}
Use the portal's search function to find "Service Health".

![Service Health Alert Creation](/img/posts/ServiceHealth02.PNG){: .img-fluid}
Open the menu to create a new Service Health Alert.

![Service Health Alert Subscription Selection](/img/posts/ServiceHealth03.PNG){: .img-fluid}
Choose the subscription you want to create your health alert for.

![Service Health Alert Subscription Selection](/img/posts/ServiceHealth04.PNG){: .img-fluid}
Choose the services and regions you want to monitor. You can limit the services and regions to the ones that are relevant for you. Yout don't want to receive too many messages that are not relevant to you as "false positives" could lead to loosing the focus on the relevant messages.

![Service Health Action Group Creation](/img/posts/ServiceHealth05.PNG){: .img-fluid}
Choose an existing Action Group or create a new one. We will create a new AC in this example.

![Service Health Action Group Information](/img/posts/ServiceHealth06.PNG){: .img-fluid}
Provide the necessary information.

![Service Health Notification Options](/img/posts/ServiceHealth07.PNG){: .img-fluid}
Now you can choose how you want to being informed. You can choose notifications (email, SMS, ...). Additionally you can define actions like using webhoods, an ITSM, or an Azure Function. Like this you can automate tasks based on the alerts.

![Service Health Notification Options](/img/posts/ServiceHealth08.PNG){: .img-fluid}
Let's stay with Email for now.

![Service Health Action Group Created](/img/posts/ServiceHealth09.PNG){: .img-fluid}
Your Action Group was created and can be used now and for future alerts.

![Provide the missing information for your alert](/img/posts/ServiceHealth10.PNG){: .img-fluid}
Provied the missing information for your alert.

![Review your settings and create your Service Health Alert](/img/posts/ServiceHealth11.PNG){: .img-fluid}
Review your settings and create your Service Health Alert

## Conclusion

Service Health Alerts keep you on top of planned maintenance, service disruptions and upcoming changes of services. With just a few steps you can create an alert and stay informed. It's crucial to using this kind of informartion for all your subscriptions but only for the relevant services and regions.
