**Azure Governance: Die Hierarchie von Managementgruppen und Ressourcenorganisation**

In der **Azure-Cloud** ist eine durchdachte Organisation deiner Ressourcen entscheidend, um Zugriffsrechte, Richtlinien und Compliance zu verwalten. Eine Möglichkeit, dies zu erreichen, besteht darin, **Managementgruppen** zu verwenden.

1. **Was sind Azure Managementgruppen?**
   - **Managementgruppen** sind Container, die mehrere **Subscriptions** enthalten können. Sie bieten eine Governance-Ebene über den Subscriptions
   - Die Policies, die du auf eine Managementgruppe anwendest, werden automatisch auf alle zugehörigen Subscriptions vererbt
   - Managementgruppen ermöglichen eine unternehmensweite Verwaltung, unabhängig von der Art der Subscriptions

2. **Hierarchie von Managementgruppen und Subscriptions:**
   - du kannst eine flexible Struktur von Managementgruppen und Subscriptions erstellen, um deine Ressourcen in einer Hierarchie zu organisieren
   - Nehmen wir an, du möchtest eine Richtlinie festlegen, die die Erstellung von virtuellen Maschinen (VMs) auf die Region "West Europe" beschränkt
   - du erstellst eine Managementgruppe namens "Corp" und wendest diese Richtlinie darauf an
   - Alle Subscriptions, die unterhalb dieser Managementgruppe sind, erben diese Richtlinie
   - Dadurch wird die Governance verbessert, da die Ressourcen- oder Subscription-Owner (die höchste Berechtigungsstufe in Azure) die Sicherheitsrichtlinie nicht einfach ändern können

3. **Weitere Szenarien für Managementgruppen:**
   - **Zugriffsverwaltung**: Wenn du Benutzern Zugriff auf mehrere Subscriptions gewähren möchtest, kannst du diese Subscriptions unter einer Managementgruppe zusammenfassen
   - **Skalierbarkeit**: Bis zu 10.000 Managementgruppen können in einem Verzeichnis unterstützt werden
   - **Tiefe der Hierarchie**: Eine Managementgruppenstruktur kann bis zu sechs Ebenen tief sein

4. **Wichtige Fakten zu Managementgruppen:**
   - Jede Managementgruppe kann viele „Children“ haben, aber nur einen „Parent“
   - Alle Subscriptions und Managementgruppen befinden sich in einer einzigen Hierarchie in jedem Tenant

**Fazit:**
Die Verwendung von **Managementgruppen** ermöglicht eine klare Strukturierung Ihrer Azure-Ressourcen und eine effiziente Verwaltung von Zugriffsrechten und Richtlinien. Denk daran, dass Managementgruppen derzeit in den **Cost Management**-Funktionen für **Microsoft Customer Agreement (MCA)**-Abonnements nicht unterstützt werden¹⁴.