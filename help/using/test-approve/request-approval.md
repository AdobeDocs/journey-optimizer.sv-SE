---
title: Begär godkännande
description: Lär dig hur du begär godkännande innan du publicerar dina resor och kampanjer.
role: User
level: Beginner
feature: Approval
exl-id: 75dafecd-805d-4aa2-86c6-99e6da4d378b
source-git-commit: 692b539f2c7623a14192558c3eba55d90c54f22d
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Begär godkännande {#request-approval}

Åtkomsten till arbetsflödet för godkännande avgörs av ditt specifika användningsfall:

* **Det finns ingen aktiv godkännandeprincip**

   * **Kampanjer**: Om ingen godkännandeprincip är aktiv för Campaign-objektet i en sandlåda visas knappen **[!UICONTROL Activate]** så att du kan aktivera dem utan att behöva godkänna dem.

   * **Resor**: Om ingen godkännandeprincip är aktiv för Resenney-objektet, kommer resorna att visa knappen **[!UICONTROL Publish]** så att du kan publicera direkt.

* **Aktiva godkännandeprinciper finns**

   * **Kampanjer**: Om det finns en eller flera aktiva godkännandeprinciper för Campaign-objektet i en sandlåda visas knappen **[!UICONTROL Request Approval]** för alla kampanjer i den sandlådan.
Om ingen godkännandeprincip gäller för det markerade objektet när användaren klickar på knappen **[!UICONTROL Request Approval]**, kommer arbetsflödet för automatiskt godkännande att aktiveras.

   * **Resor**: Om det finns en eller flera aktiva godkännandeprinciper för reseobjektet i en sandlåda visas knappen **[!UICONTROL Request Approval]** för alla resor.
Om ingen godkännandeprincip gäller för det markerade objektet när användaren klickar på knappen **[!UICONTROL Request Approval]**, kommer arbetsflödet för automatiskt godkännande att aktiveras.

## Skicka begäran om godkännande

Klicka på knappen **[!UICONTROL Request Approval]** när du har skapat kampanjen eller resan. Detta kontrollerar om det finns en aktiv godkännandeprincip i sandlådan som gäller kampanjen eller resan.

* Om en giltig godkännandeprincip hittas skickas din kampanj eller resa för granskning.

* Om ingen godkännandeprincip gäller för kampanjen eller resan efter att du klickat på knappen **[!UICONTROL Request Approval]**, godkänns kampanjen eller resan automatiskt och aktiveras eller publiceras.

Fönstret **[!UICONTROL Request approval]** öppnas. Skriv ett meddelande till godkännarna om det behövs och klicka på **[!UICONTROL Send]** för att skicka din begäran.

![Dialogrutan Godkännandebegäran](assets/approval-request.png)

När kampanjen eller resan är **[!UICONTROL In review]** tillstånd kan du välja att avbryta godkännandebegäran. Genom att klicka på knappen **[!UICONTROL Cancel request]** återgår kampanjen eller resan till utkastsfasen och ett meddelande skickas till granskarna om att begäran har avbrutits. Sedan kan ni göra nödvändiga ändringar och skicka in kampanjen eller resan på nytt för godkännande.

![Avbryt begäran om godkännande](assets/approval-cancel.png)

## Hantera godkännandebegäranden

När godkännandebegäran har skickats till godkännarna kan de granska den och antingen aktivera resan/kampanjen för att göra den offentlig eller begära ändringar om det behövs. [Lär dig hur du granskar och godkänner en begäran](review-approve-request.md)

Om godkännarna begär ändringar meddelas du via ett e-postmeddelande och en Journey Optimizer-avisering, som är tillgänglig när du klickar på klockikonen till höger på skärmen, på fliken **[!UICONTROL Requests]**.

![Ändringarna har begärt meddelande](assets/changes-requested.png)

Om du vill gå igenom ändringsbegäran öppnar du den i e-postmeddelandet eller aviseringen för att få åtkomst till resan eller kampanjen och göra de begärda ändringarna. När din resa/kampanj är klar att granskas igen skickar du en ny godkännandebegäran med knappen **[!UICONTROL Request approval]**.
