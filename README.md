# Arbeitszeit Assistent – erster PWA-Prototyp

## Enthaltene Funktionen
- Tageserfassung mit Datum, Start, Ende, Ort und Tätigkeit
- Spracheingabe über Web Speech API, soweit der iPhone-Browser sie unterstützt; Textfeld als Fallback
- Einfache Erkennung typischer Zeitangaben und einiger häufiger Tätigkeiten
- Konfigurierbare automatische Pausenabzüge
- Sollzeit Montag bis Freitag, standardmäßig 8 Stunden
- Monatsübersicht, Monatssaldo und fortlaufendes Stundenkonto
- Druckansicht für „Als PDF sichern“ über iOS-Druckdialog
- Lokale Speicherung im Browser (`localStorage`)
- JSON-Sicherung und Wiederherstellung
- Offline-Cache nach erstem Laden über HTTPS

## Starten
Für einen schnellen Funktionstest `index.html` in einem aktuellen Browser öffnen. Für die installierbare PWA und Service Worker muss die App über HTTPS ausgeliefert werden. Auf dem iPhone: in Safari öffnen → Teilen → „Zum Home-Bildschirm“.

## PDF auf dem iPhone
„PDF erstellen“ öffnet die Druckansicht. Im iOS-Druckdialog die Vorschau öffnen und über Teilen in „Dateien“ sichern (Menü kann je nach iOS-Version leicht variieren).

## Wichtige Grenzen dieses MVP
- Spracheingabe ist browserabhängig. iOS kann die Web Speech API einschränken; iPhone-Tastaturdiktat bleibt als Fallback.
- Der Parser ist absichtlich ein einfacher Prototyp und erkennt nicht zuverlässig alle natürlich gesprochenen Varianten. Alle Werte vor dem Speichern kontrollieren.
- Automatische Pausen sind rechnerische Abzüge und kein Nachweis tatsächlich genommener Pausen. Vor betrieblicher Verwendung mit den geltenden betrieblichen und rechtlichen Anforderungen abgleichen.
- `localStorage` ist an Browser/Web-App-Installation gebunden. Browserdaten löschen kann Einträge löschen. Regelmäßig JSON-Backups und PDF-Berichte exportieren.
- Noch keine Mitarbeiterkonten, Cloud-Synchronisation, Verschlüsselung der lokalen Daten, Urlaubs-/Krankheitstypen, Feiertagskalender oder revisionssichere Änderungsprotokolle.

## Nächste Schritte
1. Auf iPhone Safari testen und den Diktier-/Mikrofonablauf verifizieren.
2. Parser durch strukturierte Extraktion mit Bestätigungsmaske verbessern.
3. Regelwerk um bezahlte/unbezahlte Pausen, Sondertage und individuelle Sollzeiten erweitern.
4. Tests für Mitternachtswechsel, Monatswechsel, negative Salden und Datenexport ergänzen.
5. Vor Mitarbeiterbetrieb Anforderungen an Datenschutz, Aufbewahrung und Nachvollziehbarkeit festlegen.

## Version 0.3 – verbesserte Spracheingabe
- Erkennt häufige deutsche Zeitangaben wie „von sieben bis halb fünf“, „halb vier“, „viertel nach sieben“ und „viertel vor fünf“.
- Sucht zuerst gezielt nach einem „von … bis …“-Zeitraum, damit Pausenlängen nicht so leicht als Arbeitsbeginn oder Feierabend fehlinterpretiert werden.
- Erkennt Datumsangaben wie „gestern“, „vorgestern“ und numerische Datumsformate.
- Übernimmt Ort und Tätigkeit aus ausdrücklich benannten Feldern oder häufigen Tätigkeitsformulierungen.
- Zeigt fehlende Angaben an; erkannte Werte müssen vor dem Speichern kontrolliert werden.
- Aktualisierter Service-Worker-Cache, damit Geräte die neue Version abrufen.

Hinweis: Die Erkennung ist eine lokale, regelbasierte Heuristik und keine KI-Transkription. Die Qualität der eigentlichen Sprache-zu-Text-Erkennung hängt von Safari/iOS ab. Pausen werden weiterhin nach den konfigurierten automatischen Regeln berechnet; gesprochene Pausenzeiten werden nicht als individuelle Pausen gespeichert.
