---
solution: Journey Optimizer
product: journey optimizer
title: Få åtkomst till och hantera innehållsmallar
description: Lär dig hur du får tillgång till och hanterar innehållsmallar
topic: Content Management
role: User
level: Beginner
exl-id: ef6110c4-1aa6-4835-b0b0-b3c4fe0e7024
source-git-commit: a9f2eae6398f92a40accb62b1d4544bda031559c
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Få åtkomst till och hantera innehållsmallar {#access-manage-templates}

## Åtkomst till innehållsmallar {#access}

Om du vill komma åt innehållsmalllistan väljer du **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** på den vänstra menyn.

![](assets/content-template-list.png)

Alla mallar som skapats i den aktuella sandlådan, antingen från en resa eller en kampanj med alternativet **[!UICONTROL Save as template]** eller från menyn **[!UICONTROL Content Templates]**, visas. [Lär dig skapa mallar](#create-content-templates)

I rutan till vänster kan du ordna innehållsmallar i mappar. Som standard visas alla mallar. När du väljer en mapp visas endast de mallar och mappar som finns i den valda mappen. [Läs mer](#folders)

![](assets/content-template-list-folders.png)

Om du vill söka efter ett visst objekt börjar du skriva ett namn i sökfältet. När en [mapp](#folders) är markerad gäller sökningen alla innehållsmallar eller mappar på den första nivån i hierarkin i mappen<!--(not nested items)-->.

Du kan sortera innehållsmallar efter:

* Typ
* Kanal
* Skapad eller ändrad den
* Taggar - [Läs mer om taggar](../start/search-filter-categorize.md#tags)

Du kan också välja att bara visa de objekt som du har skapat eller ändrat.

![](assets/content-template-list-filters.png)

>[!NOTE]
>
>Från och med mars 2025 är innehållsmallar av HTML-typ föråldrade. Du kan fortfarande komma åt befintliga HTML-innehållsmallar som tidigare skapats i [!DNL Journey Optimizer].

## Använda mappar för att hantera innehållsmallar {#folders}

Om du enkelt vill navigera bland dina innehållsmallar kan du använda mappar för att ordna dem mer effektivt i en strukturerad hierarki. På så sätt kan du kategorisera och hantera objekten efter organisationens behov.

![](assets/content-template-folders.png)

1. Klicka på knappen **[!UICONTROL All content templates]** om du vill visa alla objekt som tidigare skapats utan mappgruppering.

1. Klicka på mappen **[!UICONTROL Root]** för att visa alla mappar som skapats.

   >[!NOTE]
   >
   >Om du inte har skapat mappar än visas alla innehållsmallar.

1. Klicka på en mapp i mappen **[!UICONTROL Root]** för att visa dess innehåll.

1. När du klickar på mappen **[!UICONTROL Root]** eller någon annan mapp visas knappen **[!DNL Create folder]** . Markera den.

   ![](assets/content-template-create-folder.png)

1. Ange ett namn för den nya mappen och klicka på **[!UICONTROL Save]**. Den nya mappen visas ovanpå listan med innehållsmallar i mappen **[!UICONTROL Root]**, eller inuti den markerade mappen.

1. Du kan klicka på knappen **[!UICONTROL More actions]** om du vill byta namn på eller ta bort mappen.

   ![](assets/content-template-folder-more-actions.png)

1. Med knappen **[!UICONTROL More actions]** kan du också flytta innehållsmallen till en annan befintlig mapp.

   ![](assets/content-template-folder-moved.png)

1. Navigera till mappen som du nyss skapade. Varje ny innehållsmall som du [skapar](create-content-templates.md) från här sparas i den aktuella mappen.

   ![](assets/content-template-folder-create.png)

## Redigera och ta bort innehållsmallar {#edit}

* Om du vill redigera ett mallinnehåll klickar du på önskat objekt i listan och gör önskade ändringar. Du kan också redigera egenskaperna för innehållsmallen genom att klicka på redigeringsknappen bredvid mallens namn.

  ![](assets/content-template-edit.png)

* Om du vill ta bort en mall markerar du knappen **[!UICONTROL More actions]** bredvid önskad mall och väljer **[!UICONTROL Delete]**.

  ![](assets/content-template-list-delete.png)

>[!NOTE]
>
>När en mall redigeras eller tas bort påverkas inte kampanjer eller resor inklusive innehåll som skapats med den här mallen.

## [!BADGE Begränsad tillgänglighet]{type=Informative} Visa mallar som miniatyrbilder {#template-thumbnails}

Välj läget **[!UICONTROL Grid view]** om du vill visa varje mall som en miniatyrbild.

>[!AVAILABILITY]
>
>Den här funktionen lanseras i begränsad tillgänglighet (LA) för en liten grupp kunder.

![](assets/content-template-grid-view.png)

>[!NOTE]
>
>Korrekta miniatyrbilder kan bara skapas för e-postmallar av HTML-typ.

När du uppdaterar innehåll väntar du några sekunder på att ändringarna ska visas i miniatyrbilden.

## Exportera innehållsmallar till en annan sandlåda {#export}

Med Journey Optimizer kan du kopiera en innehållsmall från en sandlåda till en annan. Du kan till exempel kopiera en mall från sandlådemiljön på scenen till produktionssandlådan.

Kopieringsprocessen utförs via en **paketexport och import** mellan käll- och målsandlådan. Detaljerad information om hur du exporterar objekt och importerar dem till en målsandlåda finns i det här avsnittet: [Kopiera objekt till en annan sandlåda](../configuration/copy-objects-to-sandbox.md)

