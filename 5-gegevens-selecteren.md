## Gegevens selecteren
Als we gegevens in onze database hebben, dan is het ook handig als je die weer kunt selecteren.

- Selecteer een database
- Gebruik New Query (CTRL+N) om een nieuw query-venster te openen

### SELECT
Eenvoudigste vorm:
```sql
SELECT *
FROM Deelnemers
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
