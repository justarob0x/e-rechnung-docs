# Kostenloser XRechnung-Viewer

Unter <https://erechnung.justarobot.online/xrechnung-oeffnen> können Sie eine E-Rechnung kostenlos im Browser lesen.
Sie brauchen weder das Add-on noch ein Konto.

## Benutzung

1. Die Seite öffnen.
2. Die `.xml`-Datei (XRechnung) oder das ZUGFeRD-/Factur-X-PDF in das Feld ziehen oder `Datei auswählen` anklicken.
3. Die Rechnung erscheint lesbar; auf Wunsch lässt sich auch die rohe XML anzeigen.

## Was der Viewer kann

- Liest XRechnung 3.x (UBL und CII), ZUGFeRD 2.x und Factur-X. Bei PDFs wird die eingebettete XML ausgelesen.
- Zeigt Verkäufer, Käufer, Positionen, Umsatzsteuer, Summen und Zahlungsdaten.
- Läuft vollständig in Ihrem Browser. Die Datei wird nicht hochgeladen und nicht gespeichert.
- Die Seite gibt es auch auf Englisch (`?lang=en`).

## Was der Viewer nicht kann

- Er **prüft nicht**, ob die Rechnung nach EN 16931 gültig ist. Dafür gibt es die [Prüfung](validation.md) im Add-on
  oder den KoSIT-Validator.
- Er legt nichts in einer Tabelle ab. Für Eingangsrechnungsliste und DATEV-Export nutzen Sie
  [Eingangsrechnungen](incoming.md) im Add-on.
- Ein PDF ohne eingebettete E-Rechnung wird nicht gelesen.

Der Viewer ist keine Steuerberatung.
