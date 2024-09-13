---
layout: post
title: "So erstellst du deinen Service Health Alert"
date: 2024-07-14
subtitle: "Hands on Azure"
background: '/img/posts/ServiceHealth01.PNG'
---
# Hands on Azure - erstelle deinen Service Health Alert
In diesem Hands on Azure zeige ich dir, wie du einen Azure Service Health Alert erstellen kannst. Zuerst machen wir das über das Azure Portal. Anschließend nutzen wir Terraform, um es automatisiert per Infrastructure as Code bereit zu stellen. 

## Was ist Azure Service Health?
Service Health bietet dir die Möglichkeit eine personalisierte Sicht auf die Verfügbarkeit von Azure Diensten und Regionen zu bekommen. Mit Hilfe von Service Health Alerts kannst du dich darüber informieren lassen, wenn bspw. in der Region "Germany West Central" Dienstprobleme bestehen, wann geplante Wartungsfenster sind, oder Änderungen an Services bevorstehen. So bist du informiert, ob die Grundlage für deine Services "healthy" ist. 

## Warum nicht Azure Monitoring nutzen? 
Der Service Azure Monitor überwacht deine Services eine Ebene höher. Wo Service Health auf die Verfügbarkeit der Platform schaut, wertet Azure Monitor Metriken der Services aus. Das kann die CPU Auslastung, Netzwerktraffic, und vieles mehr sein. Für das Monitoring deiner Cloud Infrastruktur ist es nicht nur wichtig die Applikationen und bspw. die Performance deiner Services im Blick zu haben, du solltest zudem ein Auge auf die Plattform an sich werfen.

Azure Service Health und seine Alterts sind dafür dein Mittel der Wahl. 

## Schritt für Schritt deinen Health Alert anlegen
Willst du Service Health Alerts anlegen, dann kannst du das auf mehrere Arten tun. Das geht z.B. über das Azure Portal, CLI, PowerShell, Bicep, Terraform, ... Wir schauen uns hier die Bereitstellung über das Portal und mit Hilfe von Terraform an. 

### Service Health Alert mit dem Azure Portal bereitstellen
<img src="/img/posts/ServiceHealth02.PNG" width="720" />

<img src="/img/posts/ServiceHealth03.PNG" width="720" />

<img src="/img/posts/ServiceHealth04.PNG" width="720" />

<img src="/img/posts/ServiceHealth05.PNG" width="720" />

<img src="/img/posts/ServiceHealth06.PNG" width="720" />

<img src="/img/posts/ServiceHealth07.PNG" width="720" />

<img src="/img/posts/ServiceHealth08.PNG" width="720" />

<img src="/img/posts/ServiceHealth09.PNG" width="720" />

<img src="/img/posts/ServiceHealth10.PNG" width="720" />

<img src="/img/posts/ServiceHealth11.PNG" width="720" />


### Service Health Alert automatisiert mit Terraform erstellen

## Fazit
