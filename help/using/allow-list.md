---
title: Tillåtelselista
description: Lär dig hur du använder tillåtelselista.
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
source-git-commit: 2edb3535c50f83d18ce4d6429a6d76f44b694ac6
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Tillåtelselista {#allow-list}

Det är nu möjligt att definiera en specifik sändningssäker lista på [sandbox](administration/sandboxes.md)-nivå för att ha en säker miljö för testningsändamål. I icke-produktionssituationer, där misstag kan inträffa, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder.

Med tillåtelselista kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som ska ha behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda. Detta kan förhindra att du av misstag skickar e-post till verkliga kundadresser när du befinner dig i en testmiljö.

>[!CAUTION]
>
>Den här funktionen är **inte** tillgänglig i produktionssandlådor. Det gäller bara för e-postkanalen.

## Aktivera tillåtelselista {#enable-allow-list}

Om du vill aktivera tillåtelselista i en icke-produktionssandlåda måste du uppdatera de allmänna inställningarna med motsvarande API-slutpunkt i tjänsten för meddelandeförinställningar.

* Med detta API kan du när som helst inaktivera funktionen.

* Du kan uppdatera tillåtelselista innan eller efter att du har aktiverat funktionen.

* Logiken i tillåtelselista gäller när funktionen är aktiverad **och** om tillåtelselista är **inte** tom. Läs mer i [det här avsnittet](#logic).

<!--To enable this feature on a non-production sandbox, update the allowed list so that it is no longer empty. To disable it, clear up the allowed list so that it is again empty.

Learn more on the allowed list logic in this section.
-->

>[!NOTE]
>
>När det här alternativet är aktiverat respekteras funktionen tillåtelselista vid körning av resor, men också när du testar meddelanden med [korrektur](preview.md#send-proofs) och testar resor med [testläge](building-journeys/testing-the-journey.md).

## Lägg till enheter i tillåtelselista {#add-entities}

Om du vill lägga till nya e-postadresser eller domäner i tillåtelselista för en viss sandlåda måste du anropa API:t för inaktivering med `ALLOWED`-värdet för attributet `listType`. Exempel:

![](assets/allow-list-api.png)

Du kan utföra åtgärderna **Lägg till**, **Ta bort** och **Hämta**.

>[!NOTE]
>
>Tillåtelselista kan innehålla upp till 1 000 poster.

<!--
Learn more on making these API calls in the API reference documentation.
Found this link in Experience Platform documentation, but may not be the final one: (https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en).-->

## Tillåtelselista logik {#logic}

<!-- When the allowed list is enabled (enable-allow-list) at the sandbox level using the API call above, the following applies.-->

När tillåtelselista är **tom** används inte logiken för tillåtelselista. Det innebär att du kan skicka e-postmeddelanden till alla profiler, förutsatt att de inte finns med i [listan](suppression-list.md).

När tillåtelselista är **inte tom** används tillåtelselista-logiken:

* Om en entitet är **inte på tillåtelselista**, och inte på listan över inaktiveringar, kommer motsvarande mottagare inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Not allowed]**.

* Om en entitet är **på tillåtelselista**, och inte på listan över inaktiveringar, kan e-postmeddelandet skickas till motsvarande mottagare. Om entiteten också finns med i [listan](suppression-list.md) kommer den motsvarande mottagaren inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Suppressed]**.

>[!NOTE]
>
>Profilerna med **[!UICONTROL Not allowed]**-status exkluderas under meddelandesändningsprocessen. Samtidigt som **reseservrapporterna** visar dessa profiler som om de har flyttats genom resan ([Läs segment](building-journeys/read-segment.md) och [Meddelande](building-journeys/journeys-message.md)-aktiviteter), kommer **e-postrapporterna** inte att inkludera dem i **[!UICONTROL Sent]**-måtten eftersom de filtreras ut innan e-postmeddelandet skickas.
>
>Läs mer i [Live-rapporten](reports/live-report.md) och [Global Report](reports/global-report.md).

## Uteslutningsrapportering {#reporting}

När den här funktionen är aktiverad i en icke-produktionssandlåda kan du hämta e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. För att göra detta kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html) för att göra API-anropen nedan.

Använd följande fråga om du vill hämta **antalet e-postmeddelanden** som inte skickades eftersom mottagarna inte var i tillåtelselista:

```
SELECT count(distinct _id) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID = '<MESSAGE_EXECUTION_ID>' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

Använd följande fråga om du vill hämta **listan över e-postadresser** som inte skickades eftersom mottagarna inte var i tillåtelselista:

```
SELECT distinct(_experience.customerJourneyManagement.emailChannelContext.address) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID IS NOT NULL AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

