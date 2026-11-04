# Erste Schritte

Der Weg von der leeren Tabelle zur ersten fertigen E-Rechnung dauert wenige Minuten. Die Beispieldaten sind so
angelegt, dass sie ohne Änderung prüfbar und erstellbar sind.

## 1. Add-on installieren

Installieren Sie „E-Rechnung für Sheets – XRechnung & ZUGFeRD“ aus dem Google Workspace Marketplace und öffnen Sie
eine Google-Tabelle. Beim ersten Start fragt Google nach Berechtigungen; welche das sind und warum, steht unter
[Preise, Lizenz, Datenschutz](pricing-and-privacy.md).

## 2. Einrichten

*Erweiterungen → E-Rechnung für Sheets → Einrichten (Tabs & Vorlage)*. Das Add-on legt an:

- die Tabs `Rechnungen`, `Kunden`, `Verkäufer`, `Einstellungen` mit Beispieldaten,
- den Drive-Ordner „E-Rechnungen“,
- die bearbeitbare Google-Docs-Vorlage „E-Rechnung Vorlage“.

Vorhandene Tabs mit diesen Namen bleiben unverändert; fehlende werden ergänzt (das Add-on fragt vorher nach). Danach
öffnet sich die Seitenleiste. Die Beispielrechnungen heißen `RE-<Jahr>-001` (Beratung und Fachbuch mit 19 % und 7 %,
Rabatt), `-002` (Behörde mit Leitweg-ID) und `-003` (innergemeinschaftliche Lieferung nach Österreich).

## 3. Beispielrechnung prüfen und erstellen

In der Seitenleiste (Reiter `Ausgang`) eine Rechnung anklicken, dann `Prüfen`. Sie sehen „Keine Fehler – bereit zum
Erstellen.“ sowie Netto, USt und Brutto. Dann `Erstellen` (dauert etwa 10–20 Sekunden). Die Dateien erscheinen als
Links; in der Spalte `Status` steht „erstellt TT.MM.JJJJ HH:MM“.

## 4. Eigene Daten eintragen

1. Tab `Verkäufer`: Ihre Firma ersetzen (Name, Anschrift, USt-IdNr. oder Steuernummer, IBAN, Ansprechpartner,
   Telefon, E-Mail).
2. Tab `Kunden`: Ihre Rechnungsempfänger eintragen, jeweils mit eindeutiger `Kundennr.`.
3. Tab `Rechnungen`: Beispielzeilen durch eigene ersetzen.
4. Tab `Einstellungen`: `Ausgabe` und `GiroCode auf PDF` wählen. Für DATEV zusätzlich Kontenrahmen, Berater- und
   Mandantennummer.

Die Details stehen in [Tabelle ausfüllen](invoice-sheet.md).

## 5. Layout anpassen (optional)

Die Docs-Vorlage öffnen (Link nach dem Einrichten, außerdem im Drive-Ordner) und Logo, Farben und Texte ändern.
Siehe [Dateien erstellen](creating-files.md#die-pdf-vorlage).

## Hilfe in der App

*Erweiterungen → E-Rechnung für Sheets → Hilfe* zeigt einen Link zur Hilfeseite. Die Seitenleiste folgt der Sprache
Ihres Google-Kontos (Deutsch oder Englisch); die Tab- und Spaltennamen in der Tabelle sind immer deutsch.
