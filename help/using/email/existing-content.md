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
source-git-commit: ddbab603e4ac612a49a3853fcac428950def1d98
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Importera e-postinnehåll {#existing-content}

Med [!DNL Journey Optimizer] kan du importera befintligt HTML-innehåll för att utforma dina e-postmeddelanden. Innehållet kan vara:

* En **HTML-fil** med en inbyggd formatmall;
* En **.zip-mapp** som innehåller en HTML-fil, formatmallen (.css) och bilder.

  >[!NOTE]
  >
  >ZIP-filstrukturen har inga begränsningar. Referenserna måste dock vara relativa och passa in i trädstrukturen i ZIP-mappen.

<!--DOCAC-13676
>[!TIP]
>
>If you have image designs (JPEG or PNG) instead of HTML files, you can use the [Template Accelerator](image-to-html.md) to automatically convert them into editable HTML email templates using AI.-->

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
