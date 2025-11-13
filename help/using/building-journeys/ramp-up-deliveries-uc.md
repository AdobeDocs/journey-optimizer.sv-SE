---
solution: Journey Optimizer
product: journey optimizer
title: Räck upp leveranserna
description: Lär dig hur du får fler leveranser
feature: Journeys, Use Cases, IP Warmup Plans
topic: Content Management
role: User, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
keywords: leverans, resa, användningsfall, e-post, anseende
exl-id: 83d1b68d-011a-4109-b5f0-6ca1ade2944d
version: Journey Orchestration
source-git-commit: 7822e9662d03e6c6b2d5bc5ecb9ca85dc32f0942
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 2%

---

# Användningsfall: öka leveranserna{#use-case-ramp-up-your-deliveries}

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda. Lär dig hur du kan öka ditt e-postanseende med IP-uppvärmning i [Guiden ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html){target="_blank"} Leveranssätt med bästa praxis.

För att värma upp era immateriella tillgångar kan ni gradvis öka antalet leveranser. Läs mer om [att optimera leveransen i Journey Optimizer](../reports/deliverability.md).

Syftet med det här användningsexemplet är att skapa en resa för att förbättra e-postleveranserna. Så här konfigurerar du den här resan:

1. Skapa en resa. [Läs mer](journey-gs.md).

1. Lägg till en **[!UICONTROL Condition]**-aktivitet på resan. [Läs mer](condition-activity.md).

1. Ange det maximala antalet mottagare för leveransen i aktivitetsinställningarna för **[!UICONTROL Condition]**:

   1. I aktivitetsinställningarna för **[!UICONTROL Condition]** anger du **[!UICONTROL Type]**-fältet till **[!UICONTROL Profile cap]**. [Läs mer](condition-activity.md#profile_cap).

   1. Ställ in fältet **[!UICONTROL Limit]** till maximalt antal mottagare för den här leveransen.

   ![Konfiguration av villkor för profillistvillkor för kontroll av leveransvolym](assets/profile-cap-condition.png)

   Du kan gradvis öka gränsen upp till det totala antalet prenumeranter.

1. Lägg till en **[!UICONTROL Email]**-åtgärdsaktivitet i den nominella sökvägen efter **[!UICONTROL Condition]**-aktiviteten.

   ![Konfigurering av e-postmeddelanden i en ramlad leveransresa](assets/ramp-up-deliveries-message.png)

   När resan körs skickas meddelandet till de profiler som anges, upp till det maximala antal profiler som du har angett. När den här gränsen nås får de inmatade profilerna den alternativa sökvägen.

1. Slutför resan med de aktiviteter du själv väljer.

Du kan ta bort det här villkoret när IP-adressen har värmt upp.
