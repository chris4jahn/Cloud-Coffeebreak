---
layout: post
title: "Overlooked Azure Backup Feature"
date: 2025-01-01
subtitle: "Additional Security with Multi-User Authorization (MUA)"
background: '/img/header.webp'
---

When it comes to protecting your data in the cloud, backup isn’t the goal—**reliable recovery** is. No one needs backups for their own sake; we need them to restore data when things go wrong. Whether it’s accidental deletion, ransomware attacks, or outages, your recovery strategy must be airtight.  

Back in the day, we secured backup tapes by physically taking them offsite to safeguard against disasters like fire or theft. In the cloud, **Multi-User Authorization (MUA)** serves as your modern equivalent of a safe place for backups. Azure stores data across multiple zones or regions to protect against local disasters, but without MUA, any backup admin with access can modify or delete backups. MUA strengthens your security by enforcing strict role-based controls for sensitive actions.  

## Why You Need Azure Backup with Multi-User Authorization (MUA)

Imagine a scenario where a backup operator's credentials are compromised during a cybersecurtiy attack. Even though Azure Backup is secure by design and prevents the encryption of backup data, attackers might still attempt to harm the organization by deleting the backups. This is where **Multi-User Authorization (MUA)** comes in as a game-changer.

By requiring administrative access to perform sensitive actions like deleting backups, MUA adds a critical layer of protection. It ensures that even if one account is compromised, malicious actors cannot single-handedly tamper with or delete your backup data.

### What is Multi-User Authorization (MUA)?

MUA adds another layer of security by requiring explicit authorization from the **Resource Guard** service for critical actions such as deletion or modification of backups. This drastically reduces the risk of insider threats or accidental misconfigurations.

MUA is one of the most **overlooked yet vital solutions** that every organization should adopt. Not only is it free, but it also provides an essential safeguard for backup operations.

## Configuring Multi-User Authorization for Azure Backup

Here’s a step-by-step guide on how to configure MUA to protect your Azure Backup or Recovery Services Vault effectively.

### Step 1: Create a Resource Guard in Another Tenant

Start by logging into the Azure Portal and creating a new Resource Guard resource. For optimal security, it’s recommended to create the Resource Guard in a **different tenant** to separate security accounts and operations completely.

![Azure Portal showing the mask for creating a Resource Guard](../img/posts/create-resource-guard.png){: .img-fluid}

1. Assign a name to the Resource Guard and ensure it is in the **same region** as your backup vault.  
2. Configure the operations the Resource Guard will protect, such as "Delete protection" and "Modify protection."  
3. Use the **"Access Control (IAM)"** blade to grant access.  
4. Assign the **Reader role** to the external backup administrator by entering their email. The user will receive an email invitation, which must be accepted before proceeding.  

![Azure Portal showing the operations Resource Guard could protect like "Delete protection", "Modify protection", etc.](../img/posts/configure-protected-operations.png){: .img-fluid}

### Step 2: Configure the Backup Vault in the Other Tenant

Once the Resource Guard is set up, switch to the other tenant where the Azure Backup Vault resides and configure it to use the Resource Guard.  

1. Navigate to the **Backup Vault's settings page** and select "Settings -> Properties."  
2. Update the MUA settings to enable protection with the Resource Guard.  

![Azure Portal that shows the settings page and its properties. "Multi-User Authorization" is highlighted.](../img/posts/update-backup-vault-settings-for-mua.png){: .img-fluid}

3. Authenticate and select the Resource Guard from the other tenant. The backup administrator, with Reader permission, will now be able to access and link the Resource Guard to the Backup Vault.  

![Azure Portal that shows the option to add a Resource Guard either by giving the Resource Guard's URI or selecting it. We choose Select.](../img/posts/select-resource-guard.png){: .img-fluid}

### Step 3: What Happens When a Delete Operation is Triggered?

If a backup administrator attempts to delete a backup without the appropriate permissions on the Resource Guard, the operation will be blocked. Only users with the **"Backup MUA Operator"** role on the Resource Guard can authorize such critical actions.  

![Azure Portal showing the Resource Guard protection when trying to delete a backup.](../img/posts/stop-backup-resource-guard-protection.png){: .img-fluid}

This ensures that unauthorized deletion attempts—whether accidental or malicious—are effectively prevented.

## What's next? Securing the Roles using Privileged Identity Management (PIM)

In one of my next blog posts I will go into using Privileged Identity Management (PIM). With PIM you can enable priviledged roles on demand and add an approval workflow on top of that. As this would go beyond the scope of this blog post, I will write a separate article about it in the next days.
Update: Here is the blog post to [using PIM for securing backups](./2025-01-20-enhancing-backup-security-with-azure-pim.md).

## Conclusion: Secure Your Backup Strategy with MUA

Azure Backup provides a robust foundation for data recovery, but adding **Multi-User Authorization (MUA)** elevates your backup security to the next level. MUA ensures that no single account can compromise your backups, protecting your organization from accidental deletions, insider threats, and ransomware attacks.

Configuring MUA is straightforward, free, and incredibly effective. By integrating a Resource Guard from another tenant, you can establish a strong separation of duties and enhance your overall security posture.

Don’t wait for a data loss incident to realize the importance of recovery readiness. **Secure your Azure Backup strategy today with Multi-User Authorization and stay prepared for any scenario!**
