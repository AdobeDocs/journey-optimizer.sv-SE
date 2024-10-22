---
title: Begär godkännande
description: Lär dig hur du begär godkännande innan du publicerar dina resor och kampanjer.
role: User
level: Beginner
feature: Approval
source-git-commit: 8fecd0d4812ba875dba1d47bc32ab08178a13f2c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Begär godkännande {#request-approval}

Om arbetsflödeskapaciteten för godkännande har aktiverats för din organisation kommer du att märka att knapparna **[!UICONTROL Activate]** och **[!UICONTROL Publish]** inte längre är tillgängliga i arbetsflödena för att skapa kampanj och skapa resande. Dessa knappar har ersatts av knappen **[!UICONTROL Request Approval]**.

När du har skapat din kampanj eller resa måste du klicka på knappen **[!UICONTROL Request Approval]**. Detta kontrollerar om det finns en aktiv godkännandeprincip i sandlådan som gäller kampanjen eller resan. Om en relevant godkännandeprincip hittas, börjar godkännandeprocessen. Om det inte finns någon tillämplig godkännandepolicy godkänns kampanjen eller resan automatiskt och aktiveras eller publiceras.

Fönstret **[!UICONTROL Request approval]** öppnas. Skriv ett meddelande till godkännarna om det behövs och klicka på **[!UICONTROL Send]** för att skicka din begäran.

![](assets/approval-request.png)

När kampanjen eller resan är **[!UICONTROL In review]** tillstånd kan du välja att avbryta godkännandebegäran. Genom att klicka på knappen **[!UICONTROL Cancel request]** återgår kampanjen eller resan till utkastsfasen och ett meddelande skickas till granskarna om att begäran har avbrutits. Sedan kan ni göra nödvändiga ändringar och skicka in kampanjen eller resan på nytt för godkännande.

![](assets/approval-cancel.png)

När godkännandebegäran har skickats till godkännarna kan de granska den och antingen aktivera resan/kampanjen för att göra den offentlig eller begära ändringar om det behövs. [Lär dig hur du granskar och godkänner en begäran](review-approve-request.md)

Om godkännarna begär ändringar meddelas du via ett e-postmeddelande och en Journey Optimizer-avisering, som är tillgänglig när du klickar på klockikonen till höger på skärmen, på fliken **[!UICONTROL Requests]**.

![](assets/changes-requested.png)

Om du vill gå igenom ändringsbegäran öppnar du den i e-postmeddelandet eller aviseringen för att få åtkomst till resan eller kampanjen och göra de begärda ändringarna. När din resa/kampanj är klar att granskas igen skickar du en ny godkännandebegäran med knappen **[!UICONTROL Request approval]**.
