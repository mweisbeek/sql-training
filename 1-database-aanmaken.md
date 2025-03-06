## Database aanmaken
Op de server heb ik een gebruiker aangemaakt die alleen nieuwe databases mag aanmaken (alleen lid van **dbcreator**-rol):

Deze kun je gebruiken om met de test-server te verbinden en een eigen database aan te maken:
- open SQL Server Management Studio (SSMS)
  - heb je die nog niet, dan kun je deze installeren via de Company Portal
- [verbind via SSMS met de server](0-inloggen_op_server.md)
- rechtsklik op **Databases** en kies voor **New Database...**
- geef de database een naam (liefst met jouw eigen naam erin, zodat we die later kunnen herkennen)

![alt text](<2025-02-27 18_33_18-New Database.png>)

## Manieren van inloggen
Er zijn 2 manieren om in te loggen op SQL Server:
- via Windows Authentication
- via SQL Authentication

In deze training gebruiken wij de manier via SQL Authenticatie. Dat betekent dat we zelf een nieuwe gebruiker gaan aanmaken op de server.

## Partial containment
Normaal gesproken maak je SQL-gebruikers op de server aan. 
Wij willen deze graag bij de database houden. Daarom kiezen we voor **Partial Containment**.

![alt text](partial-containment.png)

[Maak nu een eigen gebruiker aan](2-gebruiker-aanmaken.md)
