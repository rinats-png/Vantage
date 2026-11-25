# Belastbare Prognosen ohne neue Messinfrastruktur

Nutze vorhandene Git-/PR-/Backlog-/CI-Historie. Ein PT ist nur die definierte Schätzeinheit, kein gemessener menschlicher oder KI-Arbeitstag. Kläre ob Kalender- oder Arbeitstage; gleiche Einheiten bei Rest und Rate. Verwende vergleichbare Aufgabenklassen und Zeiträume. Initialschub nicht als Dauerleistung extrapolieren.

## Minimalrechnung
- Baseline der offenen vereinbarten Arbeit am Stichtag festhalten.
- Bruttoabschluss: ursprüngliche Schätzeinheiten tatsächlich abgenommener bestehender Aufgaben; getrennt von neu angelegten und sofort erledigten Aufgaben.
- Unterscheide neu bestellte Funktion, neu entdeckte notwendige Arbeit, Schätzkorrektur und reine Umgliederung vorhandener Arbeit. Eine Paketaufteilung erhöht nicht automatisch den Arbeitsumfang. Kurze Lebensdauer beweist keine bloße Buchführung. Teilfortschritte separat belegen; keine Statusfaktoren als Messung und keine Doppelzählung zwischen Eltern- und Teilpaketen.
- Nettoabbau = belegter Abbau bestehender Restarbeit minus zusätzliche offene Arbeit (Schätzrevisionen getrennt). Bei null/negativem Nettoabbau ist ein unverändert fortgesetzter Zufluss kein tragfähiger Weg zu einem Endtermin. Eine Prognose für einen begrenzten, eingefrorenen Lieferumfang bleibt möglich, wenn dessen Rest und Kapazität ausreichend belegt sind. Kein Nettoabbau bedeutet nicht, dass kein Produktnutzen entstanden ist.
- Vergleiche verfügbare Zeitfenster (z.B. 7/14/30 Tage) ohne dieselben überlappenden Wochen als unabhängige Messungen zu behandeln. Rate als Schätzpunkt-Durchsatz kennzeichnen, nicht Ist-Stunden.
- Rest je Produktbereich aus tatsächlichen offenen Abnahmen und belegten Teilfortschritten; unbekannte Anteile als Bandbreite. Nicht alle Pakete neu schätzen, nur entscheidungsrelevante große Abweichungen.
- Rest / beobachteter vergleichbarer Durchsatz ist eine bedingte Szenariorechnung, keine belastbare Untergrenze und keine Garantie. Sie setzt vergleichbare Schätzeinheiten, Aufgaben, verfügbare Kapazität und Arbeitsweise voraus. Ist die Rate für das ganze Team gemessen, nicht noch einmal mit der Agentenzahl multiplizieren. Abhängigkeiten und gemeinsam genutzte Kapazität berücksichtigen: unabhängig bearbeitbar bedeutet nicht kostenlos parallel. Keine doppelte Addition überlappender Bereiche, Wartezeiten oder Puffer.

## Ausgabe
Bei einer angefragten Prognose: Stichtag, Scope, Quellen, Rest, vergleichbare Rate, Abhängigkeiten und wesentliche Unsicherheiten nennen. Die Detailtiefe an die Entscheidung anpassen. Je Meilenstein Szenarien nur bei ausreichender Datenbasis; sonst unbekannt und fehlende Evidenz. Optimistisch/realistisch/konservativ sind keine statistischen Konfidenzintervalle. Auch eine breite Spanne braucht eine begründete Herleitung. Externe Bearbeitungs- und Pilotzeiten nicht aus einem anderen Projekt übernehmen oder ohne belegte Zusage als terminlich gesichert behandeln. Relevante Reifegrade getrennt ausweisen.

## Optimierung verifizieren
Vorher/nachher anhand bestehender Daten: tatsächlich abgenommene Nutzerfunktionen, reale Releases, Nettoabbau, Kosten soweit bekannt, CI-/Review-Wartezeiten und Regressionen. Zeilen/PRs als Diagnoseindikatoren, nicht Produktivitätsmaß. Ein reduzierter Scope darf bei identischer Rate und Abhängigkeit nicht später enden; falls Prognose dennoch später ist, neue Annahmen explizit erklären. Zielwerte von nachgewiesener Kapazität trennen.
