# Review, Befunde und Scope-Kontrolle

## Entscheidungsmatrix
| Kategorie | Beispiel | Reaktion |
|---|---|---|
| Kritisch / hoch | Mandantenleck, Auth-Bypass, Datenverlust, systemweiter DoS | Stoppe betroffenen Merge/Release, belege und korrigiere; eskaliere unverzüglich |
| Wesentlich | falsche Berechnung, umgehbare zugesagte Löschsperre, fehlender zwingender Nutzerpfad | Im Ursprungspaket beheben; blockiere betroffene Abnahme |
| Konkreter Verdacht mit potenziell hohem Schaden | geänderter Restore umgeht möglicherweise eine geltende Zugriffssperre | gezielt klären, betroffene Freigabe bis zur Klärung zurückhalten |
| Niedrig | lokaler sauber abgefangener Fehler, unkritischer Randfall | abhängig von verbindlicher Abnahme klein beheben oder transparent zurückstellen |
| Optional | Geschmack, zusätzliche Abstraktion, hypothetisches Skalierungsproblem | kein aktiver Folgeauftrag |

Schwere aus Eintrittsbedingungen, Reichweite, Auswirkung und Evidenz ableiten; nicht aus der Bezeichnung des Reviewers. Ein fehlender Nachweis ist nicht automatisch ein nachgewiesener Fehler; ein glaubhafter schwerer Verdacht erfordert aber keine erfolgreiche Schadensauslösung vor der Reaktion. Nenne genau, ob Verhalten, Nachweis oder Anforderung fehlt. Kein automatisches Herabstufen. Tatsächlichen gefährlichen Befund außerhalb des Diffs melden. Stoppe nur betroffene Vorgänge; unabhängige autorisierte Arbeit kann weiterlaufen. Melden bedeutet nicht automatisch Erlaubnis zu beliebigen Änderungen oder Produktionsmaßnahmen.

Leite aus allgemeinen Schutzzielen keine zusätzlichen Produktverbote ab. Beispiel: Der Import einer vom berechtigten Nutzer bereitgestellten Datei mit fremder Herkunftskennung beweist allein keinen unbefugten Mandantenzugriff. Prüfe die zugesagte Importsemantik, den Datenzugriff und mögliche vorgeschaltete Kontrollen gezielt. Bezeichne eine fehlende Prüfung erst als Fehler, wenn ihre Notwendigkeit belegt ist; sonst als konkrete offene Frage, ohne schon eine bestimmte Architekturkorrektur zu verlangen.

## Review-Grenze
Auftrag: prüfe konkrete Abnahme und real betroffene Abhängigkeiten. Keine allgemeine Suche nach Verbesserungsmöglichkeiten. Kritische gemeinsame Pfade (Import, Restore, alternative APIs, Altbestand, Rollenwechsel, Parallelzugriffe) ausdrücklich prüfen, sofern relevant. Vorhandene Tests auf Aussagekraft prüfen; nicht nur auf Anzahl. Ergänze Tests für konkrete Verhaltensrisiken, nicht für jede reversible Text- oder Formatänderung. Mutationen gezielt zur Prüfung wichtiger Schutzmechanismen, keine Quote. Beende die Prüfung, sobald der vereinbarte Umfang mit ausreichender Evidenz geklärt ist; keine neue Prüfrunde nur um weitere Befunde zu finden.

## Folgepaket-Entscheidung
1. Bestehender Fehler im laufenden Auftrag? Fix im selben Paket/PR, sofern sicher und reviewbar.
2. Fehler außerhalb des Auftrags? Melden und zuständigem bestehenden Paket zuordnen; bei dringender Gefährdung priorisieren.
3. Eigenständiger notwendiger Umfang ohne zuständiges Paket? Nur dann minimal neues Paket mit Abnahme und Grund; wesentliche Erweiterung zur Nutzerentscheidung.
4. Optional? Kurzer Vermerk, keine aktive Arbeit. Kein neues Dokument allein dafür.
5. Ist eine größere Korrektur im Ursprungspaket nicht reviewbar? Separate PRs dürfen dasselbe Paket bedienen; Abschluss erst nach sämtlichen notwendigen Teilen.

## Delta-Review
Binde Freigabe an den tatsächlich geprüften Stand, prüfe Diff und Basis seit letzter fachlicher Freigabe. Bei rein mechanischem Kommentarfix genügt eine risikogerechte Delta-Prüfung plus vorgeschriebene CI, soweit die Projektregeln dies erlauben. Bei geändertem Code prüfe Wechselwirkungen und relevante Tests. Auch Änderungen an Konfiguration, Abhängigkeiten, Build oder Testumgebung können Nachweise entwerten; dann gezielt erweitern. Kein pauschales Wiederverwenden veralteter Freigaben. Warte auf die verbindlich erforderlichen Ergebnisse und erfülle die vereinbarten Abnahmen; unterscheide success, pending, skipped und failure. Behaupte nicht alle Checks seien grün, wenn nur die Pflichtprüfungen erfolgreich sind.

## Prozesskorrektur
Jede neue Verfahrensregel braucht reales Schutzziel, beobachtetes Problem, kleinste Änderung, Kosten und erwarteten Nutzen. Bestehende Freigaberegeln nicht eigenmächtig umgehen. Keine eigene Toolchain für einen einmaligen manuellen Schritt. Prozessverbesserung nach Nutzen überprüfen und bei fehlendem Mehrwert im Rahmen der Freigaben zurücknehmen.
