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
source-git-commit: d7ebba4144eeb5b29e9e6fa21afde06a7e520e07
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Målgruppsaktivering i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

I kampanjer och resor kan ni välja alla målgrupper som genereras med segmentdefinitioner, anpassad uppladdning, arbetsflöden för disposition eller Federated Audience Composition.

>[!AVAILABILITY]
>
>Användningen av målgrupper och attribut från målgruppssammansättning är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten. [Lär dig använda attribut för målgruppsberikning i Journey Optimizer](../audience/about-audiences.md#enrichment)

## Fördröjning för målgruppsaktivering {#activation}

Publiken är redo att användas i Journey Optimizer direkt efter att intaget har slutförts. Detta är vanligtvis inom en timme, men kan variera. Publiken som är resultatet av kompositionerna bör vara tillgänglig 24 timmar efter publiceringen.

## Anpassad uppladdning och sammanställning av externa målgrupper

Observera följande skyddsutkast för Custom Upload och Federated Audience Composition-målgrupper:

* **Stöd för förhandsgranskning och korrektur:** För närvarande stöds inte förhandsgranskning och korrektur för målgrupper som skapats med CSV-överföring eller sammanställning av federerade målgrupper. Tänk på detta när ni planerar era kampanjer.

* **Nya profiler:** Om det inte går att hitta någon matchning mellan en post och en UPS-profil skapas en ny tom profil. Den här profilen är kopplad till anrikningsattributen som lagras i datasjön. Eftersom den nya profilen är tom är målfält som vanligtvis används i Journey Optimizer (t.ex. personalEmail.address, mobilePhone.number) tomma och kan därför inte användas som mål.

  För att lösa detta kan du ange &quot;körningsfält&quot; (eller &quot;körningsadress&quot; beroende på kanal) i kanalkonfigurationen som &#39;identityMap&#39;. På så sätt säkerställs att det attribut som väljs som identitet när målgrupper skapas blir det som används för målgruppsanpassning i Journey Optimizer.

* **Aktiverade poster och identitetssammanfogning:** Alla poster i målgruppen aktiveras, inklusive eventuella dubbletter. Under nästa UPS-profilexport kommer dessa poster att genomgå identitetssammanfogning. Det innebär att antalet aktiverade poster kan skilja sig från antalet profiler efter identitetssammanfogning.

## Målgrupper i [!DNL Journey Optimizer]

Du kan utnyttja målgrupper i **[!DNL Journey Optimizer]** på olika sätt:

* Välj en målgrupp för en **kampanj**, där meddelandet skickas till alla personer som tillhör den valda målgruppen. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Läs målgruppsorganisation** i en resa för att få alla personer i målgruppen att komma in på resan och ta emot de meddelanden som ingår i din resa. Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en målgruppsaktivitet för läsning](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

  >[!NOTE]
  >
  >Alla resor som utnyttjar en målgrupp från målgruppskomposition eller anpassade uppladdningar i aktiviteten&quot;Läs målgrupp&quot; kommer att ha profilattribut som är lika färska som den senaste grupputvärderingen. Detta inkluderar samtycke/undertryckande under resan.

* Använd aktiviteten **Villkor** i en resa för att skapa villkor baserat på målgruppsmedlemskap. [Lär dig hur du använder målgrupper i villkor](../building-journeys/condition-activity.md#using-a-segment).

* Använd aktiviteten **Målgruppskvalificering** för att få enskilda personer att komma in på eller gå framåt i resan baserat på Adobe Experience Platform målgruppsinkomster och utträden. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig hur du konfigurerar en målgruppsklassificeringsaktivitet](../building-journeys/audience-qualification-events.md).

  >[!NOTE]
  >
  >På grund av gruppbeskaffenheten hos målgrupper som skapats med kompositionsarbetsflöden, anpassad uppladdning eller Federated Audience Composition, kan du inte rikta in dessa målgrupper i en&quot;Audience Qualification&quot;-aktivitet. Endast målgrupper som skapats med segmentdefinitioner kan utnyttjas i den här aktiviteten.
