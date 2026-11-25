# Risikogerechte Qualität und Delivery

## Prüftiefe
- Dokumentation/mechanisch: sachliche Korrektheit und betroffene formale Prüfungen. Wirkung statt Dateiendung beurteilen: Runbooks, Konfiguration und Berechtigungsregeln können trotz kleiner Textänderung hohe Risiken haben.
- UI/gewöhnliche Funktion: relevanter Nutzerablauf, Fehlerzustand, Regression, Barrierefreiheit nach vereinbartem Umfang.
- Auswirkungen auf Datenintegrität, Vertraulichkeit, Berechtigungen, Geldflüsse oder kritische automatisierte Aktionen: unabhängiger vertiefter Review und passende negative Tests. Alternative Pfade, atomare Änderungen, Grenzen und Wiederherstellung nach konkretem Risiko prüfen. Eine reine Datenanzeige oder harmlose Hilfsautomatisierung fällt nicht allein wegen ihres Namens in diese Stufe.
- Hochriskante fachliche Entscheidungen: fachliche/rechtliche Abnahme durch zuständige Stelle; KI-Codeprüfung ersetzt sie nicht.

## Technische Risiken (nur relevante vertiefen)
- Berechtigungen serverseitig, Mandantengrenzen, alle betroffenen API-/Import-/Restore-/Einladungs-/Altbestandspfade.
- Eingaben, Dateiformate, Größen, Typen, Grenzwerte; kumulierte Kosten, parallele Anfragen und Ressourcenverbrauch. Ein Zeitcheck vor synchronem Lauf unterbricht diesen nicht; keine harte Deadline behaupten ohne wirksamen Mechanismus.
- Datenintegrität, konkurrierende Writes, idempotente Wiederholung, Fehlerbehandlung, Migration und Widerrufs-/Sicherheitszustände. Kein Rollback, der widerrufene Zugänge oder alte Berechtigungen wiederbelebt.
- Geheimnisse, Abhängigkeiten, Protokolle ohne sensible Inhalte, minimale Rechte, Deployment- und Betriebszugriffe.
- Fachliche Regeln, Zeit-/Datumsgrenzen, Währungen, Revisionen, menschliche Kontrolle und Nachvollziehbarkeit soweit relevant.

## Release-Kandidat
1. Exakter Code-/Build-Stand und CI/Review-Nachweise; keine Freigabe eines anderen Commits.
2. Unfertige Funktionen nur ausklammern, wenn tatsächlich serverseitig isoliert, nicht über alternative Pfade erreichbar und gemeinsame Komponenten sicher sind.
3. Sicherung und Restore passend zum Datenrisiko; bei realen Daten auch Konsistenz, Aufbewahrung, Verlust-/Widerrufsrisiken. Vorhandene Backup-Dienste zuerst verifizieren statt pauschal ersetzen.
4. Migration/Startschreibvorgänge und Rückweg vorab klären. Sauberer Neustart nur bei nachweislich entbehrlichem Bestand, geprüftem Backup und ausdrücklicher Autorisierung. Keine Löschung als Standard. Bei irreversibler Migration Forward-Recovery planen.
5. Betreiberzugang, Konfiguration, Healthchecks, relevante echte Nutzerabläufe, Monitoring und Abbruchkriterien. Nur autorisiert deployen; tatsächlichen Live-Stand verifizieren. Healthcheck allein reicht nicht.
6. Recht/Datenschutz, Verträge, fachliche Abnahmen und ggf. Pentest risikogerecht und parallel vorbereiten; keine Rechtskonformität behaupten ohne Beleg. Keine kostenpflichtige Beauftragung ohne Freigabe.

## Auslieferungsstrategie
Kleine kohärente Releases, nicht jedes Commit und nicht monatelange Großintegration. Vorhandene sichere Umgebung nutzen, keine permanente Staging-Infrastruktur als Default. Technische Erprobung mit synthetischen Daten von realem Pilot und Marktstart trennen, soweit diese Stufen zum Projekt gehören. Ein Teiltest liefert Erkenntnisse über seinen Umfang und ist deshalb nicht nutzlos; er belegt keine ungetestete Gesamtfunktion. Prüfe vor der jeweiligen Freigabe die dafür vereinbarten Nutzerabläufe. Keine zentralen Differenzierungsmerkmale eigenmächtig aus dem Launch streichen; eine ausdrücklich beschlossene Zieländerung respektieren.
