## Tabel aanmaken
Nu wordt het interessant, want we gaan onze eerste tabel aanmaken :-)

Daarvoor klik je met de rechtermuisknop op Tables en kies je voor **New > Table...**

Dan opent een venster met de Table Designer.

### Voorbeeld van een tabel


```sql
CREATE TABLE [dbo].[Deelnemers](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Naam] [varchar](100) NOT NULL,
	[Locatie] [varchar](100) NOT NULL DEFAULT('Nijkerk'),
	[Created] [datetime] NOT NULL DEFAULT(GETDATE()),
	[Opmerkingen] [varchar](8000) NULL,
	[LaterAansluiten] [bit] NOT NULL DEFAULT(0),
	[Rol] [varchar](50) NULL,
	[Department] [varchar](50) NULL,
 CONSTRAINT [PK_Deelnemers] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
))
GO
```

### Data types

#### VARCHAR + NVARCHAR
Voor het opslaan van tekst

#### CHAR
Dit is het type kolom dat Exact Globe standaard gebruikt. Exact gebruikt dit ook om spaties in de waarden op te slaan, voor een natuurlijke uitlijning. 
**Let op:** dit is erg onhandig, so please don't try this at home. Dit type bij voorkeur niet gebruiken, want varchar is efficienter.

#### INT
Voor het opslaan van gehele getallen, zoals 1, 2, 3, et cetera.

#### FLOAT / DECIMAL(x,y)
Vor het opslaan van gebroken getallen, bijvoorbeeld ook bedragen (prijzen van artikelen, et cetera)

DECIMAL is preciezer dan FLOAT. Float kom je nogal eens tegen in de tabellen van Exact Globe.

#### MONEY
Voor het opslaan van prijzen kun je ook het type MONEY gebruiken, maar je kunt beter DECIMAL gebruiken.

#### BIT
Deze kan een waarde 0 of 1 hebben, oftewel True / False. Daarmee kun je dus registreren of iets waar is of juist niet.

#### DATE + DATETIME
Als je een datum wilt vastleggen, gebruik dan DATETIME (of DATETIME2 / DATETIME2 / DATETIMEOFFSET).

In het **DATE**-formaat leg je alleen een datum vast, zonder de bijbehorende tijd.

**Tip:** via de GETDATE() functie krijg je de huidige datum terug:
```sql
select GETDATE()
```

#### UNIQUEIDENTIFIER
Dit is een Globally Unique Identifier, oftewel een GUID.
**Voorbeeld:** FA5B9754-335A-4EDE-915D-64C0AD495CDF

**Tip:** Deze kun je automatisch laten genereren met de functie NEWID() 

```sql
select newid()
```
