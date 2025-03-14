* Inhoud
{:toc}

## Primary Keys (PK)
*Relationele databases* bestaan doorgaans uit *meerdere tabellen* die je handig aan elkaar kunt koppelen (linken).

Dit werkt met *Primary Keys (PK)* en *Foreign Keys (FK)*.

De Deelnemers-tabel die we vorige keer hebben aangemaakt, kunnen we eenvoudig een Primary Key geven: 
- open in SSMS de tabel in de Designer
- klik met de rechtermuisknop op de Id-kolom
- kies voor Set Primary Key
- sla de wijzigingen in de tabel op

Met een Primary Key geef je aan dat er in die kolom alleen maar unieke waarden mogen staan. Dat kan bijvoorbeeld een Code zijn die je zelf bedenkt, maar ook een automatisch gegenereerde waarde (zoals een *Identity-waarde* of een *NEWID()*). Deze waarde *moet uniek zijn*, zodat je op basis van deze waarde een uniek record in die tabel kunt vinden. Zo kan er bijvoorbeeld een docent zijn met medewerkernummer=1. Die kun je daarmee eenvoudig aan een lesrooster koppelen.

## Foreign Keys (FK)
Foreign keys (FK) worden in databases gebruikt om een veld in een tabel aan een andere tabel te koppelen.
1 tabel kan meerdere Foreign Keys hebben, die elk weer naar een andere tabel kunnen verwijzen.

Elk van deze Foreign Keys kun je zien als een soort opzoekfunctie. In de hoofdtabel hoef je dan alleen maar de verwijzing op te nemen. Met die verwijzing (code) kan de database in de andere tabel het bijbehorende record selecteren.

Dit wordt ook wel het *normaliseren* van tabellen genoemd. Zo kun je gegevens logisch aan elkaar koppelen. Als dan in 1 tabel een waarde wijzigt, dan hoeft die alleen maar op die plaats te worden bijgewerkt. Toch profiteren alle gelinkte records daar direct van. Dit voorkomt het dubbel opslaan van gegevens, wat je bijvoorbeeld vaak doet in een Excel-sheet.

## Nieuwe Provincies-tabel aanmaken
```sql
CREATE TABLE [dbo].[Provincies](
	[Code] [varchar](2) NOT NULL,
	[Omschrijving] [varchar](100) NULL,
	[InwonerAantal] [int] NULL,
	[Oppervlakte] [int] NULL,
PRIMARY KEY CLUSTERED 
(
	[Code] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) 
)
GO
```

![Relaties tussen tabellen](<images/tabel-referenties.png>)
