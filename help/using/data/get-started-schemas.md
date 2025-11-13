---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med scheman
description: Lär dig använda Adobe Experience Platform-scheman i Adobe Journey Optimizer
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: scheman, plattform, data, struktur
exl-id: c2a8df2e-ff94-4f9a-a53e-bbf9f663cc81
source-git-commit: 059670c143595b9cacdf7e82a8a5c3efda78f30b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

---

# Kom igång med scheman {#schemas-gs}

[!DNL Adobe Journey Optimizer] förlitar sig på **Adobe Experience Platform-scheman** för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. Ett schema innehåller en abstrakt definition av ett objekt i verkligheten (till exempel en person) och visar vilka data som ska inkluderas i varje instans av objektet (till exempel namn, födelsedag och så vidare). När data hämtas till Experience Platform är de alltid strukturerade enligt ett **XDM-schema**.

## Standard- och relationsscheman

Det finns två typer av scheman i Adobe Experience Platform:

* **Standardscheman** är hierarkiska scheman som använder klasser och fältgrupper för att hämta post- eller tidsseriedata.

  Ett standardschema består av:

   * En **klass** (som definierar databeteendet: post- eller tidsserie).
   * En eller flera **fältgrupper** (som lägger till specifika fält i schemat).

  I Journey Optimizer används standardscheman vanligtvis för att representera **enskilda personer och deras attribut**, hämta **tidsserieinteraktioner**, t.ex. klick, köp eller inloggningar, och **Real-Time Customer Profile** för segmentering och personalisering.

  ➡️ [Lär dig hur du skapar och konfigurerar ett standardschema i den här videon](#video-schema) (video)

* **Relationsscheman** är platta, icke-hierarkiska scheman som inte använder klasser eller fältgrupper. De används för att samla in postdata för relationsenheter och används främst i [!DNL Journey Optimizer] **orkestrerade kampanjer**.

  Exempel på relationsenheter är:
   * Bokningar, kontrakt eller prenumerationer
   * Produkter eller kataloger
   * Lager, platser eller partners

  Med relationsscheman kan du skicka ett meddelande per enhet (t.ex. per bokning, per prenumeration), skapa segment baserat på entitetsattribut (t.ex. produktkategori, butiksplats) och förbättra adresserbarheten genom att nå alla kontakter som är kopplade till en enhet.

  Så här fungerar relationsscheman:

   1. **Skapa scheman manuellt eller importera via DDL**
   1. **Länka scheman** för att definiera relationer mellan entiteter och personer (t.ex. lojalitetstransaktioner som är länkade till medlemmar, belöningar som är länkade till varumärken).
   1. **Infoga data** i datauppsättningen från källor som stöds.

  ➡️ [Lär dig hantera relationsscheman och datauppsättningar](../orchestrated/gs-schemas.md)
➡️ [Kom igång med samordnade kampanjer](../orchestrated/gs-schemas.md)

## Instruktionsvideo{#video-schema}

Lär dig hur du skapar ett standardschema, lägger till fältgrupper, skapar och konfigurerar anpassade fältgrupper.

>[!VIDEO](https://video.tv.adobe.com/v/334461?quality=12)

>[!MORELIKETHIS]
>
>* [Skapa ett schema, en datauppsättning och inmatningsdata för att lägga till testprofiler i Journey Optimizer](../audience/creating-test-profiles.md)
>* [Översikt över XDM-systemet](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}
>* [Bästa tillvägagångssätt för datamodellering](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=sv-SE){target="_blank"}
>* [Skapa ett schema med API:t för schemaregister](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-api.html?lang=sv-SE){target="_blank"}
>* [Definiera en relation mellan två scheman med Schemaredigeraren](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-ui.html?lang=sv-SE){target="_blank"}
