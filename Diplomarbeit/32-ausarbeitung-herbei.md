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

2. [Evaluierung bestehender Lösungen und Alternativen](#2-evaluierung-bestehender-lösungen-und-alternativen)  
   2.1 [Bestehende Kauflösungen](#21-bestehende-kauflösungen)      
         2.1.1 [Kostenlose Alternativen](#211-kostenlose-alternativen)  
         2.1.2 [Kostenpflichtige Alternativen](#212-kostenpflichtige-alternativen)  
         2.1.3 [Fazit zu den Kauflösungen](#213-fazit-zu-den-kauflösungen)     
   2.2 [Programmierung einer Excel-Erweiterung](#22-programmierung-einer-excel-erweiterung)


# 1. Theoretische Grundlagen

## 1.1 Begriffsklärung: Inventarisierung

Unter Inventarisierung versteht man den strukturierten Prozess der Erfassung, Organisation und Dokumentation von materiellen Vermögenswerten einer Organisation. Im schulischen Kontext betrifft dies insbesondere Geräte wie Monitore, Personal Computer, Beamer, Fernbedienungen, Tastaturen und weitere technische oder pädagogische Ausstattung.

Die Einführung einer digitalen Inventarisierungslösung ermöglicht eine effizientere und transparentere Verwaltung dieser Gegenstände. Insbesondere bei einer größeren Anzahl an Geräten oder häufigen Standortwechseln stößt eine manuelle Erfassung mit Papierlisten oder Tabellenprogrammen schnell an ihre Grenzen.

## 1.2 Ziel der Digitalisierung: Vereinfachung des schulischen Prozesses

Die Digitalisierung des Inventarisierungsprozesses verfolgt das Ziel, den Aufwand für schulisches Verwaltungspersonal deutlich zu reduzieren und zugleich die Genauigkeit der Bestandsdaten zu erhöhen. Eine einfache Erfassung verringert die Fehleranfälligkeit, beschleunigt den Zugriff auf Informationen und verbessert die Wartbarkeit der Inventardaten erheblich. Dabei steht nicht nur die Effizienz im Vordergrund, sondern auch die langfristige Entlastung der schulischen Infrastruktur durch transparente, leicht wartbare Datenstrukturen.

## 1.3 QR-Codes als technologische Grundlage

Die geplante Lösung basiert auf dem Einsatz von QR-Codes zur Identifikation und Verknüpfung einzelner Inventargegenstände mit digitalen Datensätzen in einer zentralen Datenbank. QR steht für „Quick Response“, also „schnelle Antwort“, und bezeichnet einen zweidimensionalen Code, der aus mindestens 21 × 21 und maximal 177 × 177 quadratischen Modulen besteht (siehe Abbildung 1). In einem QR-Code können Informationen wie URLs, Textdaten, Telefonnummern oder ID-Nummern codiert werden. Der große Vorteil liegt in der schnellen und einfachen Lesbarkeit durch handelsübliche Smartphones oder Tablets, wodurch eine mobile, ortsunabhängige Nutzung gewährleistet wird.

![QR-Code](img/qrcode.gif)

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

# 2. Evaluierung bestehender Lösungen und Alternativen

Bevor man überhaupt an eine neue Entwicklung denken kann, muss man zuerst evaluieren, ob es aktuelle bestehende Lösungen oder auch relevante Alternativen gibt. In diesem Kapitel werden verschiedene Ansätze analysiert und hinsichtlich anhand der Vor- und Nachteile bewertet.

## 2.1 Bestehende Kauflösungen

Am Markt existieren sowohl kostenlose als auch kostenpflichtige Inventarisierungsprogramme. Der wesentliche Unterschied zwischen beiden Ansätzen liegt dabei nicht primär im Preis, sondern vielmehr im Funktionsumfang. Während kostenlose Varianten oft nur einen sehr eingeschränkten Umfang bieten, beinhalten kostenpflichtige Lösungen in der Regel erweiterte Funktionen, die insbesondere für größere Organisationen oder Unternehmen von Bedeutung sind. Für Schulen stellt sich daher die Frage, ob der zusätzliche Funktionsumfang den Mehraufwand und die höheren Kosten rechtfertigt.

### 2.1.1 Kostenlose Alternativen

Eine speziell auf Schulen zugeschnittene kostenlose Inventarisierungssoftware existiert derzeit nicht auf dem Markt. Vielmehr richten sich die vorhandenen kostenlosen Programme an kleine Unternehmen oder den E-Commerce-Bereich. Beispiele hierfür sind:

- [Zoho Inventory](https://www.zoho.com/inventory/)  
- [Odoo Inventory](https://www.odoo.com/de_DE/app/inventory)  

Diese Lösungen bieten eine Vielzahl von Funktionen wie Lagerverwaltung, Bestellwesen und Lieferkettenmanagement. Für den schulischen Bereich ist dieser Funktionsumfang jedoch überdimensioniert und führt zu einem unnötigen Verwaltungsaufwand.  

**Vorteile**:  
- kostenlos nutzbar  
- professionell entwickelte Software mit stabiler Basis  
- modular erweiterbar  

**Nachteile**:  
- keine QR-Code-Integration für einfache Inventarisierung vor Ort  
- Fokus auf Warenwirtschaft und Verkauf, nicht auf schulische Inventarverwaltung  
- hohe Komplexität in der Einrichtung und Bedienung, die nicht im Verhältnis zum Nutzen steht  
- keine direkte Anpassung an die Bedürfnisse einer Schule möglich  

Damit sind kostenlose Alternativen für den angestrebten Anwendungsbereich ungeeignet, da sie mehr Aufwand erzeugen als Nutzen bringen.

### 2.1.2 Kostenpflichtige Alternativen

Im Bereich der kostenpflichtigen Softwarelösungen existieren mehrere Anbieter, die Inventarisierung speziell für Institutionen wie Schulen oder öffentliche Einrichtungen anbieten. Zwei Beispiele sollen im Folgenden exemplarisch betrachtet werden:

#### Hoppe

Die [Hoppe Inventarsoftware](https://www.inventarsoftware.de/Default.html) ist eine etablierte Lösung zur Inventarisierung, die vor allem von Behörden, Krankenhäusern und mittelständischen Unternehmen genutzt wird. Sie wird in über 11 Ländern mit mehr als 3300 Kunden eingesetzt.

**Vorteile**:

- einmalige Lizenzgebühr ab 195 € (kein Abo-Modell)
- umfangreiche Funktionen wie Barcode- und RFID-Erfassung, Standort- und Lifecycle-Management
- mobile App für Smartphones und Tablets verfügbar
- regelmäßige Updates und professioneller Support
- vielfach ausgezeichnet (u. a. Industriepreis, Innovationspreis Mittelstand)
- Referenzen von großen Organisationen (z. B. Bundesamt für Verfassungsschutz, Deutsches Rotes Kreuz)

**Nachteile**:

- keine QR-Code integration
- keine transparente Preisübersicht, genaue Kosten meist nur auf Anfrage
- Installation und ggf. Schulung notwendig
- keine reine Cloud-Lösung
- Funktionsumfang eher auf Unternehmen und Behörden ausgelegt,
- für Schulen überdimensioniert
- zusätzliche Kosten bei Erweiterungen oder Support

#### Timly 

Die [Timly Inventarsoftware](https://timly.com/inventar-software/) ist eine moderne, cloudbasierte Lösung zur Inventarisierung von Assets und Geräten. Sie wird vor allem von Unternehmen eingesetzt, die eine mobile, flexible Verwaltung ihrer Bestände benötigen.

**Vorteile**:

- cloudbasiert, mobil nutzbar via Web-App oder Smartphone-App
- Echtzeit-Tracking von Assets durch GPS, QR-Code-Scanning und IoT-Integration
- automatisierte Wartungsplanung mit Erinnerungen und Fristenmanagement
- Integration mit ERP-Systemen wie SAP, DATEV oder Microsoft Dynamics 365 über REST-API
- benutzerfreundliche Oberfläche mit anpassbaren Feldern und Rollenmanagement

**Nachteile**:

- hohe Kosten (ab 185 CHF im Monat)
- keine Offline-Nutzung möglich
- ständige Internetverbindung erforderlich

#### Endoo Organize

Die Lösung [Endoo Organize](https://endoo-organize.de/funktionen-inventarisierung/) richtet sich ausdrücklich auch an Schulen und Bildungseinrichtungen. Sie bietet neben einer QR-Code-Integration auch zahlreiche zusätzliche Funktionen wie:

- Verwaltung von Zubehör  
- Ausleihmanagement  
- Reservierung von Objekten  
- zentrale Verwaltung von Geräten und Materialien  

**Vorteile**:  
- speziell für Schulen ausgelegt  
- integrierte QR-Code-Lösung  
- vielfältige Zusatzfunktionen, die den Schulalltag vereinfachen können  
- professionelle Unterstützung durch den Anbieter  

**Nachteile**:  
- keine transparente Preisgestaltung (Preisinformationen nur nach Kontaktaufnahme)  
- verpflichtende Terminvereinbarung für eine Online-Beratung oder Live-Präsentation (zeitaufwändig)  
- mögliche laufende Lizenzkosten, die schwer abschätzbar sind  
- Abhängigkeit vom Anbieter bei Erweiterungen und Wartung  

#### inFlow Inventory

Eine weitere Lösung stellt [inFlow Inventory](https://www.inflowinventory.com/inflow-inventory) dar, die für verschiedene Anwendungsbereiche von kleinen bis mittelgroßen Unternehmen konzipiert ist.  

**Vorteile**:  
- 14-tägige kostenlose Testphase  
- benutzerfreundliche Oberfläche  
- für verschiedene Plattformen (Web, Desktop, Mobile) verfügbar  
- international weit verbreitet und gut dokumentiert  

**Nachteile**:  
- sehr hohe Kosten: Das günstigste Paket „Entrepreneur“ beginnt bei 186 USD/Monat und bietet nur eingeschränkte Funktionen (z. B. Zugriff für nur zwei Benutzer, begrenzter technischer Support). Die teuersten Pakete für mittelgroße Unternehmen kosten bis zu 999 USD/Monat ([Preisübersicht](https://www.inflowinventory.com/software-pricing)).  
- viele Funktionen sind nur in höheren Preiskategorien enthalten  
- Kosten-Nutzen-Verhältnis für eine Schule nicht vertretbar  

### 2.1.3 Fazit zuden Kauflösungen

Zusammenfassend lässt sich feststellen, dass sowohl kostenlose als auch kostenpflichtige Kauflösungen für den schulischen Einsatz problematisch sind. Kostenlose Varianten sind funktional nicht passend, da sie nicht für den Bildungssektor entwickelt wurden und wichtige Funktionen wie QR-Code-Integration fehlen. Kostenpflichtige Lösungen hingegen bieten zwar umfangreiche Funktionen, sind jedoch mit hohen und oft intransparenten Kosten verbunden.  

Für Schulen ergibt sich daraus die Herausforderung, entweder mit einer zu komplexen oder zu teuren Lösung zu arbeiten. Eine speziell entwickelte, kostengünstige Eigenlösung erscheint daher als sinnvoller Ansatz, da sie exakt an die Bedürfnisse der Schule angepasst werden kann.

## 2.2 Programmieren einer Excel-Erweiterung

Die Inventarisierungsliste der HTL Leoben basiert, wie bereits erwähnt, auf Microsoft Excel. Daher wäre die Möglichkeit, eine Excel-Erweiterung zu programmieren, auf den ersten Blick eine naheliegende Idee. Excel-Add-ins (Erweiterungen) ermöglichen es, neue Funktionen direkt in Excel einzubinden, wie beispielsweise automatisierte Berechnungen, Datenvalidierungen oder benutzerdefinierte Menüleisten. Sie können Arbeitsabläufe deutlich vereinfachen und sind insbesondere dann sinnvoll, wenn wiederkehrende Aufgaben standardisiert werden sollen.

Allerdings sprechen mehrere Punkte dagegen, diese Lösung tatsächlich umzusetzen:

1. **Zugriff auf Originaldaten fehlt**  
    Der Zugriff auf die originale Inventarliste ist nicht möglich. Ein Add-in könnte daher nur auf der Kopie entwickelt werden, die nicht den tatsächlichen Datenbestand widerspiegelt. Somit wäre die Lösung nicht einsatzfähig für die echte Inventarisierung.
    
2. **Keine Lösung des Kernproblems**  
    Die zentrale Herausforderung der Inventarisierung ist die **Unübersichtlichkeit** großer Datenmengen, das Risiko von Duplikaten und die fehleranfällige Zuordnung von Objekten. Ein Excel-Add-in würde lediglich die vorhandene Liste geringfügig vereinfachen, ändert jedoch nichts an der eigentlichen Problematik.
    
3. **QR-Code-Zuordnung nicht automatisierbar über ein Add-in**  
    Für die geplante Digitalisierung der Inventarliste ist es notwendig, dass jedem Objekt ein eigener QR-Code zugewiesen wird. Dies lässt sich nicht über ein Excel-Add-in automatisch umsetzen. Die QR-Codes müssen in der Excel-Datei selbst generiert und korrekt zugeordnet werden. Ein Add-in würde hier keinen nennenswerten Vorteil bringen, da die Generierung und Zuweisung der Codes weiterhin manuell erfolgen müsste.
    
4. **Optik und Benutzerfreundlichkeit**  
    Ein Add-in kann zwar bestimmte Funktionen automatisieren, verändert jedoch nicht die Übersichtlichkeit oder Gestaltung der Excel-Liste. Die Darstellung bleibt unverändert und es entstehen keine zusätzlichen Hilfen, die das Arbeiten mit vielen Datensätzen erleichtern.
    
Die Entwicklung einer Excel-Erweiterung würde den Aufwand erhöhen und nur einen geringen Nutzen bringen. Sie greift nicht die Kernprobleme der Inventarisierung an und ist zudem aufgrund fehlender Originaldaten nicht praktisch umsetzbar. 

# Literaturverzeichnis:

Kister, F. (2024, 7. Mai). _Was versteht man unter Inventarisierung?_ Entek Systems GmbH.  
Abgerufen am 15.07.2025, von [https://www.enteksystems.de/blog/was-versteht-man-unter-inventarisierung](https://www.enteksystems.de/blog/was-versteht-man-unter-inventarisierung)

Bendel, O. (o. D.). _QR-Code_. Gabler Wirtschaftslexikon.  
Abgerufen am 15.07.2025, von [https://wirtschaftslexikon.gabler.de/definition/qr-code-53515](https://wirtschaftslexikon.gabler.de/definition/qr-code-53515)

*Basic writing and formatting syntax*. (o. D.). GitHub Docs.  
Abgerufen am 07.08.2025, von [https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

Theel, M. (2024, 18. Januar). _Internetquellen einfach zitieren: Unterschiede & Beispiele_. Scribbr.  
Abgerufen am 07.08.2025, von [https://www.scribbr.at/richtig-zitieren-at/internetquellen-zitieren/](https://www.scribbr.at/richtig-zitieren-at/internetquellen-zitieren/)

Glöckler, L. (2023, 31. März). _Quellenangaben von Bildern aus dem Internet_. Scribbr.   
Abgerufen am 07.08.2025, von [https://www.scribbr.at/richtig-zitieren-at/quellenangabe-bild-internet/](https://www.scribbr.at/richtig-zitieren-at/quellenangabe-bild-internet/)

_Fischer, T._ (2024, 26. Februar). _Beste Inventarsoftware kostenlos: Die 10 besten Tools im Vergleich_.  
Abgerufen am 15.08.2025, von [https://omr.com/de/reviews/contenthub/beste-inventarsoftware-kostenlos](https://omr.com/de/reviews/contenthub/beste-inventarsoftware-kostenlos)

_Hofer, N._ (2025, 21. Mai). _Open Source Inventory Management: Die besten kostenlosen Tools im Überblick_. Wondershare.  
Abgerufen am 15.08.2025, von [https://pdf.wondershare.de/business/open-source-inventory-management.html](https://pdf.wondershare.de/business/open-source-inventory-management.html)

*Odoo Inventory – Bestandsverwaltung*. (o. D.). Odoo.  
Abgerufen am 18.08.2025, von [https://www.odoo.com/de_DE/app/inventory](https://www.odoo.com/de_DE/app/inventory) 

Hoppe Unternehmensberatung. (o. D.). _Inventarmanager – Inventarisieren ganz einfach_. Inventarsoftware.  
Abgerufen am 21.08.2025, von [https://www.inventarsoftware.de/Inventarmanager.html](https://www.inventarsoftware.de/Inventarmanager.html)

Timly Software AG. (o. D.). Die Inventar Software für eine optimale Übersicht.   
Abgerufen am 21.08.2025, von [https://timly.com/inventar-software](https://timly.com/inventar-software)

Kowalski, W. (2024, 28. März). _How to Create and Use an Excel Add-in_. SCAND.    
Abgerufen am 21.08.2025, von [https://scand.com/company/blog/how-to-create-and-use-an-excel-add-in/](https://scand.com/company/blog/how-to-create-and-use-an-excel-add-in/)

# Abbildungsverzeichnis:

*QR-Code*. (o. D.). ActiveBarcode.  
Abgerufen am 07.08.2025, von [https://www.activebarcode.com/de/codes/qrcode](https://www.activebarcode.com/de/codes/qrcode)



