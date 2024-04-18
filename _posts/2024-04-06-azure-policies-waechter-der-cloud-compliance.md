---
layout: post
title: "Azure Policies: Der Wächter deiner Cloud-Compliance"
date: 2024-04-06
subtitle: "Azure Governance"
background: '/img/02AzurePolicyAssignPolicy.png'
---
# Azure Policies: Der Wächter deiner Cloud-Compliance

Azure Policies sind eine Sammlung von Regeln und Best Practices, die dir dabei helfen, deine Azure-Ressourcen konform und sicher zu halten. Sie ermöglichen es dir, deine Cloud-Umgebung nach deinen eigenen Governance-Vorgaben, bzw. denen deines Unternehmens, zu gestalten und zu überwachen.

## Warum sind Policies wichtig?

Azure Policies sind entscheidend, um sicherzustellen, dass alle Ressourcen in der Cloud den Unternehmensrichtlinien, regulatorischen und Compliance Anforderungen entsprechen, sowie Sicherheitsanforderungen berücksichtigt und verbessert werden. Sie bieten die Möglichkeit, die Cloud-Umgebung automatisch zu überwachen und zu steuern, was in den meisten Fällen manuell kaum zu bewältigen wäre.

## Welche Usecases gibt es?

Azure Policies können für eine Vielzahl von Anwendungsfällen eingesetzt werden, von der Sicherstellung, dass nur genehmigte Ressourcentypen erstellt werden, über die Durchsetzung von Netzwerksicherheitsregeln bis hin zur Überwachung und Korrektur von Konfigurationen in Echtzeit.

Insbesondere auch im Zusammenspiel mit Defender for Cloud um regulatorische Anforderungen (z.B. für NIST, CIS, oder PCI-DSS) zu erfüllen, bieten Azure Policies eine nahtlose Integration, um Sicherheits- und Compliance-Standards automatisiert durchzusetzen und zu verwalten. Sie ermöglichen es, Sicherheitsbewertungen durchzuführen, potentiellen Bedrohungen zu erkennen und diese zu verbessern, was eine starke Sicherheitsgrundlage für jede Cloud-Umgebung schafft.

- **Automatisierte Compliance:** Durchsetzung von regulatorischen Standards wie NIST, CIS oder PCI-DSS
- **Sicherheit mit Defender for Cloud:** Integrierte Sicherheitsbewertungen und Bedrohungserkennung
- **Kostenkontrolle:** Vermeidung unnötiger Ausgaben durch Durchsetzung von Ressourcenbeschränkungen
- **Ressourcenmanagement:** Konsistente Anwendung von Tags und Namenskonventionen über Ressourcengruppen hinweg

## Wie konfigurierst du Azure Policies?

Navigiere zum [Azure Portal](https://portal.azure.com) und nutze die Suchfunktion. Suche nach "Policy" und wähle den Eintrag aus.

<img src="/img/01AzurePolicy.png" width="720" />

Hier kannst du die Option "Assign Policy" auswählen, um eine bestehende Policy auszuwählen und anzuwenden.

<img src="/img/02AzurePolicyAssignPolicy.png" width="720" />

Wähle die gewünschte Policy aus. In meinem Fall, habe ich eine der Standard Policies ausgewählt, die nahezu bei jedem Kunden Anwendung findet. Mit der Policy "Allowed resource deployment regions" schränkst du ein, in welchen Regionen Azure Ressourcen erstellt werden dürfen.

<img src="/img/03AzurePolicyAssignBasic.png" width="720" />

Unter den Parameter Settings kannst du auswählen, in welchen Regionen die Ressourcen angelegt werden dürfen und für welchen Scope das gilt. In meinem Fall ist der Scope die "Tenant Root Group". Das bedeutet es gilt für alle darunterligenden Subscriptions. Ich habe mich für dieses Beispiel auf die Regionen in Deutschland beschränkt. Da es tlw. Ressourcen gibt, die global bereitgestellt werden, wähle ich auch diese mit aus. Ansonsten können manche Ressourcen wie z.B. Entra ID, Azure Traffic Manager, oder Azure DNS nicht erstellt werden.

Hinweis: Da noch nicht alle Ressourcen in den deutschen Regionen bereitstehen, empfehle ich die Settings so nur bedingt.

<img src="/img/04AzurePolicyParameter.png" width="720" />

Mit der "Non Compliance Message" kann ich definieren, welche Meldung ein Administrator erhält, wenn er versucht eine Ressource z.B. in den USA zu erstellen. Das hilft, dem Admin zu verstehen, warum sein Deployment nicht klappt.

Tipp: Es macht Sinn hier weiterführende Informationen zu hinterlegen, z.B. wen der Benutzer ansprechen kann.

<img src="/img/05AzurePolicyNonComplianceMessage.png" width="720" />

Neben den bereits existenten Policies können auch eigene erstellt werden.

Policies können unterschiedliche Actions haben. Während des Deployments können non-coompliant Resources

- verboten werden
- auditiert werden
- die Ressource vor dem Change angepasst werden
- die Ressource nach dem Change angepasst werden
- verknüpfte Ressourcen erstellt werden, um die Compliance sicher zu stellen
- Aktionen bei Ressourcen verhindert werden

Dank dieser Actions bieten sich mit Policies ein ganzer Blumenstrauß an Möglichkeiten, um die eigenen Anforderungen stets im Blick zu halten. 

## Fazit

Azure Policies sind ein mächtiges Werkzeug, um die Sicherheit, Compliance und das Kostenmanagement in Ihrer Cloud-Umgebung zu optimieren. In Kombination mit Defender for Cloud bieten sie eine robuste Lösung, um regulatorische Anforderungen effizient zu erfüllen und Ihre Ressourcen proaktiv zu schützen.

Dieser Post ist Teil der Serie ["Governance in der Cloud: Ein Leitfaden für den Einstieg"](2024-03-18-governance-in-der-cloud.md)
