
# Teilaufgabe André Karner

## Verwendete Technologien

Für die Entwicklung der webbasierten Inventarisierungslösung kamen verschiedene, aufeinander abgestimmte Technologien zum Einsatz.  
Diese bilden das Fundament für eine moderne, stabile und benutzerfreundliche Anwendung, die sowohl auf Desktop- als auch auf mobilen Geräten zuverlässig funktioniert.  

Die Auswahl der Technologien erfolgte auf Basis folgender Kriterien:  

- **Kompatibilität und Standardisierung:** Alle eingesetzten Technologien entsprechen gängigen Webstandards und werden von aktuellen Browsern sowie Betriebssystemen unterstützt.  
- **Trennung von Struktur, Darstellung und Logik:** Durch die konsequente Trennung von HTML, CSS, JavaScript und serverseitiger Logik wird eine klare und wartbare Softwarearchitektur gewährleistet.  
- **Effizienz und Benutzerfreundlichkeit:** Die Kombination aus clientseitigen und serverseitigen Technologien ermöglicht schnelle Ladezeiten, interaktive Oberflächen und eine intuitive Bedienung.  
- **Zukunftssicherheit:** Die eingesetzten Technologien sind weit verbreitet, gut dokumentiert und bieten eine langfristige Perspektive für Wartung und Erweiterung.  

Im Folgenden werden die einzelnen Technologien, ihre Einsatzgebiete, Entscheidungsgründe und Vorteile im Detail erläutert. Dies umfasst sowohl die **Frontend-Technologien** (HTML, CSS, JavaScript, AJAX) zur Gestaltung der Benutzeroberfläche als auch die **Backend-Technologien** (PHP, SQL Server, IIS) für Datenverarbeitung, Speicherung und Zugriffskontrolle. Abschließend wird das eingesetzte Framework vorgestellt, das die Entwicklung strukturierter und effizienter gestaltet.

### HyperText Markup Language (HTML)

#### Erläuterung  
HTML (HyperText Markup Language) stellt die strukturelle Grundlage der webbasierten Inventarisierungslösung dar. Es wird zur semantischen Beschreibung und klaren Gliederung sämtlicher Inhalte der Benutzeroberfläche eingesetzt. Dazu zählen unter anderem Eingabeformulare, Tabellen zur Darstellung von Inventardaten, Navigationsbereiche sowie verschiedene Bedienelemente. Durch die Verwendung semantischer HTML-Elemente wird sowohl die Lesbarkeit des Codes als auch die Zugänglichkeit der Anwendung verbessert.[@mdn_html]

#### Entscheidungsgrundlage  
HTML ist der international anerkannte Standard zur Strukturierung von Webinhalten und wird von allen gängigen Webbrowsern vollständig unterstützt. Aufgrund seiner Stabilität, langfristigen Zukunftssicherheit sowie der nahtlosen Kombinierbarkeit mit CSS und JavaScript eignet sich HTML besonders gut für die Entwicklung einer webbasierten Anwendung im schulischen Umfeld.[@mdn_html]

#### Vorteile  
- Plattform- und browserunabhängig  
- Klare und semantische Strukturierung von Inhalten  
- Hohe Wartbarkeit und Erweiterbarkeit des Codes  
- Standardisierte und bewährte Webtechnologie[@mdn_html]



### Cascading Style Sheets (CSS)

#### Erläuterung  
Cascading Style Sheets (CSS) werden zur visuellen Gestaltung der Webanwendung verwendet. Mithilfe von CSS werden Layout, Farbgestaltung, Schriftarten, Abstände sowie responsive Anpassungen definiert. Dadurch entsteht ein übersichtliches, modernes und benutzerfreundliches Erscheinungsbild der Inventarisierungsoberfläche, das die Bedienbarkeit wesentlich unterstützt.[@mdn_css]

#### Entscheidungsgrundlage  
Durch die konsequente Trennung von Struktur (HTML) und Darstellung (CSS) wird eine saubere und übersichtliche Softwarearchitektur realisiert. CSS ist ein etablierter Webstandard und bietet umfangreiche Möglichkeiten zur Gestaltung responsiver Benutzeroberflächen, die auf unterschiedlichen Endgeräten korrekt dargestellt werden.[@mdn_css]

#### Vorteile  
- Klare Trennung von Inhalt und Darstellung  
- Einheitliches Design über alle Seiten hinweg  
- Unterstützung für responsive und adaptive Layouts  
- Verbesserung der Benutzerfreundlichkeit und Übersichtlichkeit[@mdn_css]  


### Hypertext Preprocessor (PHP)

#### Erläuterung  
PHP ist eine serverseitige Skriptsprache und bildet gemeinsam mit der Datenbank das Backend der Inventarisierungslösung. Sie wird zur Verarbeitung von Benutzereingaben, zur Umsetzung der Geschäftslogik sowie zur Kommunikation mit der Datenbank eingesetzt. Darüber hinaus kommt PHP für serverseitige Prozesse wie die Generierung von QR-Codes und die Zugriffskontrolle zum Einsatz.[@php_manual]

#### Entscheidungsgrundlage  
PHP ist besonders für webbasierte Anwendungen geeignet und wird seit vielen Jahren erfolgreich eingesetzt. Durch die breite Verfügbarkeit, die umfangreiche Dokumentation sowie die einfache Wartbarkeit ist PHP eine zuverlässige Wahl für die Umsetzung der vorliegenden Aufgabenstellung.[@php_manual]

#### Vorteile  
- Serverseitige Verarbeitung sensibler Daten  
- Gute Integration mit relationalen Datenbanksystemen  
- Weit verbreitet und umfangreich dokumentiert  
- Geeignet für wartungsfreundliche und skalierbare Webanwendungen[@php_manual]


### JavaScript (JS)

#### Erläuterung  
JavaScript wird clientseitig verwendet, um die Benutzeroberfläche interaktiv zu gestalten. Dazu zählen dynamische Formularvalidierungen, Benutzerinteraktionen sowie die Steuerung von Abläufen, die ohne vollständige Seitenneuladungen auskommen. Dadurch wird die Reaktionsfähigkeit der Anwendung deutlich erhöht.[@mdn_javascript]

#### Entscheidungsgrundlage  
JavaScript ist die Standardsprache für clientseitige Webentwicklung und wird von allen modernen Browsern unterstützt. Der gezielte Einsatz von JavaScript ermöglicht eine spürbare Verbesserung der Benutzererfahrung und trägt zu einer intuitiven Bedienung der Anwendung bei.[@mdn_javascript]

#### Vorteile  
- Hohe Interaktivität der Benutzeroberfläche  
- Verbesserte Benutzererfahrung und Reaktionsgeschwindigkeit  
- Direkte und nahtlose Integration mit HTML und CSS[@mdn_javascript]  


### Asynchronous JavaScript and XML (AJAX)

#### Erläuterung  
AJAX ermöglicht eine asynchrone Kommunikation zwischen Client und Server. Dadurch können Daten, wie Inventareinträge, Suchergebnisse oder Filteroptionen, im Hintergrund geladen oder aktualisiert werden, ohne dass die gesamte Webseite neu geladen werden muss.[@mdn_ajax]

#### Entscheidungsgrundlage  
Für eine moderne Inventarisierungslösung ist eine schnelle und reaktionsfähige Benutzeroberfläche essenziell. Der Einsatz von AJAX unterstützt dieses Ziel maßgeblich und trägt zur Effizienz sowie zur positiven Nutzererfahrung der Anwendung bei.[@mdn_ajax]

#### Vorteile  
- Keine vollständigen Seitenneuladungen notwendig  
- Schnellere Reaktionszeiten der Anwendung  
- Reduzierte Server- und Netzwerkbelastung  
- Deutlich erhöhte Benutzerfreundlichkeit[@mdn_ajax]  


### SQL Server Management Studio (SSMS)

#### Erläuterung  
Das SQL Server Management Studio (SSMS) dient zur Verwaltung und Pflege der relationalen Datenbank der Anwendung. Es wird zur Erstellung und Anpassung von Tabellen, zur Ausführung von Abfragen sowie zur Verwaltung und Analyse der gespeicherten Inventardaten eingesetzt.[@microsoft_ssms]

#### Entscheidungsgrundlage  
SSMS ist ein etabliertes Administrationswerkzeug für Microsoft SQL Server. Die Nutzung ermöglicht eine strukturierte, zuverlässige und nachvollziehbare Verwaltung der Datenbank und unterstützt die Entwicklung sowie Wartung der Anwendung.[@microsoft_ssms]

#### Vorteile  
- Intuitive grafische Benutzeroberfläche  
- Leistungsfähige Verwaltungs- und Abfragefunktionen  
- Hohe Stabilität und Zuverlässigkeit  
- Gute Integration in Microsoft-Systeme[@microsoft_ssms]


### Internet Information Services (IIS)

#### Erläuterung  
Internet Information Services (IIS) wird als Webserver für den Betrieb der Inventarisierungsanwendung eingesetzt. Der Webserver stellt sowohl die PHP-Anwendung als auch statische Inhalte wie HTML-, CSS- und JavaScript-Dateien bereit und ermöglicht den Zugriff über das interne Netzwerk.[@microsoft_iis]

#### Entscheidungsgrundlage  
IIS ist Bestandteil von Windows-Server-Systemen und bietet eine stabile sowie sichere Plattform für den Betrieb von Webanwendungen. Die Kombination aus IIS, PHP und Microsoft SQL Server ermöglicht einen zuverlässigen und wartungsfreundlichen Betrieb der Inventarisierungslösung.[@microsoft_iis]

#### Vorteile  
- Hohe Stabilität und Sicherheit  
- Zentrale Verwaltung der Webanwendung  
- Gute Integration mit Windows-Diensten  
- Geeignet für den produktiven Einsatz im Schulumfeld[@microsoft_iis]


### Benutzte Frameworks

Für die Umsetzung der Anwendung in PHP und JavaScript wurde ein firmeneigenes Framework der **BasicSystems GmbH** verwendet. Dieses Framework ermöglicht eine effiziente und strukturierte Kommunikation mit der Datenbank und vereinfacht gleichzeitig die Implementierung sowie Verwaltung von AJAX-Abläufen. Dadurch werden Entwicklungsprozesse übersichtlicher und besser nachvollziehbar.

Aus rechtlichen Gründen können keine detaillierten technischen Informationen zu diesem Framework bereitgestellt werden. Die HTL Leoben erhält ausschließlich das Nutzungs- und Bearbeitungsrecht der Anwendung. Eine Weitergabe oder Veröffentlichung des Quellcodes an Dritte ist ausdrücklich untersagt.

---

## Datenauswertung & Datenbankerstellung  

### Datenquelle  
Die Grundlage für die Datenbankstruktur bildet eine von der Schule bereitgestellte Excel-Liste mit dem Namen  
[`HTLGesamtinventar_Monitorbeispiel.xlsx`](doc/HTLGesamtinventar_Monitorbeispiel.xlsx).  
Diese Datei diente als initiale Datenbasis und lieferte einen ersten Überblick über den bestehenden Inventarbestand sowie über die verwendeten Datenfelder.

Im weiteren Verlauf der Analyse wurde diese Basis aufgrund einer erweiterten und aktuelleren Excel-Liste  
[`HTLGesamtinventar_Auszug20251120.xlsx`](doc/HTLGesamtinventar_Auszug20251120.xlsx) ergänzt.  
Diese zweite Datei enthielt zusätzliche Datensätze sowie weitere Informationen, die für die vollständige Abbildung des Inventars notwendig waren.

Der geplante Tabellenaufbau aller Datenbanktabellen ist zusätzlich in der Excel-Datei  
[`da_inventory_TableSchema.xlsx`](doc/da_inventory_TableSchema.xlsx) dokumentiert.  
Diese Datei dient als verbindliche Referenz für die Struktur, Benennung und Datentypen der einzelnen Felder.


### Erkenntnisse  
Aus der Analyse der Excel-Listen, einem persönlichen Gespräch mit dem Auftraggeber sowie aus der praktischen Entwicklung der Anwendung ergaben sich mehrere wesentliche Erkenntnisse, die maßgeblich Einfluss auf das Datenbankdesign und die Applikationslogik hatten.


### Inventarnummer – Erkenntnisse  
Die Inventarnummer setzt sich aus **vier numerischen Bestandteilen** zusammen, welche jeweils eine bestimmte Bedeutung haben:

- **Erste Zahl:**  
  Kennzahl aus der Anlagenkennzahlenübersicht, zum Beispiel **408** für Datenverarbeitungsanlagen.  

- **Zweite Zahl:**  
  Unterkategorie, die gemäß einer HTL-internen Liste aufsteigend nummeriert ist, zum Beispiel **09** für Monitore.  

- **Dritte Zahl:**  
  Fortlaufende Nummer des im jeweiligen Kalenderjahr angeschafften Geräts, zum Beispiel **10** für den zehnten Monitor im entsprechenden Jahr.  

- **Vierte Zahl:**  
  Kalenderjahr der Anschaffung, zum Beispiel **2025**.  

Eine vollständige Beispiel-Inventarnummer ergibt somit folgendes Format:  
**408-09-10-25**

Diese Struktur ermöglicht eine eindeutige Identifikation jedes Inventargegenstandes und liefert gleichzeitig wichtige Informationen über Kategorie, Typ und Anschaffungsjahr.



### Anlagenkennzahl – Erkenntnisse  
Zusätzlich zeigte die Analyse der Kennzahlenliste  
[`AnlagenkennzahlübersichtRIMGesamt_09_kompakt.xlsx`](doc/AnlagenkennzahlübersichtRIMGesamt_09_kompakt.xlsx),  
dass eine eigene Tabelle für Anlagenkennzahlen notwendig ist.

Dabei ist besonders zu beachten, dass die Kennzahlen **hierarchisch aufgebaut** sind.  
Es existieren sogenannte **Überkategorien (Parent)**, aus denen mehrere **Unterkategorien (Child)** hervorgehen.

Zur besseren Veranschaulichung ist nachfolgend ein Ausschnitt aus der Excel-Liste dargestellt:

![ Kennzahlen Beispiel.](img/KennzahlenBeispiel.JPG)  

*Abbildung: KennzahlenBeispiel*


### Erklärung des Anlagenkennzahlbeispiels  
In diesem Beispiel stellt **Tische (100)** die übergeordnete Kategorie (Parent) dar, während **PC-Tische (100-01)** eine untergeordnete Kategorie (Child) ist.  

Um diese Hierarchie korrekt in der Datenbank abzubilden, wurde folgende grundlegende Struktur umgesetzt:

| Feldname               | Datentyp                   | Beschreibung                    |
|------------------------|----------------------------|--------------------------------|
| PRODUCTTYPE_ID         | uniqueidentifier ROWGUIDCOL | [PRIMARY_KEY + ROW_GUID]       |
| ProductType_ParentID   | uniqueidentifier           | ID des Elternelements          |

Die Tabelle enthält selbstverständlich weitere Felder, welche an dieser Stelle jedoch bewusst **nicht** detailliert erläutert werden, da sie für das grundlegende Verständnis der Hierarchie nicht erforderlich sind.


### Erklärung der Felder  

| Feldname               | Erklärung                    |
|------------------------|------------------------------|
| PRODUCTTYPE_ID         | ID des Child-Objekts         |
| ProductType_ParentID   | ID des Elternelements        |


### Hinfällige Felder  
Im Zuge der Umstrukturierung und Normalisierung der Datenbank ergab sich, dass einige Spalten aus der ursprünglichen Excel-Liste nicht mehr benötigt werden. Diese Felder sind im neuen System hinfällig:

- **Stk**  
- **Gesamt**  

Diese Informationen lassen sich entweder ableiten oder sind für die digitale Inventarisierung nicht mehr relevant.


### Datenfelder  
Weiters wurde festgestellt, dass bestimmte Datenfelder in der Anwendung nicht als Freitextfelder, sondern als **Dropdown-Menüs** umgesetzt werden sollen, um eine einheitliche Dateneingabe sicherzustellen.

Dies betrifft folgende Felder:

| Daten               |
|--------------------|
| Bereich             |
| Lieferant           |
| Standort            |
| Einbringer/in       |
| Verantwortliche/r   |


### Auswahl der Datenbank  
Als Datenbanksystem wurde **SQL Server Management Studio 2019 (SSMS)** gewählt.

Die Entscheidung fiel unter anderem aufgrund der privaten Vorerfahrung mit SQL Server Management Studio, wodurch das notwendige Fachwissen bereits vorhanden war.  
Zusätzlich bietet **SSMS** zahlreiche leistungsstarke Funktionen, darunter:

- Views  
- Funktionen  
- Stored Procedures  

Insbesondere **Stored Procedures** stellen einen zentralen Bestandteil einer sicheren Anwendung dar, da sie unter anderem einen wirksamen **Schutz vor SQL-Injection-Angriffen** ermöglichen.


### Ticketsystem-Anbindung  
Aus dem Gespräch mit dem Auftraggeber ergab sich zusätzlich die Anforderung, das neue Inventarisierungssystem zukünftig mit einem bereits bestehenden Ticketsystem zu verbinden.  

Die derzeitige Lösung sieht vor, eine zusätzliche Spalte in der Datenbank zu integrieren, welche die jeweilige ID aus dem Ticketsystem speichert.  
Diese Erweiterung dient ausschließlich der Vorbereitung einer späteren Anbindung und ist **nicht Bestandteil dieser Diplomarbeit**.

### LDAP-Anbindung  
Ebenso wurde der Wunsch geäußert, das System künftig an ein LDAP-System anzubinden.  

Auch hierfür ist vorgesehen, eine zusätzliche Spalte zur Speicherung der LDAP-ID zu integrieren.  
Die tatsächliche Umsetzung einer LDAP-Anbindung ist jedoch **nicht Teil der Diplomarbeit**, sondern lediglich konzeptionell vorbereitet.

---

## Datenbankmodell Erstellung

### T_Account

| Feldname                         | Datentyp                         | Beschreibung |
|----------------------------------|----------------------------------|--------------|
| ACCOUNT_ID                       | uniqueidentifier ROWGUIDCOL      | PRIMARY_KEY + ROW_GUID = newsequentialid() |
| Convert_ID                       | varchar(50)                      | DatenImport Reference Number |
| Account_Info_CreateFrom          | varchar(100)                     | Nicht sichtbarer Name des Erstellers |
| Account_Info_CreateDate          | datetime                         | Nicht sichtbares Datum der Erstellung |
| Account_ExternalID               | varchar(200)                     | ID von externen Systemen (LDAP) |
| Account_Shortcut                 | varchar(10)                      | Benutzer-Kurzzeichen |
| Account_DisplayName              | varchar(250)                     | Anzeigename |
| Account_Username                 | varchar(100)                     | Account-Username |
| Account_Password                 | varchar(500)                     | Verschlüsseltes Passwort |
| Account_Email                    | varchar(200)                     | Benutzer-E-Mail |
| Account_CountLogins              | int                              | Anzahl der Logins |
| Account_LastLoginDate            | datetime                         | Letztes Login-Datum |
| Account_LastLoginSource          | varchar(350)                     | Letzte Anmeldequelle |
| Account_IsEnabled                | bit                              | Account aktiv |
| Account_IsLocked                 | bit                              | Account gesperrt |
| Account_LockReason               | varchar(512)                     | Sperrgrund |
| Account_TwoWayAuthEnabled        | bit                              | 2FA aktiviert (derzeit nicht verwendet) |
| Account_TwoWayAuthMode           | varchar(200)                     | 2FA-Art (SMS, E-Mail) |
| Account_TwoWayAuthRecoverKey     | varchar(200)                     | 2FA-Wiederherstellungsschlüssel |
| Account_Settings                 | text                             | Website-Einstellungen (JSON) |
| Account_RightAllowEditConfig     | bit                              | Recht: Konfiguration bearbeiten |
| Account_RightAllowEditProduct    | bit                              | Recht: Produkte bearbeiten |
| Account_RightAllowExport         | bit                              | Recht: Daten exportieren |



### T_Account_History

| Feldname                         | Datentyp                         | Beschreibung |
|----------------------------------|----------------------------------|--------------|
| ACCOUNTHISTORY_ID                | uniqueidentifier ROWGUIDCOL      | PRIMARY_KEY + ROW_GUID = newsequentialid() |
| ACCOUNT_ID                       | uniqueidentifier                 | Referenz auf Account |
| AccountHistory_ActionCodeNum     | int                              | Aktionscode (0=Text, 1=Login, 2=Logout, …) |
| AccountHistory_Date              | datetime                         | Datum |
| AccountHistory_ActionCode        | varchar(100)                     | Aktionsbeschreibung |
| AccountHistory_ShortInfo         | varchar(250)                     | Kurzbeschreibung (optional) |
| AccountHistory_Details           | varchar(2048)                    | Detailinformationen (JSON, optional) |



### T_Product

| Feldname                         | Datentyp                         | Beschreibung |
|----------------------------------|----------------------------------|--------------|
| PRODUCT_ID                       | uniqueidentifier ROWGUIDCOL      | PRIMARY_KEY + ROW_GUID = newsequentialid() |
| Convert_ID                       | varchar(50)                      | DatenImport Reference Number |
| Product_InfoCreateFrom           | varchar(100)                     | Ersteller (automatisch gesetzt) |
| Product_InfoCreateDate           | datetime                         | Erstellungsdatum (automatisch gesetzt) |
| Product_ExternalID               | varchar(200)                     | Externe ID |
| Product_CreateDate               | datetime                         | Erstellungsdatum |
| Product_InvNum                   | varchar(100)                     | Inventarnummer |
| Product_Name                     | varchar(200)                     | Produktname |
| Product_Description              | varchar(300)                     | Produktbeschreibung |
| Product_CostGross                | money                            | Bruttokosten |
| Product_InvoiceDate              | datetime                         | Rechnungsdatum |
| Product_InvoiceNum               | varchar(100)                     | Rechnungsnummer |
| Product_SerialNumber             | varchar(100)                     | Seriennummer |
| Product_WarrantyUntil            | datetime                         | Garantie bis |
| Product_DeInventoryReason        | varchar(500)                     | Entinventarisierungsgrund |
| Product_DeInventoryDate          | datetime                         | Entinventarisierungsdatum |
| Product_TypeID                   | uniqueidentifier                 | Produkttyp |
| Product_AreaID                   | uniqueidentifier                 | Bereich |
| Product_SupplierID               | uniqueidentifier                 | Lieferant |
| Product_LocationID               | uniqueidentifier                 | Standort |
| Product_DepositorAccountID       | uniqueidentifier                 | Einbringer |
| Product_ResponsiblePersonID      | uniqueidentifier                 | Verantwortliche Person |



### config_ProductType

| Feldname                        | Datentyp                         | Beschreibung |
|---------------------------------|----------------------------------|--------------|
| PRODUCTTYPE_ID                  | uniqueidentifier ROWGUIDCOL      | PRIMARY_KEY + ROW_GUID = newsequentialid() |
| Convert_ID                      | varchar(50)                      | DatenImport Reference Number |
| ProductType_ParentID            | uniqueidentifier                 | Elternelement |
| ProductType_CreateFrom          | varchar(100)                     | Ersteller |
| ProductType_CreateDate          | datetime                         | Erstellungsdatum |
| ProductType_Number              | varchar(50)                      | Inventarkennzahl |
| ProductType_Name                | varchar(200)                     | Typenname |
| ProductType_InfoText            | varchar(500)                     | Beschreibung |
| ProductType_LifetimeInYears     | int                              | Gültigkeit in Jahren |
| ProductType_IsSelectable        | bit                              | Auswählbar |



### config_DetailInfo

| Feldname                        | Datentyp                         | Beschreibung |
|---------------------------------|----------------------------------|--------------|
| DETAILINFO_ID                   | uniqueidentifier ROWGUIDCOL      | PRIMARY_KEY + ROW_GUID = newsequentialid() |
| Convert_ID                      | varchar(50)                      | DatenImport Reference Number |
| DetailInfo_InfoCreateFrom       | varchar(100)                     | Ersteller |
| DetailInfo_InfoCreateDate       | datetime                         | Erstellungsdatum |
| DetailInfo_ExternalID           | varchar(200)                     | Externe ID |
| DetailInfo_RefType              | int                              | Referenztyp |
| DetailInfo_Name                 | varchar(200)                     | Name |
| DetailInfo_InfoText             | varchar(500)                     | Beschreibung |



### RefTypes

| Konfiguration            | Wert | Beschreibung |
|--------------------------|------|--------------|
| config_Area              | 1    | Bereich / Verwendung |
| config_Supplier          | 2    | Lieferant |
| config_Location          | 3    | Standort (Raum) |
| config_ResponsiblePerson | 4    | Zuständige Person |
| config_Depositor         | 5    | Einbringer (ACCOUNT_ID) |

**RefType Erklärung:**  
Diese Lösung ermöglicht eine einfache Wartbarkeit sowie eine zentrale Konfiguration der Daten.  
Zusätzlich erlaubt sie die Umsetzung einer einheitlichen Benutzeroberfläche für die Bearbeitung dieser Daten, wobei lediglich der jeweilige **RefType** variiert.

---

## Testdaten  
Die verwendeten Testdaten stammen aus der Excel-Liste  
[`HTLGesamtinventar_Auszug20251120.xlsx`](doc/HTLGesamtinventar_Auszug20251120.xlsx)  
und wurden manuell in die Datenbank übernommen.

### T_Account  
Das verwendete Passwort entspricht **nicht** dem tatsächlichen Passwort.  
Aus Sicherheitsgründen wird dieses hier lediglich als **xxx** angegeben.

```sql
exec sp_Account_Create
(
      @infoCreateFrom = 'Andre Karner',
      @shortcut       = 'ANKA',
      @displayName    = 'Andre Karner',
      @userName       = 'a_Karner',
      @password       = 'xxx',
      @email          = 'andre@basic-systems.at',
      @externalID     = NULL,
      @isEnabled      = 1
);
GO
```

### config_ProductType
Diese Daten stammen aus der Datei [`AnlagenkennzahlübersichtRIMGesamt_09_kompakt.xlsx`](doc/AnlagenkennzahlübersichtRIMGesamt_09_kompakt.xlsx) und wurden mithilfe von SSMS aufbereitet.
Es werden hier bewusst nicht alle Einträge angeführt, da dies den Umfang der Arbeit unverhältnismäßig vergrößern würde.
Nachfolgend sind lediglich einige exemplarische Beispiele dargestellt:

```sql
exec sp_ProductType_Create 'Andre Karner','116-01','Schultafel',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','116-02','Bildwand für Projektionszwecke',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','116-03','Mülltonne, Mülleimer',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','116-04','Matten für Rohstofftechnikum',NULL,NULL

exec sp_ProductType_Create 'Andre Karner','408-01','Computer mit Bildschirm',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','408-02','Diskettenstation',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','408-03','Steckkarten',NULL,NULL
exec sp_ProductType_Create 'Andre Karner','408-04','Drucker',NULL,NULL
```

### config_ProductType RefType 1
```sql
exec sp_ProductArea_Create 'Andre Karner','####','AV',NULL
exec sp_ProductArea_Create 'Andre Karner','####','IT',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Physik',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Medien/Schulwerbung',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Werkstoffprüfung',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Biotech',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Ofenraum',NULL
exec sp_ProductArea_Create 'Andre Karner','####','ET',NULL
exec sp_ProductArea_Create 'Andre Karner','####','MakerLab',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Automatisierung',NULL
exec sp_ProductArea_Create 'Andre Karner','####','RET',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Chemie',NULL
exec sp_ProductArea_Create 'Andre Karner','####','MAT',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Allgemein',NULL
exec sp_ProductArea_Create 'Andre Karner','####','Hydraulik',NULL
```

### config_ProductType RefType 2
```sql
exec sp_ProductSupplier_Create 'Andre Karner','####','TEKAEF',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','MediaMarkt',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Triotronik',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','omegacom',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Conatex',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','-',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','electronicshop24',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','InfrarotTec Systems',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Festo',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Bartelt',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Conrad',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Kellner & Kunz',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Anneliese Hemmer',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','WINLAB',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Amazon',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','mylemon',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','AustroTec',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','LBE GmbH',NULL
exec sp_ProductSupplier_Create 'Andre Karner','####','Neuson Hydrotec',NULL
```

### config_ProductType RefType 3
```sql
exec sp_ProductLocation_Create 'Andre Karner','####','BK',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','ENTSORGT',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','N6',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','fehlt',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','eingebaut in PC',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K12',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K13',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K13a',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K4',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K5',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K6',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','N7',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','R14',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','-',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','K10',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','Internat',NULL
exec sp_ProductLocation_Create 'Andre Karner','####','R13',NULL
```

### config_ProductType RefType 4
```sql
exec sp_ProductResponsible_Create 'Andre Karner','####','KEP',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','Kep',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','HG',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','Kam',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','OST',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','HA',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','PRE',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','BA',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','SUP',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','LECH',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','POA',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','Ost',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','-',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','Pre',NULL
exec sp_ProductResponsible_Create 'Andre Karner','####','Kach',NULL
```

### config_ProductType RefType 5
```sql
exec sp_ProductDepositor_Create 'Andre Karner','####','-',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','Kep',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','KUW',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','SUP',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','POA',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','Pre',NULL
exec sp_ProductDepositor_Create 'Andre Karner','####','Kach',NULL
```

### T_Product
Im folgenden Abschnitt wird bewusst nur ein einzelnes SQL-Skript angeführt, da eine vollständige Auflistung aller Testdatensätze den Umfang deutlich überschreiten würde.

```sql
exec 
  sp_Product_Create
    @infoCreateFrom     = 'Andre Karner',
    @number             = '408-34-01-19',
    @name               = 'Logitech Lautsprecher Z200',
    @description        = NULL,
    @serialNum          = NULL,
    @costGross          = $29.0000,
    @invoiceDate        = '2019-10-04 00:00:00',
    @invoiceNum         = 'TVAAR1321151',
    @warrantyUntil      = NULL,
    @deInventoryReason  = NULL,
    @deInventoryDate    = NULL,
    @typeID             = 'AACEB9AC-CCE7-F011-B7B6-7085C2DCD5F6',
    @areaID             = '14ED736F-80E9-F011-B7B8-7085C2DCD5F6',
    @supplierID         = '17ED736F-80E9-F011-B7B8-7085C2DCD5F6',
    @locationID         = '1CED736F-80E9-F011-B7B8-7085C2DCD5F6',
    @depositorID        = '20ED736F-80E9-F011-B7B8-7085C2DCD5F6',
    @responsibleID      = '23ED736F-80E9-F011-B7B8-7085C2DCD5F6'
GO
```

---

## Designentwicklung

### MockUp-Designentwicklung

Das MockUp der Inventar-Webseite wurde aus Gründen der zeitlichen Effizienz vollständig mit Unterstützung einer **KI** erstellt. Es dient als visuelle Leitlinie und zeigt das geplante Layout, besitzt jedoch keinerlei Funktionalität. Das **Endprodukt** wurde anschließend komplett eigenständig entwickelt und währenddessen weiter optimiert, um die **Usability** und **Nutzerfreundlichkeit** zu maximieren.

#### Inspirationen

Für die Such- und Filterfunktionen wünschte sich der Auftraggeber ein Design, das an die Plattform **Geizhals** angelehnt ist:

![ Geizhals Suchfilteroptionen.](img/GeizhalsFilterOptionen.png)  

Weitere Inspirationen stammen aus dem MockUp selbst und wurden während der Umsetzung gezielt angepasst, um die **Benutzerfreundlichkeit** zu erhöhen.

---

## Tatsächliche Umsetzung

Das Endprodukt fungiert als **Onepager**, bei dem der Seiteninhalt je nach Aktion dynamisch über **Ajax** ausgetauscht wird. Dadurch bleibt die URL unverändert, während nur der Inhalt aktualisiert wird.  

Ein besonderes Feature ist die QR-Code-Integration: Jeder QR-Code wird im Bearbeitungsmodus angezeigt und kann auf dem realen Objekt angebracht werden, sodass die zugehörigen Daten direkt abgerufen werden können. Unter jedem QR-Code wird zusätzlich die **Inventarnummer** angezeigt, damit diese auch für Menschen leicht lesbar ist.  

Die Webseite ist **vollständig responsiv** und kann sowohl auf dem Desktop als auch auf mobilen Endgeräten genutzt werden.

### Navigationsleiste

Die Navigationsleiste besteht aus drei Hauptpunkten:

- **Einstellungen**  
  Hier können kontobezogene Einstellungen angepasst werden, z. B. die Standardanzahl der angezeigten Einträge in der Produktliste. Administratoren verfügen über zusätzliche Optionen, wie das Anpassen des Speicherpfads für QR-Codes.

- **Drucken**  
  Zeigt alle gespeicherten QR-Codes an, sodass diese gesammelt ausgedruckt werden können.

- **Ausloggen**  
  Ermöglicht das Abmelden vom System.

### Such- und Filterfunktion

Die Anwendung bietet umfangreiche Such- und Filtermöglichkeiten:

- **Suche nach:**  
  - Name  
  - Inventarnummer  

- **Filter nach:**  
  - Produktkategorie  
  - Bereich  
  - Lieferant  
  - Standort  
  - Verantwortliche Person  
  - Hinterleger  
  - Erscheinungsdatum  

![ Such- und Filterfunktion.](img/FilterUndSuche.png)  

### Anzeige der Produkte

Die Produkte werden tabellarisch dargestellt. Nutzer können die Anzahl der angezeigten Einträge anpassen und zwischen Seiten wechseln. Die Liste aktualisiert nur den sichtbaren Inhalt, wodurch langes Scrollen vermieden wird.  

Jedes Produkt kann durch einen Klick auf einen Pfeil geöffnet werden, um zusätzliche Informationen anzuzeigen. Über ein Kopiersymbol lässt sich die Inventarnummer direkt kopieren.  

![ Produktliste.](img/ProduktListe.png)  

### Erstellung neuer Produkte

Ein großes **Plus-Symbol** in der Produktliste ermöglicht das Hinzufügen neuer Produkte. Dabei kann gewählt werden, ob die Daten von einer bestehenden Inventarnummer übernommen oder ein komplett neues Produkt erstellt werden sollen.  

In beiden Fällen müssen eine **Produktkategorie** und ein **Erstellungsdatum** angegeben werden, um die korrekte Inventarnummer automatisch zu generieren. Eine manuelle Änderung der Inventarnummer ist **nicht möglich**, da dies sonst zu **Inkonsistenzen in der fortlaufenden Nummerierung** führen könnte.

### Bearbeitung eines Produktes

Bei jedem Produkt gibt es ein **Bearbeitungssymbol**, das die Bearbeitungsansicht öffnet. Dort können alle Produktinformationen geändert werden, **mit Ausnahme der Inventarnummer und der Produktkategorie**, um die Datenkonsistenz zu wahren. Das **Erstellungsdatum** kann im Bearbeitungsmodus angepasst werden, da es die Inventarnummer nicht beeinflusst.

In der Bearbeitungsansicht steht eine **Top-Bar** mit folgenden Funktionen zur Verfügung:

- **Drucken**  
  Fügt den QR-Code zur Druckansicht hinzu, sodass mehrere QR-Codes gemeinsam ausgedruckt werden können.

- **Speichern**  

- **Abbrechen**  

![ Produktbearbeitungs- und -Erstellungsseite](img/Produktseite.png)  

### Unterschiede zwischen Bearbeitung und Erstellung

Sowohl im **Erstellungsmodus** als auch im **Bearbeitungsmodus** können die **Inventarnummer** und die **Produktkategorie** **nicht geändert werden**.  
Dies ist bewusst so implementiert, um **Inkonsistenzen bei der automatischen Vergabe nachfolgender Inventarnummern** zu verhindern und die **Datenintegrität** zu gewährleisten.  

Ein wesentlicher Unterschied besteht darin, dass im **Erstellungsmodus** das **Erstellungsdatum fixiert** ist, während es im **Bearbeitungsmodus** angepasst werden kann. So bleibt die fortlaufende Nummerierung zuverlässig und konsistent.

---
