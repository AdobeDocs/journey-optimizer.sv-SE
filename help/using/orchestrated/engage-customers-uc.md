---
solution: Journey Optimizer
product: journey optimizer
title: Engagera kunderna genom att surfa
description: Engagera kunderna genom att surfa
feature: Use Cases
version: Campaign Orchestration
source-git-commit: 619db0a371b96fbe9480300a874839b7b919268d
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Engagera kunderna genom att surfa {#engage-customers-uc}

>[!BEGINSHADEBOX]

Observera att det här användningsexemplet börjar med en publik som redan finns i Experience Platform, närmare bestämt en webbpublik i realtid som samlar in webbläsaraktiviteter när de inträffar. [Läs mer i Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/rtcdp/intro/rtcdp-intro/get-started#audiences)

**Scheman som behövs för det här användningsfallet:**

* **Mottagare**: används som måldimension, med fält: `email`, `churnprop`
* **Önsklista**: med fält: `description`, `priceref`, `imageurl`

➡️ [Lär dig konfigurera modellbaserade scheman](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-interest-14.png){zoomable="yes"}

Den här kampanjen riktar sig till kunder som har gått igenom övningsutrustningskategorin. Publiken är deduplicerad och segmenterad av bortfallsrisk, vilket är sannolikheten att någon slutar engagera eller köpa.

Högriskkunder samlas in i en separat ny målgrupp som senare kommer att användas för en viss kommunikation, medan kunder med låg- och medelrisknivå går igenom en flerstegsresa med personaliserade e-postmeddelanden och uppföljningar.

1. Börja med att konfigurera en ny kampanj som är särskilt inriktad på **Önsklisteåterengagemang**. Detta garanterar att ert budskap fokuserar på kunder som redan har visat sig vilja köpa genom att spara produkter i deras önskelista.

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. Fyll i **[!UICONTROL Campaign Settings]**, t.ex. kampanjnamn, beskrivning, start- och slutdatum och relevanta taggar.

1. Lägg till en **[!UICONTROL Read audience]**-aktivitet för att välja en fördefinierad målgrupp från Adobe Experience Platform, här kunder som har bläddrat i övningsutrustningskategorin på din webbplats.

   Mottagarna identifieras med sina e-postadresser markerade i fältet **[!UICONTROL Entity]**.

   ![](assets/uc-interest-1.png){zoomable="yes"}

1. Lägg till en **[!UICONTROL Deduplication]**-aktivitet för att ta bort dubblettadresser från din målgrupp och se till att varje kund bara får ett meddelande.

1. Klicka på **[!UICONTROL Add attribute]** och välj e-post som attribut för borttagning av dubbletter.

   ![](assets/uc-interest-2.png){zoomable="yes"}

1. Därefter lägger du till en **[!UICONTROL Split]**-aktivitet för att segmentera kunder genom deras sannolikhet för bortfall, så att du kan leverera personaliserade upplevelser som är skräddarsydda för varje kundgrupp.

   ![](assets/uc-interest-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Add segment]** om du vill skapa tre grupper:

   * Låg risk

   * Medium risk

   * Hög risk

   ![](assets/uc-interest-5.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Create filter]** för att definiera sannolikhet för förändring för varje grupp.

   Använd **villkorsredigeraren** för att ange specifika värden som bestämmer varje kunds bortfallsrisk.

   ![](assets/uc-interest-6.png){zoomable="yes"}

1. Varje segment hanteras på olika sätt:

   * [Låg/medelhög risk](#low-medium-risk)
   * [Hög risk](#high-risk)

1. När kampanjen är testad och klar klickar du på **[!UICONTROL Publish]** för att göra den offentlig.

När kampanjen är klar kan du utforska kontrollpanelen för rapporter och granska resultatvärden och viktiga insikter.

➡️ [Läs mer om rapportering](../reports/campaign-global-report-cja.md)

## Högrisksegment {#high-risk}

Skapa ett dedikerat målgruppssegment för kunder som identifieras som kunder med stor risk för bortfall. Den här målgruppen används senare för separat, riktad kommunikation.

1. Lägg till en **[!UICONTROL Save Audience]**.

   ![](assets/uc-interest-7.png){zoomable="yes"}

1. Lägg till en **[!UICONTROL Label]** till din målgrupp och välj **[!UICONTROL Profile mapping field]** här **mottagare-e-post**.

   ![](assets/uc-interest-8.png){zoomable="yes"}

Den här målgruppen sparas sedan i Experience Cloud, där den senare kan användas för en specifik riktad kampanj.

## Låg/medelrisksegment {#low-medium-risk}

För kunder med låg och medelstor risk för bortfall ska ni skapa en flerstegskampanj som syftar till att stärka engagemanget:

1. Kombinera både låg- och Medium-risker med en **[!UICONTROL Union]**-aktivitet.

   ![](assets/uc-interest-9.png){zoomable="yes"}

1. Lägg till en **[!UICONTROL Enrichment]**-aktivitet för att anpassa kampanjen med önskelista och produktinformation.

1. Klicka på **[!UICONTROL Add attribute]** om du vill skapa följande tre attribut:

   * `Wishlist > description`
   * `Wishlist > priceref`
   * `Wishlist > imageurl`

   Detta berikar meddelandet med detaljerad önskelisteinformation.

   ![](assets/uc-interest-10.png){zoomable="yes"}

1. Skapa en ny målgrupp för återmarknadsföring baserat på engagemang med e-post.

   Här skapar vi en målgrupp baserat på klickningshändelser för e-post, för att omdirigera alla personer som interagerade med ett tidigare skickat e-postmeddelande, och mer specifikt klickade på en länk i meddelandet.

   ![](assets/uc-interest-11.png){zoomable="yes"}

1. Dela engagemanget jämnt för att skicka en uppföljning via SMS eller push-meddelanden för att uppmuntra konverteringar.

   ![](assets/uc-interest-12.png){zoomable="yes"}

1. Skapa meddelandeinnehåll för varje kanal, inklusive profilattribut, t.ex. mottagarens namn, tillsammans med anrikningsdata, t.ex. önskelisteobjekt, för att anpassa varje meddelande.

   ![](assets/uc-interest-13.png){zoomable="yes"}
