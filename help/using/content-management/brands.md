---
solution: Journey Optimizer
product: journey optimizer
title: Hantera varumärke
description: Lär dig skapa och hantera riktlinjer för ert varumärke
badge: label="Beta" type="Informative"
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: b1b7abbe-8600-4a8d-b0b5-0dbd49abc275
source-git-commit: 9d87d133bb580ebed94a265beded5895f7fd0301
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 0%

---

# Skapa och hantera varumärken {#brands}

>[!CONTEXTUALHELP]
>id="ajo_brand_overview"
>title="Kom igång med varumärken"
>abstract="Skapa och anpassa egna varumärken för att definiera din unika visuella och verbala identitet samtidigt som det blir enklare att generera innehåll som matchar varumärkets stil och röst."

>[!CONTEXTUALHELP]
>id="ajo_brand_ai_menu"
>title="Välj ditt varumärke"
>abstract="Välj ert varumärke för att se till att allt AI-genererat innehåll är anpassat efter varumärkets specifikationer och riktlinjer."

>[!CONTEXTUALHELP]
>id="ajo_brand_score_overview"
>title="Märkesmarkering"
>abstract="Välj ert varumärke för att säkerställa att ert innehåll utformas i enlighet med dess specifika riktlinjer, standarder och identitet, samtidigt som ni upprätthåller enhetlighet och varumärkesintegritet."

>[!CONTEXTUALHELP]
>id="ajo_brand_score"
>title="Poäng för varumärkesjustering"
>abstract="Poängen för varumärkesanpassning mäter hur väl ert innehåll följer ert varumärkes riktlinjer och säkerställer enhetlighet vad gäller färger, teckensnitt, logotyp, bilder och stil."

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

>[!CONTEXTUALHELP]
>id="ajo_brand_imagery"
>title="Bildstreck"
>abstract="Bildstreck"

>[!CONTEXTUALHELP]
>id="ajo_brand_writing_style"
>title="Skriva formatpoäng"
>abstract="Skriva formatpoäng"

>[!AVAILABILITY]
>
>Den här funktionen är en privat betaversion. Den kommer att finnas tillgänglig successivt för alla kunder i framtida versioner.

Varumärkesriktlinjerna är en detaljerad uppsättning regler och standarder som bygger upp ett varumärkes visuella och verbala identitet. De fungerar som referenser för att upprätthålla en enhetlig varumärkesrepresentation på alla marknadsförings- och kommunikationsplattformar.

I [!DNL Journey Optimizer] har du nu möjlighet att ange och ordna din varumärkesinformation manuellt eller överföra varumärkesriktlinjer för automatisk informationshämtning.

## Få tillgång till varumärken {#generative-access}

För att få åtkomst till menyn **[!UICONTROL Brands]** i [!DNL Adobe Journey Optimizer] måste användarna beviljas behörigheterna **[!UICONTROL Managed brand kit]** eller **[!UICONTROL Enable AI assistant]**. [Läs mer](../administration/permissions.md)

+++  Lär dig hur du tilldelar varumärkesrelaterade behörigheter

1. Gå till fliken **Roller** i produkten **Behörigheter** och välj önskad **roll**.

1. Klicka på **Redigera** om du vill ändra behörigheterna.

1. Lägg till resursen **AI Assistant** och välj sedan **Hanterat varumärkespaket** eller **[!UICONTROL Enable Ai assistant]** i listrutan.

   Observera att behörigheten **[!UICONTROL Enable Ai assistant]** endast ger skrivskyddad åtkomst till menyn **[!UICONTROL Brands]**.

   ![](assets/brands-permission.png){zoomable="yes"}

1. Klicka på **Spara** om du vill använda ändringarna.

   Alla användare som redan har tilldelats den här rollen får sina behörigheter automatiskt uppdaterade.

1. Om du vill tilldela den här rollen till nya användare går du till fliken **Användare** på kontrollpanelen **Roller** och klickar på **Lägg till användare**.

1. Ange användarens namn, e-postadress eller välj i listan och klicka sedan på **Spara**.

1. Om användaren inte har skapats tidigare, se [den här dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/users).

+++

## Skapa ert varumärke {#create-brand-kit}

>[!CONTEXTUALHELP]
>id="ajo_brands_create"
>title="Skapa ert varumärke"
>abstract="Ange ditt varumärkesnamn och överför din varumärkesstödfil. Verktyget extraherar automatiskt nyckeldetaljer, vilket gör det enklare att behålla varumärkets identitet."

Om du vill skapa och hantera varumärkesriktlinjerna kan du antingen ange detaljerna själv eller överföra dokumentet med varumärkesriktlinjer så att informationen extraheras automatiskt:

1. Klicka på **[!UICONTROL Create brand]** på menyn **[!UICONTROL Brands]**.

   ![](assets/brands-1.png)

1. Ange en **[!UICONTROL Name]** för ditt varumärke.

1. Dra och släpp eller markera filen för att ladda upp varumärkesriktlinjerna och extrahera automatiskt relevant varumärkesinformation. Klicka på **[!UICONTROL Create brand]**.

   Processen för informationsextrahering börjar nu. Observera att det kan ta flera minuter att slutföra.

   ![](assets/brands-2.png)

1. Standarderna för att skapa innehåll och visuellt innehåll är nu automatiskt ifyllda. Bläddra bland de olika flikarna för att anpassa informationen efter behov.

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) på fliken **[!UICONTROL Writing Style]** om du vill lägga till en stödlinje eller ett undantag, inklusive exempel.

   ![](assets/brands-3.png)

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) på fliken **[!UICONTROL Visual content]** om du vill lägga till ytterligare en stödlinje eller ett undantag.

1. Om du vill lägga till en bild som visar korrekt användning väljer du **[!UICONTROL Example]** och klickar på **[!UICONTROL Select image]**. Du kan också lägga till en bild som visar felaktig användning som ett exkluderingsexempel.

   ![](assets/brands-4.png)

1. När konfigurationen är klar klickar du på **[!UICONTROL Save]** och sedan på **[!UICONTROL Publish]** för att göra din varumärkesriktlinje tillgänglig i AI Assistant.

1. Klicka på **[!UICONTROL Edit brand]** om du vill ändra det publicerade varumärket.

   >[!NOTE]
   >
   >Detta skapar en temporär kopia i redigeringsläge och ersätter den publicerade versionen.

   ![](assets/brands-8.png)

1. Öppna den avancerade menyn på din **[!UICONTROL Brands]**-kontrollpanel genom att klicka på ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) för att:

   * Visa varumärke
   * Redigera
   * Duplicera
   * Publicera
   * Avpublicera
   * Ta bort

   ![](assets/brands-6.png)

Riktlinjerna för ditt varumärke finns nu i listrutan **[!UICONTROL Brand]** i AI Assistant-menyn, vilket gör det möjligt att generera innehåll och resurser som är anpassade till dina specifikationer. [Läs mer om AI Assistant](gs-generative.md)

![](assets/brands-7.png)
