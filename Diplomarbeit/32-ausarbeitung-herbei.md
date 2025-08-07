# Teilaufgabe Gabriel Herbei
---
### Analyse, Anwendung und Testen der digitalen Inventarisierungslösung/en basierend auf QR-Codes
---
# Inhaltsverzeichnis

1. [Theoretische Grundlagen](#1-theoretische-grundlagen)  
   1.1 [Begriffsklärung: Inventarisierung](#11-begriffsklärung-inventarisierung)  
   1.2 [Ziel der Digitalisierung: Vereinfachung des schulischen Prozesses](#12-ziel-der-digitalisierung-vereinfachung-des-schulischen-prozesses)  
   1.3 [QR-Codes als technologische Grundlage](#13-qr-codes-als-technologische-grundlage)  
   1.4 [Aktueller Inventarisierungsprozess an Schulen](#14-aktueller-inventarisierungsprozess-an-schulen)

# 1. Theoretische Grundlagen

## 1.1 Begriffsklärung: Inventarisierung

Unter Inventarisierung versteht man den strukturierten Prozess der Erfassung, Organisation und Dokumentation von materiellen Vermögenswerten einer Organisation. Im schulischen Kontext betrifft dies insbesondere Geräte wie Monitore, Personal Computer, Beamer, Fernbedienungen, Tastaturen und weitere technische oder pädagogische Ausstattung.

Die Einführung einer digitalen Inventarisierungslösung ermöglicht eine effizientere und transparentere Verwaltung dieser Gegenstände. Insbesondere bei einer größeren Anzahl an Geräten oder häufigen Standortwechseln stößt eine manuelle Erfassung mit Papierlisten oder Tabellenprogrammen schnell an ihre Grenzen.

## 1.2 Ziel der Digitalisierung: Vereinfachung des schulischen Prozesses

Die Digitalisierung des Inventarisierungsprozesses verfolgt das Ziel, den Aufwand für schulisches Verwaltungspersonal deutlich zu reduzieren und zugleich die Genauigkeit der Bestandsdaten zu erhöhen. Eine einfache Erfassung verringert die Fehleranfälligkeit, beschleunigt den Zugriff auf Informationen und verbessert die Wartbarkeit der Inventardaten erheblich. Dabei steht nicht nur die Effizienz im Vordergrund, sondern auch die langfristige Entlastung der schulischen Infrastruktur durch transparente, leicht wartbare Datenstrukturen.

## 1.3 QR-Codes als technologische Grundlage

Die geplante Lösung basiert auf dem Einsatz von QR-Codes zur Identifikation und Verknüpfung einzelner Inventargegenstände mit digitalen Datensätzen in einer zentralen Datenbank. QR steht für „Quick Response“, also „schnelle Antwort“, und bezeichnet einen zweidimensionalen Code, der aus mindestens 21 × 21 und maximal 177 × 177 quadratischen Modulen besteht (siehe Abbildung 1). In einem QR-Code können Informationen wie URLs, Textdaten, Telefonnummern oder ID-Nummern codiert werden. Der große Vorteil liegt in der schnellen und einfachen Lesbarkeit durch handelsübliche Smartphones oder Tablets, wodurch eine mobile, ortsunabhängige Nutzung gewährleistet wird.

![QR-Code](DA-2526-Inventarisierung-von-QR-Codes/Diplomarbeit/img/qrcode.gif)

*Abbildung 1: Darstellung eines QR-Codes.*  
(Quelle: QR-Code, [ActiveBarcode](https://www.activebarcode.com/de/codes/qrcode) abgerufen am 07.08.2025)

Ein einzelner QR-Code kann dabei bis zu 7.089 numerische Zeichen oder 4.296 alphanumerische Zeichen speichern – ausreichend, um beispielsweise eine eindeutige Identifikationsnummer oder einen Verweis auf ein Webformular zur Inventarverwaltung zu hinterlegen.

## 1.4 Aktueller Inventarisierungsprozess an Schulen

Derzeit erfolgt die Inventarisierung von Objekten, Werkzeugen sowie IT-Hardware an unserer Schule mit einer herkömmlicher Excel-Tabelle. Ein Beispiel dafür wurde uns in [diesem GitHub-Dokument](https://github.com/Herbei-Gabo/DA-2526-Inventarisierung-von-QR-Codes/blob/main/Diplomarbeit/doc/HTLGesamtinventar_Monitorbeispiel.xlsx) zur Verfügung gestellt. Dabei werden Informationen wie Bereich, Objektbezeichnung, Lieferant, Seriennummer, Standort Zuständigkeit und vieles weiteres manuell erfasst und gepflegt. Diese Form der Datenhaltung bringt jedoch zahlreiche Herausforderungen mit sich:

- **Hoher manueller Aufwand**: Jede Änderung – sei es eine Standortverschiebung, Reparatur oder Neuanschaffung – muss manuell in die Liste eingetragen werden.
- **Fehleranfälligkeit**: Durch manuelle Eingabe entstehen leicht Tippfehler oder doppelte Einträge.
- **Mangelnde Transparenz**: Bei mehreren Verantwortlichen kann es zu Versionskonflikten kommen, da keine zentrale und gleichzeitige Bearbeitung möglich ist.
- **Keine Mobilität**: Zugriff auf die Liste ist meist nur stationär an einem Schul-PC möglich. Eine mobile Erfassung oder Abfrage ist nicht vorgesehen.
- **Fehlende Automatisierung**: Prozesse wie das Einpflegen neuer Objekte oder das automatische Verwalten von Zuständen und Zuständigkeiten sind nicht vorhanden.

Diese Nachteile machen deutlich, dass der aktuelle Prozess weder effizient noch zukunftsfähig ist. Insbesondere bei wachsendem Bestand und höherem Digitalisierungsgrad wird eine professionelle, digitale Lösung notwendig, die zentrale Datenhaltung, Mehrbenutzerfähigkeit und mobile Zugriffsmöglichkeiten vereint.

# Literaturverzeichnis:


*Was versteht man unter Inventarisierung?*  (o. D.). Entek Systems GmbH. 
Abgerufen am 15.07.2025, von https://www.enteksystems.de/blog/was-versteht-man-unter-inventarisierung](https://www.enteksystems.de/blog/was-versteht-man-unter-inventarisierung)

*QR-Code*. (o. D.). Gabler Wirtschaftslexikon.  
Abgerufen am 15.07.2025, von [https://wirtschaftslexikon.gabler.de/definition/qr-code-53515](https://wirtschaftslexikon.gabler.de/definition/qr-code-53515)

*Basic writing and formatting syntax*. (o. D.). GitHub Docs.  
Abgerufen am 07.08.2025, von [https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

*Internetquellen zitieren*. (o. D.). Scribbr.  
Abgerufen am 07.08.2025, von [https://www.scribbr.at/richtig-zitieren-at/internetquellen-zitieren/](https://www.scribbr.at/richtig-zitieren-at/internetquellen-zitieren/)

https://www.scribbr.at/richtig-zitieren-at/quellenangabe-bild-internet/

# Abbildungsverzeichnis:

*QR-Code*. (o. D.). ActiveBarcode.  
Abgerufen am 07.08.2025, von [https://www.activebarcode.com/de/codes/qrcode](https://www.activebarcode.com/de/codes/qrcode)
