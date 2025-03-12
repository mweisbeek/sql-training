## Gegevens groeperen: GROUP BY
Heel mooi dat we gegevens kunnen selecteren (met SELECT), filteren (met WHERE) en ook kunnen sorteren (met ORDER BY).

* TOC
{:toc}

### TOP 5
Stel dat we een TOP 5 willen samenstellen van de gegevens.

Dat kan als volgt:
```sql
SELECT TOP 5 Rol, Count(Id)
FROM Deelnemers
GROUP BY Rol
ORDER BY 2 DESC
```

Met **TOP** geef je aan dat je alleen de bovenste x records van het resultaat wilt zien.

De **ORDER BY 2** verwijst naar de 2e kolom.

**DESC** staat voor **Descending**, oftewel **Aflopend**. Daarmee geven we aan dat degene met de hoogste waarde bovenaan moet komen. Dat is wat je doorgaans doet als je een TOP-x wilt tonen. Vaak ben je dan geinteresseerd in wat de grootste waarde heeft.

**ASC** betekent **Ascending**, oftewel **oplopend**. Die hoef je niet altijd op te geven, want dat is de standaardwaarde voor het sorteren.

### HAVING
Wat WHERE doet in een standaard SELECT-query, dat doet HAVING samen met een GROUP BY.

Hier groeperen we eerst op basis van de rol van een deelnemer. 
Direct daarna zeggen we dat we alleen geinteresseerd zijn in de rollen die meer dan 2 keer voorkomen.

```sql
SELECT TOP 5 Rol, Count(Id)
FROM Deelnemers
GROUP BY Rol
HAVING Count(Id) > 2
ORDER BY 2 DESC
```

Op deze manier kun je ook heel goed dubbele waarden in een tabel opzoeken (bijvoorbeeld met HAVING COUNT(*) > 1). Soms komen er dubbele waarden in een tabel terecht, maar die wil je eruit verwijderen als je een unieke index wilt aanmaken.

### DISTINCT: eenvoudige manier om dubbele waarden te filteren
Met DISTINCT kun je alleen de unieke waarden tonen. Deze is eenvoudiger dan GROUP BY, maar daarmee ook minder krachtig. Als je snel unieke waarden nodig hebt, dan werkt *DISTINCT* wel goed. Als je iets meer wilt, denk dan aan **GROUP BY**.

```sql
SELECT DISTINCT Rol
FROM Deelnemers
ORDER BY 1
```