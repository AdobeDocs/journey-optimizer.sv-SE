---
title: Övervaka era webbkampanjer
description: Lär dig övervaka webbkampanjer i Journey Optimizer
feature: Web Channel, Reporting
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: d89795bb-c51d-4d1f-b7ed-2b2c5d278922
source-git-commit: 503bedc30c35305537c62f9452f4a2dc07424523
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Övervaka era webbkampanjer {#monitor-web-experiences}

## Kontrollera webbrapporter {#check-web-reports}

När webbupplevelsen är live kan du kontrollera fliken **[!UICONTROL Web]** i [reserapporten](../reports/journey-global-report-cja.md#web-cja) och [ kampanjrapporten](../reports/campaign-global-report-cja.md#web) för att jämföra element som antalet visningar, klickfrekvens och antal aktiviteter med webbsidan.

<!--You can check the **[!UICONTROL Web]** tab of the campaign reports. Learn more on the campaign web [live report](../reports/campaign-live-report.md#web-tab) and [global report](../reports/campaign-global-report.md#web-tab).-->

Om du vill förbättra webbupplevelseövervakningen ytterligare kan du också spåra klick på specifika delar av webbplatsen. På så sätt kan du visa antalet klick på det elementet i webbrapporterna. [Lär dig hur](#use-click-tracing)

## Använda klickspårning {#use-click-tracing}

Med webbdesignern kan du markera valfritt element på webbplatsen och spåra klick på det elementet.

Den här informationen kan vara användbar för att förbättra webbplatsens användarupplevelse. Om [webbrapporterna](../reports/campaign-global-report.md#web-tab) till exempel visar att många användare klickar på ett element som inte är klickbart, kanske du vill lägga till en länk till det elementet.

1. Markera ett element på sidan och välj **[!UICONTROL Click track element]** på snabbmenyn.

   ![](assets/web-designer-click-track.png)

   >[!NOTE]
   >
   >Alla objekt, klickbara eller inte, kan markeras.

1. Motsvarande spårade åtgärd visas automatiskt i rutan **[!UICONTROL Click track]** till vänster.

   ![](assets/web-designer-click-track-pane.png)

1. Lägg till en meningsfull etikett för att hantera alla spårade element och hitta dem enkelt i rapporterna. Fältet **[!UICONTROL CSS selector]** innehåller information om att hitta det valda elementet.

1. Upprepa stegen ovan om du vill markera så många andra element som behövs för klickspårning. Alla motsvarande åtgärder visas i den vänstra rutan.

   ![](assets/web-designer-click-tracking-actions.png)

1. Om du vill ta bort klickspårning för ett element markerar du motsvarande borttagningsikon.

När kampanjen är aktiv kan du kontrollera antalet klick för varje element i kampanjwebbrapporten [live](../reports/campaign-live-report.md#web-tab) och [global rapport](../reports/campaign-global-report.md#web-tab).
