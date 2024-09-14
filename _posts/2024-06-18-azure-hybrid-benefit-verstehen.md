---
layout: post
title: "Der Azure Hybrid Benefit lohnt sich fast immer!"
date: 2024-06-18
subtitle: "selbst wenn du die Lizenzen dafür einkaufst"
background: '/img/posts/005.png'
---
Auf den Punkt gebracht ermöglicht der Azure Hybrit Benefit (ehemals Azure Hybrid Use Benefit) dir deine bestehenden Windows Server und SQL Server Lizenzen auch in der Cloud zu nutzen. Der Azure Hybrid Benefit (AHB) ermöglicht auf diese Art immense Einsparmöglichkeiten bei der Verwendung der Microsoft Server Produkte. 

<img class="container" src="/img/01AzureHybridBenefit.png"/>

## Wie funktioniert der Azure Hybrid Benefit?
Um den AHB nutzen zu können, benötigst du Windows Server, bzw. SQL Lizenzen inkl. einer gültigen Software Assurance aus einem Enterprise Agreement (EA), oder eine CSP Subscription. Verfügst du über diese Lizenzen, dann kannst du sie für deine Workloads in Azure, oder für die Lizenzierung von Azure Stack HCI (Azure aus deinem eigenen Rechenzentrum heraus) einsetzen und so die Kosten für das Windows Betriebssystem sparen. 

## Was kostet das Windows Betriebssystem in der Pay as you go Subscription?
Wenn du deine Lizenzen über Azure Pay as you go beziehst, was der Standard ist, dann fallen dafür monatliche Kosten an. Die Kosten belaufen sich Stand 09.2024 in der Region Germany Central auf monatlich 241,37 € für eine VM D8s V5 (8 Cores). Das bedeutet jährliche Kosten von knapp 3.000 €. Diese Kosten kannst du einsparen, wenn du über eine gültige Windows Server Lizenz verfügst. Das entspricht einem Einsparpotenzial von knapp 45%. Davon kannst du einen Großteil einsparen!

## Wie muss ich meine VMs in Azure mit AHB lizenzieren?
Um eine korrekte Lizenzierung der Azure VMs sicherzustellen, musst du für jede virtuelle Maschine mindestens ein 8-Core Pack der Windows Server Lizenzen verwenden, auch wenn die Azure VM weniger vCores verwendet. Für VMs, die mehr als 8 vCores haben, musst du die weiteren Cores mit 2-Core Packs, oder weiteren 8-Core Packs ergänzen. Du kannst dafür Windows Server Standard, oder Datacenter Lizenzen verwenden. Wichtig ist wie oben erwähnt eine aktive Software Assurance, oder Subscription.
Windows Server Standard Lizenzen dürfen entweder on Premises, oder in der Cloud verwendet werden. Gleichzeitig ist das nur für einen Zeitraum von 180 Tagen während einer Migration zu Azure erlaubt. 
Windows Server Datacenter Lizenzen dürfen in der Cloud und on Premises genutzt werden. Hier besteht keine zeitliche Beschränkung, außer bei der Verwendung von Dedicated Hosts in Azure. In diesem Fall gilt der gleiche 180 Tage Migrationszeitraum wie bei der Standard Lizenz.
Die unlimitierte Nutzung von virtuellen VMs auf einem Dedicated Host in Azure bleibt der Datacenter Edition vorbehalten. 
Das bedeutet, dass sich der AHB für Organisationen, die Hybrid aufgestellt sind doppelt rechnen kann. 

## Wie muss ich Azure Stack HCI mit AHB lizenzieren?
Wenn du Azure Stack HCI per AHB lizenzieren möchtest, kannst du darauf eine beliebige Anzahl an Windows Server VMs betreiben. Voraussetzung ist das für jeden physischen Core auf der Hardware eine Windows Server Core Lizenz vorgehalten wird. Nur die Datacenter Edition ist hierfür nurtzbar. 

## Fazit
Der AHB ist eine weitere Möglichkeit für dein FinOps Team deine Kosten in der Cloud zu reduzieren. Der Einsatz lohnt sich in den meisten Fällen selbst dann, wenn du die VM nicht dauerhaft läift und du die Lizenz per Subscription extra für diesen Zweck beziehst. Organisationen, die die Hybrid Cloud Strategie verfolgen profitieren am meisten vom AHB, da sie mit einer Lizenz sowohl die On Premises, als auch die Cloud Server lizenzieren können. 
Willst du mehr über den AHB wissen und selbst Geld sparen, dann kontaktiere mich!
