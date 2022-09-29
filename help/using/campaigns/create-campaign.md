---
title: Skapa en kampanj
description: Lär dig hur du skapar kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
source-git-commit: 0167ce16198acc485da687a4a05c13fae85d088d
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---

# Skapa en kampanj {#create-campaign}

>[!NOTE]
>
>Innan du skapar en ny kampanj måste du se till att du har en ytkanal (dvs. meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att använda. Läs mer i följande avsnitt:
>
>* [Skapa kanalytor](../configuration/channel-surfaces.md)
>* [Kom igång med segment](../segment/about-segments.md)


## Skapa din första kampanj {#create}

1. Öppna **[!UICONTROL Campaigns]** menyn och klicka sedan på **[!UICONTROL Create campaign]**.

   >[!NOTE]
   >
   >Du kan också duplicera en befintlig livekampanj och skapa en ny. [Läs mer](modify-stop-campaign.md#duplicate)

   ![](assets/create-campaign.png)

1. I **[!UICONTROL Properties]** anger du när kampanjen ska köras:

   * **[!UICONTROL Scheduled]**: köra kampanjen direkt eller på ett angivet datum. Schemalagda kampanjer syftar till att skicka **marknadsföring** typmeddelanden.
   * **[!UICONTROL API-triggered]**: köra kampanjen med ett API-anrop. API-utlösta kampanjer är avsedda att skicka **transaktionsbaserad** meddelanden, dvs. meddelanden som skickas ut efter en åtgärd som utförts av en individ: lösenordsåterställning, övergivna kort osv. [Lär dig hur du utlöser en kampanj med API:er](api-triggered-campaigns.md)

1. I **[!UICONTROL Actions]** väljer du kanal och kanal för att skicka meddelandet och klickar sedan på **[!UICONTROL Create]**.

   En yta är en konfiguration som har definierats av en [Systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >Endast kanalytor som är kompatibla med marknadsföringskampanjtypen visas i listrutan.

1. Ange en titel och en beskrivning för kampanjen.

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. I **[!UICONTROL Actions]** konfigurerar du meddelandet som ska skickas med kampanjen:

   1. Klicka på **[!UICONTROL Edit content]** och sedan konfigurera och utforma meddelandeinnehållet. [Läs mer om meddelanden](../messages/get-started-content.md).

      Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sida:

      * [Skapa ett e-postmeddelande](../messages/create-email.md)
      * [Skapa push-meddelanden](../messages/create-push.md)
      * [Skapa ett SMS-meddelande](../messages/create-sms.md)
   1. När innehållet är definierat kan du använda **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler. [Läs mer](../design/preview.md).

   1. Klicka på pilen för att gå tillbaka till skärmen för att skapa kampanjer.

      ![](assets/create-campaign-design.png)

   1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

      Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report.md)


1. Definiera målgruppen. Om du vill göra det klickar du på **[!UICONTROL Select audience]** om du vill visa en lista över tillgängliga Adobe Experience Platform-segment. [Läs mer om segment](../segment/about-segments.md)

   >[!NOTE]
   >
   >För API-utlösta kampanjer måste målgruppen anges via API-anrop. [Läs mer](api-triggered-campaigns.md)

   I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace)

   ![](assets/create-campaign-namespace.png)

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kommer inte att omfattas av kampanjen.

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

1. Konfigurera **[!UICONTROL Schedule]** -avsnitt. [Lär dig schemalägga kampanjer](#schedule)

1. Klicka på knappen **[!UICONTROL Manage access]** -knappen. [Läs mer om OLA (Object Level Access Control)](../administration/object-based-access.md)

När kampanjen är klar kan ni granska och publicera den. [Läs mer](#review-activate)

## Schemalägg en kampanj {#schedule}

Som standard börjar kampanjer när de har aktiverats manuellt och avslutas så snart meddelandet har skickats en gång.

Du kan definiera hur ofta kampanjens meddelande ska skickas. Om du vill göra det använder du **[!UICONTROL Action triggers]** alternativ på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

Om du inte vill genomföra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med **[!UICONTROL Campaign start]** alternativ. The  **[!UICONTROL Campaign end]** kan du ange när en återkommande kampanj ska sluta köras.

![](assets/create-campaign-schedule.png)

## Snabb leverans {#rapid-delivery}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_rapid_delivery"
>title="Snabb leverans"
>abstract="Snabb leverans är ett Journey Optimizer-tillägg som gör att du snabbt kan använda icke-personaliserade meddelanden till målgrupper under 30M-profiler."

Snabb leverans, som tidigare kallades Burst-läge under resor, är ett [!DNL Journey Optimizer] tillägg som gör det möjligt att skicka mycket snabba push-meddelanden i stora volymer via kampanjer.

Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp.

Mer information om prestanda när du använder läget Snabb leverans finns i [Adobe Journye Optimizer - produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html).


### Förutsättningar {#prerequisites}

Snabba leveransmeddelanden innehåller följande krav:

* Snabb leverans av **[!UICONTROL Scheduled]** endast kampanjer och inte för API-utlösta kampanjer,
* Ingen personalisering tillåts i push-meddelandet,
* Målgruppen måste innehålla färre än 30M profiler,
* Du kan köra upp till 5 kampanjer samtidigt i läget Snabb leverans.

### Aktivera läget Snabb leverans

1. Skapa en push-meddelandekampanj och aktivera **[!UICONTROL Rapid delivery]** alternativ.

![](assets/create-campaign-burst.png)

1. Konfigurera meddelandeinnehållet och välj målgrupp. [Lär dig hur du skapar en kampanj](#create)

   >[!IMPORTANT]
   >
   >Se till att meddelandeinnehållet inte innehåller någon personalisering och att målgruppen innehåller färre än 30 miljoner profiler.

1. Granska och aktivera kampanjen som vanligt. Observera att i testläge skickas inga meddelanden via läget Snabb leverans. [Lär dig hur du granskar och aktiverar en kampanj](review-activate-campaign.md)
