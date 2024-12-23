---
layout: post
title: "Turn off if not needed"
date: 2024-11-30
subtitle: "Azure Cost Optimization Part 5"
background: '/img/header.webp'
---

The cloud is meant to be used differently than on-premises resources. There's no "we have it, we use it" mindset in Azure. If you want to get the most out of your cloud environment, you need to adopt the **pay-as-you-go (PAYG)** model. This also means shutting down services you don’t need. Make use of the flexibility Azure offers you.

## Why Turning Things Off Matters

Have you tried turning it off and on again? That’s not just the standard advice from *The IT Crowd* - it can also save you a lot of money. The **pay-as-you-go** model in the cloud lets you only pay for what you actually consume. This creates an opportunity to rethink how you run your IT. There’s no need to run services 24/7 if they’re only used during core working hours on weekdays.

Many organizations have services that run regularly but aren’t used every day. These services can be shut down and restarted only when needed. Some customers save significantly by embracing **serverless technology** like Azure Functions with a consumption plan. With this model, costs are based on how often the service runs. If it’s idle, it doesn’t cost anything - billing only starts when the function is triggered.

## How Can Automation Help You Turn Things Off?

To efficiently turn off services during nights and weekends, **automation** is your best friend.

### Auto-Shutdown for Virtual Machines

The simplest way to start is by enabling **Auto-Shutdown** for Azure Virtual Machines. This feature is perfect for test environments or developer machines that don’t need to run overnight. Developers can start their environments manually when they begin work the next day.
![Azure Auto-Shutdown Feature](/img/posts/Azure-Auto-Shutdown.png){: .img-fluid}
*The Auto-Shutdown feature in the Azure Portal simplifies managing costs for Virtual Machines.*

### Using Tags for Systematic Shutdown

When managing larger environments, using **tags** to organize and automate shutdown processes is highly recommended. Tags help you categorize resources, making it easier to identify and manage them systematically.

For example, you could add a tag:

- `Shutdown: 6to6`

This indicates the resource should be shut down at 6 PM and restarted at 6 AM on workdays. With automation scripts, you can use these tags to systematically shut down and restart resources as needed.

### Autoscaling: Smarter Resource Management

Autoscaling is another effective way to manage costs, especially for services like **Azure Virtual Desktop (AVD)**. Let’s consider this scenario:

- 1,000 concurrent sessions on workdays (8 AM–8 PM)
- 50 sessions overnight (8 PM–8 AM)
- 50 sessions over the weekend

In this case, you could purchase **Reserved Instances (RIs)** for session hosts for 50 Users (24/7 usage) and use PAYG for the remaining sessions. By combining RIs and PAYG with autoscaling, you could achieve up to **65% cost savings**.

Turn off or scale down services you don’t need outside of core working hours and during weekends. These simple steps can quickly save you **60% or more** on compute costs.

## How to Identify Candidates for Shutting Down

Identifying which resources to shut down requires thorough **monitoring**. Here are some steps to get started:

1. **Analyze Metrics**: Look for services with flatline metrics during specific periods (e.g., nighttime or weekends).
2. **Review Logs**: Check usage logs to confirm activity patterns.
3. **Engage with Stakeholders**: Talk to the accountable teams or individuals to verify that your findings align with actual requirements.

Transforming your business to a 9-to-5 model in IT can save costs, but it’s not just a technical change — it’s an **organizational shift**. Teams need to move away from the mindset of “we’ve always done it this way” and embrace the cloud's flexibility. Be prepared to repeat the message often: adopt **PAYG** and adapt your processes to it.

## How to Actually Shut Down Resources

After engaging with stakeholders and confirming which resources can be shut down, implement automation to manage the process efficiently.

### Step 1: Use Tags

Apply tags to the resources you want to manage. For example:

- **Tag Name**: `Shutdown`
- **Tag Value**: `9pm`

Tags make it easier to identify and group resources for automated processes.

### Step 2: Create an Azure Automation Account

Set up an **Azure Automation Account** to manage shutdown and restart tasks.
![Create an Azure Automation Account](/img/posts/Azure-Automation-Account.png){: .img-fluid}
Search for "Automation" and create an Azure Automation Account.

### Step 3: Create a Runbook

Within the Automation Account, create a **Runbook** to define the script that will handle the shutdown and restart of resources.

### Step 4: Add Your PowerShell Script

Here’s an example of a PowerShell script to shut down tagged resources:

```powershell
$tagName = "Shutdown"
$tagValue = "9pm"

# Get all virtual machines in the subscription
$vms = Get-AzVM

# Filter virtual machines with the specified tag name and value
$vmsToShutdown = $vms | Where-Object { 
    $_.Tags.Keys -eq $tagName -and $_.Tags.Value -eq $tagValue 
}

# Loop through the filtered virtual machines and stop them
foreach ($vm in $vmsToShutdown) {
    $resourceGroup = $vm.ResourceGroupName
    $vmName = $vm.Name

    Write-Output "Stopping virtual machine: $vmName in resource group: $resourceGroup"
    Stop-AzVM -ResourceGroupName $resourceGroup -Name $vmName -Force
}
```

You can schedule this script to run at specific times (e.g., every weekday at 9 PM) using Azure Automation.

## Other Posts in the Cost Optimization Series

- [Azure Cost Optimization Part 0 - Are you paying too much for your cloud?](./2024-09-25-are-you-paying-too-much-for-your-cloud.md)
- [Azure Cost Optimization Part 1 - Know your costs](./2024-10-01-azure-cost-optimization-part-1-know-your-costs.md)
- [Azure Cost Optimization Part 2 - Stay alert](./2024-10-10-azure-cost-optimization-part-2-stay-alert.md)
- [Azure Cost Optimization Part 3 - Identify cloud waste](./2024-10-16-azure-cost-optimization-part-3-identify-cloud-waste.md)
- [Azure Cost Optimization Part 4 - Rightsize your resources](./2024-10-28-azure-cost-optimization-part-4-rightsize-your-resources.md)
- [Azure Cost Optimization Part 5 - Turn off if not needed](./2024-11-30-azure-cost-optimization-part-5-turn-off-if-not-needed.md)
- [Azure Cost Optimization Part 6 - Start small with commitments](./2024-12-13-azure-cost-optimization-part-6-start-small-with-commitments.md)
- [Azure Cost Optimization Part 7 - Bring cloud cost optimization into your organization](./2024-12-23-azure-cost-opmization-part-7-bring-cloud-cost-optimization-to-your-organization.md)

## Conclusion

The cloud offers immense flexibility, but unlocking its full potential means adapting how you manage your IT. Shutting down unused resources outside of core hours is a simple yet powerful way to optimize costs. With tools like Azure Automation, tagging, and autoscaling, you can save significant amounts on your cloud bills while maintaining an efficient IT environment.

Start small, automate where possible, and repeat the process until it becomes a habit.

Happy optimizing!
