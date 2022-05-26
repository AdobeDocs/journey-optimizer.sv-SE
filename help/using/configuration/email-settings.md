---
title: Konfigurera e-postinställningar
description: Lär dig hur du konfigurerar e-postinställningar på den förinställda nivån för meddelanden
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 13536962-7541-4eb6-9ccb-4f97e167734a
source-git-commit: 13fbe0583affb48269932134ea6bc214180903dd
workflow-type: tm+mt
source-wordcount: '2152'
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
* Det förinställningsnamn som e-postadressen (eller svaret till) ska användas för.
* Aktuell **[!UICONTROL Reply to (email)]** adressuppsättningen på förinställningsnivå.

>[!NOTE]
>
>Det får bara finnas en e-postadress per underdomän. Om flera förinställningar använder samma underdomän måste därför samma e-postadress för alla förinställningar användas.

E-postadressen för vidarebefordran kommer att konfigureras av Adobe. Detta kan ta 3 till 4 dagar.

## BCC-e-post {#bcc-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_bcc"
>title="Definiera en e-postadress för hemlig kopia"
>abstract="Du kan behålla en kopia av skickade e-postmeddelanden genom att skicka dem till en inkorg för hemlig kopia. Ange den e-postadress du vill använda så att alla e-postmeddelanden som skickas är blinda och kopieras till den här BCC-adressen. Den här funktionen är valfri.  "

Du kan skicka en identisk kopia (eller en blind kopia) av ett e-postmeddelande som skickats av [!DNL Journey Optimizer] till en BCC-inkorg. Med den här valfria funktionen kan du behålla kopior av e-postmeddelanden som du skickar till användarna för att uppfylla regelkrav och/eller arkivera. Detta visas inte för leveransmottagarna.

### Aktivera BCC-e-post {#enable-bcc}

Aktivera **[!UICONTROL BCC email]** anger du den e-postadress du vill använda i det dedikerade fältet. Du kan ange en extern adress i rätt format, förutom en e-postadress som har definierats på den delegerade underdomänen. Om den delegerade underdomänen till exempel är *marketing.luma.com*, alla adresser som *abc@marketing.luma.com* är förbjudet.

>[!NOTE]
>
>Du kan bara definiera en e-postadress för hemlig kopia. Kontrollera att det finns tillräckligt med mottagningskapacitet på BCC-adressen för att lagra alla e-postmeddelanden som skickas med den aktuella förinställningen.

![](assets/preset-bcc.png)

Alla e-postmeddelanden som använder den här förinställningen kopieras automatiskt till den e-postadress för hemkopia som du angav. Därifrån kan de bearbetas och arkiveras i ett externt system.

>[!CAUTION]
>
>Användningen av din BCC-funktion räknas av mot det antal meddelanden som du har licens för. Aktivera det därför bara i de förinställningar som används för viktig kommunikation som du vill arkivera. Kontrollera om det finns licensierade volymer i ditt avtal.

Inställningen för e-postadress för hemlig kopia sparas och bearbetas omedelbart på förinställningsnivå. När du [skapa ett nytt meddelande](../messages/get-started-content.md#create-new-message) med den här förinställningen visas e-postadressen för BCC automatiskt.

![](assets/preset-bcc-in-msg.png)

BCC-adressen hämtas dock upp för att skicka kommunikation enligt logiken nedan:

* För batch- och burst-resor gäller det inte batch- eller burst-körning som redan hade startats innan BCC-inställningen gjordes. Ändringen hämtas vid nästa återkommande eller nya körning.

* För transaktionsmeddelanden hämtas ändringen omedelbart för nästa kommunikation (upp till en minut).

>[!NOTE]
>
>Du behöver inte publicera om ett meddelande eller en resa för att BCC-inställningen ska hämtas.

### Recommendations och begränsningar {#recommendations-limitations}

* Kontrollera att e-postadressen för hemlig kopia är korrekt angiven. Om så inte är fallet kan dina kunders personligt identifierbara information (PII) skickas till en oönskad adress.

* Av sekretesskäl måste e-post från innehållsförteckningen behandlas av ett arkiveringssystem som kan lagra säkert personligt identifierbar information (PII).

* Den här funktionen kan leverera till e-postadressen för den lokala kopian innan den skickas till mottagarna, vilket kan leda till att BCC-meddelanden skickas trots att de ursprungliga leveranserna kan ha [studsade](../reports/suppression-list.md#delivery-failures).

   <!--OR: Only successfully sent emails are taken in account. [Bounces](../reports/suppression-list.md#delivery-failures) are not. TO CHECK -->

* Om e-postmeddelanden som skickas till BCC-adressen öppnas och klickas igenom, kommer detta att beaktas i det totala antalet öppningar och klick från sändningsanalysen, vilket kan orsaka felberäkningar i [rapporter](../reports/message-monitoring.md). På samma sätt kan du markera BCC-e-postmeddelanden som landar i din inkorg eftersom skräppost kan göra att e-postmeddelanden hamnar i skräppostmappen i din inkorg.

* Din inkorg som används för BCC bör hanteras på rätt sätt för utrymme och leverans. Om inkorgen returnerar studsar kanske vissa e-postmeddelanden inte tas emot och kommer därför inte att arkiveras.

>[!CAUTION]
>
>Undvik att klicka på länken för att avbryta prenumerationen i e-postmeddelanden som skickas till BCC-adressen eftersom du omedelbart kommer att avbeställa motsvarande mottagare.

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

Du kan komma åt den här datauppsättningen via användargränssnittet. Välj **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** > **[!UICONTROL Browse]** och aktivera **[!UICONTROL Show system datasets]** växla från filtret för att visa systemgenererade datauppsättningar. Läs mer om hur du får åtkomst till datauppsättningar i [det här avsnittet](../start/get-started-datasets.md#access-datasets).

![](assets/preset-bcc-dataset.png)

Om du vill köra frågor mot den här datauppsättningen kan du använda Frågeredigeraren från [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;}. Om du vill komma åt den väljer du **[!UICONTROL Data management]** > **[!UICONTROL Queries]** och klicka **[!UICONTROL Create query]**. [Läs mer](../start/get-started-queries.md)

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
   >För att få `<journey version id>`väljer du motsvarande [reseversion](../building-journeys/journey-versions.md) från **[!UICONTROL Journey management]** > **[!UICONTROL Journeys]** -menyn. Resursversions-ID visas i slutet av den URL som visas i webbläsaren.
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
