---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med målgruppsmaterial
description: Läs mer om publiksammansättning
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: af71d24d-77eb-44df-8216-b0aeaf4c4fa4
source-git-commit: 435898d7e806e93ee0154c3da22f6a011fc78175
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%

---

# Kom igång med målgruppsmaterial {#get-start-audience-composition}

>[!CONTEXTUALHELP]
>id="ajo_ao_create_composition"
>title="Skapa en komposition"
>abstract="Skapa ett dispositionsarbetsflöde för att kombinera befintliga Adobe Experience Platform-målgrupper till en visuell arbetsyta och utnyttja olika aktiviteter (dela, exkludera..) för att skapa nya målgrupper."

>[!BEGINSHADEBOX]

Dokumentationen innehåller detaljerad information om hur du arbetar med målgruppsdispositioner i Adobe Journey Optimizer. Om du bara är kund i realtid och inte använder Adobe Journey Optimizer klickar du [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/audience-composition.html){target="_blank"}.

>[!ENDSHADEBOX]

Med målgruppskomposition kan du skapa **kompositionsarbetsflöden**, där du kan kombinera befintliga Adobe Experience Platform-målgrupper till en visuell arbetsyta och utnyttja olika aktiviteter (dela, exkludera..) för att skapa nya målgrupper.

När det är klart sparas de **resulterande målgrupperna** i Adobe Experience Platform tillsammans med befintliga målgrupper och kan utnyttjas i Journey Optimizer kampanjer och resor till målkunder. Lär dig målinrikta målgrupper i Journey Optimizer
![](assets/audiences-process.png)

>[!IMPORTANT]
>
>Användningen av målgrupper och attribut från målgruppssammansättning är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.
>
>Anrikningsattribut är ännu inte integrerade med policystyrningen. Därför kommer de etiketter för dataanvändning som du använder för dina anrikningsattribut inte att användas i Journey Optimizer kampanjer eller resor.

Målgruppskomposition finns på Adobe Journey Optimizer **[!UICONTROL Audiences]**-menyn:

![](assets/audiences-browse.png)

* Fliken **[!UICONTROL Overview]** innehåller en dedikerad instrumentpanel med nyckelvärden som är relaterade till organisationens målgruppsdata. Mer information finns i [Adobe Experience Platform Dashboards guide](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/segments.html).

* Fliken **[!UICONTROL Browse]** visar alla befintliga målgrupper som lagras i Adobe Experience Platform.

* På fliken **[!UICONTROL Compositions]** kan du skapa kompositionsarbetsflöden där du kan kombinera och ordna målgrupper för att skapa nya.

## Skapa ett dispositionsarbetsflöde {#create}

Så här skapar du ett dispositionsarbetsflöde:

1. Gå till menyn **[!UICONTROL Audiences]** och välj **[!UICONTROL Create Audience]**.

1. Välj **[!UICONTROL Compose Audience]**.

   ![](assets/audiences-create.png)

1. Arbetsytan i kompositionen visas med två standardaktiviteter:

   * **[!UICONTROL Audience]**: startpunkten för kompositionen. Med den här aktiviteten kan du välja en eller flera målgrupper som grund för ditt arbetsflöde,

   * **[!UICONTROL Save]**: det sista steget i kompositionen. Med den här aktiviteten kan du spara resultatet av arbetsflödet till en ny målgrupp.

1. Öppna dispositionsegenskaperna för att ange en titel och en beskrivning.

   Om ingen titel har definierats i egenskaperna ställs kompositionens etikett in på &quot;Disposition&quot; följt av datum och tid då den skapades.

   ![](assets/audiences-properties.png)

1. Konfigurera kompositionen genom att lägga till så många aktiviteter som behövs mellan **[!UICONTROL Audience]** och **[!UICONTROL Save]** aktiviteter. Mer information om hur du skapar en komposition finns i [dokumentationen om målgruppskomposition](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-composition).

   ![](assets/audiences-publish.png)

1. När kompositionen är klar klickar du på knappen **[!UICONTROL Publish]** för att publicera kompositionen och spara målgrupperna i Adobe Experience Platform.

   >[!IMPORTANT]
   >
   >Du kan publicera upp till 10 kompositioner i en given sandlåda. Om du har nått det här tröskelvärdet måste du ta bort en disposition för att frigöra utrymme och publicera en ny.

   Om något fel inträffar under publiceringen visas varningar med information om hur du löser problemet.

   ![](assets/audiences-alerts.png)

1. Dispositionen publiceras. Målgrupperna sparas i Adobe Experience Platform och kan nu användas i Journey Optimizer. [Lär dig målinrikta målgrupper i Journey Optimizer](../audience/about-audiences.md#segments-in-journey-optimizer)

>[!NOTE]
>
>Målgrupper från **målgruppskomposition** körs dagligen, så du kan behöva vänta upp till 24 timmar på att använda dem i Journey Optimizer. Förbättrade attribut i målgrupper för målgruppssammansättning är lika fräscha som den senaste kompositionen, som kan vara upp till 24 timmar tidigare.

## Åtkomst till kompositioner {#access}

>[!CONTEXTUALHELP]
>id="ajo_ao_publish"
>title="Publicera er målgrupp"
>abstract="Publicera materialet för att spara målgrupper i Adobe Experience Platform."

Alla skapade kompositioner kan nås från fliken **[!UICONTROL Compositions]**. Du kan när som helst duplicera eller ta bort en befintlig komposition med hjälp av ellipsknappen i listan.

Kompositioner kan ha flera statusvärden:

* **[!UICONTROL Draft]**: kompositionen pågår och har inte publicerats.
* **[!UICONTROL Published]**: kompositionen har publicerats, resulterande målgrupper har sparats och är tillgängliga för användning.

![](assets/audiences-compositions.png)

>[!NOTE]
>
>Målgruppskomposition är för närvarande inte integrerat med funktionen för återställning av sandlådor. Innan du initierar en sandlådeåterställning måste du ta bort dina kompositioner manuellt för att se till att de associerade målgruppsdata rensas ordentligt. Detaljerad information finns i Adobe Experience Platform [sandlådedokumentation](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html#delete-audience-compositions)
