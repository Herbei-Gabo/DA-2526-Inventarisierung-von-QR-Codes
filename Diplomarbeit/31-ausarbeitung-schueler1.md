# Teilaufgabe Schüler André Karner
# Programmierung einer Funktionierenden Weblösung
---
# Inhaltsverzeichnis

- [1. Datenauswertung & Datenbankerstellung](#1-datenauswertung--datenbankerstellung)
  - [1.1 Analyse der bereit gestellten Excel Datei der aktuellen Inventarisierung](#11-analyse-der-bereit-gestellten-excel-datei-der-aktuellen-inventarisierung)
  - [1.2 Auswahl der Datenbank](#12-auswahl-der-datenbank)
  - [1.3 Datenbankmodell Erstellung](#13-datenbankmodell-erstellung)
- [Tabellen Schema Abbildung](#tabellen-schema-abbildung)
  - [Excel Datei mit Abbildung der Tabellen `da_inventory_TableSchema.xlsx`](#excel-datei-mit-abbildung-der-tabellen-dainventory_tableschemaxlsx)
  - [T_Account](#t_account)
  - [T_Product](#t_product)
  - [config_DetailInfo](#config_detailinfo)
  - [Abgeleitete Konfigurationstabellen aus `config_DetailInfo`](#abgeleitete-konfigurationstabellen-aus-config_detailinfo)
    - [config_ProductArea (RefType = 1)](#config_productarea-reftype--1)
    - [config_Supplier (RefType = 2)](#config_supplier-reftype--2)
    - [config_Location (RefType = 3)](#config_location-reftype--3)
    - [config_Depositor (RefType = 4)](#config_depositor-reftype--4)
    - [config_ResponsiblePerson (RefType = 5)](#config_responsibleperson-reftype--5)
- [Dokumente](#dokumente)
  - [DA_2025-07-15_HoferText.docx](#da_2025-07-15_hofertextdocx)
  - [HTLGesamtinventar_Monitorbeispiel.xlsx](#htlgesamtinventar_monitorbeispiellxlsx)
  - [da_inventory_TableSchema.xlsx](#da_inventory_tableschemaxlsx)
- [Feature: QR-Code-Generierung für Objekte](#feature-qr-code-generierung-für-objekte)

---
<div id="DatenauswertungUndDatenbankerstellung"></div>

## 1. Datenauswertung & Datenbankerstellung 

<div id="AnalyseExcelDatei"></div>

## 1.1 Analyse der bereit gestellten Excel Datei der aktuellen Inventarisierung

### Datenquelle 
Die Basis der Datenbank entspricht aus dieser uns bereit gestellten Excel Liste `HTLGesamtinventar_Monitorbeispiel.xlsx`

### Erkenntnisse
**1.** In Summe gibt es 5. verschiedene Listen mit Daten, welche später in Dropdown Menüs abgebildet werden:
   + Bereich
   + Lieferant
   + Standort ( Die Standort Bezeichnung wird im Standort selbst mit gespeichert )
   + Einbringer/in
   + Verantwortliche/r`

**2.** Die aufgezählten Spalten können ignoriert werden, da diese Daten Laut der Nachricht von Herr Hofer bereits im Ticketsystem vorhanden sind.

   > "Dazu kommt, dass im Ticketsystem bereits jetzt Rechnungen, Lieferscheine und andere Dokumente zu den Anschaffungen abgelegt werden." 
   `DA_2025-07-15_HoferText.docx`

   + Redat
   + ReNr
   + Stk
   + Betrag inkl. MWSt.
   + Gesamt

Hier muss nur eine Verbindung zwischen Ticketsystem und neuem System erstellt werden, was jedoch kein großes Problem darstellt, 
da man die ID - die aktuell im Ticketsystem benutzt wird - in der neuen Inventarisierung einfach integrieren kann.
-> Lösung dafür: Eine Spalte einfügen, wo diese fortlaufende Nummer eingetragen wird.


### Entscheidungen & Begründungen

- **Entscheidung:** Da es 5. Verschiedene Dropdown Menüs geben wird, wird daraus **EINE** Tabelle gemacht und die verschiedenen Typen werden mit einem REF_TYPE versehen.
Dies würde wiefolgt aussehen.
	- *REF_TYPE 1* = **Area**
	- *REF_TYPE 2* = **Supplier**
	- *REF_TYPE 3* = **Location**
	- *REF_TYPE 4* = **Depositor**
	- *REF_TYPE 5* = **ResponsiblePerson**
- **Begründung:** Dies ermöglicht eine einfache Wartbarkeit sowie Konfiguration der Daten. Die Namensgebung wurde in Englisch gewählt,
 da diese eine universale Lesbarkeit der Datenbank ermöglicht.

### Nächste Schritte
- Auswahl der Datenbank
- Datenbankmodell Erstellung 

---
<div id="AuswahlDatenbank"></div>

## 1.2 Auswahl der Datenbank

### Entscheidungen & Begründungen
- **Entscheidung:** SQL Server Management Studio 2019 (SSMS) wird als SQL-Server benutzt.
  - **Begründung:** Schnelles Verständnis, da man eine klare Dateneinsicht hat und ich persönlich schon sehr viel Zeit  
    mit SSMS verbracht habe und mich daher mit den Features wie:  
    - Views  
    - Funktionen  
    - Stored Procedure  

	sehr gut auskenne, wobei **Stored Procedures** ein wichtiger Bestandteil einer sicheren Anwendung sind **(Schutz vor SQL-Injection).**


### Nächste Schritte
- Datenbankmodell Erstellung 

---

<div id="DatenbankmodellErstellung"></div>

## 1.3 Datenbankmodell Erstellung

### Entscheidungen & Begründungen
- **Entscheidung:** Da es 5. Verschiedene Dropdown Menüs geben wird, wird daraus eine **Config-Tabelle** gemacht und die verschiedenen Typen werden mit einem Ref_Type versehen.
Dies würde wiefolgt aussehen:
	- *Ref_Type 1* = **Area**
	- *Ref_Type 2* = **Supplier**
	- *Ref_Type 3* = **Location**
	- *Ref_Type 4* = **Depositor**
	- *Ref_Type 5* = **ResponsiblePerson**
- **Begründung:** Dies ermöglicht eine einfache Wartbarkeit sowie Konfiguration der Daten und die Namensgebung wurde in Englisch gewählt, da diese eine Universale Lesbarkeit der Datenbank ermöglicht.

# Tabellen Schema Abbildung:

## Excel Datei mit Abbildung der Tabellen `da_inventory_TableSchema.xlsx`

## T_Account

| Feldname                  | Datentyp                       | Beschreibung                              |
|---------------------------|--------------------------------|-------------------------------------------|
| ACCOUNT_ID                | uniqueidentifier ROWGUIDCOL    | [ PRIMARY_KEY + ROW_GUID ]                |
| Convert_ID                | varchar(50) NULL               | ID welche vom Datenimport stammt          |
| Account_Info_CreateFrom   | varchar(100) NULL              | Datum Erstellt am                         |
| Account_Info_CreateDate   | datetime NULL                  | Name des Erstellers                       |
| Account_Username          | varchar(100) NULL              | Account Username                          |
| Account_Password          | varchar(500) NULL              | crypted Account password                  |
| Account_LastLoginDate     | datetime NULL                  | Letztes Login Datum                       |
| Account_CountLogin        | int NULL                       | Anzahl der Logins                         |
| Account_IsReadable        | bit                            | Darf dieser Account Daten lesen?          |
| Account_IsWriteable       | bit                            | Darf dieser Account Daten schreiben?      |

---

## T_Product

| Feldname                    | Datentyp                       | Beschreibung                               |
|-----------------------------|--------------------------------|--------------------------------------------|
| PRODUCT_ID                  | uniqueidentifier ROWGUIDCOL    | [ PRIMARY_KEY + ROW_GUID ]                 |
| Convert_ID                  | varchar(50) NULL               | ID welche vom Datenimport stammt           |
| Product_InfoCreateFrom      | varchar(100) NULL              | Name des Erstellers                        |
| Product_InfoCreateDate      | datetime NULL                  | Datum Erstellt am                          |
| Product_InventarNummer      | varchar(100) NULL              | Fortlaufende Inventarnummer                |
| Product_Name                | varchar(200) NULL              | Individueller Produkt Name                 |
| Product_Purpose             | varchar(300) NULL              | Produkt Zweck                              |
| Product_SerialNumber        | varchar(100) NULL              | Produkt Seriennummer                       |
| Product_Type                | varchar(100) NULL              | Produkt Typ                                |
| Product_WarrantyUntil       | datetime NULL                  | Produkt Garantie bis                       |
| Product_DeInventoryReason   | varchar(500) NULL              | Produkt Entinventarisierungsgrund          |
| Product_DeInventoryDate     | datetime NULL                  | Produkt Entinventarisierungsdatum          |
| Product_Area                | uniqueidentifier NULL          | Produkt Bereich -> IT, MAT etc             |
| Product_Supplier            | uniqueidentifier NULL          | Produkt Lieferant                          |
| Product_Location            | uniqueidentifier NULL          | Produkt Standort (Raum)                    |
| Product_Depositor           | uniqueidentifier NULL          | Produkt Einbringer                         |
| Product_ResponsiblePerson   | uniqueidentifier NULL          | Produkt Verantwortlicher                   |

---

## config_DetailInfo

| Feldname               | Datentyp                       | Beschreibung                    |
|------------------------|--------------------------------|---------------------------------|
| DETAILINFO_ID          | uniqueidentifier ROWGUIDCOL    | [ PRIMARY_KEY + ROW_GUID ]     |
| Convert_ID             | varchar(50) NULL               | ID welche vom Datenimport stammt |
| DetailInfo_CreateDate  | datetime NULL                  | Datum Erstellt am              |
| DetailInfo_RefType     | int NULL                       | Welcher Reftype?               |
| DetailInfo_Name        | varchar(200)                   | Name des RefTypes              |
| DetailInfo_InfoText    | varchar(500)                   | Informationstext               |

---

## Abgeleitete Konfigurationstabellen aus `config_DetailInfo`

Alle untenstehenden Tabellen basieren auf der Basistabelle `config_DetailInfo`. Der jeweilige `DetailInfo_RefType` filtert die Einträge für die unterschiedlichen Kategorien.

## Übersicht: RefTypes

| RefTypes                 | Value |
|--------------------------|-------|
| config_Area              | 1     |
| config_Supplier          | 2     |
| config_Location          | 3     |
| config_Depositor         | 4     |
| config_ResponsiblePerson | 5     |

---

### config_ProductArea (RefType = 1) 
```sql
SELECT
  AREA_ID            			= 	DETAILINFO_ID,
  Area_Bezeichnung   			= 	DetailInfo_Name,
  Area_InfoText      			= 	DetailInfo_InfoText
FROM 
	dbo.config_DetailInfo
WHERE 
	( DetailInfo_RefType = 1 );
```

---

### config_Supplier (RefType = 2) 
```sql
SELECT
  SUPPLIER_ID          			= 	DETAILINFO_ID,
  Supplier_Bezeichnung 			= 	DetailInfo_Name,
  Supplier_InfoText    			= 	DetailInfo_InfoText
FROM 
	dbo.config_DetailInfo
WHERE 
	( DetailInfo_RefType = 2 );
```

---

### config_Location (RefType = 3) 
```sql
SELECT
  LOCATION_ID         			= 	DETAILINFO_ID,
  Location_Name       			= 	DetailInfo_Name,
  Location_InfoText  			= 	DetailInfo_InfoText
FROM 
	dbo.config_DetailInfo
WHERE 
	( DetailInfo_RefType = 3 );
```

---

### config_Depositor (RefType = 4)
```sql
SELECT
  DEPOSITOR_ID        			= 	DETAILINFO_ID,
  Depositor_Name      			= 	DetailInfo_Name,
  Depositor_InfoText  			= 	DetailInfo_InfoText
FROM 
	dbo.config_DetailInfo
WHERE 
	( DetailInfo_RefType = 4 );
```

---

### config_ResponsiblePerson (RefType = 5) 
```sql
SELECT
  RESPONSIBLEPERSON_ID        	= 	DETAILINFO_ID,
  ResponsiblePerson_Name      	= 	DetailInfo_Name,
  ResponsiblePerson_InfoText  	= 	DetailInfo_InfoText
FROM 
	dbo.config_DetailInfo
WHERE 
	(  DetailInfo_RefType = 5 );
```

## Dokumente 

#### **DA_2025-07-15_HoferText.docx**
#### **HTLGesamtinventar_Monitorbeispiel.xlsx**
#### **da_inventory_TableSchema.xlsx**  
---


### VORLAGE --> Features

# Feature: QR-Code-Generierung für Objekte

## Beschreibung
Beim Anlegen eines neuen Objekts wird automatisch ein QR-Code erzeugt, der auf die Objekt-Detailseite verweist. Dieser QR-Code wird im System gespeichert und kann heruntergeladen oder gedruckt werden.

## Technologie
- JavaScript-Bibliothek: `qrcode.js`
- Eingabedaten: Objekt-ID
- Ausgabe: QR-Code im PNG-Format

## Entscheidung
- Die QR-Codes werden clientseitig erzeugt, um Serverlast zu vermeiden.
- PNG wird verwendet, da es verlustfrei druckbar ist.

## Umsetzung
- `generateQRCode(data)` Funktion im Frontend-Modul `qr.js`
- Aufruf in `object-form.js` nach erfolgreichem POST zur Datenbank

## Probleme
- Canvas war zu klein auf mobilen Geräten → dynamische Skalierung eingebaut
- PNG-Download funktionierte nicht in Safari → Workaround mit `toBlob()`-Funktion

## Screenshot
- `screenshots/qr-generator-example.png`

## Getestet
- Chrome, Firefox, Safari
- QR-Code führt korrekt zur jeweiligen Objekt-URL

## Verknüpfte Komponenten
- `object-form.js`
- `qr.js`
- Backend-Router für Objektdaten (`/api/objects`)

