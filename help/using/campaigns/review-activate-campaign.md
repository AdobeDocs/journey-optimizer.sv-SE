---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera en kampanj
description: Lär dig hur du granskar och aktiverar kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
source-git-commit: 5c12ea559876d30a08f9aaf593d1b40b1f5b8bae
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Granska och aktivera en kampanj {#review-activate}

När kampanjen har konfigurerats måste du granska dess parameter och innehåll innan du aktiverar den. Följ dessa steg för att göra detta:

1. Klicka på **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

   >[!IMPORTANT]
   >
   >Om fel uppstår kan du inte aktivera kampanjen. Åtgärda felen innan du fortsätter.

   ![](assets/create-campaign-alerts.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

   ![](assets/create-campaign-review.png)

1. Kampanjen är nu aktiverad. Dess status är **[!UICONTROL Live]**, eller **[!UICONTROL Scheduled]** om du angav ett startdatum. [Läs mer om kampanjstatus](get-started-with-campaigns.md#statuses).

   Meddelandet som konfigurerats i kampanjen skickas omedelbart eller på det angivna datumet.

   >[!NOTE]
   >
   >The **[!UICONTROL Completed]** status tilldelas automatiskt en kampanj 3 dagar efter att den har aktiverats eller vid kampanjens slutdatum om den har ett återkommande körningsfel.
   >
   >Om inget slutdatum har angetts kommer kampanjen att behålla **[!UICONTROL Live]** status. Om du vill ändra den måste du stoppa kampanjen manuellt. [Lär dig stoppa en kampanj](modify-stop-campaign.md)

1. När en kampanj har aktiverats kan du när som helst kontrollera dess information genom att öppna den. Sammanfattningen gör att du kan få statistik om antalet målprofiler och levererade och misslyckade åtgärder.

   Du kan även få ytterligare statistik i dedikerade rapporter genom att klicka på **[!UICONTROL Reports]** -knappen. [Läs mer](../reports/campaign-global-report.md)

   ![](assets/create-campaign-summary.png)
