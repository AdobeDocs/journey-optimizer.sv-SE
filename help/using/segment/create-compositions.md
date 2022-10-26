---
solution: Journey Optimizer
product: journey optimizer
title: Skapa kompositionsarbetsflöden
description: Lär dig hur du skapar arbetsflöden för disposition för att kombinera och ordna befintliga målgrupper.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 2160d52f24af50417cdcf8c6ec553b746a544c2f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Skapa kompositionsarbetsflöden {#create-compositions}

Med arbetsflöden för kompositioner kan ni kombinera och ordna befintliga målgrupper för att skapa nya målgrupper.

## Skapa ett dispositionsarbetsflöde {#create}

1. Öppna **[!UICONTROL Segments]** meny och välj **[!UICONTROL Create Audience]**.

1. Välj **[!UICONTROL Compose Audience]**.

   >[!NOTE]
   >
   >The **[!UICONTROL Build rule]** kan du skapa en ny segmentdefinition med [Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/audiences-create.png)

1. Arbetsytan visas med två standardaktiviteter:

   * **[!UICONTROL Audience]**: startpunkten för kompositionen. Med den här aktiviteten kan du välja en eller flera målgrupper som grund för ditt arbetsflöde,

   * **[!UICONTROL Save]**: det sista steget i kompositionen. Med den här aktiviteten kan du spara resultatet av arbetsflödet till en ny målgrupp.
   Mer information om hur du konfigurerar aktiviteter på arbetsytan för dispositionsarbetsflöden finns i [Arbeta med arbetsytan](composition-canvas.md).

1. Välj **[!UICONTROL Audience]** och sedan ange en etikett för kompositionen.

   >[!IMPORTANT]
   >
   >The **[!UICONTROL Audience]** aktivitetsetiketten är etiketten för din komposition. Ange ett beskrivande namn för att enklare hämta kompositionen i listan.

   ![](assets/audiences-new-composition.png)

1. Konfigurera kompositionen genom att lägga till så många aktiviteter som behövs mellan **[!UICONTROL Audience]** och **[!UICONTROL Save]** verksamhet. [Lär dig arbeta med arbetsytan](composition-canvas.md)

   ![](assets/audiences-publish.png)

1. När kompositionen är klar klickar du på **[!UICONTROL Publish]** för att publicera kompositionen och spara målgrupperna i Adobe Experience Platform.

   Om något fel inträffar under publiceringen visas varningar med information om hur du löser problemet.

   ![](assets/audiences-alerts.png)

1. Dispositionen publiceras. De resulterande målgrupperna sparas i Adobe Experience Platform. <!-- and are ready to be targeted in Journey Optimizer campaigns. [Get started with campaigns](../campaigns/get-started-with-campaigns.md)-->

## Åtkomst till kompositioner {#access}

>[!CONTEXTUALHELP]
>id="ajo_ao_publish"
>title="Publicera er målgrupp"
>abstract="Publicera materialet för att spara målgrupper i Adobe Experience Platform."

Alla skapade kompositioner kan nås via **[!UICONTROL Compositions]** -fliken. De kan ha flera statusar:

* **[!UICONTROL Draft]**: kompositionen pågår och har inte publicerats.
* **[!UICONTROL Published]**: kompositionen har publicerats, målgrupperna har sparats. <!-- and are available for use.-->
* **[!UICONTROL Archived]**: kompositionen har arkiverats.

![](assets/audiences-compositions.png)

>[!NOTE]
>
>Du kan när som helst duplicera eller ta bort en befintlig komposition med hjälp av ellipsknappen i listan.

Läs mer:

* [Kom igång med målgruppsmaterial](get-started-audience-orchestration.md)
* [Arbeta med arbetsytan](composition-canvas.md)
* [Få åtkomst till och hantera målgrupper](access-audiences.md)
