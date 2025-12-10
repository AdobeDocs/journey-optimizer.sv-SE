---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 78b95ccd-bc28-46cd-937a-f68e3f34cc1e
source-git-commit: c30a74ccdaec81cbbb28e3129d5c351a0fe64bfc
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 0%

---

# Målgruppsaktivering i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

I kampanjer och resor kan ni välja alla målgrupper som genereras med segmentdefinitioner, anpassad uppladdning, arbetsflöden för disposition eller Federated Audience Composition.

>[!AVAILABILITY]
>
>Användningen av målgrupper och attribut från målgruppssammansättning är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten. [Lär dig använda attribut för målgruppsberikning i Journey Optimizer](../audience/about-audiences.md#enrichment)

## Fördröjning för målgruppsaktivering {#activation}

Publiken är redo att användas i Journey Optimizer direkt efter att intaget har slutförts. Detta är vanligtvis inom en timme, men kan variera. Publiken som är resultatet av kompositionerna bör vara tillgänglig 24 timmar efter publiceringen.

För målgrupper som härrör från batchsegmenteringsjobb kan aktiveringen fördröjas på grund av att batchintaget kan variera. För målgruppsresor som schemaläggs dagligen kan du definiera ett tidsfönster i färdegenskaperna för att säkerställa att nya målgruppsdata är tillgängliga före körning av resan. Om segmenteringsjobbet inte slutförs inom det definierade tidsintervallet hoppas resan över tills nästa förekomst inträffar. [Lär dig schemalägga en läsarresa](../building-journeys/read-audience.md)

## Anpassad uppladdning och sammanställning av externa målgrupper

Observera följande skyddsutkast för Custom Upload och Federated Audience Composition-målgrupper:

* **Stöd för förhandsgranskning och korrektur:** För närvarande stöds inte förhandsgranskning och korrektur för målgrupper som skapats med CSV-överföring eller sammanställning av federerade målgrupper. Tänk på detta när ni planerar era kampanjer.

* **Nya målprofiler:** Om det inte går att hitta någon matchning mellan en post och en enhetlig profiltjänstprofil skapas en ny tom profil. Den här profilen är kopplad till anrikningsattributen som lagras i datasjön. Eftersom den nya profilen är tom är målfält som vanligtvis används i Journey Optimizer (t.ex. personalEmail.address, mobilePhone.number) tomma och kan därför inte användas som mål.

  För att lösa detta kan du ange &quot;körningsfält&quot; (eller &quot;körningsadress&quot; beroende på kanal) i kanalkonfigurationen som &#39;identityMap&#39;. På så sätt säkerställs att det attribut som väljs som identitet när målgrupper skapas blir det som används för målgruppsanpassning i Journey Optimizer.

* **Aktiverade poster och identitetssammanfogning:** Alla poster i målgruppen aktiveras, inklusive eventuella dubbletter. Under nästa export av en enhetlig profiltjänstprofil kommer dessa poster att genomgå identitetssammanfogning. Det innebär att antalet aktiverade poster kan skilja sig från antalet profiler efter identitetssammanfogning.

## Målgrupper i [!DNL Journey Optimizer]

Du kan utnyttja målgrupper i **[!DNL Journey Optimizer]** på olika sätt:

* Välj en målgrupp för en **kampanj**, där meddelandet skickas till alla personer som tillhör den valda målgruppen. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Läs målgruppsorganisation** i en resa för att få alla personer i målgruppen att komma in på resan och ta emot de meddelanden som ingår i din resa. Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en målgruppsaktivitet för läsning](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

  För resor där målgrupper från målgruppssammansättning eller anpassad uppladdning används är profilattributen lika färska som den senaste grupputvärderingen vid registrering på resan. Efter en **Wait**-aktivitet uppdaterar resan profilattribut från UPS (Unified Profile Service) och hämtar de senaste tillgängliga data, vilket innebär att profilattributen kan ändras under körningen. [Läs mer om profiluppdatering efter en Wait-aktivitet](../building-journeys/wait-activity.md#profile-refresh)

* Använd aktiviteten **Villkor** i en resa för att skapa villkor baserat på målgruppsmedlemskap. [Lär dig hur du använder målgrupper i villkor](../building-journeys/condition-activity.md#using-a-segment).

* Använd aktiviteten **Målgruppskvalificering** för att få enskilda personer att komma in på eller gå framåt i resan baserat på Adobe Experience Platform målgruppsinkomster och utträden. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig hur du konfigurerar en målgruppsklassificeringsaktivitet](../building-journeys/audience-qualification-events.md).

  >[!NOTE]
  >
  >På grund av gruppbeskaffenheten hos målgrupper som skapats med kompositionsarbetsflöden, anpassad uppladdning eller Federated Audience Composition, kan du inte rikta in dessa målgrupper i en&quot;Audience Qualification&quot;-aktivitet. Endast målgrupper som skapats med segmentdefinitioner kan utnyttjas i den här aktiviteten.
