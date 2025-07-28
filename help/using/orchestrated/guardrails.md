---
solution: Journey Optimizer
product: journey optimizer
title: Samordnade kampanjer skyddar mot detaljer och begränsningar
description: Läs mer om säkra kampanjer och begränsningar
hide: true
hidefromtoc: true
exl-id: 82744db7-7358-4cc6-a9dd-03001759fef7
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 0%

---

# Skyddsritningar och begränsningar {#guardrails}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en orkestrerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

## Begränsningar för dataflöde till datauppsättning

Varje datauppsättning i Adobe Experience Platform kan bara kopplas till ett aktivt dataflöde i taget. Denna kardinalitet om 1:1 används strikt av plattformen.

Om du behöver byta datakälla (t.ex. från Amazon S3 till Salesforce):

Du måste ta bort det befintliga dataflödet som är anslutet till datauppsättningen.

Skapa sedan ett nytt dataflöde med den nya källan mappad till samma datauppsättning.

Detta garanterar tillförlitlig datainhämtning och är nödvändigt när du använder Change Data Capture (CDC), som är beroende av en definierad primärnyckel och ett versionsattribut (t.ex. lastmodifierad) för inkrementella uppdateringar.


## Relationsscheman/begränsningar för dataöverföring

* Upp till 200 relationsscheman (tabeller) stöds i relationsdatalagret.

* Den totala storleken på ett relationsschema som används för kampanjsamordning får inte överstiga 100 GB.

* Batchintag för kampanjsamordning bör inte ske oftare än en gång var 15:e minut.

* Dagliga ändringar i ett relationsschema bör ligga under 20 % av det totala antalet poster.

## Datamodellering

* Versionsbeskrivare är obligatoriskt för alla scheman, inklusive faktatabeller.

* En primärnyckel krävs för varje tabell.

* Det table_name som tilldelas när datauppsättningar skapas används för segmenteringsgränssnittet och personaliseringsfunktionerna.

  Det här namnet är permanent och kan inte ändras efter att det har skapats.

* Fältgrupper stöds för närvarande inte.

## Datainmatning

* Profil + relationsdataöverföring krävs.

* Ett ändringsfält krävs för filbaserad inmatning, medan registerloggning måste aktiveras för inmatning av molndatabasen. Detta är nödvändigt för registrering av ändringsdata (CDC).

* Fördröjning från intag till datatillgänglighet i Snowflake varierar mellan 15 minuter och 2 timmar, beroende på datavolym, samtidighet och typ av åtgärder (infogningar är snabbare än uppdateringar).

* Dataövervakning i Snowflake håller på att utvecklas, och för närvarande finns det ingen inbyggd bekräftelse för lyckat intag.

* Direktuppdateringar till Snowflake eller datauppsättningen stöds inte. Alla ändringar måste göras via CDC-källor.

  Frågetjänsten är skrivskyddad.

* ETL stöds inte - kunderna måste ange data i det format som krävs.

* Delvisa uppdateringar tillåts inte. Varje rad måste anges som en fullständig post.

* Inmatningen bygger på Query Service och Data Distiller.

## Segmentering

* LOV (List of Values) och uppräkningar är för närvarande tillgängliga.

* Sparade målgrupper är statiska listor, deras innehåll avspeglar de data som finns tillgängliga när kampanjen körs.

* Tillägg till en sparad publik stöds inte. Uppdateringar kräver en fullständig överskrivning.

* Målgrupper måste bestå av enbart skalära attribut. Kartor och arrayer stöds inte.

* Segmentering stöder i första hand relationsdata. När det är tillåtet att blanda med profildata kan prestanda påverkas om stora profildatauppsättningar används. För att förhindra detta:

* Det finns stödlinjer, som att begränsa antalet profilattribut som har valts i grupper eller direktuppspelade målgrupper.

* Läser målgrupper cachelagras inte - varje kampanjkörning utlöser en fullständig läsning.

  Optimering krävs för stora eller komplexa målgrupper.