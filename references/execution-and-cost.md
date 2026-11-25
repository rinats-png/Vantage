# Ausführung, Ressourcen und Kosten

## Routing
| Aufgabe | Standard | Eskalation |
|---|---|---|
| Status, mechanische Dokumentation, Format | kleines Modell | semantische Unsicherheit |
| normale Produktfunktion, Regression | mittleres Modell | komplexe Abhängigkeiten / wiederholtes Scheitern |
| kritische Rechte, Daten, Sicherheit, komplexe Algorithmen | starkes Modell für Analyse/Review; Implementierung nach Komplexität | unabhängige Fachprüfung wenn nötig |
| Delta nach Freigabe | risikogerecht, mechanisch nur wenn wirklich mechanisch | relevante Code-/Basisänderung |

Modellnamen und Fähigkeiten der tatsächlichen Umgebung prüfen. Kein Modellwechsel, wenn nicht unterstützt; dann die Arbeitsaufteilung anpassen und die Einschränkung benennen. Kein Versprechen geringerer Kosten ohne Messung. Unabhängigen Review mit Auftrag, Kriterien, Diff und relevanten Nachweisen versorgen; keine gewünschte Freigabe vorgeben. Ein frischer Agent ist keine Garantie für unabhängige Fehlererkennung, besonders bei gleichem Modell und gleichen Annahmen.

## Kapazität
Unterscheide lokale Builds/Tests von entfernt laufenden Modellen: Sie belasten unterschiedliche Ressourcen. Nutze vorhandene Kapazitätsgrenzen und getrennt bearbeitbare Aufgaben. Erhöhe Parallelität nur soweit Konflikte, Ressourcen und Review-Kapazität dies zulassen; bei Unsicherheit klein beginnen, ohne erst eine Messplattform zu bauen. Eine lange Laufzeit allein beweist keinen CPU-Engpass. Prüfe bei Verzögerung die konkrete Ursache, etwa Warteschlange, IO, Timeouts oder echte Rechenlast. Gezielte lokale Prüfungen und bestehende CI sinnvoll aufteilen; verbindliche Prüfungen bleiben. Keine fremden Worktrees löschen oder Prozesse blind beenden. Zuständigkeit erst nach belegtem Abschluss oder Übergabe übernehmen. Unabhängige Arbeit während CI-Wartezeiten nur innerhalb des Auftrags vorziehen.

## Kontextökonomie
Progressive disclosure: Auftrag, betroffene Dateien, relevante Entscheidungen und vorhandene Tests. Suche gezielt, erweitere bei Evidenzlücken. Bei Compact einen kurzen Wiederanlaufzustand verwenden: Branch/Commit, Ziel, Abnahme, Änderungen, offene Befunde, ausgeführte Tests, nächste Aktion, Zuständigkeit. Geheimnisse nie in Gedächtnis oder Logs. Keine erneute Vollanalyse nach jeder Sitzung.

## Kostenkontrolle
Nutze vorhandene Telemetrie für API-Kosten, Tokens, CI-Minuten, Wiederholungen, Laufzeit und Drittanbieter, soweit verfügbar und entscheidungsrelevant. Keine fiktiven Preise oder Ersparnisse. Bereits freigegebene Nutzung fortsetzen; unbekannte neue Zahlungsverpflichtungen vor Abschluss klären. Bei wiederholten Fehlläufen Ursache statt blindem Retry; bei transientem Fehler begrenzt erneut versuchen und Blockade melden. Keine zusätzliche Infrastruktur für theoretische Beschleunigung. Vergleiche Gesamtaufwand einschließlich Kontext, Review und Nacharbeit; billiger pro Aufruf bedeutet nicht billiger pro fertigem Ergebnis.

## Automatisierung
Bestehende Runner, Wakeups und Agentenfortsetzungen nur nutzen, wenn verfügbar, erlaubt und tatsächlich funktionsfähig. Keine unendlichen Schleifen, kein unkontrollierter Verbrauch. Stop bei Budgetgrenze, fehlender Berechtigung, Konflikt oder erfüllt abgeschlossenem Auftrag. Keine neuen Automationen allein weil der Skill sie erwähnt.
