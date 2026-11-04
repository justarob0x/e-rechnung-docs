# Preise, Lizenz, Datenschutz

## Preise (Google Sheets, inkl. USt.)

| Plan | Für wen | Monat | Jahr |
|---|---|---|---|
| Testphase | jeder, 30 Tage ab erster Nutzung, alle Funktionen, ohne Kreditkarte | kostenlos | – |
| Einzelplatz | ein Google-Konto | 2,99 € | 29 € |
| Unternehmen | alle Nutzer einer Google-Workspace-Domain | 9,99 € | 99 € |

Das Abo ist jederzeit zum Ende des Abrechnungszeitraums kündbar. Die Zahlung läuft über Stripe. Preise und Kauf:
<https://erechnung.justarobot.online/#preise>. Das Excel-Add-in hat eigene Preise ([Excel](excel.md)).

## Testphase und Lizenzschlüssel

- Die 30 Tage beginnen bei der ersten Nutzung in Ihrem Google-Konto. Die Seitenleiste zeigt „Testphase: noch N Tage.“
- Nach dem Kauf tragen Sie den Schlüssel im Tab `Einstellungen` in die Zeile `Lizenzschlüssel` ein. Die Seitenleiste
  zeigt dann „Lizenz aktiv (Einzelplatz)“ bzw. „(Unternehmen)“.
- Eine Einzelplatz-Lizenz gilt für ein Google-Konto, eine Unternehmenslizenz für die Workspace-Domain.
- Eine geprüfte Lizenz wird 7 Tage zwischengespeichert; ein Ausfall des Lizenzservers sperrt zahlende Nutzer nicht.

## Nach Ablauf der Testphase ohne Lizenz

Es lässt sich nichts mehr erstellen („Die Testphase ist abgelaufen ...“). Es bleiben nutzbar: Rechnungen ansehen und
prüfen, eingehende E-Rechnungen lesen und übernehmen, DATEV-Buchungsstapel erzeugen. Ist ein Lizenzschlüssel
eingetragen, aber ungültig oder abgelaufen, meldet die Seitenleiste „Lizenzschlüssel ungültig oder abgelaufen.“

## Welche Google-Berechtigungen das Add-on braucht

| Berechtigung | Wofür |
|---|---|
| Aktuelle Tabelle (`spreadsheets.currentonly`) | Rechnungszeilen lesen, Tabs und Statusspalte schreiben; nur die geöffnete Tabelle |
| Drive-Dateien des Add-ons (`drive.file`) | Ordner „E-Rechnungen“, Vorlage und erzeugte Dateien; nicht Ihre übrigen Drive-Dateien |
| Seitenleiste und Menü (`script.container.ui`) | Oberfläche anzeigen |
| Externe Anfragen (`script.external_request`) | Drive/Docs-Schnittstellen und die Lizenzprüfung |
| E-Mail-Adresse (`userinfo.email`) | Hash bilden, um die Lizenz an Ihr Konto zu binden |

## Datenschutz in Kürze

- Rechnungsdaten, Kunden und erzeugte Dateien bleiben in Ihrem Google-Konto und werden nicht an uns übertragen.
- Zum Server gehen nur der Lizenzschlüssel (falls eingetragen) und SHA-256-Hashes von Konto und Domain. Ihre
  E-Mail-Adresse selbst wird nicht übertragen. In der Testphase wird nichts gesendet.
- Google-Daten werden nicht für Werbung, nicht verkauft und nicht zum Training von KI-Modellen genutzt.
- Zahlungen wickelt Stripe ab.
- Verantwortlich: Universal Exporters LLC (justarobot.online), Kontakt support+erechnung@justarobot.online.
  Vollständige Erklärung: <https://erechnung.justarobot.online/datenschutz>.

Das Excel-Add-in verarbeitet ebenfalls alles auf Ihrem Gerät; hier gehen nur Lizenzschlüssel und ein Hash einer
zufälligen Geräte-ID an den Lizenzserver.
