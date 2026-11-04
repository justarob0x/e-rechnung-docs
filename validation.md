# Prüfung

`Prüfen` in der Seitenleiste testet die gewählte Rechnung gegen die Regeln von EN 16931 und XRechnung, **bevor** etwas
erzeugt wird. `Erstellen` ist gesperrt, solange Fehler offen sind („Bitte zuerst die Fehler beheben.“).

## So werden Meldungen angezeigt

- **Fehler** (rot) verhindern das Erstellen. **Warnungen** (gelb) nicht.
- Jede Meldung steht im Klartext, dahinter der Regelcode (z. B. `BR-DE-15`) und die Zelle (z. B. `Kunden!I3`).
- **Ein Klick auf die Meldung markiert die Zelle** in der Tabelle.
- Darunter: Netto, USt, Brutto und das Format (XRechnung 3.0 oder EN 16931 (ZUGFeRD)); bei aktivem GiroCode eine Vorschau.
- Ohne Befund: „Keine Fehler – bereit zum Erstellen.“

## Was geprüft wird (Auswahl)

**Dokument:** Rechnungsnummer und -datum vorhanden; Fälligkeit nicht vor Rechnungsdatum; Fälligkeitsdatum oder
Zahlungsbedingungen angegeben; Leistungsdatum (Warnung nach § 14 UStG); Gutschrift ohne Bezug (Warnung).

**Leitweg-ID / Käuferreferenz:** Bei XRechnung Pflicht. Hat die Leitweg-ID das Format, aber eine falsche Prüfziffer,
erscheint eine Warnung – fragen Sie beim Auftraggeber nach.

**Verkäufer und Kunde:** Name, Ort, PLZ, Land als Ländercode; Format der USt-IdNr. (z. B. `DE123456789`);
Verkäufer: USt-IdNr. oder Steuernummer. Für XRechnung zusätzlich Verkäufer-Ansprechpartner, -Telefon, -E-Mail sowie
eine E-Mail-Adresse des Kunden (entfällt bei Leitweg-ID).

**Positionen:** Bezeichnung, Menge, Einzelpreis (nicht negativ), Einheit (unübliche Codes ergeben eine Warnung).
Rabatt/Zuschlag: Grund und Betrag größer 0.

**Steuer:** Satz passt zur Kategorie (`S` über 0 %, alle anderen genau 0 %); ungewöhnlicher Satz in Deutschland
(nicht 19/7 %) als Warnung; Pflichtangaben je Fall, siehe [Steuerfälle](tax-cases.md).

**Zahlung:** IBAN vorhanden und gültig (Prüfziffer), BIC-Format, negativer Gesamtbetrag.

## Häufige Meldungen und was zu tun ist

| Meldung (sinngemäß) | Ursache und Abhilfe |
|---|---|
| Leitweg-ID bzw. Käuferreferenz fehlt | Spalte `Leitweg-ID` im Tab `Kunden` ausfüllen; ohne Leitweg-ID dient `Bestellnr.` oder `Kundennr.` als Käuferreferenz, eines von beiden muss gefüllt sein |
| Verkäufer: Ansprechpartner/Telefon/E-Mail fehlt | Tab `Verkäufer` ergänzen (bei XRechnung Pflicht) |
| Verkäufer: USt-IdNr. oder Steuernummer angeben | Tab `Verkäufer`, Zeile `USt-IdNr.` oder `Steuernummer` |
| Kategorie S braucht einen Steuersatz über 0 % | `USt %` ausfüllen oder Kategorie `Z`, `E`, `AE`, `K`, `G` wählen |
| IBAN ... ist ungültig | Tab `Verkäufer`, Zeile `IBAN` korrigieren |
| Reverse Charge: USt-IdNr. des Kunden fehlt | Tab `Kunden`, Spalte `USt-IdNr.` |
| Fälligkeitsdatum oder Zahlungsbedingungen angeben | `Fällig am` oder `Zahlungsziel (Tage)` bzw. `Zahlungsbedingungen` |
| Rechnung ... nicht gefunden | `Rechnungsnr.` in Spalte A der Rechnungszeilen prüfen |

## Wie weit die Prüfung geht

Die Prüfung deckt die Regeln ab, an denen E-Rechnungen in der Praxis scheitern. Sie ersetzt nicht den offiziellen
Validator der Empfängerseite. Entwicklungsseitig werden die erzeugten Dateien gegen den KoSIT-Validator
(XRechnung-Konfiguration) und Mustang/veraPDF getestet.
