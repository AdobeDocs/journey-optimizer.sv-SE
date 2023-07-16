---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med Adobe Campaign Standard
description: Lär dig integrera Journey Optimizer med Adobe Campaign Standard
feature: Actions
topic: Administration
role: Admin,Developer
level: Intermediate
keywords: kampanj, standard, integrering, capping, action
exl-id: 2f0218c9-e1b1-44ba-be51-15824b9fc6d2
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 3%

---

# Integrera med Adobe Campaign Standard {#using_adobe_campaign_standard}

Du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Standard Transactional Messaging-funktioner.

Om du har Adobe Campaign Standard finns det en inbyggd åtgärd som tillåter anslutning till Adobe Campaign Standard.

Campaign Standardens transaktionsmeddelande och tillhörande händelse måste publiceras för att kunna användas i Journey Optimizer. Om händelsen publiceras men meddelandet inte visas, visas den inte i Journey Optimizer-gränssnittet. Om meddelandet publiceras men dess associerade händelse inte är det, visas det i Journey Optimizer-gränssnittet, men det går inte att använda det.

## Viktiga anteckningar {#important-notes}

* En begränsning på 4 000 anrop per 5 minuter definieras automatiskt för Adobe Campaign Standard-åtgärder. Detta motsvarar den officiella skalan för Adobe Campaign Standard Transactional Messaging. Läs mer om SLA för transaktionsmeddelanden i [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html).

* Integreringen med Adobe Campaign Standard görs via en särskild inbyggd åtgärd i åtgärdslistan. Detta måste konfigureras för varje sandlåda.

* Du kan inte använda en Campaign Standard-åtgärd med en publikkvalificering eller en målgruppsaktivitet.

* En resa kan inte använda både meddelanden och Campaign Standard-åtgärder.

## Konfigurera åtgärden {#configure-action}

Så här konfigurerar du den:

1. Välj **[!UICONTROL Configurations]** på menyn Administration. I  **[!UICONTROL Actions]** avsnitt, klicka **[!UICONTROL Manage]**. Listan med åtgärder visas.

1. Välj det inbyggda **[!UICONTROL AdobeCampaignStandard]** åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](assets/actioncampaign.png)

1. Kopiera din Adobe Campaign Standard-instans-URL och klistra in den i **[!UICONTROL URL]** fält.

1. Klicka på **[!UICONTROL Test the instance URL]** för att testa instansens giltighet.

   >[!NOTE]
   >
   >Detta test verifierar att
   >
   >Värden är &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; eller &quot;.adls.adobe.com&quot;.
   >
   >URL:en börjar med https,
   >
   >Den ORG som är associerad med den här Adobe Campaign Standard-instansen är samma som Journey Optimizer ORG.

När du utformar din resa kommer tre åtgärder att vara tillgängliga i **[!UICONTROL Action]** kategori: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (se [Använda Adobe Campaign-åtgärder](../building-journeys/using-adobe-campaign-standard.md)).

![](assets/journey58.png)

Du kan använda en **Reaktioner** händelse för att reagera på spårningsdata som rör ett Campaign Standard-meddelande som skickas inom samma resa. För push-meddelanden kan du reagera på klickade, skickade eller misslyckade meddelanden. För SMS-meddelanden kan du reagera på skickade eller misslyckade meddelanden. För e-postmeddelanden kan du reagera på klickade, skickade, öppnade eller misslyckade meddelanden. Se [Reaktionshändelser](../building-journeys/reaction-events.md).

Om du använder ett tredjepartssystem för att skicka meddelanden måste du lägga till och konfigurera en anpassad åtgärd. Se [Om anpassad åtgärdskonfiguration](../action/about-custom-action-configuration.md).