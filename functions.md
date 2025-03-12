## Functies

* Inhoud
{:toc}

### Eenvoudige functies
In een SELECT kun je eenvoudige functies gebruiken, zoals ISNULL() en LEN().

[Zie hier](https://learn.microsoft.com/en-us/sql/t-sql/functions/string-functions-transact-sql) een voorbeeld van diverse functies die je op tekstuele waarden kunt toepassen.

Zo zijn er nog [veel meer functies](https://learn.microsoft.com/en-us/sql/t-sql/functions/functions) die SQL Server kent.

Ook kun je functies met elkaar combineren door de uitvoer van een functie weer in een andere functie te gebruiken:

```sql
-- verwijder alle spaties links en rechts van een waarde met LTRIM() en RTRIM()
SELECT LTRIM(RTRIM(Naam))
FROM Deelnemers
ORDER BY 1
```

### Met gegroepeerde gegevens
Functies zoals MIN(), MAX(), COUNT() etc kun je gebruiken met gegroepeerde gegevens (GROUP BY).

Zo kun je bijvoorbeeld ook alle waarden in een kolom bij elkaar optellen:
```sql
SELECT SUM(InwonerAantal)
FROM Provincies
ORDER BY 1 DESC
```

[Zie hier](https://learn.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql) voor nog meer functies die je kunt gebruiken met gegroepeerde gegevens.