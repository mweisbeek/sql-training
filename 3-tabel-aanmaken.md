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

Zie hier een lijst met [data-types](data-types.md) 
