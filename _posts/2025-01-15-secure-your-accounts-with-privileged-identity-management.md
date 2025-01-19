---
layout: post
title: "Azure Privileged Identity Management"
date: 2025-01-15
subtitle: "Secure your Accounts with PIM"
background: '/img/header.webp'
---

Recently I wrote a blog post about securing your backups so that one cannot do adminstrative changes using Azure Secure Guard. This is realized by using a certain Azure Administrative Role that this person needs to have. To enhance security in this and other cases even more let's use Azure Privileged Identity Management (PIM).

I'm a huge fan of PIM as it enables the principle of least privilege and at the same time ensures that admins are able to get the privileges they need to do their job.

## What is Privileged Identity Management?

Generally said PIM enables you to give a user an admin role at the time he or she needs it to get the administrative tasks done and not having that role permanently. This ensures that the person can do his work but on the other side reducing the permissions to realize a model of just enough access (JEA) or the principle of least privilege.

With PIM you can use the admin roles on demand and timely bound. And for highly priviliged roles you can even add another security layer with an approval workflow.

## Prerequesites for PIM

For being able to use PIM in your tenant you need to have the appropriate Entra ID licenses. Every User that uses PIM needs to have an Entra ID P2 license or an equivalent. Guest users are free. There is also a free trial option if you didn't use it yet. See the [Microsoft documentation](https://learn.microsoft.com/en-us/entra/id-governance/licensing-fundamentals#starting-a-trial){:target="_blank"} for more details on that.

To configure PIM you need to have one of the following roles: Privileged Role Administrator or Global Administrator.

## What are the features?

Privileged Identity Management provides time-based and approval-based role activation to mitigate the risks of excessive, unnecessary, or misused access permissions on resources that you care about. Here are some of the key features of Privileged Identity Management:

- Entra ID Roles
- Azure Admin Roles

- Provide just-in-time privileged access to Microsoft Entra ID and Azure resources
- Assign time-bound access to resources using start and end dates
- Require approval to activate privileged roles
- Enforce multifactor authentication to activate any role
- Use justification to understand why users activate
- Get notifications when privileged roles are activated
- Conduct access reviews to ensure users still need roles
- Download audit history for internal or external audit
- Prevents removal of the last active Global Administrator and Privileged Role Administrator role assignments

## Setting up PIM step by step

Let's take our example from the last blog post. [Backups are protected by Resource Guard](./2025-01-01-overlooked-azure-backup-feature-additional-security-with-multi-user-authorization-mua.md) and only users with the role "Backup MUA Operator" are able to execute secured backup operations like deleting backups.

So let's use PIM to give a user the possiblity to do these secured tasks. 

## Pro Tipp

Approval workflows can take some time. If you want to be sure to get the permissions at a certain time, you can request a role for a certain timeframe in the future.

## Conclusion
