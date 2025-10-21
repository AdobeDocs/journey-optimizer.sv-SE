---
solution: Journey Optimizer
product: journey optimizer
title: Kanalrapporter
description: Kom igång med kanalrapporter
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 247b966d-4f84-453b-8178-9c9ebcd494ef
source-git-commit: 722d37dc4bcb9ab7983ea336aa0b12a6a09e01dc
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Kom igång med kanalrapporter {#channel-report-gs}

>[!AVAILABILITY]
>
>Den nuvarande rapportupplevelsen kommer att upphöra i januari 2025. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig. [Kom igång med Journey Optimizer nya rapporteringsgränssnitt.](report-gs-cja.md)

Kanalrapporterna är ett kraftfullt verktyg som ger en omfattande översikt över trafik- och engagemangsmått i en enhetlig rapport för varje kanal, som omfattar alla åtgärder från alla kampanjer och resor. Den delas in i olika widgetar, som vart och ett ger en specifik bild av hur kampanjen eller resan fungerar.

Kanalrapporterna är helt anpassningsbara, så du kan ändra storlek på eller ta bort widgetar och skapa en instrumentpanel som passar dina specifika behov. Du kan också exportera rapportdata till en PDF- eller CSV-fil för ytterligare analys.

Läs mer om de olika mätvärden och widgetar som är tillgängliga för kanalrapporter på <!--[this page](channel-report.md)-->.

## Före start {#manage-reports-prereq}

Kontrollera att du har åtkomst till menyn **[!UICONTROL Reports]** innan du startar.

Om du inte kan se **[!UICONTROL Reports]**-menyn måste dina åtkomsträttigheter utökas så att de omfattar behörigheten **[!UICONTROL View Channel Reports]**. Du kan utöka dina egna behörigheter om du har tillgång till Adobe Experience Platform [behörigheter](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html){target="_blank"} för din organisation. Om inte, kontakta Adobe Journey Optimizer-administratören.

+++Lär dig hur du tilldelar rapportbehörigheter

Observera att den här behörigheten ingår i följande inbyggda **[!UICONTROL Roles]**: Campaign Manager, Campaign Approver, Campaign Viewer och Campaign Administrator.

Så här tilldelar du motsvarande behörighet till din **[!UICONTROL Role]**:

1. Gå till menyn [!DNL Permissions] i produkten **[!UICONTROL Roles]** och välj den roll som du vill uppdatera med den nya behörigheten **[!UICONTROL View Channel Reports]**.

1. Klicka på **[!UICONTROL Role]** på din **[!UICONTROL Edit]**-instrumentpanel.

   ![](assets/channel_permission_1.png)

1. Dra och släpp **[!UICONTROL Reports]**-resursen för att tilldela behörighet.

   Välj behörigheten **[!UICONTROL Report]** i listrutan **[!UICONTROL View Channel Reports]**-resurs.

   ![](assets/channel_permission_2.png)

1. Klicka på **[!UICONTROL Save]**.

Användare som är tilldelade denna **[!UICONTROL Role]** har nu åtkomst till menyn **[!UICONTROL Reports]**.

+++

## Hantera rapportinstrumentpanelen {#manage-reports}

Följ de här stegen för att få åtkomst till och hantera dina kanalrapporter:

1. Navigera till menyn **[!UICONTROL Reports]** i avsnittet **[!UICONTROL Journey Management]**.

   ![](assets/channel_report_1.png)

1. Välj en **Start** och **[!UICONTROL End time]** på din instrumentpanel för att ange specifika data som mål.

1. I listrutan **[!UICONTROL Action from]** väljer du om du vill ha kampanjer, resor eller båda som mål.

   ![](assets/channel_report_2.png)

1. Klicka på **[!UICONTROL Modify]** om du vill ändra storlek på eller ta bort widgetar för att skapa en instrumentpanel som uppfyller dina specifika behov.

   ![](assets/channel_report_3.png)

1. När du är nöjd med visningsordningen och widgetarnas storlek klickar du på **[!UICONTROL Save]**.

1. Beroende på widgeten kan du välja att växla från en tabell, ett stapeldiagram eller en munk.

1. Klicka på procentikonen om du vill visa data som frekvenser.

   ![](assets/channel_report_4.png)

## Exportera rapporter {#export-reports}

Du kan enkelt exportera dina olika rapporter till PDF- eller CSV-format så att du kan dela, ändra och skriva ut dem. Detaljerade anvisningar för hur du exporterar kanalrapporter finns på följande flikar:

>[!BEGINTABS]

>[!TAB Exportera rapporten som en PDF-fil]

1. Klicka på **[!UICONTROL Export]** i rapporten och välj **[!UICONTROL PDF file]**.

1. Konfigurera dokumentet i utskriftsfönstret efter behov. Observera att alternativen kan variera beroende på vilken webbläsare du använder.

1. Skriv ut eller spara rapporten som PDF.

1. Leta reda på mappen där du vill spara filen, byt namn på den om det behövs och klicka på Spara.

Din rapport är nu tillgänglig för visning eller delning i en PDF-fil.

>[!TAB Exportera rapporten som en CSV-fil]

1. Klicka på **[!UICONTROL Export]** i rapporten och välj **[!UICONTROL CSV file]** för att generera en CSV-fil på den övergripande rapportnivån.

1. Du kan också välja att exportera data från en viss widget. Klicka på **[!UICONTROL Export widget data to CSV]** bredvid den valda widgeten.

1. Filen hämtas automatiskt och kan finnas i dina lokala filer.

   Om du genererade filen på rapportnivå innehåller den detaljerad information för varje widget, inklusive dess titel och data.

   Om du genererade filen på widgetnivå, innehåller den specifikt data för den valda widgeten.

>[!ENDTABS]
