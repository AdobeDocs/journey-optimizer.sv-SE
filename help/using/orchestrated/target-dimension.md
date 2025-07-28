---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en måldimension
description: Lär dig mapp ett relationsschema till kundprofilen
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 2479c109-cd6f-407e-8a53-77e4477dc36f
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Konfigurera en måldimension {#configuration}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en orkestrerad kampanj](gs-campaign-creation.md)<br/><br/>[Konfigurera en måldimension](target-dimension.md) | <b>[Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)</b><br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++


<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

I många fall kan en enda kundprofil vara länkad till flera närliggande enheter, som prenumerationer, serviceavtal eller enheter, var och en med sin egen unika identifierare och kommunikationsbehov.

Med **samordnade kampanjer** kan du nu utforma och leverera riktad kommunikation på entitetsnivå med **Adobe Experience Platform relationsschemafunktioner**. På så sätt kan ni segmentera, personalisera och rapportera per enhet i stället för per mottagare.

## Skapa en måldimension {#targeting-dimension}

En enda kundprofil kan associeras med flera relaterade enheter, som kontrakt, enheter eller prenumerationer, som var och en har sin egen unika identifierare. Med den här inställningen kan du målinrikta, segmentera och rapportera varje enhet individuellt.

Börja med att konfigurera kampanjsamordning genom att mappa ett relationsschema till kundprofilen.

1. Från **[!UICONTROL Administration]** öppnar du menyn **[!UICONTROL Configurations]** och väljer **[!UICONTROL Campaign Target Dimension]**.

   ![](assets/target-dimension-1.png)

1. Klicka på **[!UICONTROL Create]** för att börja skapa **[!UICONTROL Targeting dimension]**.

1. Välj det [tidigare konfigurerade &#x200B; ](gs-schemas.md) i listrutan.

1. Välj den **[!UICONTROL Identity value]** som representerar den enhet som du vill ha som mål.

   I det här exemplet är kundprofilen länkad till flera prenumerationer, som vart och ett representeras av en unik `crmID` i `Recipient`-schemat. Genom att ange att **[!UICONTROL Target Dimension]** ska använda `Recipient`-schemat och dess `crmID`-identitet kan du skicka meddelanden på prenumerationsnivå i stället för till huvudkundprofilen, så att varje kontrakt eller rad får ett eget anpassat meddelande.

   [Läs mer i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)

   ![](assets/target-dimension-2.png)

1. Klicka på **[!UICONTROL Save]** för att slutföra konfigurationen.

När du har konfigurerat **[!UICONTROL Target Dimension]** fortsätter du med att skapa och konfigurera **[!UICONTROL Channel Configuration]** och definierar motsvarande **[!UICONTROL Execution Details]**.

## Konfigurera kanalkonfigurationen {#channel-configuration}

När du har konfigurerat din **[!UICONTROL Target Dimension]** måste du konfigurera din e-post eller ditt SMS **[!UICONTROL Channel Configuration]** och definiera rätt **[!UICONTROL Execution Details]**. Detta garanterar att meddelanden skickas med rätt identitet och mållogik.

1. Börja med att skapa och konfigurera **[!UICONTROL Channel configuration]**.

   Du kan även uppdatera en befintlig **[!UICONTROL Channel configuration]**.

   ➡️ [Följ stegen som beskrivs på den här sidan](../email/surface-personalization.md)

1. Gå till fliken **[!UICONTROL Execution details]** från avsnittet **[!UICONTROL Channel configuration]** i **[!UICONTROL Orchestrated campaigns]**.

   ![](assets/target-dimension-3.png)

1. Klicka på **[!UICONTROL Enabled]** för att göra den kompatibel med orkestrerade kampanjer.

1. Välj leveranssätt:

   * **[!UICONTROL Target Dimension]**: skicka till den primära entiteten, t.ex. mottagare.

   * **[!UICONTROL Target + Secondary Dimension]**: skicka med både primära och sekundära entiteter, t.ex. mottagare + kontrakt.

1. Välj i listrutan din [tidigare skapade Target Dimension](#targeting-dimension).

   ![](assets/target-dimension-4.png)

1. Under avsnittet **[!UICONTROL Execution Address]** väljer du vilken **[!UICONTROL Source]** som ska användas för att hämta leveransadressen, till exempel e-postadressen eller telefonnumret:

   * **[!UICONTROL Profile]**: Välj det här alternativet om leveransadressen, t.ex. e-postadressen, lagras direkt i huvudkundprofilen.

     Användbart när du skickar meddelanden till huvudkunden, inte till en specifik associerad enhet.

   * **[!UICONTROL Target Dimension]**: Välj det här alternativet om leveransadressen lagras i den relaterade entiteten, t.ex. en mottagare eller en prenumeration.

     Användbart när varje mottagare har en egen leveransadress, till exempel en annan e-postadress eller ett annat telefonnummer.

1. I fältet **[!UICONTROL Delivery address]** klickar du på ![redigeringsikonen](assets/do-not-localize/edit.svg) för att välja det specifika fält som ska användas för meddelandeleveransen.

   ![](assets/target-dimension-4.png)

1. När du har konfigurerat klickar du på **[!UICONTROL Submit]**.

Din kanal är nu klar att användas med **samordnade kampanjer**, och meddelanden levereras enligt den valda måldimensionen.
