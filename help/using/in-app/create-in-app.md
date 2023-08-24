---
title: Skapa ett meddelande i appen i en kampanj
description: Lär dig hur du skapar ett meddelande i appen i en kampanj i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
exl-id: b3b79fe2-7db3-490d-9c3d-87267aa55eea
source-git-commit: cf3e56f2c87ad39d94cb412fc605f5b235d6d1e1
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 2%

---

# Skapa ett meddelande i appen i en kampanj {#create-in-app}

<!--
>[!BEGINTABS]

>[!TAB Add an In-app message to a journey]

>[!AVAILABILITY]
>
>The In-app activity is currently available as a beta to select users only. To join the beta program, contact Adobe Customer Care.

1. Open your journey, then drag and drop an **[!UICONTROL In-app]** activity from the **[!UICONTROL Actions]** section of the palette.

    When a profile reaches the end of their journey, any in-app messages displayed to them will automatically expire. For that reason, a Wait activity is automatically added after your In-app activity to ensure proper timing.

    ![](assets/in_app_journey_1.png)

1. Enter a **[!UICONTROL Label]** and **[!UICONTROL Description]** for your message.

1. Choose the [In-app surface](inapp-configuration.md) to use.

    ![](assets/in_app_journey_2.png)

1. You can now start designing your content with the **[!UICONTROL Edit content]** button. [Learn more](design-in-app.md)

1. Click **[!UICONTROL Edit trigger]** to configure your Trigger. 

    ![](assets/in_app_journey_4.png)

1. Choose the frequency of your trigger when your In-app message is active:

    * **[!UICONTROL Show every time]**: Always show the message when the events selected in the **[!UICONTROL Mobile app trigger]** drop-down occur.
    * **[!UICONTROL Show once]**: Only show this message the first time the events selected in the **[!UICONTROL Mobile app trigger]** drop-down occur.
    * **[!UICONTROL Show until click through]**: Show this message when the events selected in the **[!UICONTROL Mobile app trigger]** drop-down occur until an interact event is sent by the SDK with an action of "clicked".

1. From the **[!UICONTROL Mobile app trigger]** dropdown(s), choose the event(s) and criteria that will trigger your message:

    1. From the left drop-down, select the event required to trigger the message.
    1. From the right drop-down, select the validation required on the selected event.
    1. Click the **[!UICONTROL Add]** button if you want the trigger to consider multiple events or criteria. Then, repeat the steps above.
    1. Select how your events are linked, e.g. choose **[!UICONTROL And]** if you want **both** triggers to be true in order for a message to be shown or choose **[!UICONTROL Or]** if you want the message to be shown if **either** of the triggers are true.
    1. Click **[!UICONTROL Save]** when your Triggers have been configured.

    ![](assets/in_app_journey_3.png)
    
1. If necessary, complete your journey flow by dragging and dropping additional actions or events. [Learn more](../building-journeys/about-journey-activities.md)

1. Once your In-app message is ready, finalize the configuration and publish your journey to activate it.

For more information on how to configure a journey, refer to [this page](../building-journeys/journey-gs.md).

>[!TAB Add an In-app message to a campaign]
-->

Så här lägger du till ett meddelande i appen i en kampanj:

1. Öppna **[!UICONTROL Campaigns]** menyn och klicka sedan på **[!UICONTROL Create campaign]**.

1. I **[!UICONTROL Properties]** väljer du när kampanjkörningstypen har schemalagts eller API-utlösts. Läs mer om kampanjtyper i [den här sidan](../campaigns/create-campaign.md#campaigntype).

1. I **[!UICONTROL Actions]** väljer du **[!UICONTROL In-app message]** och **[!UICONTROL App surface]** tidigare konfigurerat för ditt meddelande i appen. Klicka sedan på **[!UICONTROL Create]**.

   Läs mer om konfigurationen i appen i [den här sidan](inapp-configuration.md).

   ![](assets/in_app_create_1.png)

1. Från **[!UICONTROL Properties]** anger du **[!UICONTROL Title]** och **[!UICONTROL Description]** description.

1. Om du vill tilldela etiketter för anpassad eller viktig dataanvändning till meddelandet i appen väljer du **[!UICONTROL Manage access]**. [Läs mer](../administration/object-based-access.md).

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer](../audience/about-audiences.md).

   ![](assets/in_app_create_2.png)

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera personer från den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

1. Klicka **[!UICONTROL Create experiment]** för att börja konfigurera ert innehållsexperiment och skapa behandlingar för att mäta deras prestanda och identifiera det bästa alternativet för er målgrupp. [Läs mer](../campaigns/content-experiment.md)

1. Klicka **[!UICONTROL Edit triggers]** för att välja händelser och villkor som ska utlösa meddelandet. Regelbyggare gör det möjligt för användare att ange villkor och värden som, när de möts, utlöser en uppsättning åtgärder, till exempel att skicka ett meddelande i appen.

   1. Klicka på händelselistrutan för att ändra utlösaren om det behövs.

   1. Klicka **[!UICONTROL Add condition]** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor.

   1. Välj **[!UICONTROL Or]** villkor om du vill lägga till fler **[!UICONTROL Triggers]** för att ytterligare utöka regeln.

      ![](assets/in_app_create_3.png)

   1. Välj **[!UICONTROL And]** villkor om du vill lägga till **[!UICONTROL Traits]** och finjustera regeln bättre.

      +++Se tillgängliga fack.

      | Paket | Traits  | Definition |
      |---|---|---|
      | Enhetsinformation | Transportföretagets namn | Utlöses när ett av transportföretagsnamnen i listan uppfylls. |
      | Enhetsinformation | Enhetsnamn | Utlöses när ett av enhetsnamnen uppfylls. |
      | Enhetsinformation | Språk | Utlöses när något av språken i listan uppfylls. |
      | Enhetsinformation | OS-version | Utlöses när en av de angivna operativsystemsversionerna uppfylls. |
      | Enhetsinformation | Tidigare OS-version | Utlöses när någon av de angivna versionerna av föregående operativsystem uppfylls. |
      | Enhetsinformation | Körningsläge | Utlöses om körningsläget är antingen program eller tillägg. |
      | Programmets livscykel | Program-ID | Utlöses när angivet program-ID uppfylls. |
      | Programmets livscykel | Veckodag | Utlöses när den angivna veckodagen har uppnåtts. |
      | Programmets livscykel | Dag sedan första användningen | Utlöses när det angivna antalet dagar sedan första användningen uppfylls. |
      | Programmets livscykel | Dag sedan senaste användning | Utlöses när det angivna antalet dagar sedan den senaste användningen uppfylls. |
      | Programmets livscykel | Dag sedan uppgraderingen | Utlöses när det angivna antalet dagar sedan den senaste uppgraderingen har uppnåtts. |
      | Programmets livscykel | Installationsdatum | Utlöses när det angivna installationsdatumet är uppfyllt. |
      | Programmets livscykel | Launches | Utlöses när det angivna antalet starter uppfylls. |
      | Programmets livscykel | Tid på dagen | Utlöses när den angivna tidpunkten på dagen uppfylls. |
      | Platser | Aktuell POI | Utlöses av Platser SDK när kunden anger den angivna Intressepunkten (POI). |
      | Platser | Senaste inmatade POI | Utlöses av Places SDK beroende på vilken kund som senast angav Point of Interest (POI). |
      | Platser | Senaste utloggad POI | Utlöses av Places SDK beroende på din kunds sista utlämnade punkt för intresse (POI). |

+++

      ![](assets/in_app_create_8.png)

   1. Klicka **[!UICONTROL Make group]** för att gruppera utlösare tillsammans.

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt. Följande alternativ är tillgängliga:

   * **[!UICONTROL Everytime]**: Visa alltid meddelandet när de händelser som valts i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** rullgardinsmenyn inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.
   * **[!UICONTROL X number of times]**: Visa det här meddelandet X-tid.

1. Välj vid behov **[!UICONTROL Day of the week]** eller **[!UICONTROL Time of day]** meddelandet visas i appen.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

   ![](assets/in-app-schedule.png)

1. Nu kan du börja utforma ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

   ![](assets/in_app_create_4.png)

<!--
>[!ENDTABS]
-->

## Instruktionsvideor{#video}

* I videon nedan visas hur du skapar, konfigurerar och publicerar meddelanden i appen i dina kampanjer.

  >[!VIDEO](https://video.tv.adobe.com/v/3410430?quality=12&learn=on)


* I videon nedan visas hur du konfigurerar och analyserar innehållsexperiment i A/B-testmeddelanden i appen.

  >[!VIDEO](https://video.tv.adobe.com/v/3419898)



**Relaterade ämnen:**

* [Design In-app-meddelande](design-in-app.md)
* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)