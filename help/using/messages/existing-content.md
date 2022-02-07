---
title: Importera eller koda dina e-postmeddelanden
description: Lär dig hur du importerar e-postinnehåll eller kodar dina e-postmeddelanden
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 52011299-0c65-49c3-9edd-ba7bed5d7205
source-git-commit: b43e3432ede1d4985e0a6b57b57c5efc3cf60c50
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 4%

---

# Importera eller koda ditt e-postinnehåll {#existing-content}

Med Journey Optimizer kan du importera befintligt HTML-innehåll för att utforma dina e-postmeddelanden. Det här innehållet kan vara oformaterad HTML-kod eller innehåll från en befintlig HTML-fil eller en zip-mapp.

Följ stegen nedan om du vill koda HTML-innehåll eller importera befintligt innehåll:

1. [Skapa ett meddelande](create-message.md)

1. Öppna **[!UICONTROL Email Designer]** från **[!UICONTROL Edit Content]** -avsnitt.

   ![](assets/import-html_1.png)

1. Välj **[!UICONTROL Code your own]** eller **[!UICONTROL Import HTML]**. Gå till avsnitten nedan för nästa steg.

## Koda din egen {#import-raw-html-code}

Använd **[!UICONTROL Code your own]** läge för att importera råformat HTML och/eller koda ditt e-postinnehåll. Den här metoden kräver kunskaper i HTML.

>[!CAUTION]
>
> Bilder från [Adobe Experience Manager Assets Essentials](assets-essentials.md) kan inte refereras när den här metoden används. De bilder som refereras i HTML-koden måste lagras på en offentlig plats.

1. På e-postdesignerns startsida väljer du **[!UICONTROL Code your own]**.

   ![](assets/code-your-own.png)

1. Ange eller klistra in HTML-koden i Raw-format.

1. Använd den vänstra rutan för att utnyttja [!DNL Journey Optimizer] personaliseringsfunktioner. Mer information om detta finns i [det här avsnittet](../personalization/personalize.md).

   ![](assets/code-editor.png)

1. Om du vill öppna e-postdesignern för att starta e-postmeddelandet från en ny design väljer du **[!UICONTROL Change your design]** på Alternativ-menyn.

   ![](assets/code-editor-change-design.png)

1. Klicka på **[!UICONTROL Preview]** för att kontrollera meddelandets utformning och personalisering med testprofiler. Mer information om detta finns i [det här avsnittet](preview.md).

   ![](assets/code-editor-preview.png)

1. När koden är klar klickar du på **[!UICONTROL Save]** går du tillbaka till skärmen för att skapa meddelanden för att slutföra meddelandet.

   ![](assets/code-editor-save.png)

## Importera HTML {#import-html-content-from-file}

Du kan importera HTML i e-postdesignern. Innehållet kan vara:

* An **HTML-fil** med en infogad formatmall,
* A **ZIP-mapp** med HTML-filen, formatmallen (.css) och bilderna.

   >[!NOTE]
   >
   >ZIP-filstrukturen har inga begränsningar. Referenserna måste dock vara relativa och passa med trädstrukturen i ZIP-mappen.

Om du vill importera en fil som innehåller HTML-innehåll följer du stegen nedan:

1. På e-postdesignerns startsida väljer du **[!UICONTROL Import HTML]**.

   ![](assets/import-html_2.png)

1. Dra och släpp HTML- eller ZIP-filen med HTML.

1. När HTML-innehållet har överförts kan du använda e-postdesignerns funktioner för att redigera och förhandsgranska e-postmeddelandet. [Läs mer i det här avsnittet](create-email-content.md).

   ![](assets/html-imported.png)
