---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med fördefinierade filter
description: Lär dig spara, använda och hantera fördefinierade filter i samordnade kampanjer
version: Campaign Orchestration
source-git-commit: e486aae3a6635d8eec0c398bfe03b6a63a007ef1
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---


# Arbeta med fördefinierade filter {#predefined-filters}

Fördefinierade filter är sparade regler som du kan återanvända i regelbyggaren. Använd dem för att undvika att återskapa vanliga frågor och för att standardisera målinriktningslogiken för samordnade kampanjer.

Du kan markera fördefinierade filter som favoriter, dela dem med andra användare och lägga till parametrar så att markerade fält kan redigeras när filtret tillämpas.

## Skapa ett fördefinierat filter {#create}

Spara ett anpassat filter från regelbyggaren så att det blir tillgängligt för framtida bruk. Följ de här stegen:

1. Öppna regelbyggaren och definiera filtervillkoren. [Lär dig skapa en regel](../orchestrated/build-query.md)

1. Valfritt: Om du vill göra vissa fält redigerbara när du använder filtret markerar du fältet och aktiverar **[!UICONTROL Set as parameter]**. När du använder filtret kan bara dessa fält redigeras.

   ![](assets/predefined-filter-parameter-enable.png)

1. Om du vill spara filtret klickar du på **[!UICONTROL Select or save filter]** och väljer **[!UICONTROL Save as filter]**.

   ![](assets/predefined-filter-save.png)

1. Ange en etikett och en beskrivning för filtret och klicka sedan på **[!UICONTROL Save]**.

   * Om du vill spara filtret som en favorit aktiverar du alternativet **[!UICONTROL Favorite filter]**. Läs mer i [det här avsnittet](#fav-filter).
   * Aktivera alternativet **[!UICONTROL Shared filter]** om du vill göra filtret tillgängligt för andra användare. Läs mer i [det här avsnittet](#share-filter).

   ![](assets/predefined-filter-save-name.png)

Ditt anpassade filter är nu tillgängligt i listan **Fördefinierade filter**.

## Använda ett fördefinierat filter i en regel {#apply}

Fördefinierade filter är tillgängliga när du definierar frågor i regelbyggaren.

1. Klicka på **[!UICONTROL Rule properties]** i rutan **[!UICONTROL Select or save filter]**.

1. Välj **[!UICONTROL Select predefined filter]** och välj ett filter. Du kan också välja ett fördefinierat filter direkt från listan om det har lagts till i favoriter.

   ![](assets/predefined-filter-apply.png)

   >[!IMPORTANT]
   >
   >Om du väljer ett fördefinierat filter ersätts den regel som har byggts in på arbetsytan med det valda filtret.

1. Filtret öppnas på arbetsytan. Fortsätt redigera villkoret efter behov.

   ![](assets/predefined-filter-added.png)

   Om filtret som du har valt innehåller parametrar kan du bara redigera de fält som har markerats som parametrar. De visas i rutan bredvid rutan **[!UICONTROL Rule properties]**.

   ![](assets/predefined-filter-parameter-apply.png)

   Om du vill redigera själva det fördefinierade filtret klickar du på knappen ![ellips](assets/do-not-localize/rule-builder-icon-more.svg) och väljer **[!UICONTROL Switch to rule edition]**. Alla ändringar gäller bara för den aktuella regeln som du skapar. Det fördefinierade filtret ändras inte.

   ![](assets/predefined-filter-parameter-edit.png)

## Spara ett filter som en favorit {#fav-filter}

När du skapar ett fördefinierat filter ska du aktivera alternativet **[!UICONTROL Favorite filter]** så att det här fördefinierade filtret visas i dina favoriter.

När ett filter sparas som en favorit visas det i avsnittet **[!UICONTROL Favorite filters]** i filterlistan enligt nedan:

![Avsnittet Favoritfilter](assets/predefined-filter-favorites.png)

## Dela ett fördefinierat filter {#share-filter}

Som standard är fördefinierade filter som du skapar privata och bara synliga för dig. Aktivera alternativet **[!UICONTROL Shared filter]** om du vill göra ett filter tillgängligt för andra operatorer i organisationen.

![Alternativ för delat filter](assets/predefined-filter-shared.png)

Delade filter visas i den fördefinierade filterlistan för alla användare, vilket gör att de kan använda dessa filter i sina egna regler.

## Hantera fördefinierade filter {#manage-predefined-filter}

Så här redigerar eller tar du bort fördefinierade filter:

1. Öppna den fördefinierade filterlistan med knappen **[!UICONTROL Select or save filter]** i regelbygget.

1. Markera knappen ![ellips](assets/do-not-localize/rule-builder-icon-more.svg) bredvid ett filter och välj önskad åtgärd.

![](assets/predefined-filters-edit.png)
