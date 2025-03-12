## Gegevens selecteren
Als we gegevens in onze database hebben, dan is het ook handig als je die weer kunt selecteren.

- Selecteer een database (CTRL+U)
- Gebruik New Query (CTRL+N) om een nieuw query-venster te openen

* TOC
{:toc}

### SELECT
Eenvoudigste vorm:
```sql
SELECT *
FROM Deelnemers
```

### Welke kolommen? In welke volgorde?
In plaats van * (= alles) kun je ook de kolommen opgeven die je wilt zien:
```sql
SELECT Id, Naam
FROM Deelnemers
WHERE Naam = 'Martijn Weisbeek'
```

Of als je bepaalde kolommen vooraan wilt plaatsen in het resultaat wilt zien (want dan hoef je niet _op zoek_ naar een bepaalde kolom):
```sql
SELECT Id, Naam
, *
FROM Deelnemers
WHERE Naam = 'Martijn Weisbeek'
```

### Met een andere naam: AS
In welke kolommen ben je uiteindelijk geinteresseerd:
```sql
SELECT Id, Naam, Created as [Datum aangemaakt]
FROM Deelnemers
Order By Naam
```
**Tip:** gebruik blokhaken als de naam die je wilt gebruiken blauw wordt gekleurd (ten teken dat dit een gereserveerd woord is in T-SQL).
Of als je bijvoorbeeld een spatie in de kolomnaam wilt gebruiken.

### WHERE
Met WHERE kun je gegevens filteren:
```sql
SELECT *
FROM Deelnemers
WHERE Naam = 'Martijn Weisbeek'
```

### WHERE ... LIKE ....
Met LIKE kun je ook op gedeeltelijke gegevens zoeken. 
Let op het procentteken (%) dat als _wildcard_ wordt gebruikt. 

Dit voorbeeld selecteert bijvoorbeeld alle deelnemers van wie de Naam **eindigt op Weisbeek**.
```sql
SELECT *
FROM Deelnemers
WHERE Naam LIKE '%Weisbeek'
```

Je kunt ook meerdere procenttekens gebruiken:
```sql
SELECT *
FROM Deelnemers
WHERE Naam LIKE '%Weis%beek%'
```

Het bovenstaande zoekt naar een tekst met ergens **Weis** erin, gevolgd door ergens **beek**.
Let op dat zoeken in een database standaard **niet hoofdlettergevoelig** is (via de collation kun je dat wel aanpassen, maar dat is een wat geavanceerder onderwerp voor later).

### Sorteren: ORDER BY
Met **Order By** kun je de gegevens ook sorteren:
```sql
SELECT *
FROM Deelnemers
Order By Naam
```

### Exporteren in een andere vorm?
Moet(en) een of meerdere kolommen nog in een ander formaat worden geschreven?
```sql
SELECT Id,
  Naam + '_Suffix' as Naam,
  -- het formaat dat we in Nederland gewend zijn:
  CONVERT(VARCHAR(20), Created, 105) as DatumAangemaakt,
  -- een formaat dat je het beste met databases kunt gebruiken: yyyy-MM-dd hh:mm:ss
  CONVERT(VARCHAR(20), Created, 120) as [Datum Aangemaakt (sortering)]
FROM Deelnemers
Order By Naam
```

### ERROR
Wat gaat er fout in onderstaande query:

```sql
select *
from deelnemers 
where naam = 1
```

**Hint:**
```sql
Msg 245, Level 16, State 1, Line 1
Conversion failed when converting the varchar value 'Martijn Weisbeek' to data type int.
```