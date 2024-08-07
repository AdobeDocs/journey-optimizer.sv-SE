---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ditt första dispositionsarbetsflöde
description: Lär dig hur du skapar arbetsflöden för disposition för att kombinera och ordna befintliga målgrupper.
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 8b978900-fcef-46f2-bc19-70776e4f3d43
source-git-commit: 01c14590fe55d8f11c1ff2b18141933b0b3dd5ca
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 0%

---

# Skapa ditt första dispositionsarbetsflöde {#create-compositions}

>[!BEGINSHADEBOX]

Dokumentationen innehåller detaljerad information om hur du arbetar med målgruppsdispositioner i Adobe Journey Optimizer. Om du inte använder Adobe Journey Optimizer [klickar du här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/audience-composition.html){target="_blank"}.

>[!ENDSHADEBOX]

## Skapa ett dispositionsarbetsflöde {#create}

Så här skapar du ett dispositionsarbetsflöde:

1. Gå till menyn **[!UICONTROL Audiences]** och välj **[!UICONTROL Create Audience]**.

1. Välj **[!UICONTROL Compose Audience]**.

   ![](assets/audiences-create.png)

   >[!NOTE]
   >
   >Med metoden för att skapa **[!UICONTROL Build rule]** kan du skapa en ny segmentdefinition med [segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

1. Arbetsytan i kompositionen visas med två standardaktiviteter:

   * **[!UICONTROL Audience]**: startpunkten för kompositionen. Med den här aktiviteten kan du välja en eller flera målgrupper som grund för ditt arbetsflöde,

   * **[!UICONTROL Save]**: det sista steget i kompositionen. Med den här aktiviteten kan du spara resultatet av arbetsflödet till en ny målgrupp.

   Mer information om hur du konfigurerar aktiviteter i dispositionsarbetsytan finns i [Arbeta med dispositionsarbetsytan](composition-canvas.md).

1. Öppna dispositionsegenskaperna för att ange en titel och en beskrivning.

   Om ingen titel har definierats i egenskaperna ställs kompositionens etikett in på &quot;Disposition&quot; följt av datum och tid då den skapades.

   ![](assets/audiences-properties.png)

1. Konfigurera kompositionen genom att lägga till så många aktiviteter som behövs mellan **[!UICONTROL Audience]** och **[!UICONTROL Save]** aktiviteter. [Lär dig hur du arbetar med kompositionsytan](composition-canvas.md)

   ![](assets/audiences-publish.png)

1. När kompositionen är klar klickar du på knappen **[!UICONTROL Publish]** för att publicera kompositionen och spara målgrupperna i Adobe Experience Platform.

   >[!IMPORTANT]
   >
   >Du kan publicera upp till 10 kompositioner i en given sandlåda. Om du har nått det här tröskelvärdet måste du ta bort en disposition för att frigöra utrymme och publicera en ny.

   Om något fel inträffar under publiceringen visas varningar med information om hur du löser problemet.

   ![](assets/audiences-alerts.png)

1. Dispositionen publiceras. Målgrupperna sparas i Adobe Experience Platform och kan nu användas i Journey Optimizer. [Lär dig målinrikta målgrupper i Journey Optimizer](../audience/about-audiences.md#segments-in-journey-optimizer)

## Åtkomst till kompositioner {#access}

>[!CONTEXTUALHELP]
>id="ajo_ao_publish"
>title="Publish er målgrupp"
>abstract="Publish din komposition för att spara de resulterande målgrupperna i Adobe Experience Platform."

Alla skapade kompositioner kan nås från fliken **[!UICONTROL Compositions]**. Du kan när som helst duplicera eller ta bort en befintlig komposition med hjälp av ellipsknappen i listan.

Kompositioner kan ha flera statusvärden:

* **[!UICONTROL Draft]**: kompositionen pågår och har inte publicerats.
* **[!UICONTROL Published]**: kompositionen har publicerats, resulterande målgrupper har sparats och är tillgängliga för användning.

![](assets/audiences-compositions.png)

>[!NOTE]
>
>Målgruppskomposition är för närvarande inte integrerat med funktionen för återställning av sandlådor. Innan du initierar en sandlådeåterställning måste du ta bort dina kompositioner manuellt för att se till att de associerade målgruppsdata rensas ordentligt. Detaljerad information finns i Adobe Experience Platform [sandlådedokumentation](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html#delete-audience-compositions)
