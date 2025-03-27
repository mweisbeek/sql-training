## DELETE
Met het DELETE-commando kun je gegevens verwijderen.

*Let op:* een database heeft geen "Prullenbak", dus weg is dan ook echt weg.
In zo'n geval hoop ik dat je een goede backup-strategie hebt, zodat je toch nog gegevens terug kunt halen.

{:toc}

### Simpelste vorm
```sql
DELETE FROM Deelnemers
WHERE Provincie = 'OV'
```

### Of nog eenvoudiger
Ook dit is geldige SQL:
```sql
DELETE FROM Deelnemers
```
Maar daarna is je Deelnemers-tabel wel helemaal leeg... Dat kan soms de bedoeling zijn, maar *kijk uit...*

### TRUNCATE
Als je een tabel helemaal leeg wilt maken, dan kun je ook het TRUNCATE-commando gebruiken:
```sql
TRUNCATE TABLE Deelnemers
```
TRUNCATE is sneller dan DELETE, want het wordt niet bijgehouden in de log van de database.
Maar *let wel heel erg op met dit commando*, want als je het op een verkeerde tabel uitvoert dan is die ook echt heel snel heel erg leeg :-(

### Transactions to the rescue
Omdat het DELETE-commando vergaande gevolgen kan hebben, is het goed om te weten dat een database ook over transacties beschikt.

```sql
BEGIN TRAN
```

Als er iets fout ging kun je dat terugdraaien met *ROLLBACK*:
```sql
ROLLBACK TRAN
```

Als alles goed lijkt te zijn gegaan, vergeet dan niet om het te bevestigen door de transactie te *COMMIT*ten:
```sql
COMMIT TRAN
```
Vergeet je de transactie te committen, dan blijft de transactie open staan.

Pas als je het venster in SSMS afsluit, dan wordt er gevraagd wat je wilt doen met eventuele openstaande transacties. Dan heeft al die tijd een transactie open gestaan op de bewuste tabel. Dat kan ervoor zorgen dat anderen die met dezelfde database werken in de tussentijd het record niet hebben kunnen bijwerken. Dat is op zijn zachtst gezegd vervelend.