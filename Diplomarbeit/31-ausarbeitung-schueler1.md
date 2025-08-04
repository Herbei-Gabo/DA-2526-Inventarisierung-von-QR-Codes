# Teilaufgabe André Karner
---
### Entwicklung und Programmierung einer funktionierenden Webbasierenden Inventarisierungslösung.
##### ????? Inhaltsverzeichnis Links funktionieren in Github nicht, Lokal schon ( wtf ) ?????
---
# Inhaltsverzeichnis

- [1. Datenauswertung & Datenbankerstellung](#1-datenauswertung--datenbankerstellung)
  - [1.1 Analyse der bereit gestellten Excel Datei der aktuellen Inventarisierung](#11-analyse-der-bereit-gestellten-excel-datei-der-aktuellen-inventarisierung)
  - [1.2 Auswahl der Datenbank](#12-auswahl-der-datenbank)
  - [1.3 Datenbankmodell Erstellung](#13-datenbankmodell-erstellung)
    - [1.3.1 Tabellen Schema Abbildung](#tabellen-schema-abbildung)
    - [1.3.2 T_Account](#t_account)
    - [1.3.3 T_Product](#t_product)
    - [1.3.4 Fremdschlüssel Zusammenfassung](#fremdschlüssel-zusammenfassung)
    - [1.3.5 config_DetailInfo](#config_detailinfo)
    - [1.3.6 Abgeleitete Konfigurationstabellen](#abgeleitete-konfigurationstabellen)
      - [config_ProductArea (RefType = 1)](#config_productarea-reftype--1)
      - [config_Supplier (RefType = 2)](#config_supplier-reftype--2)
      - [config_Location (RefType = 3)](#config_location-reftype--3)
      - [config_Depositor (RefType = 4)](#config_depositor-reftype--4)
      - [config_ResponsiblePerson (RefType = 5)](#config_responsibleperson-reftype--5)
- [2. Erstellung von Testdaten](#2-erstellung-von-testdaten)
  - [2.1 Testdaten in T_Account](#21-testdaten-in-t_account)
  - [2.2 Testdaten in config_DetailInfo](#22-testdaten-in-config_detailinfo)
  - [2.3 Testdaten in T_Product](#23-testdaten-in-t_product)
- [Dokumente](#dokumente)
  - [DA_2025-07-15_HoferText.docx](#da_2025-07-15_hofertextdocx)
  - [HTLGesamtinventar_Monitorbeispiel.xlsx](#htlgesamtinventar_monitorbeispielxlsx)
  - [da_inventory_TableSchema.xlsx](#da_inventory_tableschemaxlsx)
- [Quellenverzeichnis](#quellenverzeichnis)


---
## 1. Datenauswertung & Datenbankerstellung 

## 1.1 Analyse der bereit gestellten Excel Datei der aktuellen Inventarisierung

### Datenquelle
Die Basis der Datenbank entspricht aus dieser uns bereit gestellten Excel Liste [`HTLGesamtinventar_Monitorbeispiel.xlsx`](#htlgesamtinventar_monitorbeispielxlsx)

### Erkenntnisse
**1.** In Summe gibt es 5. verschiedene Listen mit Daten, welche später in Dropdown Menüs abgebildet werden:
   + Bereich
   + Lieferant
   + Standort ( Die Standort Bezeichnung wird im Standort selbst mit gespeichert )
   + Einbringer/in
   + Verantwortliche/r`

**2.** Die aufgezählten Spalten können ignoriert werden, da diese Daten Laut der Nachricht von Herr Hofer bereits im Ticketsystem vorhanden sind.

   > "Dazu kommt, dass im Ticketsystem bereits jetzt Rechnungen, Lieferscheine und andere Dokumente zu den Anschaffungen abgelegt werden." 
   [`DA_2025-07-15_HoferText.docx`](#da_2025-07-15_hofertextdocx)

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

---

## 1.2 Auswahl der Datenbank

### Entscheidungen & Begründungen
- **Entscheidung:** SQL Server Management Studio 2019 (SSMS) wird als SQL-Server benutzt.
  - **Begründung:** Schnelles Verständnis, da man eine klare Dateneinsicht hat und ich persönlich schon sehr viel Zeit  
    mit SSMS verbracht habe und mich daher mit den Features wie:  
    - Views  
    - Funktionen  
    - Stored Procedure  

	sehr gut auskenne, wobei **Stored Procedures** ein wichtiger Bestandteil einer sicheren Anwendung sind **(Schutz vor SQL-Injection).**

---

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

## Tabellen Schema Abbildung:

- Alle hier abgebildeten Tabellen sind in [`da_inventory_TableSchema.xlsx`](#da_inventory_tableschemaxlsx) abgebildet

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

## Fremdschlüssel Zusammenfassung

```text
T_Product.Product_Area              	→ 	config_DetailInfo.DETAILINFO_ID WHERE DetailInfo_RefType = 1
T_Product.Product_Supplier          	→ 	config_DetailInfo.DETAILINFO_ID WHERE DetailInfo_RefType = 2
T_Product.Product_Location          	→ 	config_DetailInfo.DETAILINFO_ID WHERE DetailInfo_RefType = 3
T_Product.Product_Depositor         	→ 	config_DetailInfo.DETAILINFO_ID WHERE DetailInfo_RefType = 4
T_Product.Product_ResponsiblePerson 	→ 	config_DetailInfo.DETAILINFO_ID WHERE DetailInfo_RefType = 5
```

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

## Abgeleitete Konfigurationstabellen

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

---

## 2. Erstellung von Testdaten

### 2.1 Testdaten in T_Account
| Feldname               | Wert                                |
|-----------------------|-------------------------------------|
| ACCOUNT_ID            | 208E2ADC-666A-4AFE-AA5B-06495B2CFD7D |
| Convert_ID            | NULL                                |
| Account_Info_CreateFrom | Andre Karner                       |
| Account_Info_CreateDate | 2025-08-04 13:01:19.703           |
| Account_Username      | a_Karner                           |
| Account_Password      | dA2708!2025                       |
| Account_LastLoginDate | NULL                              |
| Account_CountLogin    | 0                                 |
| Account_IsReadable    | 1                                 |
| Account_IsWriteable   | 1                                 |

### 2.2 Testdaten in config_Detailinfo

#### Testdaten RefType 1 – Area

| Feldname              | Wert                                  |
|-----------------------|---------------------------------------|
| DETAILINFO_ID         | B2579A68-F084-4D94-B736-D3377147CFE1 |
| Convert_ID           | NULL                                  |
| DetailInfo_CreateFrom | Andre Karner                          |
| DetailInfo_CreateDate | 2025-08-04 15:37:24.480              |
| DetailInfo_RefType    | 1                                     |
| DetailInfo_Name       | Area - IT                            |
| DetailInfo_InfoText   | -                                    |

#### Testdaten RefType 2 – Supplier

| Feldname              | Wert                                  |
|-----------------------|---------------------------------------|
| DETAILINFO_ID         | 9B62BCF0-27CF-433E-9E53-B93ED0B461F0 |
| Convert_ID           | NULL                                  |
| DetailInfo_CreateFrom | Andre Karner                          |
| DetailInfo_CreateDate | 2025-08-04 15:37:24.480              |
| DetailInfo_RefType    | 2                                     |
| DetailInfo_Name       | Supplier - omegacom                  |
| DetailInfo_InfoText   | -                                    |

#### Testdaten RefType 3 – Location

| Feldname              | Wert                                  |
|-----------------------|---------------------------------------|
| DETAILINFO_ID         | 81236300-89B7-449A-8F78-005656132BF6 |
| Convert_ID           | NULL                                  |
| DetailInfo_CreateFrom | Andre Karner                          |
| DetailInfo_CreateDate | 2025-08-04 15:37:24.480              |
| DetailInfo_RefType    | 3                                     |
| DetailInfo_Name       | Location - K12                      |
| DetailInfo_InfoText   | IT Labor                            |

#### Testdaten RefType 4 – Depositor

| Feldname              | Wert                                  |
|-----------------------|---------------------------------------|
| DETAILINFO_ID         | 010501D0-6840-4033-8D12-F4E646A428F6 |
| Convert_ID           | NULL                                  |
| DetailInfo_CreateFrom | Andre Karner                          |
| DetailInfo_CreateDate | 2025-08-04 15:37:24.480              |
| DetailInfo_RefType    | 4                                     |
| DetailInfo_Name       | Depositor - Andre Karner            |
| DetailInfo_InfoText   | -                                    |

#### Testdaten RefType 5 – Responsible Person

| Feldname              | Wert                                  |
|-----------------------|---------------------------------------|
| DETAILINFO_ID         | 5A6E16FB-C889-48D4-AE8C-B0BCE46E62A3 |
| Convert_ID           | NULL                                  |
| DetailInfo_CreateFrom | Andre Karner                          |
| DetailInfo_CreateDate | 2025-08-04 15:37:24.483              |
| DetailInfo_RefType    | 5                                     |
| DetailInfo_Name       | Respo Person - Andre Karner          |
| DetailInfo_InfoText   | -                                    |

---

### 2.3 Testdaten in T_Product

#### Problem
Aus aktuellem Stand **( 04.08.2025 )** besteht keinerlei Möglichkeit eine korrekte Inventarisierungsnummer zu generieren, da es zwei unbekannte Variablen gibt `Anlagenkennzahl & Unterkatogriezahl`
Herr Prof. Leitner wurde daher eine Nachricht gesendet, um diese Listen zu bekommen.
#### Aktuelle Lösung
Bei den Testdaten werden die genannten Inventarisierungsnummern `408-09-01-14 | 408-09-04-14 | 408-09-13-14` verwendet und fiktive Zahlen erstellt.
Wenn diese Listen eintreffen werden darausgehend natürlich Datentabellen erstellt, um die korrekten Inventarisierungsnummern zu erstellen.

### GUID-Bezeichnungen (Referenzen)

```sql
------------------------------------------------------------------------------
Product_Area:
[ Area - IT ] 				= 'B2579A68-F084-4D94-B736-D3377147CFE1'
------------------------------------------------------------------------------
Product_Supplier: 
[ Supplier - omegacom  ]		= '9B62BCF0-27CF-433E-9E53-B93ED0B461F0'
------------------------------------------------------------------------------
Product_Location:  
[ Location - K12 (IT Labor) ]		= '81236300-89B7-449A-8F78-005656132BF6'
------------------------------------------------------------------------------
Product_Depositor:  
[ Depositor - Andre Karner ] 		= '010501D0-6840-4033-8D12-F4E646A428F6'  
------------------------------------------------------------------------------
Product_ResponsiblePerson:
[ Respo Person - Andre Karner ] 	= '5A6E16FB-C889-48D4-AE8C-B0BCE46E62A3'  
------------------------------------------------------------------------------
```

#### Testdaten
| Feldname                  | TestDaten1                                     | TestDaten2                                     |
|---------------------------|------------------------------------------------|------------------------------------------------|
| PRODUCT_ID                | 73CC0F72-4357-42B8-BE22-673E45E0747E           | F3AE43F6-7C86-4207-855C-7CD3A80D1998           |
| Convert_ID                | NULL                                           | NULL                                           |
| Product_InfoCreateFrom    | Andre Karner                                   | Andre Karner                                   |
| Product_InfoCreateDate    | 2025-08-04 16:13:13.143                       | 2025-08-04 16:12:47.467                       |
| Product_InventarNummer    | 408-09-04-14                                  | 408-09-01-14                                  |
| Product_Name             | Monitor AOC E2460PDA 24" inkl. 5 Jahre Vor-Ort-Garantie | Monitor AOC E2460PDA 24" inkl. 5 Jahre Vor-Ort-Garantie |
| Product_Purpose          | NULL                                           | NULL                                           |
| Product_SerialNumber     | NULL                                           | NULL                                           |
| Product_Type             | E2460PDA                                       | E2460PDA                                       |
| Product_WarrantyUntil    | 2019-01-11 00:00:00.000                       | 2019-01-11 00:00:00.000                       |
| Product_DeInventoryReason| NULL                                           | NULL                                           |
| Product_DeInventoryDate  | NULL                                           | NULL                                           |
| Product_Area             | B2579A68-F084-4D94-B736-D3377147CFE1           | B2579A68-F084-4D94-B736-D3377147CFE1           |
| Product_Supplier         | 9B62BCF0-27CF-433E-9E53-B93ED0B461F0           | 9B62BCF0-27CF-433E-9E53-B93ED0B461F0           |
| Product_Location         | 81236300-89B7-449A-8F78-005656132BF6           | 81236300-89B7-449A-8F78-005656132BF6           |
| Product_Depositor        | 010501D0-6840-4033-8D12-F4E646A428F6           | 010501D0-6840-4033-8D12-F4E646A428F6           |
| Product_ResponsiblePerson| 5A6E16FB-C889-48D4-AE8C-B0BCE46E62A3           | 5A6E16FB-C889-48D4-AE8C-B0BCE46E62A3           |

---

## Dokumente

### HTLGesamtinventar_Monitorbeispiel.xlsx

Beispielhafte Excel-Datei der aktuellen Inventarliste mit realen Daten und Struktur für die spätere Datenübernahme.

### DA_2025-07-15_HoferText.docx

Kurzes internes Schreiben von Prof. Hofer mit wichtigen Informationen.

### da_inventory_TableSchema.xlsx

Darstellung aller geplanten Tabellen, Beziehungen und Datentypen der SQL-Datenbank in Excel-Form.

---

## Quellenverzeichnis:

#### [1. Wie Dokumentiert man richtig?](https://www.diplomarbeiten-bbs.at/erstellung/erstellung-allgemeine-infos)
#### [2. Basic Markdown Syntax](https://www.markdownguide.org/basic-syntax/)
#### [3. How to link to part of the same document in Markdown?](https://stackoverflow.com/questions/2822089/how-to-link-to-part-of-the-same-document-in-markdown)
