# Tabelle ausfüllen

Das Add-on findet Spalten über ihre **Überschrift**. Sie dürfen Spalten umsortieren oder eigene hinzufügen, solange
die Überschriften unverändert bleiben. Tabs und Überschriften nicht umbenennen.

## Tab `Rechnungen` – eine Zeile pro Position

Alle Zeilen mit derselben `Rechnungsnr.` bilden eine Rechnung. Kopfdaten (Datum, Art, Kundennr. usw.) werden aus der
**ersten** Zeile der Rechnung gelesen.

| Spalte | Bedeutung |
|---|---|
| `Rechnungsnr.` | Rechnungsnummer, gruppiert die Zeilen |
| `Datum` | Rechnungsdatum (TT.MM.JJJJ) |
| `Art` | `Rechnung` oder `Gutschrift` |
| `Kundennr.` | Verweis auf den Tab `Kunden` |
| `Leistungsdatum` | Liefer-/Leistungsdatum; leer = Rechnungsdatum |
| `Fällig am` | Fälligkeit; leer = Datum + Zahlungsziel aus `Verkäufer` |
| `Bestellnr.` | Bestellreferenz des Kunden |
| `Bezug auf Rechnung` | bei Gutschriften die ursprüngliche Rechnungsnummer |
| `Zeilenart` | `Position`, `Rabatt` oder `Zuschlag` |
| `Bezeichnung`, `Beschreibung` | Text der Position (bei Rabatt/Zuschlag: der Grund) |
| `Menge`, `Einheit` | Menge und Einheit (Auswahlliste, z. B. `C62 – Stück`, `HUR – Stunde`) |
| `Einzelpreis netto` | Preis pro Einheit netto; bei Rabatt/Zuschlag der positive Betrag |
| `Steuer` | Steuerkategorie ([Steuerfälle](tax-cases.md)) |
| `USt %` | Steuersatz, z. B. 19 oder 7 |
| `Netto` | Zeilensumme (Formel aus den Beispieldaten) |
| `Status` | wird vom Add-on beschrieben („erstellt …“) |

Zahlen und Daten dürfen deutsch geschrieben sein (`1.234,56`, `31.12.2026`). Einheiten kennt das Add-on als Code
(`C62`) oder als Wort (`Stück`, `Std.`, `kg`, `Pauschale`). Eine **Gutschrift** schreiben Sie mit positiven Beträgen,
`Art` = `Gutschrift` und der ursprünglichen Rechnungsnummer unter `Bezug auf Rechnung`.

## Tab `Kunden` – eine Zeile pro Rechnungsempfänger

`Kundennr.`, `Name`, `Straße`, `PLZ`, `Ort`, `Land` (Ländercode wie DE, AT; leer = DE), `USt-IdNr.`, `E-Mail`,
`Leitweg-ID`, `Ansprechpartner`. Die `Leitweg-ID` tragen Sie nur bei öffentlichen Auftraggebern ein; sie schaltet die
Rechnung auf das Profil XRECHNUNG (das gilt auch ohne Leitweg-ID, wenn `Einstellungen → Ausgabe` eine
XRechnung-Variante ist) und wird als Käuferreferenz übernommen. Ohne Leitweg-ID dient `Bestellnr.`, sonst
die `Kundennr.` als Käuferreferenz.

## Tab `Verkäufer` – Spalte A Bezeichnung, Spalte B Wert

`Firmenname`, `Straße`, `PLZ`, `Ort`, `Land`, `USt-IdNr.`, `Steuernummer`, `Handelsregister`, `Rechtliche Angaben`,
`Ansprechpartner`, `Telefon`, `E-Mail`, `IBAN`, `BIC`, `Kontoinhaber`, `Zahlungsziel (Tage)`, `Zahlungsbedingungen`.
USt-IdNr. oder Steuernummer ist Pflicht. Für XRechnung sind außerdem Ansprechpartner, Telefon und E-Mail Pflicht.

## Tab `Einstellungen` – Spalte A Bezeichnung, Spalte B Wert

| Zeile | Wirkung |
|---|---|
| `Ausgabe` | Auswahl der Dateiformate ([Dateien erstellen](creating-files.md)) |
| `GiroCode auf PDF` | `Ja` oder `Nein` |
| `Ablageordner (Drive-ID)`, `Vorlage (Docs-ID)` | vom Add-on gefüllt; nur ändern, wenn Sie Ordner oder Vorlage wechseln |
| `Lizenzschlüssel` | Ihr Schlüssel nach dem Kauf ([Preise](pricing-and-privacy.md)) |
| `Kontenrahmen`, `DATEV Beraternummer`, `DATEV Mandantennummer`, `Debitorenkonto`, `Kreditorenkonto` | für [DATEV](datev.md) |

## Tab `Eingangsrechnungen`

Entsteht beim ersten Übernehmen einer eingehenden Rechnung ([Eingangsrechnungen](incoming.md)).

Alle Rechnungen werden in Euro ausgestellt; eine Währungsspalte gibt es nicht.
