---
title: Tillåtelselista
description: Lär dig hur du använder tillåtelselista.
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
source-git-commit: 07ef1281cff9d12c39917aecf408b2405efb3fc7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 1%

---

# Tillåtelselista {#allow-list}

Det går att definiera en specifik sändningssäker lista på [sandlåda](../administration/sandboxes.md) för att ha en säker miljö för testning.

På en icke-produktionsinstans, där fel kan uppstå, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder.

>[!NOTE]
>
>Den här funktionen är tillgänglig i sandlådor för produktion och icke-produktion.

Med tillåtelselista kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som ska ha behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda. Detta kan förhindra att du av misstag skickar e-post till verkliga kundadresser när du befinner dig i en testmiljö.

>[!CAUTION]
>
>Den här funktionen gäller endast för e-postkanalen.

## Gå till tillåtelselista {#access-allowed-list}

Om du vill få tillgång till en detaljerad lista över tillåtna e-postadresser och domäner går du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** och markera **[!UICONTROL Allowed list]**.

>[!CAUTION]
>
>Tillstånd att visa, exportera och hantera tillåtelselista är begränsade till [Reseadministratörer](../administration/ootb-product-profiles.md#journey-administrator). Läs mer om hantering [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).

## Aktivera tillåtelselista {#enable-allow-list}

Följ stegen nedan för att aktivera tillåtelselista.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Allow list]**-menyn.

1. Klicka på **[!UICONTROL Edit]**.

1. Välj **[!UICONTROL Enable allowed list]**.

1. Klicka på **[!UICONTROL Save]**. Tillåtelselista är aktiverat.

Logiken i tillåtelselista gäller när funktionen är aktiverad. Läs mer i [det här avsnittet](#logic).

>[!NOTE]
>
>När det här alternativet är aktiverat respekteras funktionen tillåtelselista vid körning av resor, men också vid testning av meddelanden med [korrektur](../design/preview.md#send-proofs) och testa resor med [testläge](../building-journeys/testing-the-journey.md).

## Lägg till enheter i tillåtelselista {#add-entities}

Om du vill lägga till nya e-postadresser eller domäner i tillåtelselista för en viss sandlåda kan du använda en [API-anrop](#api-call-allowed-list).

>[!NOTE]
>
>Tillåtelselista kan innehålla upp till 1 000 poster.

### Lägga till entiteter med ett API-anrop {#api-call-allowed-list}

Om du vill fylla tillåtelselista kan du även anropa API:t för inaktivering med `ALLOWED` värdet för `listType` -attribut. Exempel:

![](assets/allow-list-api.png)

Du kan utföra **Lägg till**, **Ta bort** och **Hämta** åtgärder.

Läs mer om hur du gör API-anrop i [Adobe Experience Platform API:er](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html)Referensdokumentation för {target=&quot;_blank&quot;}.

## Tillåtelselista logik {#logic}

När tillåtelselista är [aktiverad](#enable-allow-list), gäller följande logik:

* Om tillåtelselista är **tom**, skickas inget e-postmeddelande.

* Om en enhet **på tillåtelselista**, och inte i listan över inaktiveringar, kan e-postmeddelandet skickas till motsvarande mottagare. Om företaget också finns på [utelämningslista](../reports/suppression-list.md), kommer motsvarande mottagare inte att få e-postmeddelandet, eftersom orsaken är **[!UICONTROL Suppressed]**.

* Om en enhet **inte på tillåtelselista** (och inte i listan över inaktiveringar) kommer motsvarande mottagare inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Not allowed]**.

>[!NOTE]
>
>Profilerna med **[!UICONTROL Not allowed]** status utelämnas under meddelandesändningsprocessen. Därför är **Reserapporter** visar att dessa profiler har flyttats genom resan ([Läs segment](../building-journeys/read-segment.md) och [meddelandeaktiviteter](../building-journeys/journeys-message.md)), **E-postrapporter** kommer inte att inkludera dem i **[!UICONTROL Sent]** mätvärden när de filtreras ut innan e-postmeddelanden skickas.
>
>Läs mer på [Live-rapport](../reports/live-report.md) och [Global rapport](../reports/global-report.md).

## Uteslutningsrapportering {#reporting}

När den här funktionen är aktiverad i en icke-produktionssandlåda kan du hämta e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. Om du vill göra det kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;} för att göra API-anrop nedan.

För att få **antal e-postmeddelanden** som inte skickades eftersom mottagarna inte var i tillåtelselista använder du följande fråga:

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
