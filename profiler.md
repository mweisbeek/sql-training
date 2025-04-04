{:toc}

## [TOOLS] SQL Server Profiler
Met de SQL Server Profiler kun je heel veel bekijken omtrent jouw database of de server waar de database op draait.

### Execution Plans
Een database-server krijgt een query die uitgevoerd moet worden. Vervolgens gaat de database-server bepalen wat de beste manier is om deze query uit te voeren. Daarvoor maakt de database een plan van aanpak. Dat noemen we een Execution Plan.

### Display Estimated Execution Plan
Via het menu **Query > Display Estimated Execution Plan** kun je **vooraf** bekijken hoe een query het waarschijnlijk gaat doen. 
Daarvoor hoeft de query niet te worden uitgevoerd, dus kun je snel een antwoord krijgen op jouw vraag. **Sneltoets:** CTRL+L.

### Include Actual Execution Plan
Als je de query eerst laat uitvoeren, dan krijg je uiteraard het beste beeld van de performance.

Daarvoor is er de optie **Query > Include Actual Execution Plan**. 
Als de query dan **is uitgevoerd**, dan zie je onderin het scherm een extra tabblad dat het **Execution Plan** toont. Dat is het daadwerkelijke execution plan. Daarin kun je zien hoeveel procent van de tijd SQL Server met welk deel van jouw query bezig is.

### [TOOLS] Database Engine Tuning Advisor
Als je met SQL Server Profiler een Trace hebt gemaakt en opgeslagen, dan kun je die nog verder laten analyseren met de **Database Engine Tuning Advisor**.

Dit hulpmiddel kan ook aangeven welke indexes en statistieken handig zijn om aan te maken. Ook geeft die aan hoeveel het qua performance scheelt als je deze indexes zou aanmaken.

De Database Engine Tuning Advisor kan direct de voorgestelde indexes aanmaken, maar kan deze ook naar een SQL-bestand schrijven. Dat bestand kun je dan meenemen en op een andere sever uitvoeren.