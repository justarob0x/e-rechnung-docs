# E-Rechnung für Sheets – XRechnung & ZUGFeRD

E-Rechnung is an add-on for Google Sheets (and a sister add-in for Excel) that turns invoice rows in a spreadsheet
into German e-invoices: ZUGFeRD PDF or XRechnung XML (CII or UBL). It checks each invoice against EN 16931 and the
XRechnung rules and points at the cell that needs fixing. It also reads incoming e-invoices back into the sheet and
creates a DATEV booking batch. A free browser viewer for XRechnung files is included.

## Das Problem

Seit dem 1. Januar 2025 müssen Unternehmen in Deutschland E-Rechnungen im B2B-Bereich empfangen können. Ausstellen
müssen sie ab 2027 (Vorjahresumsatz über 800.000 €) bzw. ab 2028 (alle Unternehmen). Eine E-Rechnung ist kein
einfaches PDF, sondern strukturierte Daten nach EN 16931: ZUGFeRD (PDF mit eingebetteter XML) oder XRechnung (reine
XML, Pflicht für öffentliche Auftraggeber). Wer seine Rechnungen ohnehin in einer Tabelle führt, braucht dafür weder
eine Buchhaltungssoftware noch ein Webportal.

E-Rechnung für Sheets erfasst die Rechnung als Tabellenzeilen, prüft sie, bevor etwas erzeugt wird, und legt die
fertigen Dateien in Ihrem Google Drive ab. Ihre Rechnungsdaten bleiben in Ihrem Google-Konto.

## Das Leben einer Rechnung

1. **Einrichten.** In einer Google-Tabelle *Erweiterungen → E-Rechnung für Sheets → Einrichten (Tabs & Vorlage)*.
   Das Add-on legt die Tabs `Rechnungen`, `Kunden`, `Verkäufer` und `Einstellungen` mit Beispieldaten an, dazu den
   Drive-Ordner „E-Rechnungen“ und eine Google-Docs-Vorlage.
2. **Stammdaten eintragen.** Ihre Firma im Tab `Verkäufer`, Ihre Kunden im Tab `Kunden` (bei Behörden mit
   Leitweg-ID). Siehe [Tabelle ausfüllen](invoice-sheet.md).
3. **Rechnung schreiben.** Im Tab `Rechnungen` eine Zeile pro Position; alle Zeilen mit derselben Rechnungsnummer
   gehören zu einer Rechnung. Den Steuerfall pro Zeile in der Spalte `Steuer` wählen ([Steuerfälle](tax-cases.md)).
4. **Prüfen.** In der Seitenleiste die Rechnung wählen und `Prüfen`. Fehler und Warnungen erscheinen im Klartext;
   ein Klick springt in die Zelle ([Prüfung](validation.md)).
5. **Erstellen.** `Erstellen` erzeugt je nach `Einstellungen → Ausgabe` ZUGFeRD-PDF und/oder XRechnung-XML im
   Ordner „E-Rechnungen“ ([Dateien erstellen](creating-files.md)). In der Spalte `Status` steht „erstellt …“.
6. **Senden.** Datei(en) aus Drive an den Rechnungsempfänger schicken oder auf dem vorgesehenen Weg einreichen.
7. **Eingehende Rechnungen.** Im Reiter `Eingang` eine XML- oder ZUGFeRD-PDF-Datei wählen, lesen und in
   `Eingangsrechnungen` übernehmen ([Eingangsrechnungen](incoming.md)).
8. **Monatsende.** Im Reiter `DATEV` den Buchungsstapel für den Steuerberater erzeugen ([DATEV](datev.md)).

## Wo was liegt

- **Seitenleiste „E-Rechnung“** (*Erweiterungen → E-Rechnung für Sheets → Seitenleiste öffnen*): Reiter
  `Ausgang`, `Eingang`, `DATEV`.
- **Tabs in Ihrer Tabelle:** `Rechnungen`, `Kunden`, `Verkäufer`, `Einstellungen`, später `Eingangsrechnungen`.
- **Drive-Ordner „E-Rechnungen“:** erzeugte PDF-, XML- und CSV-Dateien.
- **Google-Docs-Vorlage „E-Rechnung Vorlage“:** das Layout Ihrer PDF-Rechnung.
- **Kostenloser Viewer im Browser:** <https://erechnung.justarobot.online/xrechnung-oeffnen> ([Viewer](viewer.md)).
- **Website, Preise, Hilfe:** <https://erechnung.justarobot.online> · Support: support+erechnung@justarobot.online

## Themen

[Erste Schritte](getting-started.md) · [Tabelle ausfüllen](invoice-sheet.md) · [Steuerfälle](tax-cases.md) ·
[Prüfung](validation.md) · [Dateien erstellen](creating-files.md) · [Eingangsrechnungen](incoming.md) ·
[DATEV](datev.md) · [Viewer](viewer.md) · [Excel](excel.md) · [Preise, Lizenz, Datenschutz](pricing-and-privacy.md) ·
[FAQ](faq.md)

## About this documentation

Diese Dokumentation ist öffentlich. Sie ist für Menschen geschrieben oder zum Einfügen in einen KI-Assistenten, damit
Sie Fragen wie „Warum meldet die Prüfung eine fehlende Leitweg-ID?“ mit Antworten klären können, die zum tatsächlichen
Verhalten der App passen. Sie beschreibt nur das Verhalten der App – keine Kundendaten, keinen Quellcode. Sie ist
keine Steuer- oder Rechtsberatung.
