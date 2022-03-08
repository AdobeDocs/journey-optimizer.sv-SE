---
title: Tillåtelselista
description: Lär dig hur du använder tillåtelselista.
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
exl-id: 70ab8f57-c132-4de1-847b-11f0ab14f422
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# Tillåtelselista {#allow-list}

Nu går det att definiera en specifik sändningssäker lista på [sandlåda](../administration/sandboxes.md) för att ha en säker miljö för testningsändamål. I icke-produktionssituationer, där misstag kan inträffa, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder.

Med tillåtelselista kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som ska ha behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda. Detta kan förhindra att du av misstag skickar e-post till verkliga kundadresser när du befinner dig i en testmiljö.

>[!CAUTION]
>
>Den här funktionen är **not** finns i produktionssandlådor. Det gäller bara för e-postkanalen.

## Aktivera tillåtelselista {#enable-allow-list}

Om du vill aktivera tillåtelselista i en icke-produktionssandlåda måste du uppdatera de allmänna inställningarna med motsvarande API-slutpunkt i tjänsten för meddelandeförinställningar.

* Med detta API kan du när som helst inaktivera funktionen.

* Du kan uppdatera tillåtelselista innan eller efter att du har aktiverat funktionen.

* Logiken i tillåtelselista gäller när funktionen är aktiverad **och** om tillåtelselista är **not** tom. Läs mer i [det här avsnittet](#logic).

<!--To enable this feature on a non-production sandbox, update the allowed list so that it is no longer empty. To disable it, clear up the allowed list so that it is again empty.

Learn more on the allowed list logic in this section.
-->

>[!NOTE]
>
>När det här alternativet är aktiverat respekteras funktionen tillåtelselista vid körning av resor, men också vid testning av meddelanden med [korrektur](preview.md#send-proofs) och testa resor med [testläge](../building-journeys/testing-the-journey.md).

## Lägg till enheter i tillåtelselista {#add-entities}

Om du vill lägga till nya e-postadresser eller domäner i tillåtelselista för en viss sandlåda måste du anropa API:t för inaktivering med `ALLOWED` värdet för `listType` -attribut. Exempel:

![](assets/allow-list-api.png)

Du kan utföra **Lägg till**, **Ta bort** och **Hämta** åtgärder.

>[!NOTE]
>
>Tillåtelselista kan innehålla upp till 1 000 poster.

Läs mer om hur du gör API-anrop i [Adobe Experience Platform API:er](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html)Referensdokumentation för {target=&quot;_blank&quot;}.

## Tillåtelselista logik {#logic}

När tillåtelselista är **tom**, används inte logiken i tillåtelselista. Det innebär att du kan skicka e-postmeddelanden till alla profiler, förutsatt att de inte finns på [utelämningslista](suppression-list.md).

När tillåtelselista är **inte tom** används tillåtelselista-logiken:

* Om en enhet **inte på tillåtelselista**, och inte i listan över inaktiveringar, kommer motsvarande mottagare inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Not allowed]**.

* Om en enhet **på tillåtelselista**, och inte i listan över inaktiveringar, kan e-postmeddelandet skickas till motsvarande mottagare. Om företaget också finns på [utelämningslista](suppression-list.md), kommer motsvarande mottagare inte att få e-postmeddelandet, eftersom orsaken är **[!UICONTROL Suppressed]**.

>[!NOTE]
>
>Profilerna med **[!UICONTROL Not allowed]** status utelämnas under meddelandesändningsprocessen. Därför är **Reserapporter** visar att dessa profiler har flyttats genom resan ([Läs segment](../building-journeys/read-segment.md) och [Meddelande](../building-journeys/journeys-message.md) verksamhet), **E-postrapporter** kommer inte att inkludera dem i **[!UICONTROL Sent]** mätvärden när de filtreras ut innan e-postmeddelanden skickas.
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
