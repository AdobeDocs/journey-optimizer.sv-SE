---
solution: Journey Optimizer
product: journey optimizer
title: Designa e-postmeddelanden
description: Lär dig utforma e-postmeddelanden
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: e-post, design, stockinnehåll, resurser
exl-id: e4f91870-f06a-4cd3-98b7-4c413233e310
source-git-commit: dd463d36550b53faaffca90691550278498c862a
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# Kom igång med e-postdesign {#get-started-content-design}

Du kan importera ett befintligt innehåll i [!DNL Journey Optimizer] eller utnyttja designfunktionerna:

* Använd [!DNL Journey Optimizer] **funktioner för e-postdesign** för att designa eller importera responsiva e-postmeddelanden. [Läs mer](content-from-scratch.md)

* Utnyttja **Adobe Experience Manager Assets Essentials** för att berika era e-postmeddelanden, bygga och hantera er egen databas för mediefiler. [Läs mer](../content-management/assets-essentials.md)

* Sök **Adobe Stock foton** för att skapa innehåll och förbättra e-postdesignen. [Läs mer](../content-management/stock.md)

* Förbättra kundernas upplevelse genom att skapa personaliserade och dynamiska meddelanden utifrån deras profilattribut. Läs mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md).

➡️ [Upptäck den här funktionen i en video](#video)

## Bästa praxis för e-postdesign {#best-practices}

När du skickar e-postmeddelanden är det viktigt att tänka på att mottagarna kan vidarebefordra dem, vilket ibland kan orsaka problem med e-postens återgivning. Detta gäller särskilt när du använder CSS-klasser som kanske inte stöds av e-postleverantören som används för vidarebefordran, till exempel om du använder CSS-klassen&quot;is-desktop-hidden&quot; för att dölja en bild på mobila enheter.

För att minimera dessa återgivningsproblem rekommenderar vi att du håller e-postdesignstrukturen så enkel som möjligt. Försök använda en enda design som fungerar bra för både datorer och mobila enheter, och undvik att använda komplexa CSS-klasser eller andra designelement som kanske inte stöds fullt ut av alla e-postklienter. Genom att följa dessa rutiner kan du se till att dina e-postmeddelanden återges korrekt, oavsett hur mottagarna visar eller vidarebefordrar dem.

## Viktiga steg för att skapa e-postinnehåll {#key-steps}

När du har [lade till ett e-postmeddelande](create-email.md) till en resa eller en kampanj kan du börja skapa ditt e-postinnehåll.

1. Gå igenom **[!UICONTROL Edit content]** för att komma åt e-postdesignern. [Läs mer](create-email.md#define-email-content)

   ![](assets/email_designer_edit_email_body.png)

1. På e-postdesignerns startsida väljer du hur du vill utforma e-postmeddelandet bland följande alternativ:

   * **Designa din e-post från grunden** via e-postdesignerns gränssnitt och utnyttja bilder från [Adobe Experience Manager Assets Essentials](../content-management/assets-essentials.md). Lär dig hur du utformar e-postinnehåll i [det här avsnittet](content-from-scratch.md).

   * **Kod eller klistra in Raw HTML** direkt i e-postdesignern. Lär dig koda eget innehåll i [det här avsnittet](code-content.md).

     >[!NOTE]
     >
     >I en kampanj kan du även välja **[!UICONTROL Code Editor]** från **[!UICONTROL Edit content]** skärm. [Läs mer](create-email.md#define-email-content)

   * **Importera befintligt HTML-innehåll** från en fil eller en ZIP-mapp. Lär dig hur du importerar ett e-postinnehåll i [det här avsnittet](existing-content.md).

   * **Välj ett befintligt innehåll** från en lista med inbyggda eller anpassade mallar. Lär dig hur du arbetar med e-postmallar [det här avsnittet](../email/use-email-templates.md).

   ![](assets/email_designer_create_options.png)

1. När e-postinnehållet har definierats och anpassats kan du exportera innehållet för validering eller för senare bruk. Klicka **[!UICONTROL Export HTML]** om du vill spara en ZIP-fil på datorn som innehåller HTML och resurser.

   ![](assets/email_designer_export.png)

## Instruktionsvideor {#video}

Lär dig skapa e-postinnehåll med meddelanderedigeraren.

>[!VIDEO](https://video.tv.adobe.com/v/334150?quality=12)

Lär dig hur du konfigurerar innehållsexperiment till A/B-tester och utforskar e-postinnehåll på bästa sätt för dina affärsmål.

>[!VIDEO](https://video.tv.adobe.com/v/3419893)
