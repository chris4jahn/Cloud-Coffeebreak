---
layout: post
title: "How to move resources between regions"
date: 2024-10-20
subtitle: "with Azure Resource Mover"
background: '/img/posts/Orphaned_Resources_Workbook.png'
---
What if you want to move your Azure resources to another region?

Imagine you started your cloud journey some years ago and chose the closest region to you.

In the meantime you are struggling with some services that need lower latency. So you want to use a new region that’s even closer to your HQ.

There are a lot of reasons for moving services from one region to another. But the ability to move services between regions has been very limited. Until now!

With Azure Mover you can do exactly that. Currently you can move VMs, NICs, availability sets, VNETs, public IPs, NSGs, load balancers and Azure SQL DBs.

How does it work?

- Select your resources that you want to move
- Azure Mover validates and resolves dependencies
- decide whether to move the resources or not
- decide wether to keep the resources at the origin location or not

Azure Mover allows you to move to newly built regions, response to business changes, or move because of capacity needs. 

Have you ever wanted to move your services to another region? Tell me why.
