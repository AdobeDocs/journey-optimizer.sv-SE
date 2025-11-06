---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett modellbaserat schema i Adobe Experience Platform genom att överföra en DDL
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
version: Campaign Orchestration
source-git-commit: e189bb6a52691770655a436e45c6788d1011a8ca
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 1%

---


# Kom igång med modellbaserade scheman och datauppsättningar{#gs-schemas}

I den här guiden får du hjälp med att skapa ett modellbaserat schema, konfigurera en datauppsättning för orkestrerade kampanjer och inhämta data.

![schema](assets/do-not-localize/schema_admin.png){zoomable="yes"}

## Viktiga begrepp

I samband med Orchestrated-kampanjer är en **datamängd** en lagrings- och hanteringskonstruktion för en datainsamling, vanligtvis en tabell, som innehåller ett schema (rader) och fält (kolumner). Data som har importerats till Experience Platform lagras i datasjön som datauppsättningar.

Ett **schema** representerar och validerar datastrukturen och dataformatet. Den ger en abstrakt definition av ett objekt i verkligheten (till exempel en person) och visar vilka data som ska inkluderas i varje instans av objektet (till exempel namn, födelsedag och så vidare).

En **datamodell** är den konceptuella planen för att normalisera dina data

Den beskriver:

* Enheterna (t.ex. kund, kampanj, segment)
* Attributen för dessa enheter (t.ex. kundnamn, kampanjens startdatum)
* Relationerna mellan enheter (t.ex. Kunder tillhör segment, kampanjer och målsegment)

En datamodell är logisk och begreppsmässig, och den är inte knuten till en fysisk implementering i Orchestrated Campaign

I en **modellbaserad datamodell** ordnas data i tabeller som relaterar till andra tabeller.

* Varje tabell har rader (poster) och kolumner (attribut)
* Varje tabell har en primärnyckel som unikt identifierar rader
* Relationer mellan tabeller uttrycks med hjälp av sekundärnycklar

Ett **modellbaserat schema** är den formella definitionen av den modellbaserade datamodellen.

Den anger:

* Tabelluppsättningen
* Kolumnerna i varje tabell
* Begränsningarna
* Relationerna mellan tabeller

Att ordna scheman eller tabeller i en modellbaserad datamodell handlar om att strukturera data i flera tabeller. Se till att varje register lagrar en typ av entitet/scheman

➡️ [Läs mer om scheman i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/ui/resources/schemas#create-model-based-schema)

## Implementeringssteg {#implementation}

Så här importerar du data och skapar ett modellbaserat schema:

1. Skapa [modellbaserat schema manuellt](manual-schema.md) eller [med en DDL-fil](file-upload-schema.md)

   Definiera strukturen för din datamodell, inklusive tabeller, attribut och relationer. Välj om du vill skapa schemat manuellt i användargränssnittet eller överföra en DDL-fil för snabbare konfiguration.

   När du skapar schemat manuellt måste datauppsättningen också skapas och aktiveras manuellt. När du använder en DDL-fil skapas och aktiveras datauppsättningar automatiskt.

1. [Länka scheman](file-upload-schema.md)

   Upprätta relationer mellan dina scheman för att säkerställa att data är konsekventa och möjliggöra enhetsöverskridande frågor. Länka till exempel lojalitetstransaktioner till mottagare eller belöningar till varumärken.

1. [Skapa datauppsättning](manual-schema.md#dataset)

   När du har definierat ditt schema måste du skapa en datauppsättning som baseras på det. Den här datauppsättningen fungerar som lagring för dina inkapslade data.

1. [Aktivera samordnade kampanjer](manual-schema.md#enable)

   Datauppsättningen lagrar dina inkapslade data och måste aktiveras för Orchestrated Campaigns för att den ska vara tillgänglig i Adobe Journey Optimizer.

1. [Ingrediera data](ingest-data.md)

   Hämta in data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.

