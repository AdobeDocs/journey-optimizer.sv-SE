---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
version: Campaign Orchestration
source-git-commit: 387aa023b4cb999ae4c27cbca4a2f7bcb5edf009
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---


# Kom igång med relationsscheman och datauppsättningar{#gs-schemas}

I den här guiden får du hjälp med att skapa ett relationsschema, konfigurera en datauppsättning för orkestrerade kampanjer och inhämta data.

![schema](assets/do-not-localize/schema_admin.png){zoomable="yes"}

## Viktiga begrepp

I samband med Orchestrated-kampanjer är en **datamängd** en lagrings- och hanteringskonstruktion för en datainsamling, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). Data som har importerats till Experience Platform lagras i datasjön som datauppsättningar.

Ett **schema** representerar och validerar datastrukturen och dataformatet. Den ger en abstrakt definition av ett objekt i verkligheten (till exempel en person) och visar vilka data som ska inkluderas i varje instans av objektet (till exempel namn, födelsedag och så vidare).

En **datamodell** är den konceptuella planen för att normalisera dina data

Den beskriver:

* Enheterna (t.ex. kund, kampanj, segment)
* Attributen för dessa enheter (t.ex. kundnamn, kampanjens startdatum)
* Relationerna mellan enheter (t.ex. Kunder tillhör segment, kampanjer och målsegment)

En datamodell är logisk och begreppsmässig, och den är inte knuten till en fysisk implementering i Orchestrated Campaign

I en **relationsdatamodell** ordnas data i tabeller som relaterar till andra tabeller.

* Varje tabell har rader (poster) och kolumner (attribut)
* Varje tabell har en primärnyckel som unikt identifierar rader
* Relationer mellan tabeller uttrycks med hjälp av sekundärnycklar

Ett **relationsschema** är den formella definitionen av relationsdatamodellen.

Den anger:

* Tabelluppsättningen
* Kolumnerna i varje tabell
* Begränsningarna
* Relationerna mellan tabeller

Att ordna scheman eller tabeller i en relationsdatamodell handlar om att strukturera data i flera tabeller. Se till att varje register lagrar en typ av entitet/scheman

## Implementeringssteg {#implementation}

Så här importerar du data och skapar relationsschema:

1. Skapa [relationsschema manuellt](manual-schema.md) eller [med en DDL-fil](file-upload-schema.md)

   Definiera strukturen för din datamodell, inklusive tabeller, attribut och relationer. Välj om du vill skapa schemat manuellt i användargränssnittet eller överföra en DDL-fil för snabbare konfiguration.

   När du skapar schemat manuellt måste datauppsättningen också skapas och aktiveras manuellt. När du använder en DDL-fil skapas och aktiveras datauppsättningar automatiskt.

1. [Länka schema](file-upload-schema.md)

   Upprätta relationer mellan dina scheman för att säkerställa att data är konsekventa och möjliggöra enhetsöverskridande frågor. Länka till exempel lojalitetstransaktioner till mottagare eller belöningar till varumärken.

1. [Skapa datauppsättning](manual-schema.md#dataset)

   När du har definierat ditt schema måste du skapa en datauppsättning som baseras på det. Den här datauppsättningen fungerar som lagring för dina inkapslade data.

1. [Aktivera orkestrerad kampanj](manual-schema.md#enable)

   Datauppsättningen lagrar dina inkapslade data och måste aktiveras för Orchestrated Campaigns för att den ska vara tillgänglig i Adobe Journey Optimizer.

1. [Ingrediera data](ingest-data.md)

   Hämta in data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.

