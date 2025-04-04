{:toc}

## [TOOLS] SQL Server Profiler
Met de SQL Server Profiler kun je heel veel bekijken omtrent jouw database of de server waar de database op draait.

### Display Estimated Execution Plan
Via het menu **Query > Display Estimated Execution Plan** kun je op voorhand bekijken hoe een query het waarschijnlijk gaat doen. 
Daarvoor hoeft de query niet te worden uitgevoerd, dus kun je snel een antwoord krijgen op jouw vraag. **Sneltoets:** CTRL+L.

### Include Actual Execution Plan
Als je de query eerst laat uitvoeren, dan krijg je uiteraard het beste beeld van de performance.

Daarvoor is er de optie **Query > Include Actual Execution Plan**. 
Als de query dan is uitgevoerd, dan zie je onderin het scherm een extra tabblad dat het **Execution Plan** toont.

### [TOOLS] Database Engine Tuning Advisor
Als je met SQL Server Profiler een Trace hebt gemaakt en opgeslagen, dan kun je die nog verder laten analyseren met de Database Engine Tuning Advisor.

Dit hulpmiddel kan ook aangeven welke indexes en statistieken handig zijn om aan te maken. Ook geeft die aan hoeveel het qua performance scheelt als je deze zou aanmaken.

De Database Engine Tuning Advisor kan direct de voorgestelde indexes aanmaken, maar kan deze ook naar een SQL-bestand schrijven. Dan kun je die meenemen en op een andere sever uitvoeren.