---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera den API-utlösta kampanjåtgärden
description: Lär dig hur du konfigurerar den API-utlösta kampanjåtgärden.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---


# Konfigurera den API-utlösta kampanjåtgärden {#api-action}

Använd fliken **[!UICONTROL Actions]** för att välja en kanalkonfiguration för meddelandet och konfigurera ytterligare inställningar som spårning, innehållsexperiment eller flerspråkigt innehåll.

1. **Välj kanal**.

   Navigera till fliken **[!UICONTROL Actions]**, klicka på knappen **[!UICONTROL Add action]** och markera kommunikationskanalen.

   ![](assets/api-triggered-channel.png)

   >[!NOTE]
   >
   >Vilka kanaler som är tillgängliga varierar beroende på licensmodell och tillägg.
   >
   >För API-utlösta kampanjer är endast e-post-, SMS- och push-meddelandekanaler tillgängliga.

1. **Välj en kanalkonfiguration**

   En konfiguration definieras av en [systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md)

   ![](assets/create-campaign-action.png)

1. **Skapa ett innehållsexperiment**

   Använd avsnittet **[!UICONTROL Content experiment]** för att definiera flera leveransbehandlingar för att mäta vilken som fungerar bäst för målgruppen. Klicka på knappen **[!UICONTROL Create experiment]** och följ sedan stegen som beskrivs i det här avsnittet: [Skapa ett innehållsexperiment](../content-management/content-experiment.md).

1. **Lägg till flerspråkigt innehåll**

   Använd avsnittet **[!UICONTROL Languages]** för att skapa innehåll på flera språk i kampanjen. Om du vill göra det klickar du på knappen **[!UICONTROL Add languages]** och väljer önskad **[!UICONTROL Language settings]**. Detaljerad information om hur du konfigurerar och använder flerspråkiga funktioner finns i det här avsnittet: [Kom igång med flerspråkigt innehåll](../content-management/multilingual-gs.md)

Ytterligare inställningar är tillgängliga beroende på den valda kommunikationskanalen. Expandera avsnitten nedan om du vill ha mer information.

+++**Använd regler för begränsning** (e-post, push, SMS)

I listrutan **[!UICONTROL Business rules]** väljer du en regeluppsättning för att tillämpa regler för appning på kampanjen. Genom att utnyttja kanalregeluppsättningar kan ni ange frekvensbegränsning efter kommunikationstyp för att förhindra att kunder med liknande meddelanden överbelastas. [Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

+++

+++**Spåra engagemang** (e-post, SMS).

Använd avsnittet **[!UICONTROL Action tracking]** för att spåra hur dina mottagare svarar på dina e-post- eller SMS-leveranser. Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report-cja.md)

+++

+++**Aktivera läget Snabb leverans** (push).

Snabb leverans är ett [!DNL Journey Optimizer]-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer via kampanjer. Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp. Mer information om prestanda när du använder läget Snabb leverans finns i [Adobe Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html).

+++

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan ni utforma dess innehåll. [Läs mer](api-triggered-campaign-content.md)
