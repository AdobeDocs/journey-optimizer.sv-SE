---
solution: Journey Optimizer
product: journey optimizer
title: Importera e-postinnehåll
description: Lär dig hur du importerar e-postinnehåll
feature: Email Design
topic: Content Management
role: User
level: Intermediate
keywords: e-post, import, innehåll, html, zip, css
exl-id: 52011299-0c65-49c3-9edd-ba7bed5d7205
source-git-commit: 7cfeabc85b9645be9d61ed6458e57e42ea319619
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Importera e-postinnehåll {#existing-content}

Med [!DNL Journey Optimizer] kan du importera befintligt HTML-innehåll för att utforma dina e-postmeddelanden. Innehållet kan vara:

* En **HTML-fil** med en inbyggd formatmall;
* En **.zip-mapp** som innehåller en HTML-fil, formatmallen (.css) och bilder.

  >[!NOTE]
  >
  >ZIP-filstrukturen har inga begränsningar. Referenserna måste dock vara relativa och passa in i trädstrukturen i ZIP-mappen.


>[!TIP]
>
>Om du har bilddesigner (JPEG eller PNG) i stället för HTML-filer kan du använda [bilden till HTML-konverteraren](../content-management/image-to-html.md) för att automatiskt konvertera dem till redigerbara HTML-e-postmallar med hjälp av AI.

Om du vill importera en fil som innehåller HTML-innehåll följer du stegen nedan:

1. Välj **[!UICONTROL Import HTML]** på startsidan för e-post till Designer.

   ![](assets/import-html_2.png)

1. Dra och släpp HTML- eller ZIP-filen med ditt HTML-innehåll och klicka på **[!UICONTROL Import]**.

   ![](assets/html-imported_2.png)

1. När HTML-innehållet har överförts är ditt innehåll i **[!UICONTROL Compatibility mode]**.

   I det här läget kan du bara anpassa texten, lägga till länkar eller inkludera resurser i innehållet.

1. Om du vill kunna utnyttja e-postkomponenterna för Designer-innehåll går du till fliken **[!UICONTROL HTML converter]** och klickar på **[!UICONTROL Convert]**.

   ![](assets/html-imported.png)

   >[!NOTE]
   >
   > Om du använder en `<table>`-tagg som det första lagret i en HTML-fil kan du förlora format, inklusive inställningar för bakgrund och bredd i den översta lagertaggen.

1. Du kan nu anpassa den importerade filen efter behov med e-post-Designer-funktionerna. [Läs mer](content-from-scratch.md)

## Instruktionsvideo {#video}

Lär dig hur du importerar befintligt HTML-innehåll, ändrar designen, lägger till spegelsideslänkar och länkar för att avbryta prenumerationen samt kodar ditt innehåll.

>[!VIDEO](https://video.tv.adobe.com/v/334102?quality=12)
