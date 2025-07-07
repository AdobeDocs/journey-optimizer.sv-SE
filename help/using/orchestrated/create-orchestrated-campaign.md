---
solution: Journey Optimizer
product: journey optimizer
title: Skapa och schemalägg samordnade kampanjer med Journey Optimizer
description: Lär dig skapa och schemalägga en strukturerad kampanj med Adobe Journey Optimizer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 13da680d-fef8-4749-9190-8ca3d77b060a
source-git-commit: a19fe429d34a88c6159ab3b2b4dfa3768bcd24ad
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 0%

---


# Skapa och schemalägg en orkestrerad kampanj {#create-first-campaign}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | <b>[Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)</b><br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Skapa en orkestrerad kampanj i [!DNL Adobe Journey Optimizer] och konfigurera dess körningsschema för att styra när den startar och hur ofta den körs. Välj om du vill starta kampanjen direkt, vid ett specifikt datum och vid en viss tidpunkt eller om det ska ske regelbundet med flexibla schemaläggningsalternativ som dagliga, veckovisa eller månadsvisa frekvenser.

## Skapa kampanjen {#create}

>[!CONTEXTUALHELP]
>id="ajo_campaign_creation_workflow"
>title="Lista över samordnade kampanjer"
>abstract="Fliken **Orchestration** visar alla samordnade kampanjer. Klicka på namnet på en orkestrerad kampanj för att redigera den. Använd knappen **Skapa orkestrerad kampanj** för att lägga till en ny orkestrerad kampanj."

Så här skapar du en orkestrerad kampanj:

1. Gå till menyn **[!UICONTROL Campaigns]**, välj fliken **[!UICONTROL Orchestration]** och klicka på **[!UICONTROL Create campaign]**.

   ![](assets/inventory-create.png)

1. Ange ett namn och en beskrivning för kampanjen.

1. *(valfritt)* Använd fältet **[!UICONTROL Tags]** för att tilldela enhetliga Adobe Experience Platform-taggar till kampanjen. På så sätt kan ni enkelt klassificera dem och förbättra sökningen i den samordnade kampanjlistan. [Lär dig arbeta med taggar](../start/search-filter-categorize.md#tags).

1. Klicka på **[!UICONTROL Create]**.

Din samordnade kampanj har skapats och visas i den samordnade kampanjlistan. Du kan uppdatera dessa egenskaper när som helst genom att klicka på ikonen ![Kampanjinställningar](assets/do-not-localize/campaign-settings.svg) på arbetsytan för kampanjen.

## Schemalägg kampanjen {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_scheduler"
>title="Schemaläggare"
>abstract="Som kampanjansvarig kan ni schemalägga kampanjer att startas automatiskt vid specifika tidpunkter, vilket ger exakt timing och korrekta målgruppsdata för marknadsföringskommunikation."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_validity"
>title="Schemaläggarens giltighet"
>abstract="Du kan definiera en giltighetsperiod för schemaläggaren. Den kan vara permanent (standard) eller giltig till ett visst datum."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_options"
>title="Alternativ för schemaläggare"
>abstract="Definiera frekvensen för schemaläggaren. Den kan köras vid ett specifikt tillfälle, en eller flera gånger per dag, vecka eller månad."

Som standard startar samordnade kampanjer när de aktiveras manuellt och avslutas när deras associerade aktiviteter har körts. Om du vill fördröja genomförandet eller köra kampanjen med jämna mellanrum kan du definiera ett schema för kampanjen.

Tänk på följande metodtips när du planerar samordnade kampanjer för att säkerställa optimala prestanda och förväntat beteende:

* Schemalägg inte att en orkestrerad kampanj ska köras mer än var femtonde minut eftersom det kan påverka den totala systemprestandan negativt och skapa block i databasen.
* Om du vill skicka ett enbildsmeddelande i din orkestrerade kampanj kan du ange att det ska köras **En gång**.
* Om du vill skicka ett återkommande meddelande i din samordnade kampanj måste du använda alternativen **Schemaläggning** och ange körningsfrekvens. Den återkommande leveransaktiviteten tillåter inte att du definierar ett schema.

Så här konfigurerar du kampanjschemat:

1. Öppna kampanjen och klicka på knappen **[!UICONTROL As soon as possible]**.

   ![](assets/create-schedule.png)

1. Välj en körningsfrekvens för kampanjen och konfigurera sedan de tillgängliga alternativen. Inställningarna varierar beroende på vald frekvens:

   +++En

   Kör kampanjen en gång vid ett angivet datum och en viss tidpunkt.

   * **[!UICONTROL Date]**: Välj det datum då kampanjen ska köras.
   * **[!UICONTROL Time]**: Välj den tidpunkt då kampanjen ska köras.

+++

   +++Daily

   Kör kampanjen varje dag eller på valda dagar.

   * **[!UICONTROL Daily recurrence]**: Välj hur ofta kampanjen ska köras:
      * **[!UICONTROL Every day]**: Kör kampanjen varje veckodag, inklusive helger.
      * **[!UICONTROL On weekdays]**: Kör kampanjen endast från måndag till fredag.
      * **[!UICONTROL Through a specific period]**: Kör kampanjen dagligen inom ett definierat datumintervall (t.ex. från 1 juli till 15 juli). Kampanjen kommer inte att köras utanför det här intervallet.
      * **[!UICONTROL On selected days of the week]**: Kör kampanjen endast de angivna veckodagarna (t.ex. måndag, onsdag, fredag).

   * **[!UICONTROL Start time]**: Definiera den tid som kampanjen ska köras varje dag.

+++

   +++Flera gånger om dagen

   Kör kampanjen flera gånger inom samma dag. Du kan välja specifika tider eller ange en periodisk frekvens.

   * **[!UICONTROL Selected hours]**: Välj de tider som kampanjen ska köras och konfigurera den dagliga upprepningen (verkställs varje veckodag eller på vissa dagar).
   * **[!UICONTROL Periodic]**: Välj att köra kampanjen var n minut eller timme. Du kan också definiera tidsintervallet inom dagen när körningar tillåts.

+++

   +++Vecka

   Kör kampanjen varje vecka, med alternativ för specifika dagar.

   * **[!UICONTROL Frequency]**: Välj hur ofta kampanjen ska köras (t.ex. varje vecka, varannan vecka).
   * **[!UICONTROL Starting from date]**: Välj det datum då upprepningen ska börja.
   * **[!UICONTROL Daily recurrence]**: Välj specifika veckodagar för körning (t.ex. varje måndag och torsdag).
   * **[!UICONTROL Start time]**: Ange den tid som kampanjen ska köras på valda dagar.

+++

   +++Månad

   Kör kampanjen månadsvis, med alternativ för specifika dagar.

   * **[!UICONTROL Monthly recurrence]**: Välj om kampanjen ska köras varje månad eller endast under specifika månader.
   * **[!UICONTROL Daily recurrence]**:
      * **[!UICONTROL Every day]**: Kör kampanjen varje kalenderdag i månaden, inklusive helger.
      * **[!UICONTROL Last day of the month]**: Kör kampanjen endast den sista kalenderdagen i varje månad (t.ex. 31 januari 2018/29).
      * **[!UICONTROL Specific day of the month (e.g., 15th)]**: Kör kampanjen en angiven dag (t.ex. den 15:e varje månad).
      * **[!UICONTROL First/last, or nth day of the week]** (t.ex. första måndagen):      Kör kampanjen en angiven veckodag (t.ex. den 15 i varje vecka).
      * **[!UICONTROL Selected days of the week]**: Kör kampanjen på en angiven dag.

   * **[!UICONTROL Start time]**: Ange den tid som kampanjen ska köras.

+++

1. Använd inställningen **[!UICONTROL Validity period]** för att definiera ett specifikt start- och slutdatum, vilket begränsar kampanjens körning till ett tidsbegränsat fönster.

1. Klicka på knappen **[!UICONTROL Preview launch times]** om du vill förhandsgranska de exakta kommande körningsdatumen och körningstiderna baserat på den aktuella konfigurationen. Detta hjälper till att validera schemat före aktivering och säkerställer att kampanjen körs som förväntat.

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen. Om den initiala schemalagda tiden redan har passerat för återkommande kampanjer kommer kampanjerna att föras över till nästa tillgängliga tidsrymd enligt reglerna för återkommande kampanjer.

I följande exempel är aktiviteten konfigurerad så att den samordnade kampanjen körs två gånger per dag kl. 9 och 12 varje dag i veckan från 1 oktober 2025 till 1 januari 2026.

![Schemaläggaren har konfigurerats att köra kampanjen två gånger om dagen kl. 9 och 12:00](assets/scheduler-sample.png){width="50%" align="left"}

## Nästa steg {#next}

När kampanjinställningarna och kampanjschemat har konfigurerats är du redo att börja organisera de olika uppgifter som ska utföras. [Lär dig att samordna kampanjaktiviteter](../orchestrated/orchestrate-activities.md)
