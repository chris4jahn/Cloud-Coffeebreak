---
layout: post
title: "Azure Naming Conventions Best Practices"
date: 2024-03-30
subtitle: "Azure Governance"
background: '/img/header.webp'
---
Namens Konventionen sind wichtig, da sie dabei helfen Ressourcen schnell zu identifizieren. Um welchen Typ einer Ressource handelt es sich? Wo liegt sie? Was ist die Aufgabe der Ressourcen? Usw.

## Definiere deine Namensbestandteile

Mache dir bewusst welche Bestandteile dir im Namen deiner Ressourcen dabei helfen sie zu identifizieren und einordnen zu können. Das können z.B. der Resource Type (virtuelle Maschine, Storage, VNet,…), die Umgebung (Prod, Dev, Staging, Test), der Service Name (Marketing-DB, ERP-Addon,…), etc. sein.

## Nicht jede Ressource ist gleich

Leider ist nicht jede Ressource in Azure gleich. Teilweise dürfen Namen Bindestriche enthalten, andere aber nur Kleinbuchstaben und alphanumerische Zeichen und manche müssen unique sein. Aus diesem Grund müssen Namen entweder auf den kleinsten gemeinsamen Nenner, oder etwas unterschiedlich benannt werden.

## Meine Empfehlung für Azure Naming Conventions

Meine Erfahrung zeigt, dass sich Unternehmen am leichtesten tun, die Bestandteile der Namen möglichst mit Bindestrichen getrennt sind, um die Lesbarkeit zu verbessern.
Du solltest die für dich wichtigsten Komponenten, die du im Namen haben möchtest festlegen und nutzen.
Bei virtuellen Maschinen hat es sich bewährt das Naming an das Schema der Ressourcen on Premises anzupassen, um hier konsistent zu sein.

Microsoft hat auf seiner Webseite eine sehr gute Zusammenfassung und Empfehlung erarbeitet, auf die ich hier verweisen möchte.
[Microsoft - Define your naming convention](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming?WT.mc_id=MVP_439787){:target="_blank"}

Dieser Post ist Teil der Serie ["Governance in der Cloud: Ein Leitfaden für den Einstieg"](2024-03-18-governance-in-der-cloud.md)
