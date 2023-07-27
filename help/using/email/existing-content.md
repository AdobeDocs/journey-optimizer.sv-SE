---
solution: Journey Optimizer
product: journey optimizer
title: Importera e-postinnehåll
description: Lär dig hur du importerar e-postinnehåll
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: e-post, import, innehåll, html, zip, css
exl-id: 52011299-0c65-49c3-9edd-ba7bed5d7205
source-git-commit: 4112ac79a1f21fb369119ccd801dcbceac3c1e58
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Importera e-postinnehåll {#existing-content}

[!DNL Journey Optimizer] gör att du kan importera befintligt HTML-innehåll för att utforma dina e-postmeddelanden. Innehållet kan vara:

* An **HTML-fil** med en inbyggd formatmall,
* A **ZIP-mapp** inklusive en HTML-fil, formatmallen (.css) och bilder.

  >[!NOTE]
  >
  >ZIP-filstrukturen har inga begränsningar. Referenserna måste dock vara relativa och passa in i trädstrukturen i ZIP-mappen.

Om du vill importera en fil som innehåller HTML-innehåll följer du stegen nedan:

1. På e-postdesignerns startsida väljer du **[!UICONTROL Import HTML]**.

   ![](assets/import-html_2.png)

1. Dra och släpp HTML- eller ZIP-filen med HTML och klicka på **[!UICONTROL Import]**.

   ![](assets/html-imported_2.png)

1. När HTML-innehållet har överförts är ditt innehåll **[!UICONTROL Compatibility mode]**.

   I det här läget kan du bara anpassa texten, lägga till länkar eller inkludera resurser i innehållet.

1. Om du vill kunna utnyttja e-postdesignerns innehållskomponenter ska du gå till **[!UICONTROL HTML converter]** och klicka **[!UICONTROL Convert]**.

   ![](assets/html-imported.png)

   >[!NOTE]
   >
   > Använda `<table>` taggen som det första lagret i en HTML-fil kan orsaka formatförlust, inklusive inställningar för bakgrund och bredd i den översta lagertaggen.

1. Du kan nu anpassa den importerade filen efter behov med e-postdesignerfunktionerna [Läs mer](content-from-scratch.md).

## Instruktionsvideo {#video}

Lär dig hur du importerar befintligt HTML-innehåll, ändrar designen, lägger till spegelsideslänkar och avbryter prenumerationen samt hur du kodar ditt innehåll.

>[!VIDEO](https://video.tv.adobe.com/v/334102?quality=12)
