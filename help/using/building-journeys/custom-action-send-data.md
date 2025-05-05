---
solution: Journey Optimizer
product: journey optimizer
title: Skicka data till AEP
description: Lär dig skicka data till AEP
feature: Journeys, Use Cases
topic: Content Management
role: User, Data Engineer
level: Intermediate, Experienced
keywords: resa, användningsfall
source-git-commit: f8d62a702824bcfca4221c857acf1d1294427543
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Användningsfall: skapa en anpassad åtgärd för att skicka data till Adobe Experience Platform{#send-data-to-aep}

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda. Lär dig hur du ökar ditt e-postanseende med IP-uppvärmning i [Guide för bästa praxis för slutleverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=sv-SE){target="_blank"}.

För att värma upp era immateriella tillgångar kan ni gradvis öka antalet leveranser. Läs mer om [att optimera leveransen i Journey Optimizer](../reports/deliverability.md).

Syftet med det här användningsexemplet är att skapa en resa för att förbättra e-postleveranserna. Så här konfigurerar du den här resan:

1. Skapa en resa. [Läs mer](journey-gs.md).

1. Lägg till en **[!UICONTROL Condition]**-aktivitet på resan. [Läs mer](condition-activity.md).

1. Ange det maximala antalet mottagare för leveransen i aktivitetsinställningarna för **[!UICONTROL Condition]**:

   1. I aktivitetsinställningarna för **[!UICONTROL Condition]** anger du **[!UICONTROL Type]**-fältet till **[!UICONTROL Profile cap]**. [Läs mer](condition-activity.md#profile_cap).

   1. Ställ in fältet **[!UICONTROL Limit]** till maximalt antal mottagare för den här leveransen.

   ![](assets/profile-cap-condition.png)

   Du kan gradvis öka gränsen upp till det totala antalet prenumeranter.

1. Lägg till en **[!UICONTROL Email]**-åtgärdsaktivitet i den nominella sökvägen efter **[!UICONTROL Condition]**-aktiviteten.

   ![](assets/ramp-up-deliveries-message.png)

   När resan körs skickas meddelandet till de profiler som anges, upp till det maximala antal profiler som du har angett. När den här gränsen nås får de inmatade profilerna den alternativa sökvägen.

1. Slutför resan med de aktiviteter du själv väljer.

Du kan ta bort det här villkoret när IP-adressen har värmt upp.
