---
title: Profilände
description: Profilände
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 496c7666-a133-4aeb-be8e-c37b3b9bf5f9
hide: true
hidefromtoc: true
source-git-commit: b5ce2ea81d4091b4fa9c09e83573f9043c5e55a8
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---


# Ange ditt rykte som avsändare

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda.

För att värma upp era immateriella tillgångar kan ni gradvis öka antalet leveranser. Se det här [användningsfall](../building-journeys/ramp-up-deliveries-uc.md).

## Villkorstyp för profiländpunkt {#profile_cap}

Andra villkorstyper beskrivs i detta [section](../building-journeys/condition-activity.md).

Använd den här villkorstypen om du vill ange ett maximalt antal profiler för en resebana. När den här gränsen nås får de inmatade profilerna en alternativ sökväg.

Du kan använda den här villkorstypen för att öka volymen på dina leveranser. Se det här [användningsfall](../building-journeys/ramp-up-deliveries-uc.md).

Standardvärdet är 1 000. Du kan ange ett heltalsvärde mellan 1 och 20 000.

Räknaren gäller endast den valda reseversionen. Räknaren återställs till noll efter en månad. Efter en återställning tar de infogade profilerna den nominella sökvägen igen tills räknargränsen nås.

Den nominella banan har alltid företräde framför den alternativa banan, även om du flyttar den alternativa banan ovanför den nominella banan på arbetsytan.

![](../assets/profile-cap-condition.png)

## Användningsfall: förbättra leveransen

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda. Lär dig hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html){target=&quot;_blank&quot;}.

För att värma upp era immateriella tillgångar kan ni gradvis öka antalet leveranser. Läs mer om [optimera leveransen i Journey Optimizer](../deliverability.md).

Syftet med det här användningsexemplet är att skapa en resa för att förbättra e-postleveranserna. Så här konfigurerar du den här resan:

1. Skapa en resa. [Läs mer](../building-journeys/journey-gs.md).

1. Lägg till en **[!UICONTROL Condition]** till resan. [Läs mer](../building-journeys/condition-activity.md).

1. I **[!UICONTROL Condition]** aktivitetsinställningar, ange maximalt antal mottagare för leveransen:

   1. I **[!UICONTROL Condition]** aktivitetsinställningar, ange **[!UICONTROL Type]** fält till **[!UICONTROL Profile cap]**. [Läs mer](profile-cap.md#profile_cap).

   1. Ange **[!UICONTROL Limit]** till maximalt antal mottagare för den här leveransen.

   ![](../assets/profile-cap-condition.png)

   Du kan gradvis öka gränsen upp till det totala antalet prenumeranter.

1. Lägg till en **[!UICONTROL Message]** aktivitet till den nominella banan efter **[!UICONTROL Condition]** aktivitet.

   ![](../assets/ramp-up-deliveries-message.png)

   När resan körs skickas meddelandet till de profiler som anges, upp till det maximala antal profiler som du har angett. När den här gränsen nås får de inmatade profilerna den alternativa sökvägen.

1. Slutför resan med de aktiviteter du själv väljer.

Du kan ta bort det här villkoret när IP-adressen har värmt upp.

