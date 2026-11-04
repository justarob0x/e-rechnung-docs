# Eingangsrechnungen

Seit dem 1. Januar 2025 müssen Unternehmen E-Rechnungen empfangen können. Der Reiter `Eingang` der Seitenleiste liest
eine empfangene E-Rechnung lesbar aus und übernimmt sie in Ihre Tabelle. Das funktioniert **auch ohne Lizenz**.

## Ablauf

1. Seitenleiste → Reiter `Eingang`.
2. Eine XRechnung- oder ZUGFeRD-Datei wählen (`.xml` oder `.pdf`). Sie wird in Ihrem Google-Konto verarbeitet.
3. Die Rechnung erscheint lesbar: Lieferant, Rechnungsnr., Datum, Fälligkeit, Zahlung (IBAN, Verwendungszweck),
   Positionen, Steuer und Summen. Eine Gutschrift ist als solche gekennzeichnet.
4. `In Tabelle „Eingangsrechnungen“ übernehmen` schreibt die Rechnung in den Tab `Eingangsrechnungen`.

## Welche Dateien funktionieren

- XRechnung als UBL (Invoice, CreditNote) oder UN/CEFACT CII,
- ZUGFeRD / Factur-X als PDF mit eingebetteter XML (die XML wird aus dem PDF gelesen),
- XML-Dateien anderer Formate und PDFs ohne eingebettete E-Rechnung werden abgelehnt, mit einer Meldung wie „Das
  PDF enthält keine E-Rechnung“.

Ein bloßes PDF ohne eingebettete XML ist keine E-Rechnung; es wird nicht per Texterkennung gelesen.

## Der Tab `Eingangsrechnungen`

Spalten: `Datum`, `Rechnungsnr.`, `Lieferant`, `USt-IdNr. Lieferant`, `USt %`, `Netto`, `USt`, `Brutto`, `Fällig am`,
`IBAN`, `Verwendungszweck`, `Konto`, `Format`, `Importiert am`.

- **Eine Zeile pro Steuersatz:** Hat die Rechnung 19 % und 7 %, entstehen zwei Zeilen (DATEV braucht die Aufteilung).
- **Gutschriften** stehen mit negativen Beträgen.
- **Doppelt importieren geht nicht:** Dieselbe Rechnungsnummer desselben Lieferanten wird abgelehnt („... ist bereits
  importiert“).
- Die Spalte `Konto` bleibt leer. Tragen Sie dort ein Aufwandskonto ein, wenn Sie nicht das Standardkonto aus dem
  [DATEV-Export](datev.md) wollen.

## Nur ansehen, ohne Tabelle

Wollen Sie eine Rechnung nur lesen? Der [kostenlose Viewer](viewer.md) im Browser braucht weder Add-on noch Anmeldung.

Hinweis: Das Auslesen prüft die Rechnung nicht auf Gültigkeit nach EN 16931; es zeigt, was in der Datei steht.
