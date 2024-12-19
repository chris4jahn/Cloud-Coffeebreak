---
layout: post
title: "How to move resources between regions"
date: 2024-10-17
subtitle: "with Azure Resource Mover"
background: '/img/header.webp'
---
Did you ever wanted to move resources in Azure to another region? This was not as easy as you might think. For virtual machines you could use Azure Site Recovery which is meant to replicate VMs between regions for high availability. But other resources had to be migrated one by one manually. With Azure Resource Mover you are now able to move several services between regions.

## How does Azure Resource Mover work?

As the region Germany West Central has been general available, a lot of customers asked us if we could move the resources to this new region. The answer has been, that this is possible, but it is a migration project and not that easy. Data had to be replicated and Infrastructure as Code was used to deploy new resources in the target region. With Azure Resource Mover this process has become much easier and faster.

There are many reasons why you could wish to move your services to another region. One that is very common is a closer region to your organization which could lead to lower latency. The ability to move services between regions has been very limited. Until now! With Azure Mover you can do exactly that. Currently you can move the following types of resources with Azure Resource Mover:

- Virtual Machines
- NICs
- Availability sets
- Virtual Networks
- Public IPs
- Network Security Groups
- Load balancers
- Azure SQL DBs

## How is the process for Azure Resource Manager?

With Azure Resource Mover you can now manage to plan, check for dependencies, rollback, or move your resources in one single service.

- Select your resources that you want to move
- Azure Mover validates and resolves dependencies
- decide whether to move the resources or not
- decide wether to keep the resources at the origin location or not
- delete the resources in the original region

## How to move services to another region?

Here is an example of how to move a virtual machine and its related resources from the region Westeurope to Germany West Central.
![Azure Resource Mover](img/posts/Azure-Resource-Mover-01.png){: .img-fluid}
These are the services that I want to move form West Europe to Germany West Central.

![Azure Resource Mover Step 1](/img/posts/Azure-Resource-Mover-02.png){: .img-fluid}
Search for "Azure Resource Mover" and select one of the options.

![Azure Resource Mover Step 3](/img/posts/Azure-Resource-Mover-03.png){: .img-fluid}
Add resources to the Mover.

![Select source and target region](/img/posts/Azure-Resource-Mover-04.png){: .img-fluid}
Select source and target region.

![Select the resources that you want to move](/img/posts/Azure-Resource-Mover-05.png){: .img-fluid}
Select the resources that you want to move.

![Azure Resource Mover Step 6](/img/posts/Azure-Resource-Mover-06.png{: .img-fluid})
Here you can see what is happening during the move phases.

![Azure Resource Mover Step 7](/img/posts/Azure-Resource-Mover-07.png){: .img-fluid}
During the "prepare" phase everything is being prepared dn replication of the disks is fired up.

![Azure Resource Mover Step 8](/img/posts/Azure-Resource-Mover-08.png){: .img-fluid}
In the target Resource Group (RG) a disk replica is being created for replicating the data of the VM. This takes some time. Go grab a coffee.

![Azure Resource Mover Step 9](/img/posts/Azure-Resource-Mover-09.png{: .img-fluid})
In the phase "Initiate move" a copy of the resources in the target region is being created.

![Azure Resource Mover Step 10](/img/posts/Azure-Resource-Mover-10.pn{: .img-fluid}g)
The resources in the target RG are now created.

![Azure Resource Mover Step 11](/img/posts/Azure-Resource-Mover-11.png){: .img-fluid}
Now you have the option to "Discard move" or "Commit move". We will choose commit here.

![Azure Resource Mover Step 12](/img/posts/Azure-Resource-Mover-12.png){: .img-fluid}
The last step is deleting the source after successfully testing your migration.

The move process took about 2 1/2 hours to complete. Compared to doing everything on your own this is nothing. In production scenarios I recommend having a detailed testing phase before committing the move.

In my case there was a remaining disk in the source RG. I had to delete that on my own. There was another leftover. Theresource group with the Recovery Service Vault and a storage account was not deleted after moving. Before being able to delete this RG you have to delete the locks.

## Limitations of Azure Resource Mover

- At the moment only VMs with the Security Type Standard can be moved. Trusted Launch VMs (Gen 2)  or confidetnitial VMs cannot being moved.
- Not all OS Types are supported. Check supported OS and versions at [Azure Site Recovery supported OS](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-support-matrix#replicated-machine-operating-systems)
- Not all resources and resource groups have been cleaned up. Check that on your own to be sure not to creating cloud waste.

## Conclusion

Azure Resource Mover can help you move resources between regions in a quite simple way. In the background it is using multiple Azure services to establish that. VMs are moved using Site Recovery. ARM Templates are used for deploying new resources, etc. The main benefit is that you daon't have to take care of replication or creating resources on your own. Azure Resource Mover takes that job from you.

Happy moving!
