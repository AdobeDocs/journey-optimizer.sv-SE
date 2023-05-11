---
solution: Journey Optimizer
product: journey optimizer
title: Användargränssnitt
description: Läs mer om Journey Optimizer användargränssnitt
feature: Overview
topic: Content Management
role: User
level: Intermediate
source-git-commit: fc7f996fca8b1e8e5f6b7379cc3b2b7da764e0ed
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

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

Du kommer åt filter genom att klicka på filterikonen högst upp till vänster i en lista. På filtermenyn kan du filtrera de visade elementen enligt olika villkor: Du kan välja att endast visa element av en viss typ eller status, de element du har skapat eller de element som har ändrats under de senaste 30 dagarna. Alternativen varierar beroende på sammanhanget.

Dessutom kan du använda enhetliga taggar för att filtrera en lista beroende på vilka taggar som tilldelats ett objekt. För närvarande finns det taggar för resor och kampanjer. [Lär dig hur du arbetar med taggar](#tags)

>[!NOTE]
>
>Observera att kolumner som visas kan personaliseras med hjälp av konfigurationsknappen längst upp till höger i listorna. Personalisering sparas per användare.

I listorna kan du utföra grundläggande åtgärder för varje element. Du kan till exempel skapa dubbletter eller radera en post.

![](assets/journey4.png)

## Arbeta med enhetliga taggar {#tags}

Med Adobe Experience Platform [Enhetliga taggar](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/overview.html)kan du enkelt klassificera dina Journey Optimizer-resor och -kampanjer för att förbättra sökningen från listorna.

>[!AVAILABILITY]
>
>Enhetliga taggar finns för närvarande i Beta. Dokumentationen och funktionaliteten kan komma att ändras.

### Lägga till taggar i ett objekt

The **Taggar** fält, i [resa](../building-journeys/journey-gs.md#change-properties) eller [kampanj](../campaigns/create-campaign.md#create) -egenskaper kan du definiera taggar för objektet. Du kan antingen markera en befintlig tagg eller skapa en ny.

Börja skriva namnet på den önskade taggen och markera den i listan. Om den inte är tillgänglig klickar du på **Skapa** för att skapa en ny och lägga till den. Du kan definiera så många taggar som behövs.

![](assets/tags1.png)

Listan med definierade taggar visas under **Taggar** fält.

>[!NOTE]
>
> Taggar är skiftlägeskänsliga
> 
> Om du duplicerar eller skapar en ny version av en resa eller kampanj bevaras taggarna.

### Filtrera på taggar

På resorna och kampanjlistorna visas en dedikerad kolumn så att du enkelt kan visualisera dina taggar.

Ett filter är också tillgängligt för att endast visa resor eller kampanjer med vissa taggar.

![](assets/tags2.png)

Du kan lägga till eller ta bort taggar från alla typer av resor och kampanjer (live, draft, etc.). Om du vill göra det klickar du på **Fler åtgärder** -ikon bredvid objektet och markera **Redigera taggar**.

![](assets/tags3.png)

### Hantera taggar

Administratörer kan ta bort taggar och ordna dem efter kategorier med **Taggar** meny, under **ADMINISTRATION**. Läs mer om tagghantering i [Dokumentation för enhetliga taggar](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/ui/managing-tags.html).

>[!NOTE]
>
> Taggar skapade direkt från **[!UICONTROL Tags]** i Journey Optimizer läggs automatiskt till i den inbyggda kategorin&quot;Ej kategoriserad&quot;.
