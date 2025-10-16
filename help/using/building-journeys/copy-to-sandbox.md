---
solution: Journey Optimizer
product: journey optimizer
title: Kopiera en resa till en annan sandlåda
description: Lär dig kopiera en resa till en annan sandlåda
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer, Data Engineer
level: Experienced
keywords: sandlåda, resa, kopia, miljö
exl-id: 8c63f2f2-5cec-4cb2-b3bf-2387eefb5002
version: Journey Orchestration
source-git-commit: 118bf89f56d26213fde71fa795fc6576ce764ef2
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---

# Kopiera en resa till en annan sandlåda {#copy-to-sandbox}

<!--
>[!CONTEXTUALHELP]
>id="ajo_journey_copy_main"
>title="Copy a journey to another sandbox"
>abstract="Journey Optimizer allows you to copy an entire journey from one sandbox to another. For example, you can copy a journey from the Stage sandbox environment to your Production sandbox. In addition to the Journey itself, Journey Optimizer also copies most of the objects the journey depends on."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_sandbox_details"
>title="Sandbox details"
>abstract="Select the destination sandbox you want to copy the journey to. Only sandboxes within your organization are available."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Object details"
>abstract="This is the journey you are going to copy."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Dependent objects"
>abstract="This is the list of associated objects used in the journey. This list displays the name, the object type, as well as the internal Journey Optimizer ID."
-->

Med Journey Optimizer kan du kopiera en hel resa från en sandlåda till en annan. Du kan t.ex. kopiera en resa från sandlådemiljön på scenen till produktionssandlådan.

Förutom själva resan kopierar Journey Optimizer även de flesta av de objekt som resan är beroende av: målgrupper, scheman, händelser och handlingar.

Kopieringsprocessen utförs via en **paketexport och import** mellan käll- och målsandlådan. Detaljerad information om hur du exporterar objekt och importerar dem till en målsandlåda finns i det här avsnittet: [Kopiera objekt till en annan sandlåda](../configuration/copy-objects-to-sandbox.md)
