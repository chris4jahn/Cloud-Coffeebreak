---
layout: post
title: "Understanding Azure Backup"
date: 2025-01-05
subtitle: "Your Key to Reliable Data Recovery"
background: '/img/header.webp'
---

When we talk about Azure Backup, it’s not just about creating backups; it’s about ensuring **reliable recovery** when it matters most. Nobody needs backups—they need recovery! Whether it's accidental data deletion, unexpected outages, or ransomware attacks, **Azure Backup** is an essential tool for protecting your IaaS and PaaS workloads (at least for some services).

## Why You Need Azure Backup

Imagine this scenario: A developer accidentally deletes an important database while working late at night. Without a proper backup in place, this mistake could result in significant downtime, lost productivity, and a lot of stress for everyone involved. Or consider a ransomware attack where malicious actors encrypt your critical files, demanding a hefty ransom to restore access. With Azure Backup, you can confidently say, "No thanks," and recover your data quickly and securely.

Backups are your safety net against **data loss** scenarios, such as:

- **Accidental deletion of data:** Mistakes happen. Azure Backup ensures those mistakes don’t have lasting consequences.  
- **System outages and downtimes:** Downtime can cripple business operations. A solid recovery plan minimizes disruption.  
- **Ransomware or malicious attacks:** With advanced protection mechanisms, Azure Backup ensures you’re prepared for even the worst-case scenarios.  

Azure Backup isn’t just about storing data; it’s about providing peace of mind knowing that, no matter what happens, your data is secure and recoverable.

## Services Protected by Azure Backup Vaults

Azure Backup supports a wide range of services, ensuring comprehensive protection for your Azure environment. These include:

- **Azure VMs**: Protect your virtual machines running on Azure against data loss.  
- **SQL Server databases on Azure VMs**: Keep your critical transactional data safe with regular backups.  
- **Azure Database for MySQL and PostgreSQL**: Ensure availability for these popular database solutions.  
- **Azure Kubernetes Services (AKS)**: Back up your container workloads to maintain application reliability.  
- **Windows Servers on-premises using MARS agent**: Extend Azure’s backup capabilities to your on-premises infrastructure.  
- **Azure Disks and Blobs**: Safeguard both unstructured and structured storage solutions.  
- **Azure File Shares**: Ensure shared storage is always accessible.  
- **SAP HANA and SAP ASE databases on Azure VMs**: Critical for enterprise workloads, these databases benefit from seamless Azure Backup support.  

### Backup for On-Premises Resources

For hybrid environments, Azure Backup extends protection to on-premises servers using the **Microsoft Azure Recovery Services (MARS)** agent. This solution enables seamless backup of files, folders, and even system states to Azure, ensuring a unified approach to data protection across environments.

## Ransomware Protection with Azure Backup

One of the standout features of Azure Backup is its ability to defend against ransomware attacks. These attacks often target backup systems, knowing that eliminating backups leaves victims with no choice but to pay. Azure Backup counters this with advanced security measures:

- **Isolation of backups:** Your backup data is stored in Recovery Services Vaults, which are separate from production environments. This separation ensures that even if your primary environment is compromised, your backups remain safe.  
- **Immutability and soft delete:** By enabling these features, you ensure that backups cannot be modified or deleted—even in the event of a breach. Soft delete adds an extra layer of recovery by retaining deleted data for up to 14 days.  
- **Encrypted storage accounts:** Backup data is stored in secure storage accounts that are only accessible through Azure Backup operations, minimizing the risk of unauthorized access.  

Learn more about these security measures in the [Azure Backup Security Overview](https://learn.microsoft.com/en-us/azure/backup/security-overview).

## Enhanced Backup Security Features

Azure Backup integrates multiple security measures to protect your data at every stage: in transit, at rest, and during operation.

### Data Encryption

Azure Backup ensures data security through encryption at every stage:

- **In transit:** All data transfers are encrypted using HTTPS, ensuring that your data remains secure during transmission.  
- **At rest:** Backup data is encrypted with either **platform-managed keys** or **customer-managed keys** to meet your organization’s compliance needs.  
- **For MARS backups:** Data is encrypted with a passphrase before being uploaded and decrypted only upon retrieval. This passphrase can be securely stored in Azure Key Vault, ensuring end-to-end protection.

### Immutability and Soft Delete

- **Soft delete:** Prevent accidental or malicious data loss by retaining deleted backup data for a configurable period (up to 14 days).  
- **Immutable vaults:** Protect critical recovery points by enabling immutability, which locks the data and makes it resistant to any changes or deletions.

### Multi-User Authorization (MUA)

Adding another layer of security, MUA ensures that sensitive actions like deletion or modification of backups require explicit authorization from multiple users or the **Resource Guard** service. This significantly reduces the risk of insider threats or accidental misconfigurations.

## Backup Monitoring and Reporting

Managing backups effectively requires visibility into their status and usage. Azure Backup provides robust tools for monitoring and reporting:

- **Built-in monitoring and alerts:** Stay informed about any suspicious activities or issues affecting your backups.  
- **Backup Reports:** Gain insights into usage trends, audit trails for operations, and detailed reports for granular analysis.  
- **Customizable actions:** Configure automated responses to specific events, ensuring a proactive approach to backup management.

These features allow you to identify and resolve potential issues quickly, maintaining the integrity of your backup strategy.

## Security Posture for Azure Backup Vaults

Azure Backup vaults can be configured with varying levels of security based on your organization’s needs:

1. **Excellent (Maximum):**  
   Comprehensive protection, including immutability and MUA, to defend against accidental and malicious threats.  
2. **Good (Adequate):**  
   Reliable security with either immutability or soft delete enabled, ensuring recoverability.  
3. **Fair (Minimum):**  
   Basic protection with Multi-User Authorization enabled, suitable for standard workloads.  
4. **Poor (None):**  
   Minimal security measures, protecting only against accidental deletions.  

To achieve the highest level of security, it’s recommended to enable **locked immutability** and **MUA** on your backup vaults.

## Private Endpoints for Enhanced Security

Azure Backup supports **Private Endpoints**, allowing you to securely back up data without exposing your resources to public networks. This feature is especially valuable for:

- SQL and SAP HANA databases running on Azure VMs.  
- On-premises servers using the MARS agent.  

By enabling Private Endpoints, you can ensure that all backup operations occur over your virtual network, adding another layer of security to your data protection strategy.

## Conclusion: Your Data Recovery Plan Starts with Azure Backup

Azure Backup isn’t just a backup solution—it’s your **recovery plan**. With its robust features, including ransomware protection, encryption, immutability, and private endpoints, Azure Backup ensures that your data is always secure and recoverable. 

By taking advantage of built-in monitoring and reporting tools, you can maintain visibility over your backups and respond proactively to any issues. Whether you’re safeguarding critical databases, on-premises servers, or containerized workloads, Azure Backup offers a flexible and comprehensive solution.

**In the end, it’s not about backups—it’s about recovery. Start building your recovery strategy today with Azure Backup!**

---

Azure Backup is an important solution when it comes to IaaS and PaaS (for some services at least) on Azure.

Nobody needs backup, everone needs recovery.

You need your backups for data loss. multiple cases. accidental deletion of data, outages, downtimes, ...

Which services can Azure Backup Vaults protect?

- Azure VMs
- SQL Server database on Azure VMs
- Azure Database for MySQL
- Azure Database for PostgreSQL
- Azure Kubernetes Services
- Windows Server on Premises using MARS agent
- Azure Disks
- Azure Blobs
- Azure File shares
- SAP HANA database on Azure VMs
- SAP ASE database on Azure VMs

Backup for on Premises resources through MARS agent. This has nothing to do with the planet but stands for Microsoft Azure Recovery Services.  

Azure Backup is also a ransomware protection through disconnecting Backup vault and backup items. No direct connection possible. If a virtual machine or another service is compromized there is no way of delteting backups
https://learn.microsoft.com/en-us/azure/backup/security-overview 

Storage accounts used by Recovery Services vaults are isolated and can't be accessed by users for any malicious purposes. The access is only allowed through Azure Backup management operations, such as restore.

With Azure Backup, the vaulted backup data is stored in Microsoft-managed Azure subscription and tenant. External users or guests have no direct access to this backup storage or its contents, ensuring the isolation of backup data from the production environment where the data source resides.

Backup of Azure VMs requires movement of data from your virtual machine's disk to the Recovery Services vault. However, all the required communication and data transfer happens only on the Azure backbone network without needing to access your virtual network. Therefore, backup of Azure VMs placed inside secured networks doesn't require you to allow access to any IPs or FQDNs.

You can now use Private Endpoints to back up your data securely from servers inside a virtual network to your Recovery Services vault. The private endpoint uses an IP from the VNET address space for your vault, so you don't need to expose your virtual networks to any public IPs. Private Endpoints can be used for backing up and restoring your SQL and SAP HANA databases that run inside your Azure VMs. It can also be used for your on-premises servers using the MARS agent.

Encryption protects your data and helps you to meet your organizational security and compliance commitments. Data encryption occurs in many stages in Azure Backup:

- In transit using HTTPS
- Data on rest is encrypted either with a platform managed key or a customer managed key
- Backup supports encrypted VM disks
- Backups using MARS are encrypted using a passphrase before uploading the data and decrypted only after downloading it. The passphrase can be stored in an Azure Key Vault. 

Soft delete enables you to recover data even after deletion.

Immutable vault can help you protect your backup data by blocking any operations that could lead to loss of recovery points. Further, you can lock the immutable vault setting to make it irreversible that can prevent any malicious actors from disabling immutability and deleting backups.

Multi-user authorization (MUA) for Azure Backup allows you to add an additional layer of protection to critical operations on your Recovery Services vaults and Backup vaults. For MUA, Azure Backup uses another Azure resource called the Resource Guard to ensure critical operations are performed only with applicable authorization.

Azure Backup provides built-in monitoring and alerting capabilities to view and configure actions for events related to Azure Backup. Backup Reports serve as a one-stop destination for tracking usage, auditing of backups and restores, and identifying key trends at different levels of granularity. Using Azure Backup's monitoring and reporting tools can alert you to any unauthorized, suspicious, or malicious activity as soon as they occur.

Security features to help protect hybrid backups
Azure Backup service uses the Microsoft Azure Recovery Services (MARS) agent to back up and restore files, folders, and the volume or system state from an on-premises computer to Azure. MARS now provides security features to help protect hybrid backups. These features include:

An additional layer of authentication is added whenever a critical operation like changing a passphrase is performed. This validation is to ensure that such operations can be performed only by users who have valid Azure credentials. Learn more about the features that prevent attacks.

Deleted backup data is retained for an additional 14 days from the date of deletion. This ensures recoverability of the data within a given time period, so there's no data loss even if an attack happens. Also, a greater number of minimum recovery points are maintained to guard against corrupt data. Learn more about recovering deleted backup data.

For data backed up using the Microsoft Azure Recovery Services (MARS) agent, a passphrase is used to ensure data is encrypted before upload to Azure Backup and decrypted only after download from Azure Backup. The passphrase details are only available to the user who created the passphrase and the agent that's configured with it. Nothing is transmitted or shared with the service. This ensures complete security of your data, as any data that's exposed inadvertently (such as a man-in-the-middle attack on the network) is unusable without the passphrase, and the passphrase isn't sent over the network.

Security posture and security levels
Azure Backup provides security features at the vault level to safeguard backup data stored in it. These security measures encompass the settings associated with the Azure Backup solution for the vaults, and the protected data sources contained in the vaults.

Security levels for Azure Backup vaults are categorized as follows:

Excellent (Maximum): This level represents the highest security, which ensures comprehensive protection. You can achieve this when all backup data is protected from accidental deletions and defends from ransomware attacks. To achieve this high level of security, the following conditions must be met:

Immutability or soft-delete vault setting must be enabled and irreversible (locked/always-on).
Multi-user authorization (MUA) must be enabled on the vault.
Good (Adequate): This signifies a robust security level, which ensures dependable data protection. It shields existing backups from unintended removal and enhances the potential for data recovery. To attain this level of security, you must enable either immutability with a lock or soft-delete.

Fair (Minimum/Average): This represents a basic level of security, appropriate for standard protection requirements. Essential backup operations benefit from an extra layer of protection. To attain minimal security, you must enable Multi-user Authorization (MUA) on the vault.

Poor (Bad/None): This indicates a deficiency in security measures, which is less suitable for data protection. In this level, neither advanced protective features nor solely reversible capabilities are in place. The None level security gives protection primarily from accidental deletions only.
