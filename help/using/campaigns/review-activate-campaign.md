---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera en åtgärdskampanj
description: Lär dig hur du granskar och aktiverar åtgärdskampanjer i  [!DNL Journey Optimizer].
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: kampanj, granskning, validering, aktivering, aktivering, optimering
exl-id: 7c4afc98-0d79-4e26-90f8-558bac037169
source-git-commit: 81e54a3e3428d58818805b5dcb397ede4039436a
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 3%

---


# Granska och aktivera åtgärdskampanjen {#action-campaign-review}

När åtgärdskampanjen har konfigurerats måste du granska dess parameter och innehåll innan du aktiverar den. Följ dessa steg för att göra detta:

>[!IMPORTANT]
>
> Om din kampanj omfattas av en policy för godkännande måste du begära godkännande för att kunna skicka kampanjen. [Läs mer](../test-approve/gs-approval.md)

1. Klicka på **[!UICONTROL Review to activate]** på konfigurationsskärmen för kampanjen för att visa en sammanfattning av kampanjen.

   ![](assets/campaign-review.png)

1. En sammanfattning av kampanjkonfigurationen visas, så att du kan kontrollera om någon parameter är felaktig eller saknas och ändra kampanjen om det behövs.

   Om fel uppstår kan du inte aktivera kampanjen. Åtgärda felen innan du fortsätter.

   ![](assets/create-campaign-alerts.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

1. Kampanjen är aktiverad. Dess status är **[!UICONTROL Live]**, eller **[!UICONTROL Scheduled]** om du angav ett startdatum. Meddelandet som konfigurerats i kampanjen skickas omedelbart eller på det angivna datumet.

   Status **[!UICONTROL Completed]** tilldelas automatiskt till kampanjen 3 dagar efter att den har aktiverats eller vid kampanjens slutdatum om den har en återkommande körning. [Läs mer om kampanjstatus](manage-campaigns.md#statuses).

   Om inget slutdatum har angetts behåller kampanjen statusen **[!UICONTROL Live]**. Om du vill ändra den måste du stoppa kampanjen manuellt. [Lär dig stoppa en kampanj](manage-campaigns.md)

1. När en kampanj har aktiverats kan du när som helst kontrollera dess information genom att öppna den. Sammanfattningen gör att du kan få statistik om antalet målprofiler och levererade och misslyckade åtgärder.

   Du kan även hämta ytterligare statistik i dedikerade rapporter genom att klicka på knappen **[!UICONTROL Reports]**. [Läs mer](../reports/campaign-global-report-cja.md)

   ![](assets/create-campaign-summary.png)
