---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera en kampanj
description: Lär dig granska och aktivera kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: kampanj, granskning, validering, aktivering, aktivering, optimering
exl-id: 7c4afc98-0d79-4e26-90f8-558bac037169
source-git-commit: d4ecfecdc74c26890658d68d352c36b75f7c9039
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 3%

---

# Granska och aktivera en kampanj {#review-activate}

När kampanjen har konfigurerats måste du granska dess parameter och innehåll innan du aktiverar den. Följ dessa steg för att göra detta:

1. Klicka på **[!UICONTROL Review to activate]** på konfigurationsskärmen för kampanjen för att visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

   >[!IMPORTANT]
   >
   >Om fel uppstår kan du inte aktivera kampanjen. Åtgärda felen innan du fortsätter.

   ![](assets/create-campaign-alerts.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

1. Kampanjen är nu aktiverad. Dess status är **[!UICONTROL Live]**, eller **[!UICONTROL Scheduled]** om du angav ett startdatum. [Läs mer om kampanjstatus](get-started-with-campaigns.md#statuses).

   Meddelandet som konfigurerats i kampanjen skickas omedelbart eller på det angivna datumet.

   >[!NOTE]
   >
   >Statusen **[!UICONTROL Completed]** tilldelas automatiskt till en kampanj 3 dagar efter att den har aktiverats eller vid kampanjens slutdatum om den har en återkommande körning.
   >
   >Om inget slutdatum har angetts behåller kampanjen statusen **[!UICONTROL Live]**. Om du vill ändra den måste du stoppa kampanjen manuellt. [Lär dig stoppa en kampanj](modify-stop-campaign.md)

1. När en kampanj har aktiverats kan du när som helst kontrollera dess information genom att öppna den. Sammanfattningen gör att du kan få statistik om antalet målprofiler och levererade och misslyckade åtgärder.

   Du kan även hämta ytterligare statistik i dedikerade rapporter genom att klicka på knappen **[!UICONTROL Reports]**. [Läs mer](../reports/campaign-global-report.md)

   ![](assets/create-campaign-summary.png)
