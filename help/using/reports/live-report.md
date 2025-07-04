---
solution: Journey Optimizer
product: journey optimizer
title: Live-rapport
description: Lär dig använda data från liverapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 8dd48bb2-a805-4c46-a16c-c68173a9ac08
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# Kom igång med Live Report {#live-report}

Använd **[!UICONTROL Live report]** för att i realtid mäta och visualisera påverkan och prestanda för dina resor och dina meddelanden på en inbyggd kontrollpanel. Data är tillgängliga i **[!UICONTROL Live report]** så snart din leverans har skickats eller din resa har körts från fliken **[!UICONTROL Last 24hrs]**.

* Om du vill rikta in dig på en resa i sammanhanget för en resa går du till **[!UICONTROL Journeys]**-menyn för din resa och klickar på knappen **[!UICONTROL More actions]**.**[!UICONTROL View last 24hrs report]**

  ![](assets/report_journey.png)

* Om du vill rikta in dig på en kampanj går du till **[!UICONTROL Campaigns]**-menyn och klickar på knappen **[!UICONTROL Reports]** och sedan **[!UICONTROL View last 24hrs report]**.

  ![](assets/report_campaign.png)

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](#list-of-components-live).

## Anpassa kontrollpanelen {#modify-dashboard}

Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort. Om du ändrar widgetarna påverkas bara den aktuella användarens kontrollpanel. Andra användare ser sina egna kontrollpaneler eller de som har angetts som standard.

1. I listrutan **[!UICONTROL Actions]** väljer du om du vill rapportera en viss åtgärd på dina resor.

1. Välj om du vill utesluta testhändelser från dina rapporter med hjälp av alternativfältet. Mer information om testhändelser finns på [den här sidan](../building-journeys/testing-the-journey.md).

   Observera att alternativet **[!UICONTROL Exclude test events]** bara är tillgängligt för reserapporter.

   ![](assets/report_modify_6.png)

1. Om du vill ändra storlek på eller ta bort widgetar klickar du på **[!UICONTROL Modify]**.

   ![](assets/report_modify_7.png)

1. Justera widgetarnas storlek genom att dra i det nedre högra hörnet.

   ![](assets/report_modify_8.png)

1. Klicka på **[!UICONTROL Remove]** för att ta bort widgetar som du inte behöver.

   ![](assets/report_modify_9.png)

1. När du är nöjd med visningsordningen och widgetarnas storlek klickar du på **[!UICONTROL Save]**.

1. Om du vill anpassa hur data visas kan du växla mellan olika visualiseringsalternativ, som diagram, tabeller och dondiagram.

   ![](assets/report_modify_11.png)

Kontrollpanelen har sparats. Dina olika ändringar kommer att tillämpas på nytt för en senare användning av dina liverapporter. Använd alternativet **[!UICONTROL Reset]** om det behövs för att återställa standardordningen för widgetar och widgetar.

## Exportera rapporter {#export-reports}

Du kan enkelt exportera dina olika rapporter till PDF- eller CSV-format så att du kan dela och skriva ut dem.

>[!BEGINTABS]

>[!TAB Exportera rapporten som en PDF-fil]

1. Klicka på **[!UICONTROL Export]** i rapporten och välj **[!UICONTROL PDF file]**.

   ![](assets/export_6.png)

1. Konfigurera dokumentet i utskriftsfönstret efter behov. Observera att alternativen kan variera beroende på vilken webbläsare du använder.

1. Skriv ut eller spara rapporten som PDF.

1. Leta reda på mappen där du vill spara filen, byt namn på den om det behövs och klicka på Spara.

Din rapport är nu tillgänglig för visning eller delning i en PDF-fil.

>[!TAB Exportera rapporten som en CSV-fil]

1. Klicka på **[!UICONTROL Export]** i rapporten och välj **[!UICONTROL CSV file]** för att generera en CSV-fil på den övergripande rapportnivån.

   ![](assets/export_4.png)

1. Du kan också välja att exportera data från en viss widget. Klicka på **[!UICONTROL Download CSV file]** bredvid den valda widgeten.

   ![](assets/export_5.png)

1. Filen hämtas automatiskt och kan finnas i dina lokala filer.

   Om du genererade filen på rapportnivå innehåller den detaljerad information för varje widget, inklusive dess titel och data.

   Om du genererade filen på widgetnivå, innehåller den specifikt data för den valda widgeten.

>[!ENDTABS]
