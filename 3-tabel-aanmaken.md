## Tabel aanmaken
Nu wordt het interessant, want we gaan onze eerste tabel aanmaken :-)

Daarvoor klik je met de rechtermuisknop op Tables en kies je voor **New > Table...**

Dan opent een venster met de Table Designer.

!(empty Table Designer)/<images/2025-03-06 23_09_34-2022-2P3X1T3.SqlCursus - dbo.Table_1 - Microsoft SQL Server Management Studio Pr.png>

### Voorbeeld van een tabel
Zo kun je een tabel aanmaken:
!(filled Table Designer)/<images/2025-03-06 23_24_42-2022-2P3X1T3.SqlCursus - dbo.Deelnemers - Microsoft SQL Server Management Studio.png>

Ook kun je aan een veld een standaard-waarde meegeven, bijvoorbeeld:
- NEWID() om een UniqueIdentifier automatisch van een waarde te voorzien
- GETDATE() om een DateTime automatisch van de huidige datum te voorzien

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

Zie hier een lijst met [data-types](data-types.md) 


