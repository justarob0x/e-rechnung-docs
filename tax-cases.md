# Steuerfälle

Den Steuerfall legen Sie **pro Zeile** in den Spalten `Steuer` (Auswahlliste) und `USt %` fest. Das Add-on macht
daraus die Steuerkategorie der E-Rechnung und ergänzt den vorgeschriebenen Hinweistext automatisch.

| Fall | `Steuer` | `USt %` | Automatischer Hinweistext |
|---|---|---|---|
| Normalsatz 19 % oder 7 % (auch gemischt in einer Rechnung) | `S – Normalsatz` | 19 bzw. 7 | – |
| Nullsatz (z. B. Photovoltaik) | `Z – Nullsatz` | 0 | – |
| Kleinunternehmer, § 19 UStG | `E – steuerfrei / Kleinunternehmer § 19 UStG` | 0 | „Kein Ausweis von Umsatzsteuer, da Kleinunternehmer gemäß § 19 UStG“ |
| Reverse Charge, § 13b UStG | `AE – Reverse Charge § 13b UStG` | 0 | „Steuerschuldnerschaft des Leistungsempfängers (§ 13b UStG)“ |
| Innergemeinschaftliche Lieferung | `K – innergemeinschaftliche Lieferung` | 0 | „Steuerfreie innergemeinschaftliche Lieferung (§ 4 Nr. 1b UStG)“ |
| Ausfuhr in ein Drittland | `G – Ausfuhr Drittland` | 0 | „Steuerfreie Ausfuhrlieferung (§ 4 Nr. 1a UStG)“ |
| Nicht steuerbar | `O – nicht steuerbar` | 0 | „Nicht steuerbarer Umsatz“ |

Bei allen Kategorien außer `S` darf `USt %` leer bleiben (gilt als 0). Die Kategorie `S` mit 0 % lehnt die Prüfung ab.

## Was Sie zusätzlich angeben müssen

- **Kleinunternehmer (E):** Eine Steuernummer im Tab `Verkäufer` genügt, eine USt-IdNr. ist nicht nötig.
- **Reverse Charge (AE):** USt-IdNr. oder Steuernummer des Verkäufers **und** USt-IdNr. des Rechnungsempfängers
  (Tab `Kunden`).
- **Innergemeinschaftliche Lieferung (K):** USt-IdNr. von Verkäufer und Kunde sowie das Land des Kunden. Das Add-on
  setzt die Kundenanschrift als Lieferanschrift.
- **Ausfuhr (G):** USt-IdNr. des Verkäufers.
- **Nicht steuerbar (O):** keine USt-IdNr. angeben und nicht mit anderen Kategorien in einer Rechnung mischen.

Mischen Sie `E` und `S` in einer Rechnung, erscheint eine Warnung.

## Rabatte und Zuschläge

Eine Zeile mit `Zeilenart` = `Rabatt` bzw. `Zuschlag` wirkt auf **Belegebene**. Tragen Sie in `Einzelpreis netto`
den positiven Betrag ein, in `Bezeichnung` den Grund (z. B. „Treuerabatt“) und in `Steuer`/`USt %` den Satz, auf den
sich der Rabatt bezieht. `Menge` und `Einheit` bleiben leer.

## Gutschriften

`Art` = `Gutschrift`, positive Beträge, `Bezug auf Rechnung` = Nummer der ursprünglichen Rechnung. Fehlt der Bezug,
erscheint eine Warnung. Ein negativer Rechnungsbetrag wird als Fehler gemeldet – dafür ist die Gutschrift gedacht.

Keine Steuerberatung: Welcher Steuerfall zutrifft, entscheiden Sie bzw. Ihr Steuerberater. Das Add-on prüft die
formale Stimmigkeit der Angaben.
