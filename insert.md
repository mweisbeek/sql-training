## INSERT
Gegevens toevoegen doe je met het INSERT-commando.

```sql
INSERT INTO TabelNaam (Naam, Actief)
VALUES ('Mijn naam', 1)
```

### Vanuit een SELECT
De gegevens vanuit een SELECT-commando kun je rechtstreeks aan het INSERT-commando geven.

### Snelste manier
Als de tabel *precies dezelfde opbouw* heeft, dan kan het op deze manier:

```sql
INSERT INTO TabelNaam
SELECT *
FROM TabelNaam
WHERE Actief=1
```

In het voorbeeld hierboven hebben we de veldnamen niet opgegeven. 
Dan gebruikt de database de volgorde van de kolommen in de tabel.
*Let op:* dit is gevaarlijk en er is geen garantie dat dit ook in de toekomst goed blijft werken.

### Kolom-namen opgeven
Bij voorkeur geef je de namen van de kolommen op:

```sql
INSERT INTO TabelNaam (Naam, Actief)
SELECT Naam, Actief
FROM TabelNaam
WHERE Actief = 1
```

*Let op:* Als aan een tabel nieuwe kolommen worden toegevoegd, dan gaat het eens fout als je geen kolomnamen hebt opgegeven (!)

Gebruik je wel de namen van de kolommen, dan geef je zelf de volgorde op en zal dat goed blijven gaan. Totdat iemand besluit om een kolom uit een tabel te verwijderen. Gelukkig gebeurt dat niet zo vaak. 

*Voorbeeld:* in de database van Exact Software staan kolommen die niet meer worden gevuld. Maar deze kolommen worden niet verwijderd. Dat is niet omdat ze dit zijn vergeten, maar vooral zodat bestaande queries nog steeds kunnen blijven werken.

### Tip: Snel een tabel maken
Microsoft SQL Server kent een manier om snel een tabel aan te maken op basis van een SELECT-commando:

```sql
SELECT Naam, Actief
INTO NieuweTabelNaam_20250603
FROM TabelNaam
WHERE Actief = 1
```

Zo kun je heel eenvoudig bepaalde gegevens (tijdelijk) in een tabel plaatsen, zonder dat je eerst daarvoor zelf een nieuwe tabel hoeft te maken. SQL Server kijkt dan naar de gegevens en maakt op basis daarvan een nieuwe tabel aan.

*Let op:* Als er al een tabel met de naam *NieuweTabelNaam_20250603* bestaat, dan levert dat een foutmelding op.
Dan bedenk je een nieuwe naam en kan het alsnog gaan werken.

