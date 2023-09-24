---
title: Övervaka era webbkampanjer
description: Lär dig övervaka webbkampanjer i Journey Optimizer
feature: Web Channel
topic: Content Management
role: User
level: Beginner
source-git-commit: ec071392cec9933bb73ae9ab20618292b6089061
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---

# Övervaka era webbkampanjer {#monitor-web-campaigns}

## Kontrollera webbrapporter {#check-web-reports}

När kampanjen är aktiv kan du kolla **[!UICONTROL Web]** i kampanjrapporterna för att jämföra element som antal visningar, klickfrekvens och antal aktiviteter med webbsidan. Läs mer på kampanjwebben [live-rapport](../reports/campaign-live-report.md#web-tab) och [global rapport](../reports/campaign-global-report.md#web-tab).

Om du vill förbättra webbupplevelseövervakningen ytterligare kan du också spåra klick på specifika delar av webbplatsen. På så sätt kan du visa antalet klick på det elementet i webbrapporterna. [Lär dig mer](#use-click-tracing)

## Använda klickspårning {#use-click-tracing}

Med webbdesignern kan du markera valfritt element på webbplatsen och spåra klick på det elementet.

Den här informationen kan vara användbar för att förbättra webbplatsens användarupplevelse. Om [webbrapporter](../reports/campaign-global-report.md#web-tab) visa att många användare klickar på ett element som inte är klickbart, kanske du vill lägga till en länk till det elementet.

1. Markera ett element på sidan och välj **[!UICONTROL Click track element]** på snabbmenyn.

   ![](assets/web-designer-click-track.png)

   >[!NOTE]
   >
   >Alla objekt, klickbara eller inte, kan markeras.

1. Motsvarande spårade åtgärd visas automatiskt i **[!UICONTROL Click track]** till vänster.

   ![](assets/web-designer-click-track-pane.png)

1. Lägg till en meningsfull etikett för att hantera alla spårade element och hitta dem enkelt i rapporterna. The **[!UICONTROL CSS selector]** -fältet visar information för att hitta det markerade elementet.

1. Upprepa stegen ovan om du vill markera så många andra element som behövs för klickspårning. Alla motsvarande åtgärder visas i den vänstra rutan.

   ![](assets/web-designer-click-tracking-actions.png)

1. Om du vill ta bort klickspårning för ett element markerar du motsvarande borttagningsikon.

När kampanjen är aktiv kan du kontrollera antalet klick för varje element på kampanjwebben [live-rapport](../reports/campaign-live-report.md#web-tab) och [global rapport](../reports/campaign-global-report.md#web-tab).
