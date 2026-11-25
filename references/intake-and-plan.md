# Repository-Einstieg und Plan

## Minimaler Einstieg
1. Repository und exakten Commit feststellen; lokale Änderungen und Regeln prüfen. Remote-/Produktionszustand nur bei autorisiertem Zugriff feststellen. Keine Secrets lesen/ausgeben, wenn nicht zwingend erforderlich.
2. Vorhandene Dokumentation gegen ausgewählte Entrypoints, Nutzungsabläufe und Tests abgleichen. Behauptungen als belegt, berichtet, geschätzt oder unbekannt markieren. Code und Laufzeit belegen den Ist-Zustand; die gültige Anforderung bestimmt den Soll-Zustand. Bei Widerspruch Ursache klären, nicht den Fehler zur neuen Anforderung erklären. Rechtliche Fragen nicht aus Code ableiten.
3. Produktversprechen und Hauptnutzerpfade erfassen. Bei einem unbekannten Produkt eine kompakte Frage zu Zielgruppe und wesentlichem Nutzen; bereits bekannte Informationen nicht erneut erfragen.
4. Architektur, Abhängigkeiten, Datenmodell und Betrieb nur soweit für die nächste Entscheidung nötig. Bei ernstem Verdacht gezielt vertiefen. Abhängigkeiten/Lizenzen und Drittanbieter-Kosten bei tatsächlicher Relevanz prüfen.
5. Vorhandene Arbeitsliste, laufende PRs, offene Fehler und Freigaben abgleichen. Nur notwendige fehlende Arbeit ergänzen. Keine vollständige neue Liste erzeugen, wenn eine brauchbare existiert.

## Einmalige kompakte Entscheidungsvorlage
Nur die für den Auftrag nötigen Punkte verwenden. Die Erstaufnahme ist kein vollständiges Audit; nenne die geprüften Bereiche und verbleibende wesentliche Unsicherheiten. Für eine kleine Änderung genügt die konkrete Handlung mit Nachweis.

- Ziel und Nicht-Ziele; wesentliche Annahmen und offene Betreiberfragen.
- Ist-Matrix: Funktion | Code vorhanden | integriert | getestet | live | abgenommen | Evidenz.
- Höchstens wenige wesentliche Blocker mit konkretem Risiko, kleinster Abhilfe, zuständigem bestehendem Paket.
- Nächste kohärente Lieferabschnitte mit Akzeptanzkriterien, Abhängigkeiten, Parallelisierbarkeit und realem Release-Ziel. Nur die nächsten ausführbaren Schritte detaillieren, weiter entfernte Bereiche grob halten.
- Kosten/Zeithorizont: belegte Kapazität, Aufwandsspanne, externe Voraussetzungen, unsichere Annahmen. Falls nicht belegbar: keine präzise ETA.
- Empfohlene Entscheidung und echte Alternativen, insbesondere wenn Nutzerwunsch technisch oder wirtschaftlich nicht trägt.

## Reifegrade
Prototyp = Hypothese prüfbar. Entwicklungsstand = Code vorhanden. Integration = zusammengeführt. Technische Bereitstellung = konkreter Build erreichbar. Interne Erprobung = freigegebene Testdaten. Repräsentativer Pilot = wesentliche beworbene Nutzerabläufe und Zielgruppe tatsächlich abgedeckt. Kommerziell = erforderliche fachliche, technische, rechtliche und betriebliche Voraussetzungen erfüllt. Kein automatischer Übergang.

## Neue Projekte
Vor großem Bau: Problem und Nutzenhypothese, Zielgruppe, Konkurrenzannahmen, Zahlungsbereitschaft soweit bekannt. Erst einen vollständigen Nutzerablauf liefern. Architektur einfach und reversibel halten; keine hypothetische Skalierung oder Multi-Agent-Infrastruktur als Voraussetzung. Sicherheitsbasis von Anfang an nach Risikoprofil. Kundenfeedback früh einholen, ohne unfertiges Produkt als fertig zu verkaufen.

## Bestehende Projekte
Kein pauschaler Reset. Feature-Inventar aus vorhandenen Belegen; unklare Teile gezielt prüfen. Prüfe, ob bisherige Release-Kandidaten zu viele Änderungen koppeln. Neue Schnitte nur mit belegten Abhängigkeiten, nicht blind cherry-picken. Extern blockierte Features isolieren, falls tatsächlich möglich; keine gemeinsamen Sicherheitsmechanismen ausklammern. Ändere bestätigte Ziele nur bei neuer Entscheidung. Führe keine Reifegradprüfung erneut aus, wenn ein konkreter Folgeauftrag mit ausreichendem Kontext vorliegt.
