# Dateien erstellen

`Erstellen` in der Seitenleiste erzeugt die E-Rechnung und legt sie im Drive-Ordner „E-Rechnungen“ ab. Es braucht
eine fehlerfreie Prüfung und eine gültige Testphase oder Lizenz. Die Seitenleiste zeigt die Dateien als Links.

## Ausgabeformate

Tab `Einstellungen`, Zeile `Ausgabe` (Auswahlliste):

| Wert | Ergebnis | Dateiname |
|---|---|---|
| `ZUGFeRD-PDF` | PDF/A-3 mit eingebetteter XML (ZUGFeRD 2.3 / Factur-X) | `Rechnung <Nr>.pdf` |
| `ZUGFeRD-PDF + XRechnung (CII)` | PDF plus reine XRechnung-XML | `Rechnung <Nr>.pdf`, `Rechnung <Nr> XRechnung.xml` |
| `XRechnung (CII)` | nur XML, UN/CEFACT CII | `Rechnung <Nr> XRechnung.xml` |
| `XRechnung (UBL)` | nur XML, UBL 2.1 | `Rechnung <Nr> XRechnung UBL.xml` |

Gutschriften heißen `Gutschrift <Nr> ...`. XRechnung entspricht Version 3.0. Das PDF hat das Profil EN 16931; hat der
Kunde eine Leitweg-ID oder ist die Ausgabe eine XRechnung-Variante, gilt das Profil XRECHNUNG und die zusätzlichen
Pflichtangaben der [Prüfung](validation.md).

Welches Format ist richtig? Öffentliche Auftraggeber verlangen in der Regel XRechnung (mit Leitweg-ID). Unternehmen
nehmen häufig ZUGFeRD, weil es ein lesbares PDF bleibt. Fragen Sie im Zweifel den Rechnungsempfänger.

## Die PDF-Vorlage

Das PDF entsteht aus der Google-Docs-Vorlage „E-Rechnung Vorlage“. Frei änderbar sind Logo, Farben, Schrift und Texte.
Regeln:

- Platzhalter in doppelten geschweiften Klammern stehen lassen, z. B. `{{Firma}}`, `{{Kunde}}`, `{{KundeAdresse}}`,
  `{{Titel}}`, `{{Rechnungsnr}}`, `{{Kopfdaten}}`, `{{Summen}}`, `{{Brutto}}`, `{{Hinweise}}`, `{{Zahlung}}`,
  `{{Fußzeile}}`.
- Die Positionstabelle braucht die Zeile mit `{{Bezeichnung}}` (daneben `{{Pos}}`, `{{Menge}}`, `{{Einheit}}`,
  `{{Einzelpreis}}`, `{{USt}}`, `{{Gesamt}}`); diese Zeile wird pro Position vervielfältigt.
- `{{Hinweise}}` enthält die automatischen Steuerhinweise ([Steuerfälle](tax-cases.md)).
- Unten rechts Platz für den GiroCode lassen (der Seitenrand unten ist dafür vorgesehen).

Für jede Rechnung kopiert das Add-on die Vorlage, füllt die Kopie und löscht sie danach wieder. Die Vorlage selbst
bleibt unverändert.

## GiroCode

`Einstellungen → GiroCode auf PDF` = `Ja` setzt einen EPC-QR-Code (GiroCode) unten rechts auf die letzte Seite, damit
Kunden per Banking-App zahlen. Voraussetzungen: IBAN, Rechnungsbetrag über 0 €, keine Gutschrift, Währung Euro.
Die Seitenleiste zeigt den Code schon nach `Prüfen` als Vorschau.

## Versenden und herunterladen

Die Dateien liegen in Ihrem Google Drive (Ordner „E-Rechnungen“, Link in der Seitenleiste). Laden Sie sie dort herunter
oder teilen Sie sie von dort. Die im Marketplace angebotene Version versendet nichts selbst: Ein E-Mail-Versand aus
dem Add-on ist darin nicht enthalten, senden Sie die Dateien also aus Ihrem Mailprogramm.

Hinweis zu öffentlichen Auftraggebern: Viele Behörden nehmen Rechnungen nur über Portale (z. B. ZRE/OZG-RE) oder per
E-Mail an. Klären Sie den Einreichungsweg mit dem Auftraggeber; XRechnung-XML und Leitweg-ID liefert das Add-on.

## Status

Nach dem Erstellen steht in der Spalte `Status` „erstellt TT.MM.JJJJ HH:MM“ in allen Zeilen der Rechnung. Erstellen Sie
dieselbe Rechnung erneut, entstehen neue Dateien mit dem gleichen Namen in Drive.
