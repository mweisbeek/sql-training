## Keys en indexes

* Inhoud
{:toc}

### PRIMARY KEY
Een Primary Key zorgt voor een unieke waarde in de tabel. Dit kan 1 kolom bevatten (zoals een Id), maar kan ook meerdere kolommen combineren.

### ID-kolom toevoegen
Je kunt altijd eenvoudig een kolom met een unieke waarde aan een tabel toevoegen:
- met een automatisch oplopend nummer (IDENTITY)
    - bijvoorbeeld 1,2,4,5 (hoeft niet aansluitend te zijn, want records kunnen ook verwijderd worden)
- met een UNIQUEIDENTIFIER (NEWID())
    - bijvoorbeeld D5774155-759F-4639-8696-0C3B60581634

#### Identity
In de eigenschappen van de kolom kun je aangeven dat je een Identity-waarde op deze kolom wilt inschakelen. Standaard begint deze te tellen bij 1 (= Seed) en hoogt steeds met 1 op (= Increment).

Voordeel: de gegevens zijn altijd oplopend als je sorteert op deze Id.

#### UniqueIdentifier
Met de functie NEWID() gegenereer je altijd een unieke waarde (in de vorm *D5774155-759F-4639-8696-0C3B60581634* ).

*Let op:* als je sorteert op deze waarde, dan is die niet automatisch oplopend.

*Voordeel:* gegevens uit verschillende tabellen (bijvoorbeeld vanuit verschillende databases) kun je eenvoudig samenvoegen, omdat deze waarde gegarandeerd uniek is. Dat is veel lastiger als in elke tabel een record is met Id=1 (als je met IDENTITY hierboven een unieke waarde hebt gemaakt).

*Tip:* Je kunt heel eenvoudig een unieke waarde aan een tabel toevoegen:
```sql
ALTER TABLE Deelnemers ADD NewId UNIQUEIDENTIFIER DEFAULT(NEWID())
GO

UPDATE Deelnemers SET NewId = NEWID() WHERE NewId IS NULL
```