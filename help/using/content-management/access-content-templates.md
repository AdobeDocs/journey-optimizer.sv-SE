---
solution: Journey Optimizer
product: journey optimizer
title: Få åtkomst till och hantera innehållsmallar
description: Lär dig hur du får tillgång till och hanterar innehållsmallar
topic: Content Management
role: User
level: Beginner
exl-id: ef6110c4-1aa6-4835-b0b0-b3c4fe0e7024
source-git-commit: 62b5cfd480414c898ab6f123de8c6b9f99667b7d
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Få åtkomst till och hantera innehållsmallar {#access-manage-templates}

## Åtkomst till innehållsmallar {#access}

Om du vill komma åt innehållsmalllistan väljer du **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** på den vänstra menyn.

![](assets/content-template-list.png)

Alla mallar som skapades i den aktuella sandlådan, antingen från en resa eller en kampanj med alternativet **[!UICONTROL Save as template]**, antingen från menyn **[!UICONTROL Content Templates]**, visas. [Lär dig skapa mallar](#create-content-templates)

Du kan sortera innehållsmallar efter:
* Typ
* Kanal
* Skapad eller ändrad den
* Taggar - [Läs mer om taggar](../start/search-filter-categorize.md#tags)

Du kan också välja att bara visa de objekt som du själv har skapat eller ändrat.

![](assets/content-template-list-filters.png)

## Redigera och ta bort innehållsmallar {#edit}

* Om du vill redigera ett mallinnehåll klickar du på önskat objekt i listan och gör önskade ändringar. Du kan också redigera egenskaperna för innehållsmallen genom att klicka på redigeringsknappen bredvid mallens namn.

  ![](assets/content-template-edit.png)

* Om du vill ta bort en mall markerar du knappen **[!UICONTROL More actions]** bredvid önskad mall och väljer **[!UICONTROL Delete]**.

  ![](assets/content-template-list-delete.png)

>[!NOTE]
>
>När en mall redigeras eller tas bort påverkas inte kampanjer eller resor inklusive innehåll som skapats med den här mallen.

## Visa mallar som miniatyrbilder {#template-thumbnails}

Välj läget **[!UICONTROL Grid view]** om du vill visa varje mall som en miniatyrbild.

>[!AVAILABILITY]
>
>Den här funktionen lanseras i begränsad tillgänglighet (LA) för en liten grupp kunder.

![](assets/content-template-grid-view.png)

>[!NOTE]
>
>För närvarande kan riktiga miniatyrbilder bara skapas för e-postinnehållsmallar av HTML-typ.

När du uppdaterar ett innehåll kan du behöva vänta några sekunder innan ändringarna visas i miniatyrbilden.

## Exportera innehållsmallar till en annan sandlåda {#export}

Med Journey Optimizer kan du kopiera en innehållsmall från en sandlåda till en annan. Du kan till exempel kopiera en mall från sandlådemiljön på scenen till produktionssandlådan.

Kopieringsprocessen utförs via en **paketexport och import** mellan käll- och målsandlådorna. Detaljerad information om hur du exporterar objekt och importerar dem till en målsandlåda finns i det här avsnittet: [Kopiera objekt till en annan sandlåda](../configuration/copy-objects-to-sandbox.md)
