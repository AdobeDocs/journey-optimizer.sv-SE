---
solution: Journey Optimizer
product: journey optimizer
title: Arkiveringsstöd i Journey Optimizer
description: Lär dig arkivera meddelanden
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: arkiv, meddelanden, HIPAA, BCC, e-post
exl-id: 186a5044-80d5-4633-a7a7-133e155c5e9f
source-git-commit: d1fd0b60ae60c2642108a1eb308564c9d04f5f9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 1%

---

# Stöd för arkivering {#archiving-support}

## Arkivera meddelanden {#about-archiving}

Regler som HIPAA kräver att [!DNL Journey Optimizer] ska tillhandahålla ett sätt att arkivera meddelanden som skickas till enskilda personer. Om era kunder gör anspråk bör de ha möjlighet att få en kopia av det skickade meddelandet för verifieringsändamål.

* För e-postkanalen har [!DNL Journey Optimizer] en inbyggd e-postfunktion för BCC. [Läs mer](#bcc-email)

* För alla kanaler kan du dessutom använda fältet Template i **Entity Dataset** som innehåller information om de icke-personliga meddelandemallarna. Exportera datauppsättningen med det här fältet om du vill spara metadata som vem som skickade meddelandet, till vem och när. Observera att personaliserade data inte exporteras - endast mallen (meddelandets format och struktur) beaktas. [Läs mer](../data/datasets-query-examples.md#entity-dataset)

>[!NOTE]
>
>[!DNL Journey Optimizer] har inte stöd för SMS-arkiveringskrav. Om du vill ha dedikerad arkiveringssupport kan du arbeta med din SMS-leverantör (Sinch, Infobip eller Twilio).

## Så här använder du BCC för e-post {#bcc-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_bcc"
>title="Definiera en e-postadress för hemlig kopia"
>abstract="Du kan behålla en kopia av skickade e-postmeddelanden genom att skicka dem till en inkorg för hemlig kopia. Ange den e-postadress du vill använda så att alla e-postmeddelanden som skickas är blinda och kopieras till den här BCC-adressen. Observera att BCC-adressdomänen måste vara en annan än alla underdomäner som delegerats till Adobe. Den här funktionen är valfri."

Du kan skicka en blind kopia (BCC) av ett e-postmeddelande som skickats av [!DNL Journey Optimizer] till en dedikerad BCC-adress. Med den här valfria funktionen kan du behålla kopior av e-postmeddelanden som du skickar till användarna för att uppfylla regelkrav och/eller arkivera. BCC-adressen är inte synlig för andra mottagare av meddelandet.

### Aktivera BCC-e-post {#enable-bcc}

Om du vill aktivera alternativet **[!UICONTROL BCC email]** anger du den e-postadress du vill ha i det dedikerade fältet i [kanalkonfigurationen](channel-surfaces.md) (d.v.s. meddelandeförinställningen). Du kan ange en extern adress i rätt format, förutom en e-postadress som definierats för en underdomän som delegerats till Adobe. Om du till exempel har delegerat underdomänen *marketing.luma.com* till Adobe tillåts inte adresser som *abc@marketing.luma.com*.

>[!CAUTION]
>
>Du kan bara definiera en e-postadress för hemlig kopia. Kontrollera att det finns tillräckligt med mottagningskapacitet på BCC-adressen för att lagra alla e-postmeddelanden som skickas med den aktuella kanalkonfigurationen.
>
>Fler rekommendationer visas i [det här avsnittet](#bcc-recommendations-limitations).

>[!NOTE]
>
>Om du har köpt tillägget Healthcare Shield måste du se till att BCC-adressens ISP stöder TLS 1.2-protokollet.

![](assets/preset-bcc.png)

När konfigurationen är klar kopieras alla e-postmeddelanden som är baserade på den här konfigurationen automatiskt till den e-postadress som du angav för den kontroll av webbläsarkompatibilitet som du angav. Därifrån kan meddelanden bearbetas och arkiveras i ett externt system.

>[!CAUTION]
>
>Användningen av din BCC-funktion räknas av mot det antal meddelanden som du är licensierad för. Aktivera det därför bara i de konfigurationer som används för viktig kommunikation som du vill arkivera. Kontrollera om det finns licensierade volymer i ditt avtal.

Inställningen för e-postadress för hemlig kopia sparas och bearbetas omedelbart på konfigurationsnivån. När du skapar ett nytt meddelande med den här konfigurationen, visas e-postadressen för BCC automatiskt.

![](assets/preset-bcc-in-msg.png)

BCC-adressen hämtas emellertid upp för att skicka kommunikation enligt logiken som beskrivs [här](../email/email-settings.md).

### Rekommendationer och begränsningar {#bcc-recommendations-limitations}

* För att säkerställa att din integritet efterlevs måste e-post från innehållsförteckningen behandlas av ett arkiveringssystem som kan lagra säkert personligt identifierbar information (PII).

* Eftersom meddelanden kan innehålla känsliga eller privata data, t.ex. personligt identifierbar information (PII), måste du se till att BCC-adressen är korrekt och skydda åtkomsten till meddelanden.

* Din inkorg som används för BCC bör hanteras på rätt sätt för utrymme och leverans. Om inkorgen returnerar studsar kanske vissa e-postmeddelanden inte tas emot och kommer därför inte att arkiveras.

* Meddelanden kan levereras till e-postadressen för den kopierade kopian före målmottagarna. BCC-meddelanden kan också skickas trots att de ursprungliga meddelandena har [studsat](../reports/suppression-list.md#delivery-failures).

  <!--OR: Only successfully sent emails are taken in account. [Bounces](../reports/suppression-list.md#delivery-failures) are not. TO CHECK -->

* Öppna inte och klicka inte igenom de e-postmeddelanden som skickas till BCC-adressen eftersom den tas med i det totala antalet öppningar och klickningar från sändningsanalysen, vilket kan orsaka vissa felberäkningar i [rapporter](../reports/report-gs-cja.md).

* Markera inte meddelanden som skräppost i BCC-inkorgen eftersom det påverkar alla andra e-postmeddelanden som skickas till den här adressen.

>[!CAUTION]
>
>Klicka inte på länken för att avbryta prenumerationen i de e-postmeddelanden som skickas till BCC-adressen eftersom du omedelbart kommer att avbeställa motsvarande mottagare.

### GDPR-efterlevnad {#gdpr-compliance}

I sådana förordningar som GDPR anges att registrerade bör kunna ändra sitt samtycke när som helst. Eftersom de BCC-e-postmeddelanden som du skickar med Journey Optimizer innehåller personligt identifierbar information (PII) måste du redigera **[!UICONTROL CJM Email BCC Feedback Event Schema]** för att kunna hantera dessa PII i enlighet med GDPR och liknande regler.

Följ stegen nedan för att göra detta.

1. Gå till **[!UICONTROL Data management]** > **[!UICONTROL Schemas]** > **[!UICONTROL Browse]** och välj **[!UICONTROL CJM Email BCC Feedback Event Schema]**.

   ![](assets/preset-bcc-schema.png)

1. Klicka för att expandera **[!UICONTROL _experience]**, **[!UICONTROL customerJourneyManagment]** och sedan **[!UICONTROL secondaryRecipientDetail]**.

1. Välj **[!UICONTROL originalRecipientAddress]**.

1. Bläddra nedåt till kryssrutan **[!UICONTROL Field properties]** i **[!UICONTROL Identity]** till höger.

1. Markera den och välj även **[!UICONTROL Primary identity]**.

1. Välj ett namnutrymme i listrutan.

   ![](assets/preset-bcc-schema-identity.png)

1. Klicka på **[!UICONTROL Apply]**.

>[!NOTE]
>
>Läs mer om hur du hanterar sekretess och tillämpliga regler i [Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=sv){target="_blank"}.

### BCC-rapporteringsdata {#bcc-reporting}

Det går inte att rapportera som sådant på en hemlig kopia i rese- och meddelanderapporterna. Information lagras emellertid på en systemdatauppsättning med namnet **[!UICONTROL AJO BCC Feedback Event Dataset]**. Du kan köra frågor mot den här datauppsättningen om du till exempel vill hitta användbar information för felsökning.

Om du vill komma åt den här datauppsättningen via användargränssnittet väljer du **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]**. Läs mer om hur du får åtkomst till datauppsättningar i [det här avsnittet](../data/get-started-datasets.md#access-datasets).

<!--![](assets/preset-bcc-dataset.png)-->

Om du vill köra frågor mot den här datauppsättningen kan du använda frågeredigeraren som tillhandahålls av [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target="_blank"}. Om du vill komma åt den väljer du **[!UICONTROL Data management]** > **[!UICONTROL Queries]** och klickar på **[!UICONTROL Create query]**. [Läs mer](../data/get-started-queries.md)

![](assets/preset-bcc-queries.png)

Beroende på vilken information du söker kan du köra följande frågor.

1. För alla andra frågor nedan behöver du reseåtgärds-ID:t. Kör den här frågan för att hämta alla åtgärds-ID:n som är kopplade till ett visst reseversion-ID inom de senaste två dagarna:

   ```
   SELECT
   DISTINCT
   CAST(TIMESTAMP AS DATE) AS EventTime,
   _experience.journeyOrchestration.stepEvents.journeyVersionID,
   _experience.journeyOrchestration.stepEvents.actionName, 
   _experience.journeyOrchestration.stepEvents.actionID 
   FROM journey_step_events 
   WHERE 
   _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND 
   _experience.journeyOrchestration.stepEvents.actionID is not NULL AND 
   TIMESTAMP > NOW() - INTERVAL '2' DAY 
   ORDER BY EventTime DESC;
   ```

   >[!NOTE]
   >
   >Om du vill hämta parametern `<journey version id>`väljer du motsvarande reseversion på menyn **[!UICONTROL Journey management]** > **[!UICONTROL Journeys]** . Resursversions-ID visas i slutet av den URL som visas i webbläsaren. [Läs mer om reseversioner](../building-journeys/publish-journey.md#journey-versions)
   >
   >![](assets/preset-bcc-action-id.png)

1. Kör den här frågan om du vill hämta alla meddelandefeedbackhändelser (särskilt feedbackstatus) som har genererats för ett visst meddelande som är riktat till en viss användare under de senaste två dagarna:

   ```
   SELECT  
   _experience.customerJourneyManagement.messageExecution.journeyVersionID AS JourneyVersionID, 
   _experience.customerJourneyManagement.messageExecution.journeyActionID AS JourneyActionID, 
   timestamp AS EventTime, 
   _experience.customerJourneyManagement.emailChannelContext.address AS RecipientAddress, 
   _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus AS FeedbackStatus,
   CASE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus
       WHEN 'sent' THEN 'Sent'
       WHEN 'delay' THEN 'Retry'
       WHEN 'out_of_band' THEN 'Bounce' 
       WHEN 'bounce' THEN 'Bounce'
   END AS FeedbackStatusCategory
   FROM cjm_message_feedback_event_dataset 
   WHERE  
       timestamp > now() - INTERVAL '2' day  AND
       _experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
       _experience.customerJourneyManagement.messageExecution.journeyActionID = '<journey action id>' AND  
       _experience.customerJourneyManagement.emailChannelContext.address = '<recipient email address>'
       ORDER BY EventTime DESC;
   ```

   >[!NOTE]
   >
   >Om du vill hämta parametern `<journey action id>` kör du den första frågan som beskrivs ovan med reseversion-ID:t. Parametern `<recipient email address>` är målmottagarens eller den faktiska mottagarens e-postadress.

1. Kör den här frågan om du vill hämta alla BCC-meddelandefeedbackhändelser som genererats för ett visst meddelande och som är riktat till en viss användare under de senaste två dagarna:

   ```
   SELECT   
   _experience.customerJourneyManagement.messageExecution.journeyVersionID AS JourneyVersionID, 
   _experience.customerJourneyManagement.messageExecution.journeyActionID AS JourneyActionID, 
   _experience.customerJourneyManagement.emailChannelContext.address AS BccEmailAddress,
   timestamp AS EventTime, 
   _experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS RecipientAddress, 
   _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus AS FeedbackStatus,
   CASE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackStatus
               WHEN 'sent' THEN 'Sent'
               WHEN 'delay' THEN 'Retry'
               WHEN 'out_of_band' THEN 'Bounce' 
               WHEN 'bounce' THEN 'Bounce'
           END AS FeedbackStatusCategory 
   FROM ajo_bcc_feedback_event_dataset  
   WHERE  
   timestamp > now() - INTERVAL '2' day  AND
   _experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
   _experience.customerJourneyManagement.messageExecution.journeyActionID = '<journeyaction id>' AND 
   _experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress = '<recipient email address>'
   ORDER BY EventTime DESC;
   ```

1. Kör den här frågan för att hämta alla mottagaradresser som inte har fått meddelandet, medan dess BCC-post finns inom de senaste 30 dagarna:

   ```
    SELECT
        DISTINCT 
    bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS RecipientAddressesNotRecievedMessage
    FROM ajo_bcc_feedback_event_dataset bcc
    LEFT JOIN cjm_message_feedback_event_dataset mfe
    ON 
   bcc._experience.customerJourneyManagement.messageExecution.journeyVersionID =
            mfe._experience.customerJourneyManagement.messageExecution.journeyVersionID AND    bcc._experience.customerJourneyManagement.messageExecution.journeyActionID = mfe._experience.customerJourneyManagement.messageExecution.journeyActionID AND 
   bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress = mfe._experience.customerJourneyManagement.emailChannelContext.address AND
   mfe._experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journey version id>' AND 
   mfe._experience.customerJourneyManagement.messageExecution.journeyActionID = '<journey action id>' AND
   mfe.timestamp > now() - INTERVAL '30' DAY AND
   mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus IN ('bounce', 'out_of_band') 
    WHERE bcc.timestamp > now() - INTERVAL '30' DAY;
   ```

### Använd meddelanderubrik för att stämma av BCC-kopia och skickad e-postinformation {#bcc-header}

När dina BCC-kopior för e-post arkiveras på ett externt system kan du hämta information om motsvarande skickade e-postmeddelanden med en rubrik som finns i meddelandet.

Alla e-postmeddelanden innehåller nu en rubrik med namnet `x-message-profile-id`. Värdet för det här huvudet är olika för varje profil: det är unikt för varje skickat e-postmeddelande och för motsvarande BCC-e-postkopia.

Rubriken `x-message-profile-id` lagras också i följande systemdatauppsättningar: [AJO Message Feedback Event Dataset](../data/datasets-query-examples.md#message-feedback-event-dataset) (skickade e-postmeddelanden) och [AJO BCC Feedback Event Dataset](#bcc-reporting) (BCC-kopior). Du kan söka efter dessa datauppsättningar för att stämma av kopian av den kostnadsfria kopian och motsvarande e-postadress.

* Om du vill komma åt dessa datauppsättningar via användargränssnittet väljer du **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]**. Läs mer om hur du får åtkomst till datauppsättningar i [det här avsnittet](../data/get-started-datasets.md#access-datasets).

* Använd Frågeredigeraren som tillhandahålls av [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target="_blank"}. Om du vill komma åt den väljer du **[!UICONTROL Data management]** > **[!UICONTROL Queries]** och klickar på **[!UICONTROL Create query]**. [Läs mer](../data/get-started-queries.md)

Nedan visas några exempelfrågor som du kan köra för att hämta information som motsvarar dina BCC-kopior.

**Fråga 1**

Så här sätter du ihop BCC-händelsen med motsvarande feedback-händelse för det faktiska e-postmeddelandet med kampanjåtgärdsinformationen:

```
SELECT
  mfe.timestamp AS OriginalRecipientFeedbackEventTime,
  mfe._experience.customerJourneyManagement.emailChannelContext.address AS OriginalRecipientEmailAddress,
  bcc._experience.customerJourneyManagement.emailChannelContext.address AS BCCEmailAddress,
  mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS OriginalRecipientMessageFeedbackStatus,
  mfe._experience.customerJourneyManagement.messageExecution.campaignID AS CampaignID,
  mfe._experience.customerJourneyManagement.messageExecution.campaignActionID AS CampaignActionID,
  mfe._experience.customerJourneyManagement.messageExecution.batchInstanceID AS BatchInstanceID,
  mfe._experience.customerJourneyManagement.messageExecution.messageID AS MessageID
FROM ajo_bcc_feedback_event_dataset bcc
LEFT JOIN ajo_message_feedback_event_dataset mfe
ON bcc._experience.customerJourneyManagement.messageProfile.messageProfileID =
    mfe._experience.customerJourneyManagement.messageProfile.messageProfileID AND 
    mfe.timestamp > now() - INTERVAL '30' day
WHERE 
  bcc.timestamp > now() - INTERVAL '30' DAY AND 
  bcc._experience.customerJourneyManagement.messageProfile.messageProfileID = '<x-message-profile-id>'
ORDER BY mfe.timestamp DESC;
```

**Fråga 2**

Så här sätter du ihop BCC-händelsen med motsvarande feedback-händelse för det faktiska e-postmeddelandet med information om reseåtgärder:

```
SELECT
  mfe.timestamp AS OriginalRecipientFeedbackEventTime,
  mfe._experience.customerJourneyManagement.emailChannelContext.address AS OriginalRecipientEmailAddress,
  bcc._experience.customerJourneyManagement.emailChannelContext.address AS BCCEmailAddress,
  mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS OriginalRecipientMessageFeedbackStatus,
  mfe._experience.customerJourneyManagement.messageExecution.journeyActionID AS journeyActionID,
  mfe._experience.customerJourneyManagement.messageExecution.journeyVersionID AS JourneyVersionID,
  mfe._experience.customerJourneyManagement.messageExecution.journeyVersionInstanceID AS JourneyVersionInstanceID,
  mfe._experience.customerJourneyManagement.messageExecution.batchInstanceID AS BatchInstanceID,
  mfe._experience.customerJourneyManagement.messageExecution.messageID AS MessageID
FROM ajo_bcc_feedback_event_dataset bcc
LEFT JOIN ajo_message_feedback_event_dataset mfe
ON bcc._experience.customerJourneyManagement.messageProfile.messageProfileID =
    mfe._experience.customerJourneyManagement.messageProfile.messageProfileID AND 
    mfe.timestamp > now() - INTERVAL '30' day
WHERE 
  bcc.timestamp > now() - INTERVAL '30' DAY AND 
  bcc._experience.customerJourneyManagement.messageProfile.messageProfileID = '<x-message-profile-id>'
ORDER BY mfe.timestamp DESC;
```
