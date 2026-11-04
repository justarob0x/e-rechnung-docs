# DATEV-Buchungsstapel

Der Reiter `DATEV` erzeugt aus den Ausgangs- und Eingangsrechnungen eines Monats einen Buchungsstapel im
DATEV-Format (EXTF), den Ihr Steuerberater importieren kann. Das funktioniert **auch ohne Lizenz**.

## Einmal einrichten

Tab `Einstellungen`:

| Zeile | Bedeutung | Standard, wenn leer |
|---|---|---|
| `Kontenrahmen` | `SKR03` oder `SKR04` | SKR03 |
| `DATEV Beraternummer` | Nummer Ihres Steuerberaters | 1001 |
| `DATEV Mandantennummer` | Ihre Mandantennummer | 1 |
| `Debitorenkonto` | Konto für Ausgangsrechnungen | 10000 (Sammeldebitor) |
| `Kreditorenkonto` | Konto für Eingangsrechnungen | 70000 (Sammelkreditor) |

Die Standardwerte für Berater- und Mandantennummer sind Platzhalter. Erfragen Sie die echten Nummern bei Ihrem
Steuerberater, bevor Sie den Stapel weitergeben.

## Erzeugen

1. Seitenleiste → Reiter `DATEV`.
2. `Monat` wählen (vorbelegt ist der Vormonat).
3. `Buchungsstapel erstellen`.

Ergebnis: eine CSV-Datei `EXTF_Buchungsstapel_<von>_<bis>.csv` im Drive-Ordner „E-Rechnungen“ (Windows-1252, Format
EXTF 700). Die Seitenleiste zeigt den Link sowie die Zahl der Ausgangs- und Eingangsrechnungen. Fehlt jede Rechnung im
Monat, meldet das Add-on „Keine Rechnungen im <Monat>“.

## Was gebucht wird

- **Ausgangsrechnungen** mit `Datum` im Monat: eine Buchung pro Steuersatz, Brutto auf `Debitorenkonto` im Soll, Gegenkonto
  ein Erlöskonto je Steuerfall (SKR03: 19 % 8400, 7 % 8300, § 19 8195, Reverse Charge 8337, innergemeinschaftlich 8125,
  Ausfuhr 8120, Nullsatz 8200; SKR04: 4400, 4300, 4185, 4337, 4125, 4120, 4200). Gutschriften stehen im Haben. Die
  Umsatzsteuer rechnet DATEV über die Automatikkonten.
- **Eingangsrechnungen** aus dem Tab `Eingangsrechnungen` mit `Datum` im Monat: Brutto auf das Aufwandskonto in der
  Spalte `Konto`; ist sie leer, nimmt das Add-on ein Wareneingangskonto nach Steuersatz (SKR03: 3400 / 3300 / 3200;
  SKR04: 5400 / 5300 / 5200), Gegenkonto `Kreditorenkonto`.
- Ausgangsrechnungen, die die [Prüfung](validation.md) nicht bestehen, werden **übersprungen** und in der
  Seitenleiste unter „Übersprungen (Fehler)“ aufgeführt.

Der Stapel ist nicht festgeschrieben (Festschreibung aus), Ihr Steuerberater kann ihn vor dem Buchen prüfen und die
Konten in DATEV umlegen. Bestätigen Sie die Kontenzuordnung mit ihm.

## Grenzen

Der Export enthält keine Belege (PDFs) und keine Kostenstellen. Den vollständigen DATEV-Ablauf mit Belegen für
Shopify, WooCommerce und Wix gibt es unter <https://buchungsstapel.de>.
