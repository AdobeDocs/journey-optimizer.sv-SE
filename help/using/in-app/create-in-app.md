---
title: Skapa ett meddelande i appen i Journey Optimizer
description: Lär dig skapa ett meddelande i appen i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
exl-id: b3b79fe2-7db3-490d-9c3d-87267aa55eea
source-git-commit: 94c4e0e53625fdf20f940e8bfd15d67dba1d0120
workflow-type: tm+mt
source-wordcount: '1847'
ht-degree: 1%

---

# Skapa ett meddelande i appen {#create-in-app}

Du kan lägga till ett meddelande i appen i en kampanj eller under en resa. Följ stegen nedan för att skapa ett meddelande i appen i båda kontexterna.

>[!BEGINTABS]

>[!TAB Lägg till ett meddelande i appen till en resa]

Så här lägger du till ett meddelande i appen under en resa:

1. Öppna din resa och dra och släpp en **[!UICONTROL In-app]** aktivitet från **[!UICONTROL Actions]** på paletten.

   När en profil når slutet av sin resa kommer alla meddelanden i appen som visas för dem automatiskt att upphöra att gälla. Av den anledningen läggs en Wait-aktivitet automatiskt till efter aktiviteten i appen för att säkerställa korrekt timing.

   ![](assets/in_app_journey_1.png)

1. Ange en **[!UICONTROL Label]** och **[!UICONTROL Description]** för ditt meddelande.

1. Välj [Yta i appen](inapp-configuration.md) att använda.

   ![](assets/in_app_journey_2.png)

1. Nu kan du börja utforma ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

1. Klicka **[!UICONTROL Edit triggers]** för att välja händelser och villkor som ska utlösa meddelandet. Regelbyggare gör det möjligt för användare att ange villkor och värden som, när de möts, utlöser en uppsättning åtgärder, till exempel att skicka ett meddelande i appen.

   ![](assets/in_app_journey_4.png)

   1. Klicka på händelselistrutan för att ändra utlösaren om det behövs.

      +++Se tillgängliga utlösare.

      | Paket | Utlösare | Definition |
      |---|---|---|
      | Skicka data till plattformen | Skickade data till plattformen | Utlöses när mobilappen utfärdar en edge experience-händelse för att skicka data till Adobe Experience Platform. Vanligtvis API-anropet [sendEvent](https://developer.adobe.com/client-sdks/documentation/edge-network/api-reference/#sendevent) från AEP Edge-tillägget. |
      | Core tracking | Spåra åtgärd | Utlöses när de äldre funktionerna i API:t för mobilkod finns [trackAction](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction) anropas. |
      | Core tracking | Spåra läge | Utlöses när de äldre funktionerna i API:t för mobilkod finns [trackState](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackstate) anropas. |
      | Core tracking | Samla in PII | Utlöses när de äldre funktionerna i API:t för mobilkod finns [collectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii) anropas. |
      | Programmets livscykel | Programstart | Utlöses vid varje körning, inklusive krascher och installationer. Utlöses också vid ett återköp från bakgrunden när tidsgränsen för livscykelsessionen har överskridits. |
      | Programmets livscykel | Programinstallation | Utlöses vid första körningen efter installation eller ominstallation. |
      | Programmets livscykel | Programuppdatering | Utlöses vid första körningen efter en uppgradering eller när versionsnumret ändras. |
      | Programmets livscykel | Programmet stängs | Utlöses när programmet stängs. |
      | Programmets livscykel | Programkrasch | Utlöses när programmet inte är bakgrundsbelagt innan det stängs. Händelsen skickas när programmet startas efter kraschen. Kraschrapportering för Adobe Mobile implementerar inte en global hanterare för ej infångade undantag. |
      | Platser | Ange POI | Utlöses av Places SDK när kunden anger den POI (Point of Interest) som du har konfigurerat. |
      | Platser | Avsluta POI | Utlöses av Places SDK när kunden avslutar det Point of Interest (POI) som du konfigurerade. |

+++

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

      ![](assets/in_app_journey_3.png)

   1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt:

      * **[!UICONTROL Show every time]**: Visa alltid meddelandet när de händelser som valts i **[!UICONTROL Mobile app trigger]** inträffar.
      * **[!UICONTROL Show once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
      * **[!UICONTROL Show until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** rullgardinsmenyn inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.

1. Slutför vid behov kundresan genom att dra och släppa ytterligare åtgärder eller händelser. [Läs mer](../building-journeys/about-journey-activities.md)

1. När ditt meddelande i appen är klart slutför du konfigurationen och publicerar din resa för att aktivera den.

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

>[!TAB Lägga till ett meddelande i appen till en kampanj]

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

      +++Se tillgängliga utlösare.

      | Paket | Utlösare | Definition |
      |---|---|---|
      | Skicka data till plattformen | Skickade data till plattformen | Utlöses när mobilappen utfärdar en edge experience-händelse för att skicka data till Adobe Experience Platform. Vanligtvis API-anropet [sendEvent](https://developer.adobe.com/client-sdks/documentation/edge-network/api-reference/#sendevent) från AEP Edge-tillägget. |
      | Core tracking | Spåra åtgärd | Utlöses när de äldre funktionerna i API:t för mobilkod finns [trackAction](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction) anropas. |
      | Core tracking | Spåra läge | Utlöses när de äldre funktionerna i API:t för mobilkod finns [trackState](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackstate) anropas. |
      | Core tracking | Samla in PII | Utlöses när de äldre funktionerna i API:t för mobilkod finns [collectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii) anropas. |
      | Programmets livscykel | Programstart | Utlöses vid varje körning, inklusive krascher och installationer. Utlöses också vid ett återköp från bakgrunden när tidsgränsen för livscykelsessionen har överskridits. |
      | Programmets livscykel | Programinstallation | Utlöses vid första körningen efter installation eller ominstallation. |
      | Programmets livscykel | Programuppdatering | Utlöses vid första körningen efter en uppgradering eller när versionsnumret ändras. |
      | Programmets livscykel | Programmet stängs | Utlöses när programmet stängs. |
      | Programmets livscykel | Programkrasch | Utlöses när programmet inte är bakgrundsbelagt innan det stängs. Händelsen skickas när programmet startas efter kraschen. Kraschrapportering för Adobe Mobile implementerar inte en global hanterare för ej infångade undantag. |
      | Platser | Ange POI | Utlöses av Places SDK när kunden anger den POI (Point of Interest) som du har konfigurerat. |
      | Platser | Avsluta POI | Utlöses av Places SDK när kunden avslutar det Point of Interest (POI) som du konfigurerade. |

+++

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

>[!ENDTABS]

## Instruktionsvideor{#video}

* I videon nedan visas hur du skapar, konfigurerar och publicerar meddelanden i appen i dina kampanjer.

  +++Se video

  >[!VIDEO](https://video.tv.adobe.com/v/3410430?quality=12&learn=on)

+++

* I videon nedan visas hur du konfigurerar och analyserar innehållsexperiment med A/B-testmeddelanden i appen.

  +++Se video

  >[!VIDEO](https://video.tv.adobe.com/v/3419898)

+++

* I videon nedan visas hur du skapar ett meddelande i appen under en resa och hur du testar och publicerar din resa.

  +++Se video

  >[!VIDEO](https://video.tv.adobe.com/v/3423077)

+++

**Relaterade ämnen:**

* [Design In-app-meddelande](design-in-app.md)
* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)