---
layout: post
title: "Die Hierarchie mit Management Groups etablieren"
date: 2024-01-28
subtitle: "Azure Governance"
background: '/img/header.png'
---
Azure Management Groups bieten eine effiziente Möglichkeit, den Zugriff, Richtlinien und die Konformität über viele Azure Subscriptions hinweg zu verwalten. Sie ermöglichen es, Subscriptions in einer Hierarchie zu organisieren, die eine einheitliche Richtlinien- und Zugriffsverwaltung unterstützt.

## Wichtige Fakten zu Management Groups

- Hierarchische Organisation: Management Groups erlauben es dir, Subscriptions in einer Baumstruktur zu organisieren, wobei Richtlinien und Zugriffssteuerungen von oben nach unten vererbt werden
- Policies und Zugriffssteuerung: Du kannst Richtlinien auf eine Management Group anwenden, die dann auf alle untergeordneten Abonnements und Ressourcen übertragen werden. Das gewährleistet eine konsistente Governance über alle Ressourcen hinweg
- Rollenbasierte Zugriffssteuerung (RBAC): Azure Management Groups unterstützen RBAC, um sicherzustellen, dass nur autorisierte Benutzer Zugriff auf Ressourcen haben
- Skalierbarkeit: Verwaltungsgruppen sind für die Verwaltung im großen Maßstab konzipiert und eignen sich daher besonders für Unternehmen mit vielen Subscriptions

In der **Azure-Cloud** ist eine durchdachte Organisation deiner Ressourcen entscheidend, um Zugriffsrechte, Richtlinien und Compliance zu verwalten. Eine Möglichkeit, dies zu erreichen, besteht darin, **Management Groups** zu verwenden

## Aufbau von Management Groups

1. **Root Management Group:** Wenn du Management das erste mal aktivierst, dann wird in deinem Entra Tenant eine Root Mangement Group angelegt, die die oberste Hierarchie der darstellt. Diese Gruppe kann Poliies und Zugriffsrechte auf Tenant-Ebene regeln.
   1. Der Standard Name ist "Tenant Root Group". Um den Namen zu ändern, musst du auf der Ebene der Root Management Gruppe die Rolle "Owner", oder "Contributor" haben
   2. Die Root Group kann weder verschoben, noch gelöscht werden
   3. Alle Management Groups, Subscriptions, Resource Groups und Ressourcen bekommen die Policies und Zugriffsberechtigungen der Root Group vererbt. Das trifft auf bestehende und neue Elemente zu
   4. Die Root Management Group ist für alle sichtbar. Das Management ist aber den Rolen Owner und Contributor vorbehalten
2. **Management Groups:** Unterhalb der Root Management Group befinden sich die untergeordneten Management Groups, die ihre Policies und Zugriffsberechtigungen auf die ihnen untergordneten Elemente vererben

## Fazit

Mit Azure Management Groups können komplexe Policies und Berechtigungsstrukturen des Organisation und der Fachbereiche in der Azure Cloud abgebildet werden. Meiner Erfahrung nach, haben die Management Groups ihre Daseinsberechtigung, sobald mehr als eine Subscription genutzt wird. Auf der obersten Ebene kann die zentrale IT sicherstellen, dass Break Glass Accounts berechtigt sind, genauso wie die Administratoren. Darunter können dann Strukturen aufgebaut werden, die die Anforderungen von Fachabteilungen und der IT erfüllen.

Dieser Post ist Teil der Serie ["Governance in der Cloud: Ein Leitfaden für den Einstieg"](2024-03-18-governance-in-der-cloud.md)
