## Gegevens toevoegen
Er zijn meerdere manieren om gegevens in jouw database te krijgen:
- via **Edit Table**: rij voor rij
- via **Edit Table**: meerdere via copy-paste (vanuit Excel)
- via **SQL**: INSERT INTO
- via **Tasks > Import data / Import Flat File**

### Edit table
Klik met de rechtermuisknop op een tabel en kies voor **Edit top 200 rows**.

Daar kun je records aan de tabel toevoegen door de gegevens in te voeren.

### Copy + paste
De Edit Table functionaliteit heeft ook nog een andere handigheid: 
- je kunt gegevens kopieren (bijvoorbeeld vanuit Excel)
- en daarna plakken in het Edit Table-venster

Dit is een eenvoudige manier om meerdere records toe te voegen.

Nadeel van deze methode is wel dat SQL Server voor elk record controleert of die al in de tabel bestaat. Daardoor zal dit nooit de snelste methode zijn. 
Als je veel records moet toevoegen, dan is dit waarschijnlijk niet de beste manier.

### SQL: INSERT INTO
Waar zouden we zijn zonder SQL?

```sql
insert into deelnemers (Naam) values ('Martijn Weisbeek')
```

### Gegevens importeren
Klik hiervoor met de rechtermuisknop op de naam van jouw database.
Kies voor Tasks > Import data (of Import Flat File)

Met deze functie kun je een bestand selecteren.
En opgeven in welke tabel deze gegevens moeten worden geimporteerd.

![Gegevens importeren](<images/2025-03-07 00_45_07-Import Flat File 'SqlCursus'.png>)

**Let op:** deze functie maakt standaard een nieuwe tabel aan. De gegevens die worden geimporteerd kun je altijd later in een andere tabel overnemen.  

Volgende stap: [gegevens selecteren](5-gegevens-selecteren.md): SELECT
