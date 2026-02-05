# Teilaufgabe Gabriel Herbei

## Begriffsklärung Inventarisierung
Unter Inventarisierung versteht man den strukturierten Prozess der Erfassung, Organisation und Dokumentation von materiellen Vermögenswerten einer Organisation. Im schulischen Kontext betrifft dies insbesondere Geräte wie Monitore, Personal Computer, Beamer, Fernbedienungen, Tastaturen und weitere technische oder pädagogische Ausstattung.

Die Einführung einer digitalen Inventarisierungslösung ermöglicht eine effizientere und transparentere Verwaltung dieser Gegenstände. Insbesondere bei einer größeren Anzahl an Geräten oder häufigen Standortwechseln stößt eine manuelle Erfassung mit Papierlisten oder Tabellenprogrammen schnell an ihre Grenzen. [@kister_inventarisierung_2024]

## Ziel der Digitalisierung ist die Vereinfachung des schulischen Prozesses
Die Digitalisierung des Inventarisierungsprozesses verfolgt das Ziel, den Aufwand für schulisches Verwaltungspersonal deutlich zu reduzieren und zugleich die Genauigkeit der Bestandsdaten zu erhöhen. Eine einfache Erfassung verringert die Fehleranfälligkeit, beschleunigt den Zugriff auf Informationen und verbessert die Wartbarkeit der Inventardaten erheblich. Dabei steht nicht nur die Effizienz im Vordergrund, sondern auch die langfristige Entlastung der schulischen Infrastruktur durch transparente, leicht wartbare Datenstrukturen.

Gerade im schulischen Umfeld, in dem Geräte regelmäßig den Raum wechseln, ausgeliehen oder repariert werden, ist eine aktuelle und zentrale Datenhaltung entscheidend. Eine digitale Inventarisierung ermöglicht es, Änderungen unmittelbar zu erfassen und reduziert Abhängigkeiten von einzelnen Personen oder lokalen Dateien. Dadurch wird nicht nur der Verwaltungsaufwand gesenkt, sondern auch die Nachvollziehbarkeit und Transparenz für alle Beteiligten erhöht.

## Aktueller Inventarisierungsprozess an der HTL Leoben
Derzeit erfolgt die Inventarisierung von Objekten, Werkzeugen sowie IT-Hardware an unserer Schule mit einer herkömmlicher Excel-Tabelle. Ein Beispiel dafür wurde uns in [diesem GitHub-Dokument](https://github.com/Herbei-Gabo/DA-2526-Inventarisierung-von-QR-Codes/blob/main/Diplomarbeit/doc/HTLGesamtinventar_Monitorbeispiel.xlsx) zur Verfügung gestellt. Dabei werden Informationen wie Bereich, Objektbezeichnung, Lieferant, Seriennummer, Standort Zuständigkeit und vieles weiteres manuell erfasst und gepflegt. Diese Form der Datenhaltung bringt jedoch zahlreiche Herausforderungen mit sich:

- **Hoher manueller Aufwand**: Jede Änderung, sei es eine Standortverschiebung, Reparatur oder Neuanschaffung, muss manuell in die Liste eingetragen werden.
- **Fehleranfälligkeit**: Durch manuelle Eingabe entstehen leicht Tippfehler oder doppelte Einträge.
- **Mangelnde Transparenz**: Bei mehreren Verantwortlichen kann es zu Versionskonflikten kommen, da keine zentrale und gleichzeitige Bearbeitung möglich ist.
- **Keine Mobilität**: Zugriff auf die Liste ist meist nur stationär an einem Schul-PC möglich. 

Diese Nachteile machen deutlich, dass der aktuelle Prozess weder effizient noch zukunftsfähig ist. Insbesondere bei wachsendem Bestand und höherem Digitalisierungsgrad wird eine professionelle, digitale Lösung notwendig, die zentrale Datenhaltung, Mehrbenutzerfähigkeit und mobile Zugriffsmöglichkeiten vereint.

## QR-Codes als technologische Grundlage
Die geplante Lösung basiert auf dem Einsatz von QR-Codes zur Identifikation und Verknüpfung einzelner Inventargegenstände mit digitalen Datensätzen in einer zentralen Datenbank. QR steht für „Quick Response“, also „schnelle Antwort“, und bezeichnet einen zweidimensionalen Code, der aus mindestens 21 × 21 und maximal 177 × 177 quadratischen Modulen besteht (siehe Abbildung 1). In einem QR-Code können Informationen wie URLs, Textdaten, Telefonnummern oder ID-Nummern codiert werden. Der große Vorteil liegt in der schnellen und einfachen Lesbarkeit durch handelsübliche Smartphones oder Tablets, wodurch eine mobile, ortsunabhängige Nutzung gewährleistet wird.[@bendel_qrcode_gabler @eckert_qr_vs_barcode_2023 @berger_nfc_vs_qr_2024]

![ Darstellung eines QR-Codes. [@activebarcode_qrcode_info_2025]](img/qrcode.gif) 

Für die Inventarisierung wird der QR-Code nicht als vollständiger Datenspeicher verwendet, sondern als Verweis auf einen zentralen Datensatz. Der Code enthält typischerweise eine eindeutige Identifikationsnummer oder eine URL, über die beim Scannen die aktuellen Informationen aus der Datenbank abgerufen werden. Dieses Prinzip ermöglicht es, Daten jederzeit zu aktualisieren, ohne den QR-Code neu drucken zu müssen. Zusätzlich verfügen QR-Codes über eine integrierte Fehlerkorrektur, wodurch sie auch bei teilweiser Beschädigung oder Verschmutzung noch zuverlässig gelesen werden können, welches ein wesentlicher Vorteil im schulischen Alltag ist.

## Wieso QR-Code und kein Barcode oder NFC

### Technische Vergleichskriterien
**Datenkapazität:** QR-Codes (2D-Codes) bieten eine deutlich höhere Datenkapazität als klassische eindimensionale Barcodes. Während 1D-Barcodes je nach Typ typischerweise nur ungefähr 20–25 Zeichen speichern können (siehe Abbildung 2.), können QR-Codes bis zu 2.509 Ziffern bzw. 1.520 alphanumerische Zeichen aufnehmen. In der Praxis bedeutet dies, dass QR-Codes wesentlich mehr Informationen (z. B. Inventarnummern, URLs oder Detaildaten) direkt im Code unterbringen können. Ein QR-Code kann etwa eine vollständige URL oder Text enthalten, wo ein 1D-Barcode oft nur eine kurze ID liefert. [@eckert_qr_vs_barcode_2023]

![ Darstellung eines Bar-Codes. [@tecit_barcode_generator_2025]](img/Barcode.jpg) 

NFC-Tags haben je nach Chip ebenfalls begrenzten Speicher (häufig zwischen 48 Byte bis ein paar Kilobyte, siehe Abbildung 3), was für einfache IDs oder Links ausreicht. Allerdings ist die Speicherkapazität von NFC pro Tag oft geringer als die von QR-Codes auf einem Label, und meist werden auch bei NFC nur Identifikationsnummern oder kurze Datensätze gespeichert. [@berger_nfc_vs_qr_2024]

![Darstellung eines NFC. [@homeandsmart_nfc_2025]](img/nfc-symbol.jpg) 

**Lesegeschwindigkeit und -sicherheit:** Bei Barcodes muss der Scanner (oder die Kamera) den Code zeilenweise in einer Achse lesen. 1D-Barcodes sind richtungsabhängig, sie müssen in einer bestimmten Ausrichtung erfasst werden und das Lesegerät braucht oft einen direkten, geraden „Line-of-Sight“ zum Code. Das macht sie empfindlicher für Verdrehungen oder Winkel beim Scannen. In der Praxis müssen Barcodes meist ziemlich genau ausgerichtet werden, was Zeit kosten kann. QR-Codes dagegen besitzen Ausrichtungsmarkierungen und können aus jedem Winkel schnell erkannt werden. Das beschleunigt den Scan-Vorgang, da Nutzer das Gerät nicht exakt ausrichten müssen. Beide Codearten lassen sich mit modernen Geräten zügig einlesen. Jedoch bieten QR-Codes hier einen Vorteil durch robustere Erkennung (daher der Name „Quick Response“). NFC-Scans sind in der Regel sehr schnell, ein kurzes Tap mit dem Gerät reicht. In Szenarien mit einzelnen Objekten ist NFC vom reinen Lesevorgang her ggf. am schnellsten, da kein Fokussieren der Kamera nötig ist. Allerdings muss das Gerät für NFC sehr nah (wenige cm) an den Tag gebracht werden, was bei vielen Objekten hintereinander zeitaufwendiger werden kann. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

**Kosten für Etiketten und Lesegeräte:** In Sachen Kosten sind QR-Codes und klassische Barcodes nahezu unschlagbar günstig. Sie lassen sich für ein paar Cent auf Papier oder Etiketten drucken und an den Gegenständen anbringen. Es fallen praktisch keine laufenden Kosten pro Code an, man kann mit einem Standard-Drucker oder einem Etikettendrucker hunderte QR- oder Barcode-Aufkleber billig herstellen. NFC-Tags hingegen enthalten Mikrochips und Antennen und sind deutlich teurer pro Stück. Selbst einfache NFC-Aufkleber kosten typischerweise zwischen 0,20€ und 0,50€ (hochwertige, robuste Tags oder größere Speicherkapazität noch mehr). Hinzu kommt, dass NFC-Tags spezielle Hardware im Gerät benötigen, nämlich einen NFC-Chip auslesen, während QR- und Barcodes von jeder Kamera erfasst werden können. Ein dedizierter Barcode-Laserscanner (wie er in Läden genutzt wird) kostet zwar zusätzliches Geld, wird hier aber gar nicht benötigt, da Smartphones/Tablets als Scanner dienen sollen. Somit entstehen für QR-Lösungen keine zusätzlichen Hardwarekosten, was sie äußerst kosteneffektiv macht. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

**Infrastruktur (Kamera vs. Scanner vs. NFC-Reader):** Ein großer Vorteil von QR-Codes (und auch 1D-Barcodes) ist, dass keine spezielle Infrastruktur nötig ist. Eine Kamera reicht aus. In unserem Fall soll die Inventar-Lösung ja webbasiert und mit der Kamera von Mobilgeräten funktionieren. Moderne Smartphones und Tablets haben fast alle eine Kamera, die sich via Browser nutzen lässt. Barcode-Scanner (Laser- oder CCD-Scanner) wären alternative Lesegeräte, doch diese wären Extra-Hardware, die angeschafft und mit dem System gekoppelt werden müsste. Das soll vermieden werden. NFC wiederum benötigt ein NFC-Lesegerät. Zwar haben viele neuere Smartphones einen NFC-Chip, aber nicht alle für die Schule relevanten Geräte unterstützen NFC, etwa manche günstigeren Tablets oder iPhones älterer Generation (und iPads haben teils gar kein NFC). Außerdem unterstützen gängige Webbrowser NFC noch nicht plattformübergreifend, z. B. wird Web-NFC in iOS/Safari nicht unterstützt (Stand 2025), sodass ein iPhone im Browser keinen NFC-Tag lesen könnte. Das heißt, NFC würde entweder eine native App oder spezielle Leser (z. B. USB-NFC-Reader am PC) erfordern, was der Vorgabe „ohne App und ohne Spezialhardware“ widerspricht. QR-Codes/Barcodes lassen sich hingegen direkt im Browser per Kamerazugriff scannen, dies ist plattformunabhängig möglich. Ein Smartphone oder Tablet mit Kamera genügt für QR- und Barcode-Scanning, während NFC hardware-abhängig ist (braucht NFC-fähiges Gerät). Darüber hinaus ist die Reichweite ein Faktor. Die Kamera kann einen QR-Code aus einiger Entfernung lesen (je nach Codegröße auch aus ein paar Metern, z. B. ein großer QR-Code an der Wand), während NFC eine sehr geringe Reichweite (<10 cm) hat. QR-Codes können teils gescannt werden, ohne das Objekt in die Hand nehmen zu müssen, wohingegen NFC-Tags immer durch Annähern des Lesegeräts physisch erreicht werden müssen. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

**Lesbarkeit unter Praxisbedingungen (Licht, Verschmutzung usw.):** In einem Schulalltag kann es vorkommen, dass Etiketten Schmutz abbekommen, zerkratzt werden oder bei suboptimalen Lichtverhältnissen gescannt werden müssen. QR-Codes sind hier relativ robust. Dank Error-Correction kann sogar ein teilweise verdeckter oder beschädigter QR-Code oft noch gelesen werden. 1D-Barcodes hingegen sind empfindlicher. Schon ein Riss oder Aufkleber über einem Teil des Codes macht ihn u.U. unlesbar. In dunkleren Umgebungen benötigen Kamera-Scanner genügend Licht oder den Einsatz der Geräte-Taschenlampe; dedizierte Barcode-Leser haben oft eingebaute Beleuchtung. Ein Smartphone kann aber den Blitz als Lichtquelle beim QR/Barcode-Scan verwenden, wodurch auch in weniger gut beleuchteten Räumen das Scannen möglich ist. NFC-Tags sind unempfindlich gegenüber Sichtverhältnissen, da sie per Funk ausgelesen werden, stört weder Dunkelheit noch Verschmutzung auf der Oberfläche (der Tag kann sogar unsichtbar unter einer Abdeckung sitzen). Allerdings haben auch NFC-Tags Umgebungsfaktoren. Metall in unmittelbarer Nähe oder Feuchtigkeit können das Signal dämpfen. In der Schule (z. B. Metallgestelle von Geräten oder Laptops mit Metallgehäuse) müsste man NFC-Tags eventuell mit Abstandshaltern oder speziellen on-metal Tags anbringen, um Lesbarkeit zu gewährleisten. Zudem können QR-/Barcode-Etiketten einfach mit einer Klarsichtfolie oder Laminat überzogen werden, um sie vor Verschmutzung zu schützen– das ist kostengünstig machbar. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

### Anforderungen an das geplante Inventarsystem (Browser/Plattform, Kosten, Bedienung)

**Plattformunabhängiger Browser-Einsatz:** 
Die Lösung soll auf verschiedenen Geräten (Android-Smartphones, iPhones, Tablets, ggf. Laptops mit Webcam) laufen. QR-Codes erfüllen diese Anforderung optimal, da fast jedes dieser Geräte über eine Kamera verfügt und moderne Browser den Kamerazugriff erlauben. QR-Codes können direkt im Browser per JavaScript oder native Browser-APIs erkannt werden. QR-Code-Scanning inzwischen nahezu universell. Smartphone-Kameras erkennen QR-Codes oft automatisch, und im Web lassen sich Libraries oder die BarcodeDetector-API nutzen. Barcodes (1D) könnten theoretisch ebenfalls per Kamera erfasst werden, allerdings ist die native Unterstützung nicht so benutzerfreundlich (die Handy-Kamera-App z. B. liest standardmäßig nur QR, nicht aber beliebige 1D-Codes für Weblinks). NFC scheidet hier aus, da es im Web-Browser nicht durchgängig unterstützt wird. Viele Geräte (insbesondere iOS-Geräte) erlauben NFC-Lesen nur in nativen Apps, nicht im Browser. Zudem haben längst nicht alle User-Geräte NFC (gerade im Bildungsbereich könnten ältere Geräte im Einsatz sein). QR-Codes hingegen „funktionieren auf fast allen Smartphones“ ohne zusätzliche Hardware oder spezielle App. Diese Plattformunabhängigkeit, einmal ein Browser mit Kamera reicht, prädestiniert QR-Codes für die gewünschte Weblösung. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

**Kostengünstige Umsetzung ohne Spezialhardware:** 
Schulen haben oft begrenztes Budget. Eine Lösung, die vorhandene Geräte (Lehrer-Smartphones, Schultablets) nutzt, spart Kosten. QR-Codes erfüllen das, da kein spezielles Lesegerät gekauft werden muss. Jedes handelsübliche Smartphone/Tablet wird zum Scanner. Auch die Labels selbst sind günstig. QR-Code-Aufkleber kann man selbst drucken oder für wenige Cent bestellen. Barcodes teilen diesen Vorteil der günstigen Druckkosten, auch sie könnten gedruckt werden. Allerdings würden reine Barcodes evtl. Scanner nötig machen, falls die Browser-Lösung nicht zuverlässig 1D-Codes lesen kann oder das Personal nicht mit der Kamera scannen will. Oft werden in professionellen Umgebungen Handscanner eingesetzt, was aber zusätzliche Hardware bedeutet. NFC wiederum hätte nicht nur höhere Tag-Kosten pro Objekt, sondern würde auch implizieren, dass jedes* Lesegerät NFC-fähig ist. Müsste die Schule Reader anschaffen (z. B. USB-NFC-Reader für PCs oder neue Mobilgeräte mit NFC), steigen die Kosten erheblich. Die kosteneffektivste Lösung ist eindeutig der QR-Code. Er lässt sich für „Pennies“ drucken und mit vorhandenen Smartphones scannen. Zusätzliche Anschaffungen sind nicht nötig, was die Gesamtbetriebskosten minimal hält. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

**Einfache Nutzung durch Schulpersonal:** 
Die Technik soll von Lehrkräften oder Verwaltungsmitarbeitern intuitiv bedienbar sein. QR-Codes sind hier quasi zum Alltag geworden. Seit der Corona-Zeit kennen viele das Scannen von QR-Codes (z. B. für Menü, Check-in etc.) und wissen, wie man einen QR-Code scannt. Man öffnet einfach die Kamera oder die Web-App und hält sie auf den Code. Die Hemmschwelle ist gering, da kein technisches Spezialwissen nötig ist. Barcodes wären an sich ähnlich simpel, doch viele verbinden Barcodescans mit Kassenscannern. Mit dem Smartphone einen Code128 zu scannen ist weniger verbreitet und intuitiv. Außerdem müsste man dem Personal erklären, dass sie in der Web-Anwendung dann einen Barcode anvisieren, was sicher machbar ist, aber der QR-Code genießt einen höheren Wiedererkennungswert („Ah, ein QR-Code, den kann ich mit dem Handy scannen.“). NFC würde in der Anwendung bedeuten, dass der Nutzer muss wissen, wo sich der NFC-Sensor am Gerät befindet und das Gerät an jedes Inventarstück anhalten. Für technisch weniger versierte Nutzer ist das Konzept abstrakter, da NFC-Tags unsichtbar sein können. QR-Codes sind sichtbar und haben eine klar erkennbare Aufforderung zum Scannen (man sieht den Code und weiß, was zu tun ist). Zudem entfällt bei QR die Fehlersuche „habe ich den richtigen Tag erwischt?“, man sieht eindeutig, welchen Code man scannt. Ein weiterer Punkt ist, dass kein Pairing oder keine spezielle App nötig ist. Die Nutzer öffnen einfach den Browser auf dem Tablet, drücken „Scan starten“ und verwenden die Kamera. Die Hürde, eine eigene App installieren zu müssen, entfällt komplett. Alles in allem wird das Schulpersonal mit QR-Codes am wenigsten Einarbeitungsaufwand haben. Selbst wenn jemand technisch nicht versiert ist, sind QR-Codes selbsterklärend (und falls jemand kein Smartphone nutzen will, könnten die QR-Codes auch ausgedruckt z.B. per Diensthandy gescannt werden). NFC ist dagegen eine weniger bekannte Technologie. Viele Menschen wissen gar nicht, dass ihr Handy Tags lesen kann. Für einen erfolgreichen Einsatz müsste man alle Beteiligten schulen, wo sie das Gerät auflegen müssen und wie der Lesevorgang bestätigt wird. QR-Codes haben hier klar die Nase vorn in Sachen Usability und Akzeptanz. [@eckert_qr_vs_barcode_2023] [@berger_nfc_vs_qr_2024.] [@winkler_barcode_vs_qr_2023]

## Evaluierung bestehender Lösungen und Alternativen

Bevor man überhaupt an eine neue Entwicklung denken kann, muss man zuerst evaluieren, ob es aktuelle bestehende Lösungen oder auch relevante Alternativen gibt. In diesem Kapitel werden verschiedene Ansätze analysiert und hinsichtlich anhand der Vor- und Nachteile bewertet.

## Bestehende Kauflösungen

Am Markt existieren sowohl kostenlose als auch kostenpflichtige Inventarisierungsprogramme. Der wesentliche Unterschied zwischen beiden Ansätzen liegt dabei nicht primär im Preis, sondern vielmehr im Funktionsumfang. Während kostenlose Varianten oft nur einen sehr eingeschränkten Umfang bieten, beinhalten kostenpflichtige Lösungen in der Regel erweiterte Funktionen, die insbesondere für größere Organisationen oder Unternehmen von Bedeutung sind. Für Schulen stellt sich daher die Frage, ob der zusätzliche Funktionsumfang den Mehraufwand und die höheren Kosten rechtfertigt.

### Kostenlose Alternativen

Eine speziell auf Schulen zugeschnittene kostenlose Inventarisierungssoftware existiert derzeit nicht auf dem Markt. Vielmehr richten sich die vorhandenen kostenlosen Programme an kleine Unternehmen oder den E-Commerce-Bereich. Beispiele hierfür sind:

- [Zoho Inventory](https://www.zoho.com/inventory/) [@zoho_inventory]
- [Odoo Inventory](https://www.odoo.com/de_DE/app/inventory) [@odoo_inventory]    

Diese Lösungen bieten eine Vielzahl von Funktionen wie Lagerverwaltung, Bestellwesen und Lieferkettenmanagement.[@fischer_inventarsoftware_2024] Für den schulischen Bereich ist dieser Funktionsumfang jedoch überdimensioniert und führt zu einem unnötigen Verwaltungsaufwand.  

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

### Kostenpflichtige Alternativen

Im Bereich der kostenpflichtigen Softwarelösungen existieren mehrere Anbieter, die Inventarisierung speziell für Institutionen wie Schulen oder öffentliche Einrichtungen anbieten. Folgenden Beispiele werden exemplarisch betrachtet:

#### Hoppe

Die [Hoppe Inventarsoftware](https://www.inventarsoftware.de/Default.html) [@hoppe_inventarsoftware] ist eine etablierte Lösung zur Inventarisierung, die vor allem von Behörden, Krankenhäusern und mittelständischen Unternehmen genutzt wird. Sie wird in über 11 Ländern mit mehr als 3300 Kunden eingesetzt.

**Vorteile**:

- einmalige Lizenzgebühr ab 195 € (kein Abo-Modell)
- umfangreiche Funktionen wie Barcode- und RFID-Erfassung, Standort- und Lifecycle-Management
- mobile App für Smartphones und Tablets verfügbar
- regelmäßige Updates und professioneller Support
- vielfach ausgezeichnet (u. a. Industriepreis, Innovationspreis Mittelstand)
- Referenzen von großen Organisationen (z. B. Bundesamt für Verfassungsschutz, Deutsches Rotes Kreuz) [@hoppe_inventarsoftware]

**Nachteile**:

- keine QR-Code integration
- keine transparente Preisübersicht, genaue Kosten meist nur auf Anfrage
- Installation und ggf. Schulung notwendig
- keine reine Cloud-Lösung
- Funktionsumfang eher auf Unternehmen und Behörden ausgelegt,
- für Schulen überdimensioniert
- zusätzliche Kosten bei Erweiterungen oder Support [@hoppe_inventarsoftware]

#### Timly 

Die [Timly Inventarsoftware](https://timly.com/inventar-software/) ist eine moderne, cloudbasierte Lösung zur Inventarisierung von Assets und Geräten. Sie wird vor allem von Unternehmen eingesetzt, die eine mobile, flexible Verwaltung ihrer Bestände benötigen.

**Vorteile**:

- cloudbasiert, mobil nutzbar via Web-App oder Smartphone-App
- Echtzeit-Tracking von Assets durch GPS, QR-Code-Scanning und IoT-Integration
- automatisierte Wartungsplanung mit Erinnerungen und Fristenmanagement
- Integration mit ERP-Systemen wie SAP, DATEV oder Microsoft Dynamics 365 über REST-API
- benutzerfreundliche Oberfläche mit anpassbaren Feldern und Rollenmanagement [@timly_inventarsoftware]

**Nachteile**:

- hohe Kosten (ab 185 CHF im Monat)
- keine Offline-Nutzung möglich
- ständige Internetverbindung erforderlich [@timly_inventarsoftware]

#### Endoo Organize

Die Lösung [Endoo Organize](https://endoo-organize.de/funktionen-inventarisierung/) [@endoo_organize] richtet sich ausdrücklich auch an Schulen und Bildungseinrichtungen. Sie bietet neben einer QR-Code-Integration auch zahlreiche zusätzliche Funktionen wie:

- Verwaltung von Zubehör
- Ausleihmanagement
- Reservierung von Objekten
- zentrale Verwaltung von Geräten und Materialien [@endoo_organize]

**Vorteile**:  

- speziell für Schulen ausgelegt
- integrierte QR-Code-Lösung
- vielfältige Zusatzfunktionen, die den Schulalltag vereinfachen können
- professionelle Unterstützung durch den Anbieter  [@endoo_organize]

**Nachteile**:  

- keine transparente Preisgestaltung (Preisinformationen nur nach Kontaktaufnahme)
- verpflichtende Terminvereinbarung für eine Online-Beratung oder Live-Präsentation (zeitaufwändig)
- mögliche laufende Lizenzkosten, die schwer abschätzbar sind
- Abhängigkeit vom Anbieter bei Erweiterungen und Wartung [@endoo_organize]

#### inFlow Inventory

Eine weitere Lösung stellt [inFlow Inventory](https://www.inflowinventory.com/inflow-inventory) [@hofer_open_source_inventory_2025] dar, die für verschiedene Anwendungsbereiche von kleinen bis mittelgroßen Unternehmen konzipiert ist.  

**Vorteile**:  

- 14-tägige kostenlose Testphase
- benutzerfreundliche Oberfläche
- für verschiedene Plattformen (Web, Desktop, Mobile) verfügbar
- international weit verbreitet und gut dokumentiert  [@hofer_open_source_inventory_2025]

**Nachteile**:  

- sehr hohe Kosten. Das günstigste Paket „Entrepreneur“ beginnt bei 186 USD/Monat und bietet nur eingeschränkte Funktionen (z. B. Zugriff für nur zwei Benutzer, begrenzter technischer Support). Die teuersten Pakete für mittelgroße Unternehmen kosten bis zu 999 USD/Monat ([Preisübersicht](https://www.inflowinventory.com/software-pricing)).  
- viele Funktionen sind nur in höheren Preiskategorien enthalten  
- Kosten-Nutzen-Verhältnis für eine Schule nicht vertretbar [@hofer_open_source_inventory_2025]

## Programmieren einer Excel-Erweiterung

Die Inventarisierungsliste der HTL Leoben basiert, wie bereits erwähnt, auf Microsoft Excel. Daher wäre die Möglichkeit, eine Excel-Erweiterung zu programmieren, auf den ersten Blick eine naheliegende Idee. Excel-Add-ins (Erweiterungen) ermöglichen es, neue Funktionen direkt in Excel einzubinden, wie beispielsweise automatisierte Berechnungen, Datenvalidierungen oder benutzerdefinierte Menüleisten. Sie können Arbeitsabläufe deutlich vereinfachen und sind insbesondere dann sinnvoll, wenn wiederkehrende Aufgaben standardisiert werden sollen. [@kowalski_excel_addin_2024]

Allerdings sprechen mehrere Punkte dagegen, diese Lösung tatsächlich umzusetzen:

**1. Zugriff auf Originaldaten fehlt**  
    Der Zugriff auf die originale Inventarliste ist nicht möglich. Ein Add-in könnte daher nur auf der Kopie entwickelt werden, die nicht den tatsächlichen Datenbestand widerspiegelt. Somit wäre die Lösung nicht einsatzfähig für die echte Inventarisierung.
    
**2. Keine Lösung des Kernproblems**  
    Die zentrale Herausforderung der Inventarisierung ist die **Unübersichtlichkeit** großer Datenmengen, das Risiko von Duplikaten und die fehleranfällige Zuordnung von Objekten. Ein Excel-Add-in würde lediglich die vorhandene Liste geringfügig vereinfachen, ändert jedoch nichts an der eigentlichen Problematik.
    
**3. QR-Code-Zuordnung nicht automatisierbar über ein Add-in**  
    Für die geplante Digitalisierung der Inventarliste ist es notwendig, dass jedem Objekt ein eigener QR-Code zugewiesen wird. Dies lässt sich nicht über ein Excel-Add-in automatisch umsetzen. Die QR-Codes müssen in der Excel-Datei selbst generiert und korrekt zugeordnet werden. Ein Add-in würde hier keinen nennenswerten Vorteil bringen, da die Generierung und Zuweisung der Codes weiterhin manuell erfolgen müsste.
    
**4. Optik und Benutzerfreundlichkeit**  
    Ein Add-in kann zwar bestimmte Funktionen automatisieren, verändert jedoch nicht die Übersichtlichkeit oder Gestaltung der Excel-Liste. Die Darstellung bleibt unverändert und es entstehen keine zusätzlichen Hilfen, die das Arbeiten mit vielen Datensätzen erleichtern.

Die Entwicklung einer Excel-Erweiterung würde den Aufwand erhöhen und nur einen geringen Nutzen bringen. Sie greift nicht die Kernprobleme der Inventarisierung an und ist zudem aufgrund fehlender Originaldaten nicht praktisch umsetzbar. 

## Programmieren einer TEAMS-Erweiterung

Die Idee, eine eigene Erweiterung für Microsoft Teams zu entwickeln, klingt auf den ersten Blick attraktiv, da Teams bereits ein etablierter Bestandteil des schulischen und organisatorischen Alltags ist. Dennoch spricht eine Reihe gewichtiger Argumente dagegen, diesen Ansatz für die Umsetzung einer Inventarisierungslösung zu wählen.

Eine Teams-Erweiterung ist stark an die Microsoft-365-Umgebung und speziell an die Teams-Infrastruktur gebunden. Sie bietet keine direkte Möglichkeit, eigene Datenbanken anzubinden oder komplexe externe Datenquellen zuverlässig zu verwalten. Stattdessen müssen sämtliche Daten in der Teams- bzw. Microsoft-Cloud gespeichert oder über Zwischenschritte aus externen Dateien eingebunden werden. Das macht die Lösung nicht nur unflexibel, sondern auch abhängig von bestehenden Teams-Strukturen und der Verfügbarkeit dieser Dienste. [@georg_teams_apps_2023] [@ovacapta_teams_extensions]

Soll beispielsweise ein Inventar mit mehreren hundert Geräten verwaltet werden, müssten die Daten entweder in SharePoint-Listen oder anderen Teams-internen Strukturen hinterlegt werden. Diese sind jedoch nicht für performante, strukturierte Inventardatenbank ausgelegt. Zudem müsste weiterhin auf externe Dateien zurückgegriffen werden, um etwa QR-Code-Zuordnungen oder Geräteinformationen zu verwalten. Das erhöht die Komplexität und die Fehleranfälligkeit erheblich.

Die fehlende direkte Datenbankanbindung verhindert den Aufbau einer robusten, skalierbaren Inventarisierungslösung. Da alle Daten zwangsläufig an die Teams-Umgebung gebunden sind, entsteht eine Abhängigkeit von einem Drittanbieter, der nicht nur die technische Grundlage kontrolliert, sondern auch Änderungen an Schnittstellen oder Richtlinien vornehmen kann. Dies macht die Wartung unsicher und langfristig schwer planbar. Außerdem besteht die Gefahr, dass externe Dateien oder Drittanbieter-Dienste ausfallen, was unmittelbar die Funktionalität der gesamten Lösung beeinträchtigen würde. Insgesamt überwiegen somit die Nachteile deutlich, sodass eine Teams-Erweiterung als technische Basis für eine Inventarisierungslösung nicht in Frage kommt.

## Verwendung von MS Access

Microsoft Access ist eine relationale Datenbankanwendung, die Bestandteil des Microsoft-Office-Pakets ist, welches an das aktuelle System der Schule andocken würde. Sie ermöglicht die Erstellung, Verwaltung und Abfrage von Datenbanken über eine grafische Benutzeroberfläche, ohne dass tiefgehende Programmierkenntnisse erforderlich sind. [@ionos_access_alternativen]

Im schulischen Kontext wird Access häufig zur Verwaltung von Inventar, Lehrmitteln oder Schülerdaten verwendet. Durch seine Integration in das Office-Ökosystem bietet es eine einfache Möglichkeit, Daten mit anderen Anwendungen wie Excel oder Word auszutauschen. Besonders vorteilhaft ist dabei, dass Access auch von nicht-technischem Personal, wie Lehrkräften oder Verwaltungsmitarbeitern, genutzt werden kann.

Trotz dieser Vorteile stößt Access in der Praxis schnell an seine Grenzen. Die Datenverwaltung erfolgt meist lokal auf einem einzelnen Computer, was zu reduzierter Zugänglichkeit und mangelnder Datensynchronisation führt. Zudem ist die Benutzeroberfläche nicht für mobile Endgeräte optimiert, was die Verwendung im Schulalltag – beispielsweise beim Erfassen von Inventargegenständen direkt im Raum – deutlich erschwert.

Darüber hinaus ist die Erweiterbarkeit eingeschränkt. Funktionen wie die automatische Generierung und Zuordnung von QR-Codes, eine Weboberfläche oder der gleichzeitige Zugriff mehrerer Benutzer lassen sich nur mit erheblichem Aufwand realisieren. Aus diesen Gründen eignet sich Microsoft Access zwar als Einstiegslösung für einfache Inventarverwaltungen, erfüllt jedoch nicht die Anforderungen einer modernen, plattformunabhängigen und webbasierten Inventarisierungslösung.

## Anschließen an das aktuelle Ticketsystem

Das aktuelle Ticketsystem der HTL Leoben läuft Open-Source auf https://ticket.htl-leoben.at/, erstellt von MantisBT. Dabei melden sich jeweilige Schüler und Lehrer über das Schulnetzwerk, welches über LDAP läuft, an und können einen Defekt oder einen Einwand reklamieren. [@htl_leoben_ticket]

Die Idee mit dem anschließen an dieses Ticketsystem klingt einfacher gesagt als getan. Zu aller Erst muss gesagt werden, dass wir uns dazu entschieden haben, unsere Invetarisierungslösung nicht als Open-Source veröffentlicht wird. Diese Lösung sollte ausschließlich der HTL Leoben dienen.

Eine weitere Herausforderung ist, an das bestehende LDAP Netzwerk anzuschließen um die Login Funktion zu vereinfachen. Anstatt sich zu Registrieren und neue Benutzer anzulegen, werden die Benutzer des aktuellen Ticketsystems hergenommen und per LDAP an das Login System der Inventarisierung weitergeleitet. So kann zum Beispiel der Lehrer der sich einmal in das Ticketsystem angemeldet hat, sich ohne weiteren Probleme bei der Inventarisierung anmelden.
