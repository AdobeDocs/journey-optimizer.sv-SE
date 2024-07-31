---
title: Konfigurera webbkanalen i appen
description: Lär dig hur du konfigurerar webbkanalen i appen i datainsamlingen
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
exl-id: 5a67177e-a7cf-41a8-9e7d-37f7fe3d34dc
source-git-commit: 85aee5c5ff9ceee10b2dc01ef9e31947cef9daae
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 2%

---

# Skapa ett meddelande i appen för webben {#create-in-app-web}

## Konfigurera webbkanalen i appen {#configure-web-inapp}

Följ stegen nedan för att konfigurera webbkanalen i appen:

* Installera taggtillägget Web SDK om du vill ha stöd för Web In-app Messaging. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html?lang=en)

* Anpassa utlösarna. Meddelanden i appen stöder två typer av utlösare: Skickade data till plattformen och Manuella utlösare. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-in-app-messaging.html)

## Skapa en webbkampanj i appen {#create-inapp-web-campaign}

1. Öppna menyn **[!UICONTROL Campaigns]** och klicka sedan på **[!UICONTROL Create campaign]**.

1. I avsnittet **[!UICONTROL Properties]** väljer du när kampanjkörningstypen: Schemalagd eller API-utlöst. Läs mer om kampanjtyper på [den här sidan](../campaigns/create-campaign.md#campaigntype).

1. Välj **[!UICONTROL In-app message]** i avsnittet **[!UICONTROL Actions]**. Välj Webb i listrutan **[!UICONTROL Send to]**.

   ![](assets/in_app_web_surface_1.png)

1. Definiera en appyta. Du kan göra ändringar på två sätt:

   * Du kan antingen ange en **[!UICONTROL Page URL]** för att tillämpa ändringar på en viss sida.

   * Du kan skapa en regel för flera URL:er som följer samma mönster.

+++ Så här skapar du en sidmatchningsregel.

      1. Välj **[!UICONTROL Pages matching rule]** som appyta.
      1. Klicka på **[!UICONTROL Create rule]**.

         ![](assets/in_app_web_surface_3.png)

      1. I fönstret **[!UICONTROL Edit surface rule]** definierar du dina villkor för fälten **[!UICONTROL Domain]** och **[!UICONTROL Page]**.
      1. I listrutorna kan du anpassa villkoren ytterligare.

         Här kan du till exempel redigera element som visas på alla försäljningsproduktsidor på Luma-webbplatsen genom att välja Domän > Börjar med > luma och Sida > Innehåller > Försäljning.

         ![](assets/in_app_web_surface_4.png)

      1. Spara ändringarna. Regeln visas på skärmen **[!UICONTROL Create campaign]**.

+++

   ![](assets/in_app_web_surface_2.png)

1. När appytan har valts och konfigurerats klickar du på **[!UICONTROL Create]**.

## Definiera webbkampanjen i appen {#configure-inapp}

1. I avsnittet **[!UICONTROL Properties]** anger du **[!UICONTROL Title]** och **[!UICONTROL Description]**-beskrivningen.

1. Välj **[!UICONTROL Manage access]** om du vill tilldela etiketter för anpassad eller viktig dataanvändning till meddelandet i appen. [Läs mer](../administration/object-based-access.md).

1. Klicka på knappen **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer](../audience/about-audiences.md).

   ![](assets/in_app_web_surface_5.png)

1. I fältet **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera personer från den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

1. På menyn **[!UICONTROL Action]** hittar du de inställningar som tidigare konfigurerats som **[!UICONTROL App surface]**. Du kan göra ändringar här om det behövs eller uppdatera regeln genom att klicka på **[!UICONTROL Edit Rule]**.

1. Klicka på **[!UICONTROL Create experiment]** för att börja konfigurera ditt innehållsexperiment och skapa behandlingar för att mäta deras prestanda och identifiera det bästa alternativet för målgruppen. [Läs mer](../content-management/content-experiment.md)

1. Klicka på **[!UICONTROL Edit triggers]** för att välja händelser och villkor som ska utlösa meddelandet. Regelbyggare gör det möjligt för användare att ange villkor och värden som, när de möts, utlöser en uppsättning åtgärder, till exempel att skicka ett meddelande i appen.

   1. Klicka på händelselistrutan för att ändra utlösaren om det behövs.

      +++Se tillgängliga utlösare.

      | Paket | Utlösare | Definition |
      |---|---|---|
      | Plattform | Skickade data till plattformen | Utlöses när mobilappen utfärdar en edge experience-händelse för att skicka data till Adobe Experience Platform. Vanligtvis API-anropet [sendEvent](https://developer.adobe.com/client-sdks/documentation/edge-network/api-reference/#sendevent) från AEP Edge-tillägget. |
      | Manuell | Manuell utlösare | Två associerade dataelement: en nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris), och ett värde, som är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). |

+++

   1. Klicka på **[!UICONTROL Add condition]** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor.

   1. Välj villkoret **[!UICONTROL Or]** om du vill lägga till fler **[!UICONTROL Triggers]** för att utöka regeln ytterligare.

      ![](assets/in_app_web_surface_8.png)

   1. Välj villkoret **[!UICONTROL And]** om du vill lägga till en anpassad **[!UICONTROL Trait]** och finjustera regeln bättre.

      +++Se tillgängliga fack.

      | Paket | Trait | Definition |
      |---|---|---|
      | Plattform | XDM-händelsetyp | Utlöses när den angivna händelsetypen uppfylls. |
      | Plattform | XDM-värde | Utlöses när det angivna XDM-värdet uppfylls. |

+++

      ![](assets/in_app_web_surface_9.png)

   1. Klicka på **[!UICONTROL Make group]** för att gruppera utlösare.

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt. Följande alternativ är tillgängliga:

   * **[!UICONTROL Everytime]**: Visa alltid meddelandet när de händelser som valts i listrutan **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Once]**: Visa endast det här meddelandet första gången som de händelser som är markerade i listrutan **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Until click through]**: Visa det här meddelandet när de händelser som är markerade i listrutan **[!UICONTROL Mobile app trigger]** inträffar tills en interaktionshändelse skickas av SDK med åtgärden &quot;klickad&quot;.
   * **[!UICONTROL X number of times]**: Visa det här meddelandet X-tid.

1. Om det behövs väljer du vilken **[!UICONTROL Day of the week]** eller **[!UICONTROL Time of day]** meddelandet i appen ska visas.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** för din kampanj i [det här avsnittet](../campaigns/create-campaign.md#schedule).

   ![](assets/in_app_web_surface_6.png)

1. Nu kan du börja designa ditt innehåll med knappen **[!UICONTROL Edit content]**. [Läs mer](design-in-app.md)

   ![](assets/in_app_web_surface_7.png)

**Relaterade ämnen:**

* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)
