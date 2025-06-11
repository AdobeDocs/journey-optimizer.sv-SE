---
solution: Journey Optimizer
product: journey optimizer
title: Uppdaterad rapportupplevelse
description: Kom igång med hela tidsrapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: bfd88d2a-e7b8-4e3b-85a1-4a14b0ba56dc
source-git-commit: a9349cedc4da2a8e76e53f9e2b5185270cda2558
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 2%

---

# Kom igång med hela tidsrapporten {#channel-report-gs-cja}

>[!CONTEXTUALHELP]
>id="cja_connections_enable_cja"
>title="Aktivera Customer Journey Analytics"
>abstract="Om du vill analysera den här rapporten i Customer Journey Analytics kontaktar du administratören för att kontrollera att din organisation har köpt Customer Journey Analytics och att integreringen är korrekt konfigurerad."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/email/design-email/add-content/content-components#add-content-components" text="Customer Journey Analytics"

Journey Optimizer rapportering har förbättrad interoperabilitet med Customer Journey Analytics funktioner, standardiserad rapportering på båda plattformarna och förbättrad datakonsekvens och tillförlitlighet. Denna smidiga integrering mellan Journey Optimizer och Customer Journey Analytics ger en tydligare bild av prestandamätningarna, så att användarna kan fatta mer välgrundade beslut.

Tillgång till dessa rapporteringsfunktioner beror på sammanhang och produktområden:

* **Resor** - Om du vill rikta in dig på en resa eller leveranser i samband med en resa går du till **[!UICONTROL Journeys]**-menyn och klickar på knappen **[!UICONTROL View report]**.

  I listan över befintliga resor kan du även välja **[!UICONTROL Report]** på den avancerade menyn för den valda resan. [Läs mer om reserapporten](journey-global-report-cja.md)

  ![](assets/gs-cja-report-3.png)

* **Kampanjer** - Om du vill rikta en kampanj går du till **[!UICONTROL Campaigns]** -menyn, öppnar kampanjen och klickar på **[!UICONTROL Reports]**-knappen och sedan **[!UICONTROL View all time report]**.

  I listan över befintliga kampanjer kan du även välja **[!UICONTROL Report]** på den avancerade menyn för den valda kampanjen. [Läs mer om Campaign-rapporten](campaign-global-report-cja.md)

  ![](assets/gs-cja-report-2.png)

* **Global** - Om du vill ange mätvärden för alla kampanjer och resor i din miljö, öppnar du **översiktsrapporten** genom att gå till **[!UICONTROL Reports]** -menyn i **[!UICONTROL Journey Management]** -avsnittet. [Läs mer om översiktsrapporten](channel-report-cja.md)

  ![](assets/gs-cja-report-1.png)

>[!IMPORTANT]
>
>Rapportering i Adobe Journey Optimizer är för närvarande standardiserat med UTC. Möjligheten att anpassa tidszonen för rapportering kommer att introduceras i en framtida version.

## Förhandskrav {#prerequisites}

* Om du **inte** äger Customer Journey Analytics, eller om du äger det men **inte** har tillgång till någon Customer Journey Analytics-produktprofil, hanteras behörigheter i Journey Optimizer. I det här fallet behöver du behörigheten **[!UICONTROL View channel reports]** eller relaterade roller. [Läs mer](../administration/permissions.md)

* Om du **äger** Customer Journey Analytics och har tillgång till en Customer Journey Analytics-produktprofil behöver du:

   * **[!UICONTROL Audience Creation]** och **[!UICONTROL Audience View]** behörigheter för Customer Journey Analytics. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/technotes/access-control){target="_blank"}

   * **[!UICONTROL Manage profiles]** behörighet för Adobe Journey Optimizer. [Läs mer](../administration/permissions.md)

* Dina Customer Journey Analytics-data måste konfigureras med följande inställning: **Ange som standarddatavy i Adobe Journey Optimizer**. [Läs mer om datavyer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}


## Alla tidsrapporter per kanal

Alla globala rapporter är tillgängliga för alla era kanaler. Välj rapporten för den kanal du behöver för att få mer information.

### Utgående kanaler

Välj en utgående kanal för att identifiera associerade **globala heltidsrapporter**.

<table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="e-post" src="../channels/assets/do-not-localize/email.png">
<div align="center"><p><strong>E-postkanal</strong></p><p><a href="campaign-global-report-cja-email.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-email.md"><strong>Reserapport</strong></a></p></div></td>
<td><a href="campaign-global-report-cja-sms.md"><img alt="sms" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><p><strong>SMS-kanal</strong></p><p><a href="campaign-global-report-cja-sms.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-sms.md"><strong>Reserapport</strong></a></p></div></td>
<td><a href="campaign-global-report-cja-push.md"><img alt="push" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><p><strong>Push-kanal</strong></p><p><a href="campaign-global-report-cja-push.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-push.md"><strong>Reserapport</strong></a></p></div></td>
<td><a href="campaign-global-report-cja-direct.md"><img alt="direktreklam" src="../channels/assets/do-not-localize/direct-mail.jpg"></a>
<div align="center"><p><strong>Direktpostkanal</strong></p><p><a href="campaign-global-report-cja-direct.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-direct.md"><strong>Reserapport</strong></a></p></div></td>
</tr></table>

### Inkommande upplevelser

Välj en inkommande upplevelse för att identifiera associerade **globala heltidsrapporter**.

<table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="i appen" src="../channels/assets/do-not-localize/inapp.jpg">
<div align="center"><p><strong>Kanal i appen</strong></p><p><a href="campaign-global-report-cja-inapp.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-inapp.md"><strong>Reserapport</strong></a></p></div></td>
<td><p><img alt="webb" src="../channels/assets/do-not-localize/web.jpg"></p>
<div align="center"><p><strong>Webbkanal</strong></p><p><a href="campaign-global-report-cja-web.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-web.md"><strong>Reserapport</strong></a></p></div></td>
<td><img alt="kodbaserad upplevelse" src="../channels/assets/do-not-localize/code.png">
<div align="center"><p><strong>Kodbaserade upplevelser</strong></p><p><a href="campaign-global-report-cja-code.md"><strong>Kampanjrapport</strong></a></p><p><a href="campaign-global-report-cja-code.md"><strong>Reserapport</strong></a></p></div></td>
<td><img alt="innehållskort" src="../channels/assets/do-not-localize/cards.png">
<div align="center"><p><strong>Innehållskort</strong></p><p><a href="campaign-global-report-cja-content.md"><strong>Kampanjrapport</strong></a></p><p><a href="journey-global-report-cja-content.md"><strong>Reserapport</strong></a></p></div></td>
</tr></table>

## Instruktionsvideo{#video}

I videon nedan visas hur du använder den förbättrade Journey Optimizer-rapporteringen med Customer Journey Analytics.

>[!VIDEO](https://video.tv.adobe.com/v/3443155?captions=swe)