---
solution: Journey Optimizer
product: journey optimizer
title: Arkiveringsstöd i Journey Optimizer
description: Lär dig arkivera meddelanden
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 186a5044-80d5-4633-a7a7-133e155c5e9f
source-git-commit: 7e27f5502d64d0c91de2c67e4011e650e77c6a92
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 1%

---

# Stöd för arkivering {#archiving-support}

## Arkivera meddelanden {#about-archiving}

Regeringar som HIPAA kräver att [!DNL Journey Optimizer] bör vara ett sätt att arkivera meddelanden som skickas till enskilda personer. Om era kunder gör anspråk bör de ha möjlighet att få en kopia av det skickade meddelandet för verifieringsändamål.

* För e-postkanalen [!DNL Journey Optimizer] har en inbyggd funktion för e-post i BCC. [Läs mer](#bcc-email)

* För alla kanaler kan du dessutom använda fältet &quot;Mall&quot; i **Enhetsdatauppsättning**, som innehåller information om de icke-personliga meddelandemallarna. Exportera datauppsättningen med det här fältet för att spara metadata som: som skickade meddelandet, till vem och när. Observera att anpassade data inte exporteras - endast mallen (meddelandets format och struktur) beaktas. [Läs mer](../data/datasets-query-examples.md#entity-dataset)

>[!NOTE]
>
>[!DNL Journey Optimizer] har inte stöd för kraven på SMS-arkivering. Om du vill ha dedikerat stöd för arkivering kan du arbeta med din SMS-leverantör (Synch eller Twilio).

## Så här använder du BCC för e-post {#bcc-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_bcc"
>title="Definiera en e-postadress för hemlig kopia"
>abstract="Du kan behålla en kopia av skickade e-postmeddelanden genom att skicka dem till en inkorg för hemlig kopia. Ange den e-postadress du vill använda så att alla e-postmeddelanden som skickas är blinda och kopieras till den här BCC-adressen. Observera att BCC-adressdomänen inte ska vara samma som alla underdomäner som delegerats till Adobe. Den här funktionen är valfri.  "

Du kan skicka en identisk kopia (eller en blind kopia) av ett e-postmeddelande som skickats av [!DNL Journey Optimizer] till en BCC-inkorg. Med den här valfria funktionen kan du behålla kopior av e-postmeddelanden som du skickar till användarna för att uppfylla regelkrav och/eller arkivera. Detta visas inte för leveransmottagarna.

### Aktivera BCC-e-post {#enable-bcc}

Aktivera **[!UICONTROL BCC email]** anger du den e-postadress du vill använda i det dedikerade fältet i [kanalyta](channel-surfaces.md) (t.ex. meddelandeförinställning). Du kan ange en extern adress i rätt format, förutom en e-postadress som har definierats för en underdomän som har delegerats till Adobe. Om du till exempel har delegerat *marketing.luma.com* subdomain to Adobe, any address like *abc@marketing.luma.com* är förbjudet.

>[!CAUTION]
>
>Du kan bara definiera en e-postadress för hemlig kopia. Kontrollera att det finns tillräckligt med mottagningskapacitet på BCC-adressen för att lagra alla e-postmeddelanden som skickas med den aktuella kanalytan.
>
>Fler rekommendationer finns i [det här avsnittet](#bcc-recommendations-limitations).

>[!NOTE]
>
>Om du har köpt tillägget Healthcare Shield måste du se till att BCC-adressens ISP stöder TLS 1.2-protokollet.

![](assets/preset-bcc.png)

Alla e-postmeddelanden som använder den här ytan kommer att kopieras till den e-postadress som du har angett för BCC. Därifrån kan de bearbetas och arkiveras i ett externt system.

>[!CAUTION]
>
>Användningen av din BCC-funktion räknas av mot det antal meddelanden som du har licens för. Aktivera det därför bara i de ytor som används för viktig kommunikation som du vill arkivera. Kontrollera om det finns licensierade volymer i ditt avtal.

Inställningen för BCC-e-postadressen sparas och bearbetas omedelbart på ytnivå. När du [skapa ett nytt meddelande](../messages/get-started-content.md) När du använder den här ytan visas e-postadressen för den kontroll av webbläsarkompatibilitet automatiskt.

![](assets/preset-bcc-in-msg.png)

BCC-adressen hämtas dock upp för att skicka kommunikation enligt den logik som beskrivs [här](email-settings.md).

### Recommendations och begränsningar {#bcc-recommendations-limitations}

* För att säkerställa att din integritet efterlevs måste e-post från innehållsförteckningen behandlas av ett arkiveringssystem som kan lagra säkert personligt identifierbar information (PII).

* Eftersom meddelanden kan innehålla känsliga eller privata data, t.ex. personligt identifierbar information (PII), måste du se till att BCC-adressen är korrekt och skydda åtkomsten till meddelanden.

* Din inkorg som används för BCC bör hanteras på rätt sätt för utrymme och leverans. Om inkorgen returnerar studsar kanske vissa e-postmeddelanden inte tas emot och kommer därför inte att arkiveras.

* Meddelanden kan levereras till e-postadressen för den kopierade kopian före målmottagarna. BCC-meddelanden kan också skickas trots att de ursprungliga meddelandena kan ha [studsade](../reports/suppression-list.md#delivery-failures).

   <!--OR: Only successfully sent emails are taken in account. [Bounces](../reports/suppression-list.md#delivery-failures) are not. TO CHECK -->

* Öppna inte och klicka inte igenom de e-postmeddelanden som skickas till BCC-adressen eftersom den tas med i det totala antalet öppningar och klickningar från sändningsanalysen, vilket kan orsaka vissa felberäkningar i [rapporter](../reports/global-report.md).

* Markera inte meddelanden som skräppost i BCC-inkorgen eftersom det påverkar alla andra e-postmeddelanden som skickas till den här adressen.


>[!CAUTION]
>
>Klicka inte på länken för att avbryta prenumerationen i de e-postmeddelanden som skickas till BCC-adressen eftersom du omedelbart kommer att avbeställa motsvarande mottagare.

### GDPR-efterlevnad {#gdpr-compliance}

I sådana förordningar som GDPR anges att registrerade bör kunna ändra sitt samtycke när som helst. Eftersom de BCC-e-postmeddelanden du skickar med Journey Optimizer innehåller personligt identifierbar information (PII) måste du redigera **[!UICONTROL CJM Email BCC Feedback Event Schema]** kunna hantera dessa PII i enlighet med GDPR och liknande regler.

Följ stegen nedan för att göra detta.

1. Gå till **[!UICONTROL Data management]** > **[!UICONTROL Schemas]** > **[!UICONTROL Browse]** och markera **[!UICONTROL CJM Email BCC Feedback Event Schema]**.

   ![](assets/preset-bcc-schema.png)

1. Klicka för att expandera **[!UICONTROL _experience]**, **[!UICONTROL customerJourneyManagment]** sedan **[!UICONTROL secondaryRecipientDetail]**.

1. Välj **[!UICONTROL originalRecipientAddress]**.

1. I **[!UICONTROL Field properties]** till höger rullar du nedåt till **[!UICONTROL Identity]** kryssrutan.

1. Markera den och markera den **[!UICONTROL Primary identity]**.

1. Välj ett namnutrymme i listrutan.

   ![](assets/preset-bcc-schema-identity.png)

1. Klicka på **[!UICONTROL Apply]**.

>[!NOTE]
>
>Läs mer om hur du hanterar sekretess och tillämpliga regler i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=&quot;_blank&quot;}.

### BCC-rapporteringsdata {#bcc-reporting}

Det går inte att rapportera som sådant på en hemlig kopia i rese- och meddelanderapporterna. Information lagras emellertid på en systemdatauppsättning som kallas **[!UICONTROL AJO BCC Feedback Event Dataset]**. Du kan köra frågor mot den här datauppsättningen om du till exempel vill hitta användbar information för felsökning.

Du kan komma åt den här datauppsättningen via användargränssnittet. Välj **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]** och aktivera **[!UICONTROL Show system datasets]** växla från filtret för att visa systemgenererade datauppsättningar. Läs mer om hur du får åtkomst till datauppsättningar i [det här avsnittet](../data/get-started-datasets.md#access-datasets).

![](assets/preset-bcc-dataset.png)

Om du vill köra frågor mot den här datauppsättningen kan du använda Frågeredigeraren från [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;}. Om du vill komma åt den väljer du **[!UICONTROL Data management]** > **[!UICONTROL Queries]** och klicka **[!UICONTROL Create query]**. [Läs mer](../data/get-started-queries.md)

![](assets/preset-bcc-queries.png)

Beroende på vilken information du söker kan du köra följande frågor.

1. För alla andra frågor nedan behöver du reseåtgärds-ID:t. Kör den här frågan för att hämta alla åtgärds-ID:n som är kopplade till ett visst reseversion-ID inom de senaste två dagarna:

       &quot;
       MARKERA
       DISTINCT
       CAST(TIMESTAMP AS DATE) AS EventTime,
       _experience.travelOrchestration.stepEvents.travelVersionID,
       _experience.travelOrchestration.stepEvents.actionName,
       _experience.travelOrchestration.stepEvents.actionID
       FROM travel_step_events
       VAR
       _experience.travelOrchestration.stepEvents.travelVersionID = &#39;&lt;journey version=&quot;&quot; id=&quot;&quot;>OCH
       _experience.travelOrchestration.stepEvents.actionID är inte NULL AND
       TIDSSTÄMPEL > NOW() - INTERVAL &#39;2&#39; DAY
       BESTÄLL AV EventTime DESC;
       &quot;
   
   >[!NOTE]
   >
   >För att få `<journey version id>`väljer du motsvarande [reseversion](../building-journeys/journey.md#journey-versions) från **[!UICONTROL Journey management]** > **[!UICONTROL Journeys]** -menyn. Resursversions-ID visas i slutet av den URL som visas i webbläsaren.
   >
   >![](assets/preset-bcc-action-id.png)

1. Kör den här frågan om du vill hämta alla meddelandefeedbackhändelser (särskilt feedbackstatus) som har genererats för ett visst meddelande som är riktat till en viss användare under de senaste två dagarna:

       &quot;
       MARKERA
       _experience.customerJourneyManagement.messageExecution.travelVersionID AS JourneyVersionID,
       _experience.customerJourneyManagement.messageExecution.travelActionID AS JourneyActionID,
       tidsstämpel AS EventTime,
       _experience.customerJourneyManagement.emailChannelContext.address AS RecipientAddress,
       _experience.customerjournalManagement.messagedeliveryfeedback.feedbackStatus AS FeedbackStatus,
       CASE_experience.customerjournalManagement.messageDeliveryfeedback.feedbackStatus
       NÄR&quot;skickat&quot; SÅ&quot;skickat&quot;
       NÄR &#39;delay&#39; SEDAN &#39;Retry&#39;
       WHEN &#39;out_of_band&#39; THEN &#39;Bounce&#39;
       NÄR &#39;studsa&#39; SÅ &#39;studsar&#39;
       END AS FeedbackStatusCategory
       FROM cjm_message_feedback_event_dataset
       VAR
       timestamp > now() - INTERVAL &#39;2&#39; day AND
       _experience.customerJourneyManagement.messageExecution.travelVersionID = &#39;&lt;journey version=&quot;&quot; id=&quot;&quot;>OCH
       _experience.customerJourneyManagement.messageExecution.travelActionID = &#39;&lt;journey action=&quot;&quot; id=&quot;&quot;>OCH
       _experience.customerJourneyManagement.emailChannelContext.address = &#39;&lt;recipient email=&quot;&quot; address=&quot;&quot;>&#39;
       BESTÄLL AV EventTime DESC;
       &quot;
   
   >[!NOTE]
   >
   >För att få `<journey action id>` kör du den första frågan som beskrivs ovan med resversion-ID:t. The `<recipient email address>` parametern är målmottagarens eller den faktiska mottagarens e-postadress.

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
