---
layout: post
title: "Cloud Cost Optimization in Azure"
date: 2024-05-22
subtitle: "Welche Tools unterstützen dich dabei?"
background: '/img/posts/004.png'
---
Die Cloud bringt eine neue Form des Deployments von Ressourcen mit sich und auch eine neue Kostenstruktur. IT-Kosten werden in der Cloud auf eine andere Art und Weise budgetiert, zugeordnet und reportet. Es ist gar nicht so einfach das variable Kostenmodell (OPex) zu verwalten, es lässt andererseits eine präzise Zuordnung der Kosten zu. Welche organisatorischen und kulturellen Veränderungen notwendig sind, darum geht es bei FinOps. In diesem Artikel werden wir uns auf die Azure Tools konzentrieren, die dich bei unterstützen. 

## Definition von FinOps
FinOps steht für Financial Operations und beschreibt die Disziplin Finanzverwaltung (Finance) und Betrieb (Operations) zu vereinen, um die Vorhersagbarkeit der Cloud-Kosten auf ein ähnliches Niveau, wie mit CapEx zurück zu bringen. Dazu involviert FinOps jeden in der Organisation, der Cloud Services verwaltet. 

FinOps ist eine Disziplin, die Finanzverwaltung mit Cloud Engineering und dem Betrieb kombiniert, um Unternehmen ein besseres Verständnis ihrer Cloudausgaben zu ermöglichen. Zudem hilft es ihnen, fundierte Entscheidungen zu treffen, wie sie ihre Cloudkosten zuordnen und verwalten. Wichtig: Das Ziel von FinOps besteht nicht darin, Geld zu sparen, sondern den Umsatz oder den Business Value über die Cloud zu maximieren. Deine Kosten dürfen steigen, wenn der Business Value mindestens in gleichem Maße ansteigt. Die Verknüpfung von Kosten und Nutzen sind ein wichtiger Punkt bei der Cloud Journey.

## FinOps Phasen und welche Azure Tools dafür relevant sind
In den folgenden Zeilen gehen wir auf die drei Phasen von FinOps ein und welche Tools dir bei der Umsetzung der Phasen in Azure helfen
<img class="img-fluid" src="/img/005.png" />
### Inform
Die Informationsphase ist der erste Schritt auf der FinOps-Journey. Sammle zunächst Daten aus verschiedenen Quellen, um Einblicke in deine Cloudnutzungs- und Ausgabenmuster zu erhalten. In dieser Phase konzentrierst du dich auf Berichterstellung, Anomalieerkennung, Benchmarktests, Kostenzuordnung, Taxonomie, Tagging, Prognosen und Budgetierung. 

* Schätze deine Cloudkosten mit dem Azure Preisrechner und dm TCO Rechner
* Ermögliche den Teams fundierte Entscheidungen zu treffen auf Basis von Leistungs-, Kosteninformationen und Anomalien mit dem Microsoft Cost Management und Azure Advisor
* Ordne die Kosten durch [Verwendung von Tags](2024-04-18-azure-tags-organisation-deiner-assets.md) und einer [Hierarchie aus Management Groups](2024-03-29-azure-hierarchie.md) zu  
* Verwende das Azure Cost Management, um Kosten zu sichten, zu vergleichen und vorherzusagen
* Analysiere die graphischen Dashboards im Azure Portal und nutze die Daten mithilfe von Power BI für Erkenntnisse
* Nutze Sie Azure Migrate, um ein Assessment deiner lokalen Ressourcen zu erstellen und zu bewerten, um deine Migration und Modernisierung zu planen 

### Optimize
Die Optimierungsphase ist der zweite Schritt der FinOps-Journey. Identifiziere und ergreife Maßnahmen, basierend auf den Erkenntnissen aus der Informationsphase, um deine Cloudausgaben zu optimieren und gleichzeitig die gleiche Performance zu erhalten. In dieser Phase konzentrierst du dich auf KPIs, Ergebnisse, Optimierung der Nutzung, Optimierungsrate, Business Cases.

* Nutze die Empfehlungen des Azure Advisors, um die Kosteneffizienz, Leistung, Zuverlässigkeit und Sicherheit der Cloud zu verbessern
* Optimiere die Nutzung und Kosten, indem du Einsparungsmöglichkeiten mit Azure Hybrid Benefit, Azure Reserved Instances und Azure-Saving Plans nutzt 

### Operate
Die Betriebsphase ist der letzte Schritt auf der FinOps-Journey. Richte dein Framework für die fortlaufende Cloud Kostenverwaltung und [Governance](2024-03-18-governance-in-der-cloud.md) ein, damit deine Organisation langfristig eine optimale Cloudnutzung und Kosteneffizienz gewährleisten kann. In dieser Phase konzentrierst du dich auf die organisatorische und kulturelle Einführung bewährter FinOps-Methoden. 

* Lege Richtlinien für deine Ressourcen fest, um Cloud-Compliance zu gewährleisten, fehlerhafte Konfigurationen zu vermeiden und eine konsistente Ressourcenkontrolle mit [Azure Policy](2024-04-06-azure-policies-waechter-der-cloud-compliance.md) durchzusetzen
* Vereinfache und beschleunige deine Cloud Journey mit Erkenntnissen aus Azure Migrate und Unterstützung von Experten eines Microsoft Partners, wie die <a href="https://www.provectus.de" target="_blank">Provectus Technologies</a>
* Nutze das Cloud Adoption Framework und Well-Architected Framework, um Best Practices zur Verbesserung deiner Cloud Journey einzuführen
* Ermögliche es deinem Team sich fortzubilden, um die Produktivität zu steigern, z.B. durch Microsoft-Zertifizierungen
* Fördere die Zusammenarbeit im Team mit Microsoft 365 und Microsoft Teams, um Silos aufzulösen. 

## Fazit
FinOps kann dich dabei unterstützen deine Cloud Kosten efiizient zu nutzen. Azure bietet einige Tools, die richtig eingesetzt, dich bei deiner Optimierung unterstützen. In zukünftigen Artikeln werde ich auf einzelne Aspekte und Tools genauer eingehen. 

Hast du Fragen, oder Anregungen? Dann kontaktiere mich gerne über <a href="https://www.linkedin.com/in/christian-forjahn/" target="_blank">LinkedIn</a>. 
