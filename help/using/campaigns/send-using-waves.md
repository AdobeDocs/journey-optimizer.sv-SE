---
solution: Journey Optimizer
product: journey optimizer
title: Skicka med vågor
description: Schemalägg utgående kampanjmeddelanden som ska levereras i kontrollerade batchar över tid. Påfyllnadssändning stöder leverans och bidrar till att upprätthålla avsändarens anseende.
feature: Campaigns
topic: Campaign scheduling
role: User
level: Intermediate
keywords: vågor, batchar, schema, kampanj, resa, leveransbarhet
source-git-commit: 6c509ef134c4240b243d255fd1ab7ec6bb062bf0
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Skicka med vågor i kampanjer {#send-using-waves}

Du kan dela upp leveransen av utgående kampanjmeddelanden i flera omgångar (påfyllnader) och schemalägga dem över tid. Wave-sändning hjälper till att balansera belastningen, undvika överväldigande system längre fram i kedjan (t.ex. callcenters eller landningssidor) och supporttjänster och avsändarens anseende - särskilt för stora volymer.

<!--
>[!CAUTION]
>
>Wave sending applies to **outbound** actions only (Email, SMS, Push, Direct mail).-->

Med Journey Optimizer kan du definiera antalet vågor, deras storlek (som en procentandel av publiken eller som absoluta tal) och när varje våg körs.

## Begränsningar och skyddsräcken {#limitations-guardrails}

* Påfyllnadssändning gäller endast för **utgående** åtgärder (e-post, SMS, push, direktreklam).
* Du måste definiera minst **2 vågor** och du kan lägga till upp till **10 vågor**.
* Det minsta intervallet mellan början av två vågor är **30 minuter**.
* Påfyllnadsstarten får inte vara före kampanjens början eller tidigare.

## Konfigurera påfyllnadssändning {#configure-wave-sending}

Följ stegen nedan för att konfigurera hur och när påfyllnader ska skickas i en kampanj.

1. Skapa eller öppna en [åtgärdskampanj](create-campaign.md) som innehåller en utgående åtgärd (till exempel E-post, SMS, push).

1. Välj **[!UICONTROL Schedule]** på fliken **[!UICONTROL Deliver campaign actions in waves]** i kampanjen.

   ![](assets/campaign-wave-option.png){width="100%"}

   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Deliver campaign actions in waves]** visas bara när en utgående åtgärd har valts på kampanjens **[!UICONTROL Actions]**-flik. [Läs mer](campaign-action.md)

1. Ange antalet påfyllnader som du vill skicka (till exempel 4).

   >[!NOTE]
   >
   >Du måste definiera minst 2 vågor och kan lägga till upp till 10 vågor.

1. Välj hur du vill definiera vågstorlek och tidsinställning enligt nedan.

### Lika vågor {#equal-waves}

Som standard delas målgruppen upp i vågor av samma storlek. Schemalägg tiden för den första vågen och ange ett fast intervall mellan starten av varje våg (till exempel 2 timmar).

![](assets/campaign-equal-waves.png){width="80%"}

>[!NOTE]
>
>Det minsta intervallet mellan början av två vågor är **30 minuter**.

Systemet schemalägger sedan efterföljande vågor automatiskt (till exempel den första vågen klockan 9:00, den andra klockan 11:00, den tredje klockan 1:00 och den fjärde klockan 3:00).

### Anpassad distribution {#custom-distribution}

Välj alternativet **[!UICONTROL Custom distribution]** om du vill definiera storleken för varje våg som en procentandel av den totala publiken (till exempel 15 %, 20 %, 25 %, 40 %).

![](assets/campaign-wave-percentage.png){width="80%"}

>[!NOTE]
>
>Summan för alla vågor måste vara 100 %. Om så inte är fallet visas ett varningsmeddelande.<!--are the waves actually sent or does the system prevent user from saving the campaign?-->

Välj **[!UICONTROL Numbers]** om du vill definiera storleken på varje våg som ett absolut antal profiler (till exempel 10 000; 50 000).

![](assets/campaign-wave-numbers.png){width="80%"}

>[!NOTE]
>
>När du använder siffror validerar systemet inte att summan täcker hela målgruppen. Du måste se till att vågstorlekarna täcker den målgrupp du tänker skicka till. Läs mer i [Vanliga frågor](#faq).

### Anpassat schema {#custom-schedule}

Välj **[!UICONTROL Schedule each wave]** om du vill definiera ett specifikt startdatum och en specifik starttid för varje påfyllnad. Vågor behöver inte vara jämnt fördelade (t.ex. 09:00, 11:00 AM, 5:00 PM, 8:30 PM).

![](assets/campaign-wave-custom-schedule.png){width="80%"}

>[!NOTE]
>
>Det minsta intervallet mellan början av två vågor är **30 minuter**.

## Användningsfall {#use-cases}

Wave-sändning hjälper er att styra när och hur många meddelanden som skickas ut, vilket kan förbättra leveransmöjligheterna, skydda avsändarens anseende och anpassa meddelandena efter din driftskapacitet. Använd vågor i följande scenarier:

* **Anropscenter eller svarshantering:** Begränsa hur många meddelanden som skickas per dag eller per timme så att underordnade team (t.ex. kundtjänst) kan hantera svar. Skicka t.ex. 20 meddelanden per dag för att matcha kapaciteten för kundtjänst.

  ![](assets/campaign-waves-ex-call-center.png){width="75%"}

* **Hög volym och slutbarhet:** Undvik att skicka en mycket stor kampanj i ett enda försök. Sprid leveransen över tid för att bevara avsändarens rykte och minska risken för att flaggas som skräppost.

  ![](assets/campaign-waves-ex-high-volume.png){width="75%"}

* **Rampup:** När du använder en ny plattform eller IP-adress ökar du volymen gradvis (till exempel 10 % i den första vågen, sedan 15 %, 20 % och så vidare) för att gradvis bygga upp anseendet.

  ![](assets/campaign-waves-ex-ramp-up.png){width="75%"}

## Vanliga frågor och svar {#faq}

+++ Vad händer om summan av vågstorlekarna inte motsvarar den totala publiken?

* Om summan av dina påfyllnadsstorlekar **överstiger** målgruppen (du schemalägger till exempel 100 000 i den första påfyllnaden för en målgrupp på 100 000), kommer den första påfyllnaden att skickas till hela målgruppen och de återstående påfyllnaderna har ingen kvar att skicka till - de kommer inte att köras.
* Om summan **är mindre än** än målgruppen (du definierar t.ex. fyra vågor på totalt 40 000 profiler för en målgrupp på 100 000), kommer endast de profiler som ingår i dessa vågor att få meddelandet. Resten av publiken får inte meddelandet och kommer inte att provas igen i senare vågor.

+++

+++ Kan jag tilldela olika segment eller kriterier till enskilda vågor?

Du kan bara definiera storlek och tidpunkt för vågor. Mottagarvalet är detsamma för hela kampanjen. Du kan inte tilldela olika segment eller villkor till enskilda påfyllnader.

+++

## Nästa steg {#next}

* [Schemalägg åtgärdskampanjen](campaign-schedule.md) - ange startdatum, slutdatum, frekvens och hastighetskontroll.
* [Granska och aktivera kampanjen](review-activate-campaign.md) - kontrollera kampanjen och publicera den.
