---
layout: post
title: "So erstellst du deinen Service Health Alert"
date: 2024-07-14
subtitle: "Hands on Azure"
background: '/img/header.webp'
---
In diesem Hands on Azure zeige ich dir, wie du einen Azure Service Health Alert erstellen kannst. Zuerst machen wir das über das Azure Portal. In einem der nächsten Posts nutzen wir Terraform, um es automatisiert per Infrastructure as Code bereit zu stellen. 

## Was ist Azure Service Health?

Service Health bietet dir die Möglichkeit eine personalisierte Sicht auf die Verfügbarkeit von Azure Diensten und Regionen zu bekommen. Mit Hilfe von Service Health Alerts kannst du dich darüber informieren lassen, wenn bspw. in der Region "Germany West Central" Dienstprobleme bestehen, wann geplante Wartungsfenster sind, oder Änderungen an Services bevorstehen. So bist du immer auf dem aktuellen Stand, ob die Grundlage für deine Services "healthy" ist. 

## Warum nicht Azure Monitoring nutzen?

Der Service Azure Monitor überwacht deine Services auf Virtualisierungs- und Betriebssystemebene. Wo Service Health auf die Verfügbarkeit der Platform schaut, wertet Azure Monitor Metriken der Services aus. Das kann die CPU Auslastung, Netzwerktraffic, und vieles mehr sein. Für das Monitoring deiner Cloud Infrastruktur ist es nicht nur wichtig die Applikationen und bspw. die Performance deiner Services im Blick zu haben, du solltest zudem ein Auge auf die Plattform an sich werfen. Azure Service Health und seine Alterts sind dafür dein Mittel der Wahl. 

## Schritt für Schritt deinen Health Alert anlegen

Willst du Service Health Alerts anlegen, dann kannst du das auf mehrere Arten tun. Das geht z.B. über das Azure Portal, CLI, PowerShell, Bicep, Terraform, ... Wir schauen uns hier die Bereitstellung über das Portal an. 

### Service Health Alert mit dem Azure Portal erstellen

Nutze die Suche im Azure Portal und suche nach "Service Health".

<img src="/img/posts/ServiceHealth01.PNG" class="img-fluid"/>

Öffne das Menü zum erstellen eines neuen Service Health Alerts.

<img src="/img/posts/ServiceHealth02.PNG" class="img-fluid"/>

Wähle deine Subscription aus, für die du den Alert erstellen möchtest.

<img src="/img/posts/ServiceHealth03.PNG" class="img-fluid"/>

Wähle die Services und Regionen aus, die du ins Monitoring aufnehmen willst. Hier kannst du dich auf die für dich relevanten Regionen und Services einschränken, damit du nicht False Positives bekommst für Services, die du gar nicht einsetzt, oder für Regionen, in denen du keine Ressourcen betreibst.

<img src="/img/posts/ServiceHealth04.PNG" class="img-fluid"/>

Wähle eine bestehende Action Group aus, oder erstelle eine neue. In unserem Beispiel erstellen wir eine neue Action Group.

<img src="/img/posts/ServiceHealth05.PNG" class="img-fluid"/>

Füge die notwendigen Informationen ein.

<img src="/img/posts/ServiceHealth06.PNG" class="img-fluid"/>

Jetzt kannst du entscheiden, wie du benachrichtigt werden willst. Du kannst dich per Notification (Email, SMS, ...). Zusätzlich kannst du auch Actions definieren, wie bspw. das Aufrufen eines Webhooks, eines ITSM, oder einer Azure Function. Somit kannst du automatisiert auf Meldungen reagieren.  

<img src="/img/posts/ServiceHealth07.PNG" class="img-fluid"/>

Wir haben uns auf die Benachrichtigung per E-Mail beschränkt. 

<img src="/img/posts/ServiceHealth08.PNG" class="img-fluid"/>

Deine Action Group wurde erstellt und kann ab sofort für diesen und weitere Alerts verwendet werden. 

<img src="/img/posts/ServiceHealth09.PNG" class="img-fluid"/>

Für unsere Alert Rule fehlen nur noch ein paar wenige Angaben.

<img src="/img/posts/ServiceHealth10.PNG" class="img-fluid"/>

Jetzt kannst du deine Einstellungen noch einmal prüfen und dann den Alert erstellen.

<img src="/img/posts/ServiceHealth11.PNG" class="img-fluid"/>

## Fazit

Der Service Health Alert unterstützt dich dabei über geplante Maintenance, Service Ausfälle, oder Änderungen an Diensten auf dem Laufenden zu bleiben. Mit wenigen Handgriffen hast du deinen Alert erstellt und bleibst fortan informiert. Beachte, dass du nur die Regionen und Services ins Monitoring aufnimmst, die dich interessieren, oder die du selbst einsetzt.
