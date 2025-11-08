---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera den API-utlösta kampanjen
description: Lär dig hur du granskar och aktiverar API-utlösta kampanjer.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: 561f1215-d13d-4ffc-b6f1-396ae67774c8
source-git-commit: 81e54a3e3428d58818805b5dcb397ede4039436a
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 4%

---

# Granska och aktivera den API-utlösta kampanjen {#api-review}

När din API-utlösta kampanj har konfigurerats måste du granska dess parameter och innehåll innan du aktiverar den. Följ dessa steg för att göra detta:

>[!IMPORTANT]
>
> Om din kampanj omfattas av en policy för godkännande måste du begära godkännande för att kunna skicka din kampanj. [Läs mer](../test-approve/gs-approval.md)

1. Klicka på **[!UICONTROL Review to activate]** på konfigurationsskärmen för kampanjen för att visa en sammanfattning av kampanjen.

   ![](assets/campaign-review.png)

1. En sammanfattning av kampanjkonfigurationen visas, så att du kan kontrollera om någon parameter är felaktig eller saknas och ändra kampanjen om det behövs.

   Om fel uppstår kan du inte aktivera kampanjen. Åtgärda felen innan du fortsätter.

   ![](assets/create-campaign-alerts.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

1. Kampanjen är aktiverad. Dess status är **[!UICONTROL Live]**, eller **[!UICONTROL Scheduled]** om du angav ett startdatum.

   Status **[!UICONTROL Completed]** tilldelas automatiskt till kampanjen 3 dagar efter att den har aktiverats eller vid kampanjens slutdatum om den har en återkommande körning. [Läs mer om kampanjstatus](manage-campaigns.md#statuses).

   Om inget slutdatum har angetts behåller kampanjen statusen **[!UICONTROL Live]**. Om du vill ändra den måste du stoppa kampanjen manuellt. [Lär dig stoppa en kampanj](manage-campaigns.md)

1. När en kampanj har aktiverats kan du när som helst kontrollera dess information genom att öppna den. Sammanfattningen gör att du kan få statistik om antalet målprofiler och levererade och misslyckade åtgärder.

   Du kan även hämta ytterligare statistik i dedikerade rapporter genom att klicka på knappen **[!UICONTROL Reports]**. [Läs mer](../reports/campaign-global-report-cja.md)

   ![](assets/create-campaign-summary.png)

## Nästa steg {#next}

När den API-utlösta kampanjen är klar kan du utlösa dess körning med API:er. [Läs mer](trigger-campaigns.md)
