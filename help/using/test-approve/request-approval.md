---
title: Begär godkännande
description: Lär dig hur du begär godkännande innan du publicerar dina resor och kampanjer.
role: User
level: Beginner
feature: Approval
source-git-commit: ade30d6b33467ad05146ddee3ea1c1a4115d38b2
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# Begär godkännande {#request-approval}

Åtkomsten till arbetsflödet för godkännande avgörs av ditt specifika användningsfall:

* **Det finns ingen aktiv godkännandeprincip**

   * **Kampanjer**: Om ingen godkännandeprincip är aktiv för Campaign-objektet i en sandlåda visas knappen **[!UICONTROL Activate]** så att du kan aktivera dem utan att behöva godkänna dem.

   * **Resor**: Om ingen godkännandeprincip är aktiv för Resenney-objektet, kommer resorna att visa knappen **[!UICONTROL Publish]** så att du kan publicera direkt.

* **Aktiva godkännandeprinciper finns**

   * **Kampanjer**: Om det finns en eller flera aktiva godkännandeprinciper för Campaign-objektet i en sandlåda visas knappen **[!UICONTROL Request Approval]** för alla kampanjer i den sandlådan. Detta innebär att kampanjer inte kan aktiveras direkt utan godkännande.

   * **Resor**: Om det finns en eller flera aktiva godkännandeprinciper för reseobjektet i en sandlåda visas knappen **[!UICONTROL Request Approval]** för alla resor. På samma sätt som kampanjer kan resor inte publiceras direkt om en godkännandepolicy är aktiv.

## Skicka godkännandebegäran

Klicka på knappen **[!UICONTROL Request Approval]** när du har skapat kampanjen eller resan. Detta kontrollerar om det finns en aktiv godkännandeprincip i sandlådan som gäller kampanjen eller resan.

* Om en giltig godkännandeprincip hittas skickas din kampanj eller resa för granskning.

* Om ingen godkännandeprincip gäller för kampanjen eller resan efter att du klickat på knappen **[!UICONTROL Request Approval]**, godkänns kampanjen eller resan automatiskt och aktiveras eller publiceras.

Fönstret **[!UICONTROL Request approval]** öppnas. Skriv ett meddelande till godkännarna om det behövs och klicka på **[!UICONTROL Send]** för att skicka din begäran.

![](assets/approval-request.png)

När kampanjen eller resan är **[!UICONTROL In review]** tillstånd kan du välja att avbryta godkännandebegäran. Genom att klicka på knappen **[!UICONTROL Cancel request]** återgår kampanjen eller resan till utkastsfasen och ett meddelande skickas till granskarna om att begäran har avbrutits. Sedan kan ni göra nödvändiga ändringar och skicka in kampanjen eller resan på nytt för godkännande.

![](assets/approval-cancel.png)

## Hantera godkännandebegäranden

När godkännandebegäran har skickats till godkännarna kan de granska den och antingen aktivera resan/kampanjen för att göra den offentlig eller begära ändringar om det behövs. [Lär dig hur du granskar och godkänner en begäran](review-approve-request.md)

Om godkännarna begär ändringar meddelas du via ett e-postmeddelande och en Journey Optimizer-avisering, som är tillgänglig när du klickar på klockikonen till höger på skärmen, på fliken **[!UICONTROL Requests]**.

![](assets/changes-requested.png)

Om du vill gå igenom ändringsbegäran öppnar du den i e-postmeddelandet eller aviseringen för att få åtkomst till resan eller kampanjen och göra de begärda ändringarna. När din resa/kampanj är klar att granskas igen skickar du en ny godkännandebegäran med knappen **[!UICONTROL Request approval]**.



