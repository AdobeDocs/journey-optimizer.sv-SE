---
title: Rapport i appen
description: Lär dig hur du använder data från rapporten i appen
feature: Reporting
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 3d496efc-1bf9-4895-906c-3757f92c6fe3
source-git-commit: c4683e10e4a15f99206a3e8702c1ad20591f1d67
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 3%

---

# Rapport i appen {#inapp-report}

Rapporten i appen är tillgänglig i Campaign-rapporten.

Kampanjrapportsidan visas med följande flikar:

* [Campaign](../reports/campaign-global-report.md#campaign-live)
* [E-post](../reports/campaign-global-report.md#email-live)
* [Push](../reports/campaign-global-report.md#push-live)
* [SMS](../reports/campaign-global-report.md#sms-live)
* [I appen](#in-app-global)

Kampanjen **[!UICONTROL Global report]** är uppdelat i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](../reports/global-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](../reports/global-report.md#list-of-components-global.md)

## Fliken I appen {#inapp-global}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL In-app]** -fliken innehåller huvudinformationen om de leveranser i appen som skickas i kampanjen.

![](assets/campaign_report_global_6.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten i appen.

The **[!UICONTROL In-app performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era meddelanden i appen, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som meddelandet i appen levererades till.

* **[!UICONTROL Impressions]**: Totalt antal meddelanden i appen som levereras till alla användare.

* **[!UICONTROL Click rate]**: procentandelen användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.

* **[!UICONTROL Dismiss rate]**: Andel meddelanden i appen som mottagarna avvisade.

The **[!UICONTROL In-app summary]** diagram visar hur dina visningar i appen har utvecklats för den aktuella perioden.

The **[!UICONTROL Clicks by button]** diagram och tabell innehåller tillgängliga data för mottagarnas beteende per knapp:

* **[!UICONTROL Clicks]**: Totalt antal mottagare som interagerat med knapparna i meddelandet i appen.

* **[!UICONTROL Click rate]**: procentandelen användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.
+++

**Relaterade ämnen:**

* [Skapa meddelande i appen](../in-app/create-in-app.md)
* [Design In-app-meddelande](../in-app/design-in-app.md)
* [Konfiguration i appen](../in-app/inapp-configuration.md)


>[!BEGINTABS]

>[!TAB Lägg till en push-funktion på en resa]

1. Öppna resan och dra och släpp en push-aktivitet från funktionsmakroavsnittet på paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

>[!TAB Lägga till en push-knapp i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL Push notification]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda.

1. Klicka på **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment.

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av er kampanj.

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av ditt push-meddelande:

   * En gång
   * Dagligen
   * Veckovis
   * Månadsvis

>[!ENDTABS]

Test 2:

1. Detta är ett test

>[!BEGINTABS]

>[!TAB Lägg till en push-funktion på en resa]

    1. Öppna resan och dra och släpp en push-aktivitet från funktionsmakroavsnittet på paletten.
    
    1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

>[!TAB Lägga till en push-knapp i en kampanj]

    1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL Push notification]** som du vill och välj **[!UICONTROL App surface]** att använda.
    
    1. Klicka på **[!UICONTROL Create]**.
    
    1. Från **[!UICONTROL Properties]**, redigera Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.
    
    1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment.
    
    1. I[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera personerna i det valda segmentet.
    
    1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig konfigurera **[!UICONTROL Schedule]** av er kampanj.
    
    1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av ditt push-meddelande:
    
    * En gång
    * Daglig
    * Vecka
    * Månadsvis

>[!ENDTABS]

1. Detta är en del av testet
