---
title: Märkesjustering
description: Lär dig hur du skapar, validerar och hanterar varumärkesinnehåll med hjälp av varumärkespoäng.
topic: Content Management, Artificial Intelligence
role: User
level: Beginner, Intermediate
exl-id: 01e74670-7431-4791-b98c-12278e6d3332
source-git-commit: 3f363a006ed25c07f3ea5b516f5fc306b230d029
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Märkesjustering {#brands-score}

>[!CONTEXTUALHELP]
>id="ajo_brand_score"
>title="Märkesjustering"
>abstract="Din poäng för varumärkesjustering mäter hur väl ert innehåll följer ert varumärkes riktlinjer och säkerställer enhetlighet vad gäller färger, teckensnitt, logotyp, bilder och stil."

>[!CONTEXTUALHELP]
>id="ajo_brand_colors"
>title="Färgskala"
>abstract="Färgskala"

>[!CONTEXTUALHELP]
>id="ajo_brand_fonts"
>title="Teckensnittsmusik"
>abstract="Teckensnittsmusik"

>[!CONTEXTUALHELP]
>id="ajo_brand_logos"
>title="Logos score"
>abstract="Logos score"

>[!AVAILABILITY]
>
>Du måste godkänna [användaravtalet](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} innan du kan använda AI-assistenten i Adobe Journey Optimizer. Kontakta din Adobe-representant om du vill veta mer.

Med funktionen för varumärkesjustering kan du skapa, granska och hantera innehåll som följer varumärkesriktlinjerna. Det garanterar enhetlighet i fråga om ton, meddelanden och visuell identitet i alla e-postkampanjer, samtidigt som det fungerar som en kvalitetskontroll innan innehållet publiceras.

## Validera ert innehåll med varumärkesanpassning {#validate-content}

När [ditt varumärke har konfigurerats och publicerats](brands.md) kan du bedöma varumärkesjusteringspoängen direkt i din e-postkampanj för att se till att innehållet följer varumärkesriktlinjerna:

1. Skapa din [e-postkampanj](../campaigns/create-campaign.md).

1. Öppna menyn **[!UICONTROL Brand Alignment]** i e-post-Designer.

   Ditt innehåll utvärderas automatiskt mot ditt standardvarumärke. [Lär dig hur du tilldelar ett standardmärke](brands.md).

   ![](assets/brand-score-1.png)

1. Om du vill utvärdera med ett annat varumärke väljer du det i listrutan **[!UICONTROL Brand]** och klickar på **[!UICONTROL Evaluate score]**.

   ![](assets/brand-score-2.png)

1. Bläddra igenom **[!UICONTROL Writing style]** eller **[!UICONTROL Visual content]** för att se fler insikter om ditt resultat.

   ![](assets/brand-score-3.png)

1. Klicka på ikonen ![Helskärmsläge om du vill ha mer information om resultatet.](assets/do-not-localize/Smock_FullScreen_18_N.svg "Helskärmsikonen").

   ![](assets/brand-score-5.png)

1. Välj en flaggad stödlinje om du vill visa specifik feedback och förslag. Justering av varumärke utvärderar följande kategorier:

   * **[!UICONTROL Writing style]**:
      * **[!UICONTROL Brand communication style]**: Definierar personligheten och den känslomässiga tonen för att säkerställa en enhetlig varumärkesröst i alla kanaler.
      * **[!UICONTROL Brand messaging standards]**: Strukturella regler och formateringsregler för effektiv marknadsföring och marknadsföringstext.
      * **[!UICONTROL Legal compliance standards]**: Ser till att all kommunikation uppfyller juridiska krav, inklusive textplacering och efterlevnadskontroller.

   * **[!UICONTROL Visual content]**:
      * **[!UICONTROL Photography standards]**: Krav för fotoinnehåll, inklusive upplösning, komposition, ljus och filformat.
      * **[!UICONTROL Illustration standards]**: Formatparametrar, linjebredd, färganvändning och filformatskrav för illustrationer.
      * **[!UICONTROL Icon standards]**: Specifikationer för ikondesign, inklusive rutnätssystem, linjebredder och storleksändring för enhetlighet.
      * **[!UICONTROL Usage guidelines]**: Bästa tillvägagångssätt för att välja bilder, placera och kontext för att behålla varumärkesidentiteten.



   ![](assets/brand-score-4.png)

1. Redigera ert innehåll baserat på rekommendationerna för att förbättra varumärkesanpassningen.

1. Utvärdera innehållet manuellt när du har gjort ändringar för att uppdatera justeringspoängen.

## Validera innehållskvaliteten {#validate-quality}

>[!NOTE]
>
>Utvärderingen av innehållskvaliteten är varumärkesagnostikbaserad. Även om ett varumärke väljs i listrutan tillämpas inte dess riktlinjer på kvalitetskontrollen. Varumärkesvalet är endast relevant för bedömning av varumärkesanpassning.

Förutom varumärkesanpassning kan ni utvärdera den allmänna innehållskvaliteten för att identifiera potentiella problem med läsbarhet, innehållets enhetlighet och effektivitet, oberoende av varumärkesriktlinjerna.

Så här utvärderar du innehållskvaliteten:

1. Skapa din [e-postkampanj](../campaigns/create-campaign.md).

1. Öppna menyn **[!UICONTROL Brand Alignment]** i e-post-Designer.

   ![](assets/brand-score-1.png)

1. Klicka på **[!UICONTROL Evaluate score]** om du vill generera både varumärkesjustering och innehållskvalitetspoäng.

   ![](assets/brand-score-2.png)

1. Gå till fliken **[!UICONTROL Overall quality]** om du vill granska dina innehållskvalitetsinsikter och rekommendationer.

   ![](assets/brand-score-6.png)

1. Klicka på ikonen ![Helskärm om du vill ha mer information om &#x200B;](assets/do-not-localize/Smock_FullScreen_18_N.svg "helskärmsläget") om du vill se din kvalitetspoäng.

   ![](assets/brand-score-7.png)

1. Markera ett flaggat objekt om du vill visa specifik feedback och förslag till åtgärder som kan förbättras. Poängen baseras på följande kategorier:

   * **[!UICONTROL CTA effectiveness]**: Utvärderar hur väl din call-to-action motiverar läsarna att vidta den önskade åtgärden.
   * **[!UICONTROL Subject Line]**: Utvärderar klarhet, relevans och kvalitet som får tittarna att tappa intresset för att uppmuntra e-postöppningar.
   * **[!UICONTROL Readability]**: Mäter hur enkelt och engagerande ditt innehåll är för läsarna att förstå.
   * **[!UICONTROL Spam Check]**: Identifierar vanliga skräppostutlösare som kan påverka leveransen.
   * **[!UICONTROL Content Cohesiveness]**: Ser till att ditt innehåll flyter smidigt och hålls kvar i ämnet.
   * **[!UICONTROL Proofreading]**: Kontrollerar stavning, grammatik och klarhetsproblem.

   ![](assets/brand-score-8.png)

1. Redigera innehållet baserat på rekommendationerna för att förbättra läsbarheten, innehållets enhetlighet och övergripande kvalitet.

1. Klicka på **[!UICONTROL Re-evaluate score]** när du har gjort ändringar för att uppdatera din kvalitetspoäng.

## Instruktionsvideo {#video}

I videon nedan visas hur du skapar och anpassar dina egna varumärken för att tydligt definiera din visuella och verbala identitet för olika typer av kommunikation.

+++ Se videon

>[!VIDEO](https://video.tv.adobe.com/v/3470550/?captions=swe&learn=on)

+++
