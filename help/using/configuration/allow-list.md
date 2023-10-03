---
solution: Journey Optimizer
product: journey optimizer
title: Tillåtelselista
description: Lär dig använda tillåtelselista
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
keywords: tillåtelselista, lista, säker, konfiguration
exl-id: 70ab8f57-c132-4de1-847b-11f0ab14f422
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 2%

---

# Tillåtelselista {#allow-list}

Det går att definiera en specifik sändningssäker lista på [sandlåda](../administration/sandboxes.md) nivå.

Med det här tillåtelselista kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som har behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda.

>[!NOTE]
>
>Den här funktionen är tillgänglig i sandlådor för produktion och icke-produktion.

På en icke-produktionsinstans, där fel kan uppstå, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till riktiga kundadresser, och tillhandahåller därför en säker miljö för testningsändamål.

När tillåtelselista är aktivt men tomt går ingen post ut. Om du råkar ut för något större problem kan du använda den här funktionen för att stoppa all utgående kommunikation från [!DNL Journey Optimizer] tills du åtgärdar problemet. Läs mer på [tillåtelselista logik](#logic).

>[!CAUTION]
>
>Den här funktionen gäller endast för e-postkanalen.

## Gå till tillåtelselista {#access-allowed-list}

Om du vill få tillgång till en detaljerad lista över tillåtna e-postadresser och domäner går du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** och markera **[!UICONTROL Allowed list]**.

![](assets/allow-list-access.png)

>[!CAUTION]
>
>Tillstånd att visa, exportera och hantera tillåtelselista är begränsade till [Reseadministratörer](../administration/ootb-product-profiles.md#journey-administrator). Läs mer om hantering [!DNL Journey Optimizer] användarrättigheter i [det här avsnittet](../administration/permissions-overview.md).

Om du vill exportera tillåtelselista som en CSV-fil väljer du **[!UICONTROL Download CSV]** -knappen.

Använd **[!UICONTROL Delete]** om du vill ta bort en post permanent.

Du kan söka efter e-postadresser eller domäner och filtrera på **[!UICONTROL Address type]**. När du har valt det här alternativet kan du rensa filtret som visas högst upp i listan.

![](assets/allowed-list-filtering-example.png)

## Aktivera tillåtelselista {#enable-allow-list}

Följ stegen nedan för att aktivera tillåtelselista.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Allow list]**-menyn.

1. Markera växlingsknappen.

   ![](assets/allow-list-edit.png)

1. Välj **[!UICONTROL Activate allowed list]**. Tillåtelselista är nu aktivt.

   ![](assets/allow-list-enable.png)

   >[!NOTE]
   >
   >När du har aktiverat tillåtelselista finns det en 5-minuterslatens för att den ska börja gälla under dina resor och kampanjer.

Logiken i tillåtelselista gäller när funktionen är aktiv. Läs mer i [det här avsnittet](#logic).

>[!NOTE]
>
>När den är aktiverad respekteras funktionen tillåtelselista vid körning av resor, men också vid testning av meddelanden med [korrektur](../email/preview.md#send-proofs) och testa resor med [testläge](../building-journeys/testing-the-journey.md).

## Inaktivera tillåtelselista {#deactivate-allow-list}

Följ stegen nedan för att inaktivera tillåtelselista.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Allow list]**-menyn.

1. Markera växlingsknappen.

   ![](assets/allow-list-edit-active.png)

1. Välj **[!UICONTROL Deactivate allowed list]**. Tillåtelselista är inte längre aktivt.

   ![](assets/allow-list-deactivate.png)

   >[!NOTE]
   >
   >När du har inaktiverat tillåtelselista finns det en 5-minuterslatens för att den ska börja gälla under dina resor och kampanjer.

Tillåtelselista-logiken gäller inte när funktionen är inaktiverad. Läs mer i [det här avsnittet](#logic).

## Lägg till enheter i tillåtelselista {#add-entities}

Om du vill lägga till nya e-postadresser eller domäner i tillåtelselista för en viss sandlåda kan du antingen [fylla i listan manuellt](#manually-populate-list)eller använda [API-anrop](#api-call-allowed-list).

>[!NOTE]
>
>Tillåtelselista kan innehålla upp till 1 000 poster.

### Fyll i tillåtelselista manuellt {#manually-populate-list}

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_add_header"
>title="Lägg till adresser eller domäner i tillåtelselista"
>abstract="Du kan lägga till nya e-postadresser eller domäner manuellt till tillåtelselista genom att markera dem en i taget."

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_add"
>title="Lägg till adresser eller domäner i tillåtelselista"
>abstract="Du kan lägga till nya e-postadresser eller domäner manuellt till tillåtelselista genom att markera dem en i taget."

Du kan fylla i [!DNL Journey Optimizer] tillåtelselista genom att lägga till en e-postadress eller en domän via användargränssnittet.

>[!NOTE]
>
>Du kan bara lägga till en e-postadress eller domän åt gången.

Följ stegen nedan för att göra detta.

1. Markera knappen **[!UICONTROL Add email or domain]**.

   ![](assets/allowed-list-add-email.png)

1. Välj adresstyp: **[!UICONTROL Email address]** eller **[!UICONTROL Domain address]**.

1. Ange den e-postadress eller domän som du vill skicka e-post till.

   >[!NOTE]
   >
   >Se till att du anger en giltig e-postadress (till exempel abc@company.com) eller domän (till exempel abc.company.com).

1. Ange en orsak om det behövs.

   ![](assets/allowed-list-add-email-address.png)

   >[!NOTE]
   >
   >Alla ASCII-tecken mellan 32 och 126 tillåts i **[!UICONTROL Reason]** fält. Den fullständiga listan finns på [den här sidan](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"} till exempel.

1. Klicka på **[!UICONTROL Submit]**.

### Lägga till entiteter med ett API-anrop {#api-call-allowed-list}

Om du vill fylla tillåtelselista kan du även anropa API:t för inaktivering med `ALLOWED` värdet för `listType` -attribut. Exempel:

![](assets/allow-list-api.png)

Du kan utföra **Lägg till**, **Ta bort** och **Hämta** åtgärder.

Läs mer om hur du gör API-anrop i [Adobe Experience Platform API:er](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html){target="_blank"} referensdokumentation.

## Ladda ned tillåtelselista {#download-allowed-list}

Om du vill exportera tillåtelselista som en CSV-fil följer du stegen nedan:

1. Markera knappen **[!UICONTROL Download CSV]**.

   ![](assets/allowed-list-download-csv.png)

1. Vänta tills filen har skapats.

   ![](assets/allowed-list-download-generate.png)

   >[!NOTE]
   >
   >Hämtningstiden beror på filstorleken, vilket innebär antalet adresser som finns på tillåtelselista.
   >
   >En nedladdningsbegäran kan bearbetas i taget för en viss sandlåda.

1. När filen har skapats får du ett meddelande. Klicka på klockikonen överst till höger på skärmen för att visa den.

1. Klicka på själva meddelandet för att hämta filen.

   ![](assets/allowed-list-download-notification.png)

   >[!NOTE]
   >
   >Länken gäller i 24 timmar.

## Tillåtelselista logik {#logic}

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_logic"
>title="Hantera tillåtelselista"
>abstract="När tillåtelselista är aktiverat kommer endast de mottagare som ingår i tillåtelselista att få e-postmeddelanden från den här sandlådan. När den är inaktiverad får alla mottagare e-post."

När tillåtelselista är [aktiv](#enable-allow-list), gäller följande logik:

* Om tillåtelselista är **tom**, skickas inget e-postmeddelande.

* Om en enhet **på tillåtelselista**, och inte i listan över inaktiveringar, skickas e-postmeddelandet till motsvarande mottagare. Om företaget också finns på [utelämningslista](../reports/suppression-list.md), kommer motsvarande mottagare inte att få e-postmeddelandet, eftersom orsaken är **[!UICONTROL Suppressed]**.

* Om en enhet **inte på tillåtelselista** (och inte i listan över inaktiveringar) kommer motsvarande mottagare inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Not allowed]**.

>[!NOTE]
>
>Profilerna med **[!UICONTROL Not allowed]** status exkluderas under meddelandeprocessen. Därför är **Reserapporter** visar att dessa profiler har flyttats genom resan ([Läs målgrupp](../building-journeys/read-audience.md) och [meddelandeaktiviteter](../building-journeys/journeys-message.md)), **E-postrapporter** inkluderar dem inte i **[!UICONTROL Sent]** mätvärden när de filtreras ut innan e-postmeddelanden skickas.
>
>Läs mer på [Live-rapport](../reports/live-report.md) och [Global rapport](../reports/global-report.md).

När tillåtelselista är [inaktiverad](#deactivate-allow-list), skickas alla e-postmeddelanden som du skickar från den aktuella sandlådan till alla mottagare (förutsatt att de inte finns med i listan över inaktiveringar), inklusive riktiga kundadresser.

## Uteslutningsrapportering {#reporting}

När tillåtelselista är aktivt kan du hämta e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. Om du vill göra det kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target="_blank"} för att göra API-anrop nedan.

För att få **antal mejl** som inte skickades eftersom mottagarna inte var i tillåtelselista använder du följande fråga:

```sql
SELECT count(distinct _id) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID = '<MESSAGE_EXECUTION_ID>' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

För att få **lista med e-postadresser** som inte skickades eftersom mottagarna inte var i tillåtelselista använder du följande fråga:

```sql
SELECT distinct(_experience.customerJourneyManagement.emailChannelContext.address) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID IS NOT NULL AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```
