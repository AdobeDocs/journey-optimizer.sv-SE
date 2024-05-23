---
solution: Journey Optimizer
product: journey optimizer
title: Räck upp leveranserna
description: Lär dig hur du får fler leveranser
feature: Journeys, Use Cases, IP Warmup Plans
topic: Content Management
role: User, Data Engineer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
keywords: leverans, resa, användningsfall, e-post, anseende
exl-id: 83d1b68d-011a-4109-b5f0-6ca1ade2944d
source-git-commit: e34c39c02f71361277f28b1a116a54390875f93d
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 2%

---

# Användningsfall: öka leveranserna{#use-case-ramp-up-your-deliveries}

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda. Lär dig hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html){target="_blank"}.

För att värma upp era immateriella tillgångar kan ni gradvis öka antalet leveranser. Läs mer om [optimera leveransen i Journey Optimizer](../reports/deliverability.md).

Syftet med det här användningsexemplet är att skapa en resa för att förbättra e-postleveranserna. Så här konfigurerar du den här resan:

1. Skapa en resa. [Läs mer](journey-gs.md).

1. Lägg till en **[!UICONTROL Condition]** till resan. [Läs mer](condition-activity.md).

1. I **[!UICONTROL Condition]** aktivitetsinställningar, ange maximalt antal mottagare för leveransen:

   1. I **[!UICONTROL Condition]** aktivitetsinställningar, ange **[!UICONTROL Type]** fält till **[!UICONTROL Profile cap]**. [Läs mer](condition-activity.md#profile_cap).

   1. Ange **[!UICONTROL Limit]** till det maximala antalet mottagare för den här leveransen.

   ![](assets/profile-cap-condition.png)

   Du kan gradvis öka gränsen upp till det totala antalet prenumeranter.

1. Lägg till en **[!UICONTROL Email]** verksamhet till den nominella banan efter **[!UICONTROL Condition]** aktivitet.

   ![](assets/ramp-up-deliveries-message.png)

   När resan körs skickas meddelandet till de profiler som anges, upp till det maximala antal profiler som du har angett. När den här gränsen nås får de inmatade profilerna den alternativa sökvägen.

1. Slutför resan med de aktiviteter du själv väljer.

Du kan ta bort det här villkoret när IP-adressen har värmt upp.
