# FAQ und Fehlerbehebung

## Grundlagen

**Muss ich ab sofort E-Rechnungen ausstellen?** Empfangen müssen Unternehmen in Deutschland E-Rechnungen im B2B seit
dem 1. Januar 2025. Ausstellen müssen Sie sie ab 2027, wenn Ihr Vorjahresumsatz über 800.000 € liegt, ab 2028 alle
Unternehmen. Ausnahmen (z. B. Kleinunternehmer) und Übergangsregeln klären Sie mit Ihrem Steuerberater.

**Was ist der Unterschied zwischen XRechnung und ZUGFeRD?** XRechnung ist reine XML (Pflicht für öffentliche
Auftraggeber). ZUGFeRD ist ein PDF mit eingebetteter XML. Beide folgen EN 16931. Siehe
[Dateien erstellen](creating-files.md).

**Brauche ich ein Konto bei Ihnen?** Nein. Sie installieren das Add-on und arbeiten in Ihrer Tabelle. Ein Konto
brauchen Sie nur für den Kauf bei Stripe.

## Erstellen

**„Erstellen“ ist ausgegraut.** Entweder hat die Rechnung Fehler (erst `Prüfen`, Fehler beheben, die Meldungen zeigen
die Zelle) oder die Testphase ist abgelaufen und keine gültige Lizenz eingetragen ([Preise](pricing-and-privacy.md)).

**Die Seitenleiste zeigt „Rechnung ... nicht gefunden“ oder keine Rechnungen.** Der Tab muss `Rechnungen` heißen und
die Überschrift `Rechnungsnr.` haben. Eine Rechnung ist jede Rechnungsnummer mit mindestens einer Zeile.

**Warum verlangt die Prüfung Ansprechpartner, Telefon und E-Mail des Verkäufers?** Bei XRechnung sind sie Pflicht.
Tragen Sie sie im Tab `Verkäufer` ein ([Prüfung](validation.md)).

**Wo ist meine Leitweg-ID einzutragen?** Im Tab `Kunden` in der Spalte `Leitweg-ID` des Auftraggebers. Die Leitweg-ID
nennt Ihnen der Auftraggeber. Das Add-on warnt, wenn die Prüfziffer nicht stimmt.

**Wie stelle ich Kleinunternehmer-Rechnungen aus?** Pro Zeile `Steuer` = `E – steuerfrei / Kleinunternehmer § 19 UStG`,
`USt %` = 0. Der Hinweistext wird ergänzt ([Steuerfälle](tax-cases.md)).

**Wie schreibe ich eine Gutschrift?** `Art` = `Gutschrift`, positive Beträge, `Bezug auf Rechnung` mit der
ursprünglichen Nummer.

**Das PDF hat nicht mein Logo.** Logo und Farben ändern Sie in der Docs-Vorlage „E-Rechnung Vorlage“, nicht in der
Tabelle ([Dateien erstellen](creating-files.md#die-pdf-vorlage)). Haben Sie Platzhalter wie `{{Bezeichnung}}` gelöscht,
bleibt der Text leer oder die Positionen fehlen.

**Gibt es einen E-Mail-Versand aus dem Add-on?** Die im Marketplace angebotene Version versendet nicht selbst. Senden
Sie die Dateien aus Drive über Ihr Mailprogramm.

**Wie lange dauert das Erstellen?** Etwa 10–20 Sekunden pro Rechnung.

**Wo sind meine Dateien?** Im Drive-Ordner „E-Rechnungen“. Den Link zeigt die Seitenleiste; die Drive-ID des Ordners
steht in `Einstellungen`.

## Eingang und DATEV

**Eine Datei wird beim Import abgelehnt.** Es muss eine XRechnung (XML, UBL oder CII) oder ein ZUGFeRD-/Factur-X-PDF
mit eingebetteter XML sein. Ein normales PDF enthält keine E-Rechnung ([Eingangsrechnungen](incoming.md)).

**„Rechnung ... ist bereits importiert.“** Dieselbe Rechnungsnummer desselben Lieferanten ist schon im Tab. Das ist
Absicht, damit nichts doppelt gebucht wird.

**Im DATEV-Stapel fehlt eine Rechnung.** Ausgangsrechnungen mit Fehlern werden übersprungen und in der Seitenleiste
genannt. Prüfen Sie sie. Außerdem zählt das `Datum` der Rechnung, nicht das Erstelldatum ([DATEV](datev.md)).

**Mein Steuerberater findet falsche Konten.** Die Konten sind Standardvorschläge (SKR03/SKR04, Automatikkonten);
sprechen Sie die Zuordnung mit ihm ab und tragen Sie Debitoren-, Kreditoren- und Aufwandskonten ein.

## Lizenz und Daten

**Was passiert nach der Testphase?** Erstellen ist gesperrt; Ansehen, Prüfen, Einlesen und DATEV-Export bleiben.

**Sehen Sie meine Rechnungen?** Nein. Rechnungsdaten bleiben in Ihrem Google-Konto; nur Lizenzschlüssel und Hashes
von Konto und Domain gehen an den Lizenzserver ([Datenschutz](pricing-and-privacy.md)).

**Wo kündige ich?** Per Mail an support+erechnung@justarobot.online. Das Abo ist laut Website jederzeit zum Ende des
Abrechnungszeitraums kündbar.

**Funktioniert es mit Excel?** Ja, als eigenes Add-in ([Excel](excel.md)).

## Support

support+erechnung@justarobot.online · <https://erechnung.justarobot.online/hilfe>. Nennen Sie bitte Rechnungsnummer
(nicht den Inhalt), die angezeigte Meldung und den Reiter, in dem es passiert.
