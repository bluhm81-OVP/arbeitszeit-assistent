# Arbeitszeit-Assistent – Version 0.5

## Neu in v0.5
- iPhone-Tastatur-Diktat ist jetzt der empfohlene Standard: Textfeld antippen, Mikrofon auf der iOS-Tastatur drücken, Bericht sprechen und „Angaben aus Text übernehmen“ antippen.
- Die browserinterne Mikrofonfunktion bleibt optional; bei fehlender Unterstützung oder Berechtigungsfehlern zeigt die App einen klaren Hinweis auf das Tastatur-Diktat.
- Kalender, Tagesbearbeitung und Löschen, automatische Pausenregeln, Monats-/Gesamtstundenkonto, PDF-Druck sowie lokale Datensicherung bleiben enthalten.
- Service-Worker-Cache wurde für das Update auf v0.5 umbenannt.

## Wichtig
Alle Arbeitszeitdaten werden lokal im Browser auf diesem Gerät gespeichert. Sie werden nicht in dieses GitHub-Repository geschrieben. Regelmäßig JSON-Sicherung und Monats-PDF exportieren. Das automatische Pausenmodell ist eine Rechenhilfe; tatsächliche Pausen bitte korrekt erfassen und betriebliche Vorgaben prüfen.

## Installation / Update über GitHub Pages
Die Dateien `index.html`, `app.js`, `styles.css`, `manifest.json`, `sw.js` und `README.md` in das Repository hochladen und vorhandene Dateien ersetzen. Danach die Web-App schließen und erneut öffnen. Falls eine alte Version angezeigt wird, die Seite in Safari neu laden und die installierte Web-App erneut starten.


Version 0.6: Orts-Erkennung ergänzt, damit ein Ortsname direkt nach den Uhrzeiten erkannt werden kann, z. B. „Sieben bis 16:00 Uhr Stolpe, Rasen gemäht“. Bitte erkannte Felder vor dem Speichern kontrollieren.
