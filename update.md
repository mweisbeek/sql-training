## UPDATE
Met het Update-commando kun je bestaande gegevens bijwerken.

{:toc}

### Eenvoudige UPDATE
Om gegevens bij te werken kun je het UPDATE-commando gebruiken:
```sql
update Deelnemers 
set Locatie = 'Nijkerk-Centrum'
where Locatie = 'Nijkerk'
```

**Let op** dat je altijd goed het WHERE-gedeelte controleert. Een Update kun je namelijk ook uitvoeren zonder een WHERE. Dan geldt het opeens voor *ALLE* records in de betreffende tabel / recordset.

**Tip:** voer eerst een SELECT uit van de gegevens die je wilt wijzigen, voordat je een update uitvoert.
Bijvoorbeeld:
```sql
select Locatie as Huidig, 'Nijkerk-Centrum' as Nieuw
from Deelnemers 
where Locatie = 'Nijkerk'
```

Dan zie je de huidige en de nieuwe gegevens naast elkaar en weet je dus ook wat je gaat wijzigen. En ook hoeveel records dit betreft.
Try to prevent the ["Oh no"-second](https://youtube.com/watch?v=X6NJkWbM1xk&pp=0gcJCdgAo7VqN5tD).

### Gecombineerde UPDATE
Met een JOIN kun je (ook bij een UPDATE) tabellen combineren. 
Vervolgens geef je aan welke tabel je wilt bijwerken. Dit kan ook met een alias, zoals de d in het voorbeeld hieronder:

```sql
update d
set Locatie = 'Nijkerk-Centrum'
from Deelnemers d 
inner join Provincies p on d.Provincie = p.Code
where p.Omschrijving = 'Gelderland'
```

### Edit Top 200 Rows
In SSMS kun je met de rechtermuisknop op een tabel klikken en kiezen voor **Edit Top 200 Rows**.

Dan komt er een nieuw venster met daarin de tabel, zoals je die bijvoorbeeld in Excel zou bewerken.
Zo zie je alle records in die tabel en kun je ze direct bewerken. Dan heb je daarvoor geen SQL-commando's nodig, maar kun je wel de gegevens bewerken.
Bijvoorbeeld: een nieuw record toevoegen, een bestaande bewerken of zelfs een record verwijderen.

De gegevens worden dan ook direct gecontroleerd: als je iets invoert wat niet correct is volgens het gegevensformaat van de kolom, dan wordt het afgekeurd totdat je iets invoert dat wel correct is. Zo krijg je alsnog geen vervuiling in je tabellen (behalve als het pure tekst is en iemand maar iets invult).

