---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL
exl-id: 327597f6-8a53-42dc-966a-baae49b58bb3
version: Campaign Orchestration
source-git-commit: 69644e85d9c453f34fe8c5d40e0c1e8dce2891a5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---


# Kom igång med relationsscheman och datauppsättningar{#gs-schemas}

I den här guiden får du hjälp med att skapa ett relationsschema, konfigurera en datauppsättning för orkestrerade kampanjer och inhämta data.

![](assets/do-not-localize/schema_admin.png)

En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). Data som har importerats till Experience Platform lagras i datasjön som datauppsättningar.

Ett schema representerar och validerar datastrukturen och dataformatet. Den ger en abstrakt definition av ett objekt i verkligheten (till exempel en person) och visar vilka data som ska inkluderas i varje instans av objektet (till exempel namn, födelsedag och så vidare).


1. Skapa [relationsschema manuellt](manual-schema.md) eller [med en DDL-fil](file-upload-schema.md)

   Definiera strukturen för din datamodell, inklusive tabeller, attribut och relationer. Välj om du vill skapa schemat manuellt i användargränssnittet eller överföra en DDL-fil för snabbare konfiguration.

   När du skapar schemat manuellt måste datauppsättningen också skapas och aktiveras manuellt. När du använder en DDL-fil skapas och aktiveras datauppsättningar automatiskt.

1. [Länka schema](file-upload-schema.md)

   Upprätta relationer mellan dina scheman för att säkerställa att data är konsekventa och möjliggöra enhetsöverskridande frågor. Länka till exempel lojalitetstransaktioner till mottagare eller belöningar till varumärken.

1. [Ingrediera data](ingest-data.md)

   Hämta in data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.

