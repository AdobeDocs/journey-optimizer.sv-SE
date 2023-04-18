---
title: Skapa ett meddelande i appen
description: Lär dig hur du skapar ett meddelande i appen i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
exl-id: b3b79fe2-7db3-490d-9c3d-87267aa55eea
source-git-commit: 0c32248d13c08a98e9298ddc932aa2e547ab2acd
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Skapa ett meddelande i appen {#create-in-app}

Meddelanden i appen skapas i samband med en kampanj.

>[!BEGINTABS]

>[!TAB Lägg till ett meddelande i appen till en resa]

>[!AVAILABILITY]
>
>Aktiviteten i appen är för närvarande endast tillgänglig som en betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

1. Öppna din resa och dra och släpp en **[!UICONTROL In-app]** aktivitet från **[!UICONTROL Actions]** på paletten.

   När en profil når slutet av sin resa kommer alla meddelanden i appen som visas för dem automatiskt att upphöra att gälla. Av den anledningen läggs en Wait-aktivitet automatiskt till efter aktiviteten i appen för att säkerställa korrekt timing.

   ![](assets/in_app_journey_1.png)

1. Ange **[!UICONTROL Label]** och **[!UICONTROL Description]** för ditt meddelande.

1. Välj [Yta i appen](inapp-configuration.md) att använda.

   ![](assets/in_app_journey_2.png)

1. Nu kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

1. Klicka **[!UICONTROL Edit trigger]** för att konfigurera utlösaren.

   ![](assets/in_app_journey_4.png)

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt:

   * **[!UICONTROL Show every time]**: Visa alltid meddelandet när de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Show once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Show until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** nedrullningsbar meny inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.

1. Från **[!UICONTROL Mobile app trigger]** väljer du de händelser och villkor som ska utlösa meddelandet:

   1. I den vänstra listrutan väljer du den händelse som krävs för att utlösa meddelandet.
   1. Välj den validering som krävs för den valda händelsen i den högra listrutan.
   1. Klicka på **[!UICONTROL Add]** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor. Upprepa sedan stegen ovan.
   1. Välj hur dina händelser ska länkas, t.ex. välj **[!UICONTROL And]** om du vill **båda** utlösare är true för att ett meddelande ska kunna visas eller väljas **[!UICONTROL Or]** om du vill att meddelandet ska visas om **antingen** av utlösarna är sanna.
   1. Klicka **[!UICONTROL Save]** när dina utlösare har konfigurerats.

   ![](assets/in_app_journey_3.png)

1. Slutför vid behov kundresan genom att dra och släppa ytterligare åtgärder eller händelser. [Läs mer](../building-journeys/about-journey-activities.md)

1. När ditt meddelande i appen är klart slutför du konfigurationen och publicerar din resa för att aktivera den.

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

>[!TAB Lägga till ett meddelande i appen till en kampanj]

1. Öppna **[!UICONTROL Campaigns]** menyn och klicka sedan på **[!UICONTROL Create campaign]**.

1. I **[!UICONTROL Properties]** väljer du när kampanjkörningstypen: Schemalagd eller API-utlöst. Läs mer om kampanjtyper i [den här sidan](../campaigns/create-campaign.md#campaigntype).

1. I **[!UICONTROL Actions]** väljer du **[!UICONTROL In-app message]** och **[!UICONTROL App surface]** tidigare konfigurerat för ditt meddelande i appen. Klicka sedan på **[!UICONTROL Create]**.

   Läs mer om konfigurationen i appen i [den här sidan](inapp-configuration.md).

   ![](assets/in_app_create_1.png)

1. Från **[!UICONTROL Properties]** anger du **[!UICONTROL Title]** och **[!UICONTROL Description]** description.

1. Om du vill tilldela etiketter för anpassad eller viktig dataanvändning till meddelandet i appen väljer du **[!UICONTROL Manage access]**. [Läs mer](../administration/object-based-access.md).

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment. [Läs mer](../segment/about-segments.md).

   ![](assets/in_app_create_2.png)

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer](../event/about-creating.md#select-the-namespace).

1. Klicka **[!UICONTROL Edit triggers]** för att välja händelser och villkor som ska utlösa meddelandet:

   1. Klicka **Lägg till villkor** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor.
   1. Välj hur dina händelser ska länkas, t.ex. välj **[!UICONTROL And]** om du vill **båda** utlösare är true för att ett meddelande ska kunna visas eller väljas **[!UICONTROL Or]** om du vill att meddelandet ska visas om **antingen** av utlösarna är sanna.
   1. Klicka **[!UICONTROL Make group]** för att gruppera utlösare tillsammans.

   ![](assets/in_app_create_3.png)

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt. Följande alternativ är tillgängliga:

   * **[!UICONTROL Everytime]**: Visa alltid meddelandet när de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** nedrullningsbar meny inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.
   * **[!UICONTROL X number of times]**: Visa det här meddelandet X-tid.

1. Välj vid behov **[!UICONTROL Day of the week]** eller **[!UICONTROL Time of day]** meddelandet visas i appen.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

   ![](assets/in-app-schedule.png)

1. Nu kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

   ![](assets/in_app_create_4.png)

>[!ENDTABS]

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar, konfigurerar och publicerar meddelanden i appen i dina kampanjer.

>[!VIDEO](https://video.tv.adobe.com/v/3410430?quality=12&learn=on)


**Relaterade ämnen:**

* [Design In-app-meddelande](design-in-app.md)
* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)