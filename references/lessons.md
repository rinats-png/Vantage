# Herkunft und Lessons Learned

Verallgemeinerte Erfahrungen aus einem mit KI entwickelten Softwareprojekt und der anschließenden Prüfung seiner Entwicklungsberichte und Prognosen. Grundlage waren bereitgestellte Berichte und Gesprächsverläufe, keine unabhängig reproduzierte Gesamtauswertung des Projekts. Die Beispiele begründen prüfbare Arbeitsregeln; sie belegen keine universellen Ursachen, Produktivitätsraten oder Einsparungen. Projektnamen, konkrete Betriebsdaten und Zugangsinformationen sind für die Anwendung nicht erforderlich.

| Beobachtung / Fehlinterpretation | Berichtete Evidenz und ihre Grenze | Übertragbare Korrektur |
|---|---|---|
| Lauffähig mit marktfähig verwechselt | Kein Fremdnutzernachweis, offene Rechtsunterlagen | Reifegrade und echte Nutzerabnahmen trennen |
| Big-Bang-Release | Viele Integrationsänderungen ohne entsprechende Auslieferung; die Zahl allein beweist nicht die Ursache | Kleine geprüfte Releases und frühen technischen Testbetrieb |
| PR-Menge als Fertigstellungsbeweis | Viele Merges bei weniger Paketabschlüssen; das Verhältnis allein beweist keine Verschwendung | Produktabnahme und Lieferfähigkeit prüfen, Aktivitäten ergänzend zeigen |
| Wachsende Paketanzahl pauschal als neuen Scope gelesen | Abgeschätzte Zusatzarbeit wog den Abbau alter Arbeit auf; Ursachen waren nicht vollständig getrennt | Neue Produktwünsche, entdeckte Pflichtarbeit, Umgliederung und Schätzkorrektur unterscheiden; Fixes im Ursprungspaket halten |
| Kurzlebige Pakete vorschnell als Buchführung abgewertet | Viele Pakete kurz nach Anlage abgeschlossen; daraus folgt weder Nutzlosigkeit noch geringer Aufwand | Vorher geleistete Arbeit und neue Ergebnisse anhand Inhalt und Abnahme unterscheiden |
| Tests/Doku als Zeitmaß | Hoher Anteil hinzugefügter Test- und Dokumentationszeilen | Indikator, keine direkte Arbeitszeitmessung; echte Schutzwirkung prüfen |
| Prognose aus kurzem Anfangsschub | Hohe Rate aus wenigen Tagen, später deutlich niedrigere Rate abgeschlossener Schätzeinheiten | Vergleichbare empirische Rate und ehrliche Unsicherheit; Schätzeinheiten nicht als Ist-Stunden darstellen |
| Status als Teilfortschritt | Pauschale Abschläge für laufende Aufgaben und Reviews | Belegte Teilabnahmen statt Statusabschlag |
| Lange Tests als Hardwarebeweis, Agenten als lineare Beschleunigung | Langer lokaler Volllauf berichtet; Ursache und Kapazität damit nicht gemessen | Lokale Tests und entfernte Modelle unterscheiden; konkreten Engpass prüfen, keine pauschale Agentenzahl |
| Unbelegte Einsparungen durch Modell-Routing | Routing eingeführt, Gewinn nicht isoliert gemessen | Risiko-/fähigkeitsbasiert wählen und Nacharbeit in die Kosten einbeziehen |
| Kontextoptimierung als garantiert wirksam dargestellt | Lean Delivery und selektiver Kontextabruf eingeführt, kein gesicherter Prozentgewinn | Progressive disclosure und knapper Wiederanlaufzustand; keine Wirkungsbehauptung ohne Messung |
| Review-Korrektur als neues Projekt | zahlreiche Folge-/Release-Pakete; echte und optionale Befunde vermischt | fokussierter Review, Pflicht zur Meldung echter Risiken, optionale Hinweise zurückstellen |
| Funktionsgrenze ohne Lastgrenze | unbeschränkte Regelparameter blockierten den Server; Fix mit Limits und kumuliertem Budget | Eingaben und Gesamtlast prüfen, harte Zeitgrenze nicht aus Vorabcheck ableiten |
| Nur primären Schreibweg absichern | Restore umging Validierung; Altbestand erlaubte Löschsperren-Umweg | alternative Pfade, Zustandsübergänge und Altbestand testen |
| Healthcheck als Sicherheitsnachweis | Hostverlust-Test ergänzte Buchvergleich und tatsächlich abgewiesene widerrufene Codes | relevante Sicherheitseigenschaft direkt beweisen |
| Zusätzliche Infrastruktur als Standard | Vorhandene Sicherung als mögliche Alternative zu zusätzlichem Storage erkannt; Gleichwertigkeit offen | Vorhandenen Dienst prüfen, nicht automatisch neu kaufen |
| Testdatenmigration wie Kundendatenmigration | kontrollierter Neustart als Option nach Betreiberangaben; Verifikation/Freigabe noch nötig | Datenbestand und Risiken verifizieren, nur autorisiert vereinfachen |
| Produktziel beim Beschleunigen verändert | Nutzer wollte die zentrale Automatisierung behalten und den Zielmarkt zunächst begrenzen | Verschiedene Lieferumfänge offen vergleichen und die konkrete Nutzerentscheidung respektieren; kein universelles Vollprodukt- oder MVP-Dogma |
| Externe Freigaben zu spät einplanen | rechtliche Prüfungen, Pentest und Piloten als mögliche kritische Pfade | früh parallel vorbereiten, keine kostenpflichtige Beauftragung ohne Zustimmung |
| Ständig neue Optimierungsstrategien | viele Änderungen ohne belastbare Wirkungsmessung | stabile Arbeitsperiode und vorhandene Daten, keine Optimierung der Optimierung |
| Beratungsfehler der KI als sichere Diagnose weitergegeben | Aus Zahlen wurden teils stärkere Aussagen über Verschwendung, Engpässe und Termine abgeleitet, als die Nachweise erlaubten | Auch eigene frühere Aussagen prüfen, Fehler ausdrücklich korrigieren und geänderte Annahmen nennen; keine Zustimmung aufgrund der Stimmung |

## Was nicht bewiesen ist
Die Berichte beweisen nicht, dass jede Test- oder Dokumentationsarbeit unnötig war. Unabhängige Reviews fanden laut den Berichten reale DoS-, Rechte- und Datenfehler. Der nachhaltige Gewinn von Lean-Arbeitsweise, Modell-Routing, Kontextmanagement und neuer Priorisierung wurde nicht separat gemessen. Marktreife, endgültige Backup-Eignung und langfristige Produktivität waren zum Berichtsstand offen. VANTAGE übernimmt deshalb Entscheidungsregeln, keine projektspezifischen Gates, Agentenzahlen, PT-Faktoren oder Terminversprechen. Auch ein guter Skill muss sich in tatsächlichen Projekten bewähren.
