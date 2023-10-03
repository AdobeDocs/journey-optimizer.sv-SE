---
solution: Journey Optimizer
product: journey optimizer
title: Söka, filtrera, ordna
description: Läs mer om Journey Optimizer användargränssnitt
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 6151aea2-6a34-4000-ba48-161efe4d94d7
source-git-commit: dd463d36550b53faaffca90691550278498c862a
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 9%

---

# Söka, filtrera, ordna {#search-filter-organize}

## Sökning{#unified-search}

Var som helst från Adobe Journey Optimizer-gränssnittet kan du använda sökfunktionen för enhetliga Adobe Experience Cloud i mitten av det övre fältet för att hitta resurser, resor, datauppsättningar med mera i dina sandlådor.

Börja skriva in innehåll för att visa de bästa resultaten. Hjälpartiklar om de angivna nyckelorden visas också i resultaten.

![](assets/unified-search.png)

Tryck **Retur** för att få tillgång till alla resultat och filtrera efter affärsobjekt.

![](assets/search-and-filter.png)

## Filterlistor{#filter-lists}

I de flesta av listorna använder du sökfältet för att hitta specifika objekt och definiera filtervillkor.

Du kommer åt filter genom att klicka på filterikonen högst upp till vänster i en lista. Med filtermenyn kan du filtrera de element som visas enligt olika villkor: Du kan välja att endast visa element av en viss typ eller status, de element som du har skapat eller de som har ändrats under de senaste 30 dagarna. Alternativen varierar beroende på sammanhanget.

Dessutom kan du använda enhetliga taggar för att filtrera en lista beroende på vilka taggar som tilldelats ett objekt. För närvarande finns det taggar för resor och kampanjer. [Lär dig hur du arbetar med taggar](#tags)

>[!NOTE]
>
>Observera att kolumner som visas kan personaliseras med hjälp av konfigurationsknappen längst upp till höger i listorna. Personalisering sparas per användare.

I listorna kan du utföra grundläggande åtgärder för varje element. Du kan till exempel skapa dubbletter eller radera en post.

![](assets/journey4.png)

## Arbeta med enhetliga taggar {#tags}

Med Adobe Experience Platform [Enhetliga taggar](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/overview.html)kan du enkelt klassificera dina Journey Optimizer-resor och -kampanjer för att förbättra sökningen från listorna.

### Lägga till taggar i ett objekt

The **[!UICONTROL Tags]** I kan du definiera taggar för objektet. Taggar är tillgängliga för följande objekt:

* [Resor](../building-journeys/journey-gs.md#change-properties)
* [Kampanjer](../campaigns/create-campaign.md#create)
* [Mallar](../content-management/content-templates.md)
* [Fragment](../content-management/fragments.md)
* [Prenumerationslistor](../landing-pages/subscription-list.md)
* [Landningssidor](../landing-pages/create-lp.md)

Du kan antingen markera en befintlig tagg eller skapa en ny. För att göra detta, följ nedanstående steg.

1. Börja skriva namnet på den önskade taggen och/eller markera den i listan.

   ![](assets/tags1.png)

   >[!NOTE]
   >
   > Taggar är inte skiftlägeskänsliga.

1. Om taggen som du söker efter inte är tillgänglig klickar du på **[!UICONTROL Create ""]** om du vill definiera ett nytt objekt, läggs det automatiskt till i det aktuella objektet och blir tillgängligt för alla andra objekt.

   ![](assets/tags4.png)

1. Listan med de markerade eller skapade taggarna visas under **[!UICONTROL Tags]** fält. Du kan definiera så många taggar som behövs.

>[!NOTE]
> 
> Om du duplicerar eller skapar en ny version av ett objekt behålls taggarna.

### Filtrera på taggar

I varje objektlista visas en dedikerad kolumn så att du enkelt kan se dina taggar.

Ett filter är också tillgängligt för att endast visa objekt med vissa taggar.

![](assets/tags2.png)

Du kan lägga till eller ta bort taggar från alla typer av resor och kampanjer (live, draft, etc.). Klicka på **[!UICONTROL More actions]** -ikon bredvid objektet och markera **[!UICONTROL Edit tags]**.

![](assets/tags3.png)

### Hantera taggar

Administratörer kan ta bort taggar och ordna dem efter kategorier med hjälp av **[!UICONTROL Tags]** meny, under **[!UICONTROL ADMINISTRATION]**. Läs mer om tagghantering i [Dokumentation för enhetliga taggar](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/ui/managing-tags.html).

>[!NOTE]
>
> Taggar skapade direkt från **[!UICONTROL Tags]** i Journey Optimizer läggs automatiskt till i den inbyggda kategorin&quot;Ej kategoriserad&quot;.
