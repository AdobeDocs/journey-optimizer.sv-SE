---
title: Konfigurera e-postinställningar
description: Lär dig hur du konfigurerar e-postinställningar på den förinställda nivån för meddelanden
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 13536962-7541-4eb6-9ccb-4f97e167734a
source-git-commit: 65c2ba7e0931f449a29d1e7ff01d6d68fccca448
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 1%

---

# Konfigurera e-postinställningar {#email-settings}

Definiera e-postinställningarna i det dedikerade avsnittet i meddelandeförinställningskonfigurationen. Lär dig hur du skapar meddelandeförinställningar i [det här avsnittet](message-presets.md).

![](assets/preset-email.png)

## Typ av e-post {#email-type}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_emailtype"
>title="Definiera e-postkategorin"
>abstract="Välj den typ av meddelanden som ska skickas när den här förinställningen används: Marknadsföring för kampanjmeddelanden, som kräver användargodkännande, eller Transactional för icke-kommersiella meddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang."

I **E-POSTTYP** väljer du den typ av meddelande som ska skickas med förinställningen: **Marknadsföring** eller **Transactional**.

* Välj **Marknadsföring** för kampanjmeddelanden: dessa meddelanden kräver användarens samtycke.

* Välj **Transactional** för icke-kommersiella meddelanden, t.ex. orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

>[!CAUTION]
>
>**Transactional** meddelanden kan skickas till profiler som avbeställer marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang.

När [skapa ett meddelande](../messages/get-started-content.md#create-new-message)måste du välja en giltig meddelandeförinställning som matchar den kategori du valde för meddelandet.

## Underdomän och IP-pool {#subdomains-and-ip-pools}

I **INFORMATION OM UNDERDOMÄN- OCH IP-POOL** måste du

1. Välj den underdomän som ska användas för att skicka e-postmeddelanden. [Läs mer](about-subdomain-delegation.md)

1. Välj den IP-pool som ska associeras med förinställningen. [Läs mer](ip-pools.md)

![](assets/preset-subdomain-ip-pool.png)

Du kan inte fortsätta skapa förinställningar medan den valda IP-poolen är under [utgåva](ip-pools.md#edit-ip-pool) (**[!UICONTROL Processing]** status) och har aldrig kopplats till den valda underdomänen. Annars kommer den äldsta versionen av associationen för IP-poolen/underdomänen fortfarande att användas. I så fall sparar du förinställningen som utkast och försöker igen när IP-poolen har **[!UICONTROL Success]** status.

>[!NOTE]
>
>I icke-produktionsmiljöer skapar inte Adobe körklara testunderdomäner och ger inte heller åtkomst till en delad sändande IP-pool. Du måste [delegera dina egna underdomäner](delegate-subdomain.md) och använd IP-adresserna från poolen som tilldelats din organisation.

## List-Unsubscribe {#list-unsubscribe}

Vid [välja en underdomän](#subdomains-and-ip-pools) från listan, **[!UICONTROL Enable List-Unsubscribe]** visas.

![](assets/preset-list-unsubscribe.png)

Det här alternativet är aktiverat som standard.

Om du låter det vara aktiverat inkluderas en länk för att avbryta prenumerationen automatiskt i e-posthuvudet, till exempel:

![](assets/preset-list-unsubscribe-header.png)

Om du inaktiverar det här alternativet visas ingen länk för att avbryta prenumerationen i e-posthuvudet.

Länken för att avbryta prenumerationen består av två element:

* An **avbeställ e-postadress** som alla avbeställningar skickas till.

   I [!DNL Journey Optimizer], är e-postadressen för avanmälan standard **[!UICONTROL Mailto (unsubscribe)]** som visas i meddelandeförinställningen, baserat på [vald underdomän](#subdomains-and-ip-pools).

   ![](assets/preset-list-unsubscribe-mailto.png)

* The **avbeställ URL**, vilket är URL:en till landningssidan där användaren omdirigeras när prenumerationen har upphört.

   Om du lägger till en [länk för avanmälan med ett klick](../messages/consent.md#one-click-opt-out) för ett meddelande som skapas med den här förinställningen blir avanmälnings-URL:en den URL som definierats för länken med ett klick.

   ![](assets/preset-list-unsubscribe-opt-out-url.png)

   >[!NOTE]
   >
   >Om du inte lägger till en länk för avanmälan med ett enda klick i meddelandeinnehållet visas ingen landningssida för användaren.

Läs mer om hur du lägger till en länk för att avbryta prenumerationen i dina meddelanden i [det här avsnittet](../messages/consent.md#unsubscribe-header).

<!--Select the **[!UICONTROL Custom List-Unsubscribe]** option to enter your own Unsubscribe URL and/or your own Unsubscribe email address.(to add later)-->

## Huvudparametrar{#email-header}

I **[!UICONTROL HEADER PARAMETERS]** anger du avsändarens namn och e-postadresser som är kopplade till den typ av meddelanden som skickas med den förinställningen.

>[!CAUTION]
>
>E-postadresserna måste använda den valda [delegerad underdomän](about-subdomain-delegation.md).

* **[!UICONTROL Sender name]**: Avsändarens namn, till exempel ditt varumärkes namn.

* **[!UICONTROL Sender email]**: E-postadressen som du vill använda för din kommunikation. Om den delegerade underdomänen till exempel är *marketing.luma.com* kan du använda *contact@marketing.luma.com*.

* **[!UICONTROL Reply to (name)]**: Namnet som ska användas när mottagaren klickar på **Svara** i klientprogramvaran för e-post.

* **[!UICONTROL Reply to (email)]**: E-postadressen som ska användas när mottagaren klickar på **Svara** i klientprogramvaran för e-post. Du måste använda en adress som är definierad för den delegerade underdomänen (till exempel *reply@marketing.luma.com*), annars kommer e-postmeddelandena att tas bort.

* **[!UICONTROL Error email]**: Alla fel som genereras av Internet-leverantörer efter några dagar efter att e-post har levererats (asynkrona studsar) tas emot på den här adressen.

![](assets/preset-header.png)

>[!NOTE]
>
>Adresser måste börja med en bokstav (A-Z) och får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

### Vidarebefordra e-post {#forward-email}

Om du vill vidarebefordra till en viss e-postadress får du alla e-postmeddelanden som [!DNL Journey Optimizer] för den delegerade underdomänen, kontakta Adobe kundtjänst. Du måste ange:

* Den e-postadress som du väljer. Observera att domänen för e-postadressen för vidarebefordran inte kan matcha någon underdomän som har delegerats till Adobe.
* Namn på din sandlåda.
* Förinställningsnamnet som e-postadressen ska användas för.
* Aktuell **[!UICONTROL Reply to (email)]** adressuppsättningen på förinställningsnivå.

>[!NOTE]
>
>Det får bara finnas en e-postadress per underdomän. Om flera förinställningar använder samma underdomän måste därför samma e-postadress för alla förinställningar användas.

E-postadressen för vidarebefordran kommer att konfigureras av Adobe. Detta kan ta 3 till 4 dagar.

<!--
## BCC email {#bcc-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_bcc"
>title="Define a BCC email address"
>abstract="You can keep a copy of sent emails by sending them to a BCC inbox. Enter the email address of your choice so that every email sent is blind-copied to this BCC address. This feature is optional."

You can send an identical copy (or blind carbon copy) of an email sent by [!DNL Journey Optimizer] to a BCC inbox. This optional feature allows you to retain copies of email communications you send to your users for compliance and/or archival purposes. This will be invisible to the delivery recipients.

>[!CAUTION]
>
>This capability will be available starting **May, 31**.

### Enable BCC email {#enable-bcc}

To enable the **[!UICONTROL BCC email]** option, enter the email address of your choice in the dedicated field. You can specify any external address in correct format, except an email address defined on the delegated subdomain. For example, if the delegated subdomain is *marketing.luma.com*, any address like *abc@marketing.luma.com* is prohibited.

>[!NOTE]
>
>You can only define one BCC email address. Make sure the BCC address has enough reception capacity to store all the emails that are sent using the current preset.
>
>More recommendations are listed in [this section](#bcc-recommendations-limitations).

![](assets/preset-bcc.png)

All email messages using this preset will be blind-copied to the BCC email address you entered. From there, they can be processed and archived using an external system.

>[!CAUTION]
>
>Your BCC feature usage will be counted against the number of messages you are licensed for. Hence, only enable it in the presets used for critical communications that you wish to archive. Check your contract for licensed volumes.

The BCC email address setting is immediately saved and processed at the preset level. When you [create a new message](../messages/get-started-content.md#create-new-message) using this preset, the BCC email address is automatically displayed.

![](assets/preset-bcc-in-msg.png)

However, the BCC address gets picked up for sending communications following the logic below:

* For batch and burst journeys, it does not apply to batch or burst execution that had already started before the BCC setting is made. The change will be picked up at the next recurrence or new execution.

* For transactional messages, the change is picked up immediately for the next communication (up to one minute delay).

>[!NOTE]
>
>You do not need to republish a message or journey for the BCC setting to be picked up.

### Recommendations and limitations {#bcc-recommendations-limitations}

* To ensure your privacy compliance, BCC emails must be processed by an archiving system capable of storing securely personally identifiable information (PII).

* As messages can contain sensitive or private data, such as personally identifiable information (PII), make sure the BCC address is correct, and secure the access to messages.

* Your inbox used for BCC should be properly managed for space and delivery. If the inbox returns bounces, some emails may not be received and therefore will fail to get archived.

* Messages may be delivered to the BCC email address before the target recipients. BCC messages can also been sent even though the original messages may have [bounced](../reports/suppression-list.md#delivery-failures).

    //////OR: Only successfully sent emails are taken in account. [Bounces](../reports/suppression-list.md#delivery-failures) are not. TO CHECK /////////

* Do not open or click through the emails sent to the BCC address as it is taken into account in the total opens and clicks from the send analysis, which could cause some miscalculations in [reports](../reports/message-monitoring.md). 

* Do not mark messages as spam in the BCC inbox, as it will impact all the other emails sent to this address.


>[!CAUTION]
>
>Do not click the unsubscribe link in the emails sent to the BCC address as you will immediately unsubscribe the corresponding recipients.

### GDPR compliance {#gdpr-compliance}

Regulations such as GDPR state that Data Subjects should be able to modify their consent at any time. Because the BCC emails you are sending with Journey Optimizer include securely personally identifiable information (PII), you must edit the **[!UICONTROL CJM Email BCC Feedback Event Schema]** to be able to manage these PII in compliance with GDPR and similar regulations.

To do this, follow the steps below.

1. Go to **[!UICONTROL Data management]** > **[!UICONTROL Schemas]** > **[!UICONTROL Browse]** and select **[!UICONTROL CJM Email BCC Feedback Event Schema]**.

    ![](assets/preset-bcc-schema.png)

1. Click to expand **[!UICONTROL _experience]**, **[!UICONTROL customerJourneyManagment]** then **[!UICONTROL secondaryRecipientDetail]**.

1. Select **[!UICONTROL originalRecipientAddress]**.

1. In the **[!UICONTROL Field properties]** on the right, scroll down to the **[!UICONTROL Identity]** checkbox.

1. Select it and also select **[!UICONTROL Primary identity]**.

1. Select a namespace from the drop-down list.

    ![](assets/preset-bcc-schema-identity.png)

1. Click **[!UICONTROL Apply]**.

>[!NOTE]
>
>Learn more on managing Privacy and the applicable regulations in the [Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"}.

### BCC reporting data {#bcc-reporting}

Reporting as such on BCC is not available in the journey and message reports. However, information is stored on a system dataset called **[!UICONTROL AJO BCC Feedback Event Dataset]**. You can run queries against this dataset to find useful information for debugging purpose for example.

You can access this dataset through the user interface. Select **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]** and enable the **[!UICONTROL Show system datasets]** toggle from the filter to display the system-generated datasets. Learn more on how to access datasets in [this section](../start/get-started-datasets.md#access-datasets).

![](assets/preset-bcc-dataset.png)

To run queries against this dataset, you can use the Query Editor provided by the [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target="_blank"}. To access it, select **[!UICONTROL Data management]** > **[!UICONTROL Queries]** and click **[!UICONTROL Create query]**. [Learn more](../start/get-started-queries.md)

![](assets/preset-bcc-queries.png)

Depending on what information you are looking for, you can run the following queries.

1. For all the other queries below, you will need the journey action ID. Run this query to fetch all action IDs associated with a particular journey version ID within the last 2 days:

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
    >To get the `<journey version id>`parameter, select the corresponding [journey version](../building-journeys/journey-versions.md) from the **[!UICONTROL Journey management]** > **[!UICONTROL Journeys]** menu. The journey version ID is displayed at the end of the URL displayed in your web browser.
    >
    >![](assets/preset-bcc-action-id.png)

1. Run this query to fetch all message feedback events (especially feedback status) generated for a particular message targeted to a specific user within the last 2 days:

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
    >To get the `<journey action id>` parameter, run the first query described above using the journey version id. The `<recipient email address>` parameter is the targeted or actual recipient's email address.

1. Run this query to fetch all BCC message feedback events generated for a particular message targeted to a specific user within the last 2 days:

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

1. Run this query to fetch all recipient addresses who have not received the message whereas its BCC entry exists within the last 30 days:

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
-->

## Parametrar för återförsök av e-post {#email-retry}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_retryperiod"
>title="Justera tidsperioden för återförsök"
>abstract="Försök utförs i 3,5 dagar (84 timmar) när ett e-postmeddelande inte kan skickas på grund av ett tillfälligt fel med mjuk studsning. Du kan justera den här standardperioden för återförsök så att den passar dina behov bättre."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configuration-message/email-configuration/monitor-reputation/retries.html" text="Om återförsök"

Du kan konfigurera **Parametrar för återförsök av e-post**.

![](assets/preset-retry-parameters.png)

Som standard är [återförsökstid](retries.md#retry-duration) är inställt på 84 timmar, men du kan justera den här inställningen så att den passar dina behov bättre.

Du måste ange ett heltalsvärde (i timmar eller minuter) inom följande intervall:

* För marknadsföringsmeddelanden är den minsta återförsöksperioden 6 timmar.
* För transaktionsmeddelanden är den minsta återförsöksperioden 10 minuter.
* För båda e-posttyperna är den maximala återförsöksperioden 84 timmar (eller 5 040 minuter).

Läs mer om återförsök i [det här avsnittet](retries.md).

## URL-spårning {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="URL-spårningsparametrar"
>abstract="Använd det här avsnittet om du automatiskt vill lägga till spårningsparametrar till kampanj-URL:erna som finns i ditt e-postinnehåll."

Du kan använda **[!UICONTROL URL Tracking Parameters]** för att mäta effektiviteten i era marknadsföringssatsningar över olika kanaler. Den här funktionen är valfri.  

Parametrarna som definieras i det här avsnittet läggs till i slutet av de URL:er som ingår i e-postmeddelandeinnehållet. Du kan sedan hämta parametrarna i webbanalysverktyg som Adobe Analytics eller Google Analytics och skapa olika resultatrapporter.

![](assets/preset-url-tracking.png)

Tre parametrar för URL-spårning fylls i automatiskt som exempel när du skapar en meddelandeförinställning. Du kan redigera dessa och lägga till upp till 10 spårningsparametrar med **[!UICONTROL Add new parameter]** -knappen.

Om du vill konfigurera en URL-spårningsparameter kan du ange önskade värden direkt i dialogrutan **[!UICONTROL Name]** och **[!UICONTROL Value]** eller välj från en lista med fördefinierade värden genom att navigera till följande objekt:

* Reseattribut: **Käll-ID**, **Källnamn**, **Källversions-ID**
* Åtgärdsattribut: **Åtgärds-ID**, **Åtgärdsnamn**
* Offer decisioning-attribut: **Erbjudande-ID**, **Namn på erbjudande**

![](assets/preset-url-tracking-source.png)

>[!CAUTION]
>
>Välj ingen mapp: Kontrollera att du bläddrar till den mapp som behövs och välj ett profilattribut som ska användas som spårningsparametervärde.

Nedan finns exempel på Adobe Analytics- och Google Analytics-kompatibla URL:er.

* Adobe Analytics-kompatibel URL: `www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics-kompatibel URL: `www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

>[!NOTE]
>
>Du kan kombinera textvärden och välja fördefinierade värden. Varje **[!UICONTROL Value]** fält kan innehålla upp till 255 tecken totalt.
