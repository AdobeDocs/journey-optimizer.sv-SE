---
solution: Journey Optimizer
product: journey optimizer
title: Felsöka fel innan du testar eller publicerar din resa
description: Lär dig felsöka innan du testar eller publicerar din resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: felsökning, felsökning, resa, kontroll, fel
exl-id: 03fbc4f4-b0a8-46d5-91f9-620685b11493
version: Journey Orchestration
source-git-commit: 118bf89f56d26213fde71fa795fc6576ce764ef2
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 42%

---

# Felsöka fel innan du testar din resa {#troubleshooting}

I det här avsnittet får du lära dig hur du felsöker resor innan du testar eller publicerar. Alla kontroller som anges nedan kan utföras medan resan är i testläge eller när den är live. Rekommendationen är att göra alla kontroller nedan i testläget och sedan gå vidare till publiceringen. Läs mer om testläget på [den här sidan](../building-journeys/testing-the-journey.md).

Lär dig hur du felsöker resehändelser, kontrollerar om profiler har angetts för din resa, hur de navigerar genom den och om meddelanden skickas [på den här sidan](troubleshooting-execution.md).

Om du använder inkommande åtgärder kan du lära dig att felsöka dem [på den här sidan](troubleshooting-inbound.md).

## Fel i aktiviteter {#activity-errors}

Kontrollera att alla aktiviteter är konfigurerade korrekt innan du testar och publicerar din resa. Du kan inte utföra tester eller publikationer om fel fortfarande upptäcks av systemet.

Fel visas med en varningssymbol på själva aktiviteterna på arbetsytan. Placera markören på utropstecknet för att visa felmeddelandet. Om du väljer aktiviteten visas raden med en varning. Exempel:

* om ett obligatoriskt fält är tomt visas ett fel

  ![](assets/journey63.png)

* på arbetsytan visas en varning när två aktiviteter är frånkopplade

  ![](assets/canvas-disconnected.png)

## Fel under resan {#canvas-errors}

Fel visas också från knappen **[!UICONTROL Alerts]** ovanför arbetsytan. Med den här knappen kan du se fel som upptäcks av systemet och som förhindrar aktivering av testläget eller publicering av resan.

Systemet identifierar två typer av problem: **fel** och **varningar**. Fel blockerar publicering och testaktivering. Varningar indikerar potentiella problem som inte blockerar testaktivering eller publicering. En beskrivning av problemet och ett ID från felloggen med typen ERR_XXX_XXX visas. Detta kan hjälpa till att identifiera problemet.

![](assets/journey-error-and-warning.png)

<!--Most of the time, errors detected by the system are linked to errors visible on the activities but they can also relate to other issues. In all cases, check alerts and resolve the issue using to the error description. If you cannot identify the issue, use the **[!UICONTROL Copy details]** button to store the alerts, and send them to your administrator.-->

Fel och varningar som är globala för resan visas först i listan. Fel och varningar som rör specifika aktiviteter listas därefter per aktivitetsordning eller när de dyker upp i resan från vänster till höger. Längst ned i listan med varningar kan du med knappen **[!UICONTROL Copy details]** kopiera teknisk information om resan som är användbar för att felsöka problemen.

## Lägg till en alternativ sökväg {#canvas-add-path}

Du kan definiera en reservåtgärd om ett fel uppstår för följande reseaktiviteter: **[!UICONTROL Optimize]** och **[!UICONTROL Action]**.

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få det att fortsätta är att lösa problemet. För att undvika att avbryta resan kan du även kontrollera alternativet **[!UICONTROL Add an alternative path in case of a timeout or an error]** i aktivitetens egenskaper. Läs mer i [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).
