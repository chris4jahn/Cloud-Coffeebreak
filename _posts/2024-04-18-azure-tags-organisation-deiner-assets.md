---
layout: post
title: "Azure Tags: Organisation für deine Cloud Assets"
date: 2024-04-18
subtitle: "Azure Governance"
background: '/img/header.webp'
---
Azure Tags helfen dir dabei einen Überblick über deine Cloud Ressourcen zu bewahren. Sie sind ein wichtiges Werkzeug bei der Organisation und sollten möglichst von Anfang an, oder zumindest frühzeitig etabliert und durchgesetzt werden. Die Tags hängen auch mit der [Naming Convention](2024-03-30-azure-naming-conventions.md) zusammen, weshalb die beiden Punkte gerne zusammen bearbeitet werden.

## So erstellst du deine Tag Strategie

Für die Strategie ist es wichtig, dass du dir überlegst, welche Anforderungen du aus Business Sicht hast und welche sich aus dem Betrieb für dich und dein Unternehmen ergeben.

- Aus Business Sicht kannst du sicherstellen, dass die Informationen über involvierte Teams, die Business Owner, Kosten-Verantwortung, usw. abgebildet werden.
- Aus operativer Sicht ist es sinnvoll Informationen zur Applikation, des Environments, der Kritikalität, etc. abzubilden.

Zudem muss auch hier eine Namenskonvention gelten. Ansonsten hast du mit den Tags schnell Wildwuchs, Tippfehler erzeugen Duplikate, ... die Tags sollen schließlich dabei unterstützen die Ressourcen zu kategorisieren und Automation abzuleiten. Wenn sie dann nicht einheitlich sind, dann schlägt der Plan hier fehl.

Microsoft empfiehlt folgende Überlegungen für die Tags:

|                            | BESCHREIBUNG                                                                                                                         |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Primäre Überlegungen     | Business und Betriebs-Anforderungen definieren                                                                                       |
| Baselinenamenskonventionen | Ein standardisiertes Namensschema ist die Basis                                                                                      |
| Funktionen                 | Funktion des Workloads (App, Daten usw.); Umgebung (z. B. Entwicklung, Staging, Produktion)                                          |
| Klassifizierung            | Datenklassifizierung (öffentlich, privat, vertraulich usw.); Kritikalität; SLA.                                                    |
| Buchhaltung                | Tags, die eine Nachverfolgung der Kosten im Zusammenhang mit Ressourcenvorgängen ermöglichen. z.B. Abteilung, Projekt, Region usw. |
| Zweck                      | Geschäftsprozess, geschäftliche Bedeutung, Auswirkung auf den Umsatz.                                                              |

## Was sind übliche Usecases für Tags?

- Admins können Ressourcen schnell finden, die
  - einem definierten Workload, bspw. alle Bestandteile einer Applikation
  - einer Umgebung (Dev, Test, Prod)
  - bestimmten Business Ownern
  - etc.
    zugeordnet sind
- Für das Kostenmanagement und dessen -optimierung können Tags unterstützen, die eine eindeutige Zuordnung zu Abteilungen, oder Teams definieren. Sie können dabei helfen ROI-Berechnungen, Budgets, Optimierungen, etc. nachzuverfolgen.
- SLAs können in Tags hinterlegt werden, genauso wie die Kritikalität von Services, um einen Überblick zu erhalten und so die Arbeit der operativen Teams zu erleichtern.
- Datenklassifizierungen und die Auswirkungen auf die Sicherheit schaffen Übersicht, falls es zu Sicherheitsvorfällen kommt
- Tags helfen bei der Auswertung von Governance Anforderungen
- Automatisierung: Ein passendes Organisationsschema ermöglicht die vorteilhafte Nutzung der Automatisierung im Rahmen der Ressourcenerstellung, der Betriebsüberwachung und der Erstellung von DevOps-Prozessen. Eine Automatisierung erleichtert der IT-Abteilung ebenfalls die Verwaltung von die Ressourcen

## So erstellst du Tags im Azure Portal

Tags sind eine Kombination aus "Key" und "Value". Das bedeutet, dass du Tags in "Keys" organisierst, bspw. "Abteilung" und die Werte dann beliebig wählen kannst, z.B. "Marketing".
Vorsicht: Du solltest Tags vorgeben, die verwendet werden sollen, da ansonsten schnell Wildwuchs entstehen kann, wenn jeder seine eigenen Keys, oder Values anlegt. Keys sind nicht Case-sensitive, Values aber schon.

![Tags anlegen](/img/TagsAnlegen.png){: .img-fluid}
Tags sind über jede Ressourcengruppe, oder Ressourcen verfügbar. Du kannst über den Punkt "Tag" neue Tags anlegen, oder bestehende bearbeiten.

![Tags Übersicht](/img/TagsUebersicht.png){: .img-fluid}
In der Tags-Übersicht siehst du welche Tags in deiner Subscription verwendet werden.

Auch beim erstellen von neuen Ressourcen gibt es immer einen Reiter, um die Tags zu hinterlegen.

## Wie stellst du sicher, dass alle Ressourcen getaggt werden?

Dank [Azure Policies](2024-04-06-azure-policies-waechter-der-cloud-compliance.md) kannst du Tags von Ressourcengruppen vererben, oder sogar bei der Erstellung von Ressourcen verpflichtend machen.

Wenn du Infrastructure as Code (IaC) nutzt, dann können die Tags hier ebenso als verpflichtende Parameter hinterlegt werden.

Mit diesen Mitteln sorgst du dafür, dass deine Ressourcen alle einheitlich mit den notwendigen Tags versehen werden und kannst du die Compliance monitoren, oder sogar erzwingen.

## Fazit

Die Azure Tags sind ein wichtiges Werkzeug für die Umsetzung der Governance und Compliance in Organsiationen. Das betrifft sowohl das Business, als auch den Betrieb. Durch den Einsatz kann der Überblick über große und kleinere Umgebungen verbessert werden. Tags haben sich in zahlreichen Projekten bewährt. Setze auch du sie ein, um deine Cloud Umgebung zu optimieren.

Dieser Post ist Teil der Serie ["Governance in der Cloud: Ein Leitfaden für den Einstieg"](2024-03-18-governance-in-der-cloud.md)
