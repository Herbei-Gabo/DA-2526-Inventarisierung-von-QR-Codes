
# Projekthandbuch – Diplomarbeit

\textauthor{Dietmair}

## Inventarisierung mit QR-Codes
**Stand:** 08. Jänner 2026



### Projektübersicht
**Thema:** Entwicklung einer webbasierten Inventarisierungslösung mit QR-Codes zur Verwaltung schulischer IT-Ausstattung

**Team:**
- **Dietmair Stephan** – Projektmanagement & Organisation
- **Herbei Gabriel** – Analyse, Konzeption & Qualitätssicherung 
- **Karner André** – Softwareentwicklung & technische Umsetzung 

**Betreuer:** Dipl.-Wirt.-Ing. (FH) Leitner Christoph, BEd 
**Zeitraum:** Juni 2025 – März 2026
**Schule:** HTL Leoben



### Zielsetzung
Die Zielsetzung beschreibt das allgemeine Ziel und die Motivation hinter der Diplomarbeit. Dabei werden folgende Themen adressiert:

 **Aktueller Stand:**  
  An der Schule wird die IT-Ausstattung (PCs, Monitore, Beamer etc.) derzeit manuell in einer Excel-Liste verwaltet. Diese Methode ist zeitaufwendig, unübersichtlich und fehleranfällig.

 **Motivation:**  
  Der Wunsch besteht darin, den Inventarisierungsprozess zu digitalisieren und zu vereinfachen. Durch den Einsatz von QR-Codes soll die Verwaltung moderner, schneller und mobil zugänglich werden.

 **Was möchten wir erreichen?**  
   Entwicklung einer webbasierten Inventarisierungslösung mit QR-Code-Integration  
   Vereinfachung der Erfassung, Verwaltung und Nachverfolgung von Geräten  
   Zugriff über Smartphones/Tablets ohne manuelle Eingabe  
   Nutzung vorhandener Schulressourcen ohne Zusatzkosten  
   Stärkung digitaler Kompetenzen innerhalb der Schule  

 **Was möchten wir nicht erreichen (Nicht-Ziele)?**  
   Keine vollständige Integration in externe ERP- oder Ticketsysteme  
   Kein Austausch der bestehenden Schulserver-Struktur  
   Kein Fokus auf kaufmännische Warenwirtschaft  

 **Was ändert sich durch die Arbeit?**  
   Der manuelle Aufwand entfällt weitgehend  
   Geräte können schnell und mobil identifiziert werden  
   Die Verwaltung wird übersichtlicher und weniger fehleranfällig  
   Das Schulpersonal kann eigenständig Inventar anpassen oder erfassen  



### Projektorganisation
**Kommunikation:**  
 Microsoft Teams (Austausch, Statusupdates)    
 Whatsapp Gruppe (schneller Austausch)    
 GitHub (Code & Dokumentenverwaltung)  
 Persönliche Treffen nach Bedarf (sporadisch, bei Projektfortschritten oder Problemen)  

**Dateiablage:**  
GitHub-Repository: `DA-2526-Inventarisierung-von-QR-Codes`  

**Teammeetings:**  
 Treffen erfolgen **nach Bedarf**, meist bei Abschluss eines Projektabschnitts  
 Notizen und Entscheidungen werden im Projekthandbuch dokumentiert  



### Zeitplan (aktualisiert – bis Ende Jänner 2026)

| Zeitraum | Aufgabe / Meilenstein | Verantwortlich | Status |
|-----------|----------------------|----------------|--------|
| **Juli 2025** | Projektstart, Themenfindung, Rollenverteilung | Team | abgeschlossen |
| **Ende Juli 2025** | Einrichtung GitHub-Repository & Basisstruktur | Gabriel | abgeschlossen |
| **Anfang August 2025** | Analyse der Excel-Inventarliste, Planung Datenbank | André | abgeschlossen |
| **Mitte August 2025** | Erstellung Datenbankschema & Testdaten | André | abgeschlossen |
| **Ende August 2025** | Theoretische Grundlagen & Marktanalyse (QR, Alternativen) | Gabriel | abgeschlossen |
| **September 2025** | Projektorganisation, Projekthandbuch-Erstellung, Abstimmung Frontend | Stephan | abgeschlossen |
| **14. Oktober 2025** | Planung der Frontend-Entwicklung (Layout & Architektur) | André | abgeschlossen |
| **25. Oktober – 2. November 2025 (Herbstferien)** | **Frontend-Entwicklung (UI, Seitenaufbau)** | André | abgeschlossen |
| **25. Oktober – 2. November 2025 (Herbstferien)** | **Evaluierung Technologiealternativen (Frameworks, Hosting, QR-Tools)** | Stephan | abgeschlossen  |
| **November 2025 (KW 45–48)** | Implementierung QR-Code-Funktion und Integration ins System | Gabriel + André | abgeschlossen |
| **Ende November 2025** | Erste Systemtests (mobile Nutzung, Datenbankzugriff) | Team | abgeschlossen |
| **Dezember 2025 (KW 49–52)** | Dokumentationsabschluss & Vorbereitung der Abgabe | Team (Leitung: Stephan) | offen |
| **9 Jänner 2026** | Gemeinsane Erstversion für Feedback abgegen | Team | offen |
| **Ende Jänner 2026** | Feinschliff von Suchfunktion, Admin-Menü, Druckfunktion sowie Responsive | Gabriel + André | offen



### Aktueller Projektstatus (Stand 08.01.2026)
 Datenbank- und Backend-Struktur fertiggestellt  
 Theoretische Grundlagen & Marktanalyse abgeschlossen  
 Projekthandbuch in Bearbeitung  
 Frontend-Phase & Evaluierung größtenteils abgeschlossen   
 Dokumentation in Bearbeitung    
 Finale Tests in Vorbereitung 





## To-do-Liste (nächste Schritte)

| Aufgabe | Verantwortlich | Fällig bis | Status |
|:--------|:---------------|:-----------|:-------|
| Dokumentationsabschluss & Abgabevorbereitung | Stephan | 31.12.2025 | geplant |
| Überarbeitung Admin-Menü (Struktur & Bedienbarkeit) | André | 20.01.2026 | geplant |
| Implementierung & Optimierung Suchfunktion | André & Gabriel | 31.01.2026 | offen |
| Überarbeitung QR-Code-Druckfunktion | Gabriel | 25.01.2026 | offen |
| Feinschliff Responsive Design (mobile Endgeräte) | André | 25.01.2026 | geplant |
| Erweiterte Funktionstests (Suche, QR-Druck, Mobile) | Team | 05.02.2026 | offen |



Hinweis: Abgeschlossene Aufgaben werden in Kapitel 7 (Aufgabenhistorie) dokumentiert.


## Aufgabenhistorie

| Aufgabe / Meilenstein | Verantwortlich | Zeitraum | Ergebnis |
|----------------------|----------------|----------|----------|
| Projektstart, Themenfindung & Rollenverteilung | Team | Juli 2025 | Projektstruktur festgelegt |
| Einrichtung GitHub-Repository & Basisstruktur | Gabriel | Ende Juli 2025 | Zentrale Code- & Dokuablage eingerichtet |
| Analyse der Excel-Inventarliste | André | Anfang August 2025 | Anforderungen für DB definiert |
| Planung der Datenbankstruktur | André | Anfang August 2025 | Grundlage für Schema-Erstellung |
| Erstellung Datenbankschema & Testdaten | André | Mitte August 2025 | Funktionsfähige DB-Struktur |
| Theoretische Grundlagen & Marktanalyse (QR) | Gabriel | Ende August 2025 | Vergleich & Entscheidungsbasis erstellt |
| Projektorganisation & Projekthandbuch-Erstellung | Stephan | September 2025 | PM-Struktur dokumentiert |
| Abstimmung Frontend (Konzept & Aufbau) | Stephan & André | September 2025 | Gemeinsames Verständnis hergestellt |
| Planung Frontend-Architektur & Layout | André | 14.10.2025 | Frontend-Phase vorbereitet |
| Frontend-Entwicklung (UI, Seitenaufbau) | André | 25.10.–02.11.2025 | Erste lauffähige UI-Version |
| Abschluss Projekthandbuch v0.3 | Stephan | bis 18.10.2025 | Projekthandbuch konsolidiert |
| Evaluierung QR- & Frontend-Technologien | Stephan | 25.10.–02.11.2025 | Entscheidungsgrundlage erstellt |
| Auswahl QR-Code-Bibliothek & Testintegration | Gabriel & André | bis 10.11.2025 | Bibliothek festgelegt und getestet |
| Implementierung QR-Code-Funktion | Gabriel & André | bis 20.11.2025 | QR-Scan und Gerätezuordnung umgesetzt |
| Erste Systemtests (QR-Scan, mobile Nutzung) | Team | bis 25.11.2025 | Funktionalität erfolgreich geprüft |




### Risiken & Herausforderungen
 Abhängigkeit von der Schul-IT-Infrastruktur (Serverrechte, Zugriff)  
 Zeitliche Belastung durch parallelen Schulunterricht  
 QR-Code-Leserkompatibilität auf unterschiedlichen Geräten  
 Fehlende Original-Listen für korrekte Inventarnummern  



### Dokumentenübersicht
| Dokument | Beschreibung | Speicherort |
|-----------|---------------|--------------|
| `DA_Hauptdokument.docx` | Hauptteil der Diplomarbeit | GitHub / Dokumentation |
| `projekthandbuch_v0.3.docx` | Projekthandbuch, Stand 14.10.2025 | GitHub / docs |
| `HTLGesamtinventar_Monitorbeispiel.xlsx` | Basis-Excel der bisherigen Inventarisierung | GitHub / data |
| `da_inventory_TableSchema.xlsx` | Datenbankschema & Tabellenbeziehungen | GitHub / data |



### Zusammenfassung
Im Projektzeitraum von Juni 2025 bis Dezember 2025 wurden Analyse, Konzeption, technische Umsetzung sowie erste Tests erfolgreich durchgeführt. Das System ermöglicht eine schnelle Inventarisierung und Verwaltung von Geräten über mobile Endgeräte, reduziert den administrativen Aufwand und verbessert die Übersichtlichkeit der Inventardaten.
Der aktuelle Fokus liegt auf dem Abschluss der Dokumentation, dem Feinschliff einzelner Funktionen (Suche, Admin-Menü, QR-Druck) sowie auf finalen Tests zur Vorbereitung der Abgabe.



### Projektlog & Entscheidungsdokumentation




