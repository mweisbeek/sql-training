## SQL Server Agent
SQL Server komt ook met een handige ingebouwde scheduler: SQL Server Agent.

### Wanneer gebruiken?
Soms heb je een bepaalde taak waarvan je zou willen dat die bijvoorbeeld elk uur (of elke 5 minuten of een andere tijdspanne) wordt uitgevoerd.

Normaal gesproken kun je zo'n taak starten met bijvoorbeeld de Windows Task Scheduler. Daarmee roep je dan een bepaald Windows-programma aan die vervolgens deze taak uitvoert. Maar in dit geval heb je even niet zo'n handig Windows-programma beschikbaar. Dan is het handig dat SQL Server Agent bestaat, want daarmee kun je binnen de database processen starten.

### Ook programma's starten
SQL Server Agent biedt ook de mogelijkheid om programma's buiten SQL Server te starten. Op die manier kun je best wel leuke workflows samenstellen van dingen die je in SQL Server wilt starten, aangevuld met een ander programma dat daar vervolgens weer iets handigs mee doet.

### Toegang
SQL Server Agent is alleen beschikbaar voor wie voldoende rechten heeft op de betreffende SQL Server. Dat is de system-administrator (sa) rol. Heb je die rechten niet, dan zie je waarschijnlijk ook geen SQL Server Agent verschijnen in de Object Explorer in SSMS.

### Jobs
In SQL Server Agent maak je *jobs* aan. Een job is een verzameling van stappen (steps) die in volgorde worden uitgevoerd.

### Monitoring
Via **View Job History** kun je bekijken hoe zo'n job gedraaid heeft. Ook kun je daarmee zien hoe lang de job daarover heeft gedaan. Je kunt zelfs zien hoe lang elke stap in het proces geduurd heeft. Daarmee kun je dus uitvinden welke stap in de job ervoor zorgt dat die er mischien best lang over doet.