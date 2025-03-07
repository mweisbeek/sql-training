## Gegevens selecteren
Als we gegevens in onze database hebben, dan is het ook handig als je die weer kunt selecteren.

- Selecteer een database
- Gebruik New Query (CTRL+N) om een nieuw query-venster te openen

### SELECT
Eenvoudigste vorm:
```sql
SELECT *
FROM Deelnemersx
```

### WHERE
Met WHERE kun je aangeven waar de te selecteren gegevens aan moeten voldoen:
```sql
SELECT *
FROM Deelnemers
WHERE Naam = 'Martijn Weisbeek'
```

### WHERE ... LIKE ....
Met LIKE kun je gedeeltelijke gegevens mmatchen.

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

Dit voorbeeld selecteert bijvoorbeeld alle deelnemers van wie de Naam eindigt op **Weisbeek**.
```sql
SELECT *
FROM Deelnemers
WHERE Naam LIKE '%Weisbeek'
```

Het procent-teken (%) is een _wildcard_ waarmee je aangeeft welk deel van het woord je zoekt.

### ORDER BY
Met **Order By** kun je de gegevens ook sorteren:
```sql
SELECT *
FROM Deelnemers
Order By Naam
```

### Welke kolommen?
In welke kolommen ben je uiteindelijk geinteresseerd:
```sql
SELECT Id, Naam, Created
FROM Deelnemers
Order By Naam
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
