---
solution: Journey Optimizer
product: journey optimizer
title: Hantera varumärke
description: Lär dig skapa och hantera riktlinjer för ert varumärke
badge: label="Beta" type="Informative"
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 4919c8c749f9216be526bab2437a815da0136df5
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---

# Skapa och hantera varumärken {#brands}

>[!AVAILABILITY]
>
>Den här funktionen är en privat betaversion. Den kommer att finnas tillgänglig successivt för alla kunder i framtida versioner.
>

Varumärkesriktlinjerna är en detaljerad uppsättning regler och standarder som bygger upp ett varumärkes visuella och verbala identitet. De fungerar som referenser för att upprätthålla en enhetlig varumärkesrepresentation på alla marknadsförings- och kommunikationsplattformar.

I Journey Optimizer har du nu möjlighet att ange och ordna din varumärkesinformation manuellt eller ladda upp riktlinjer för varumärken för automatisk informationshämtning.

## Åtkomstvarumärken {#generative-access}

För att få åtkomst till varumärkesmenyn i Adobe Journey Optimizer måste användarna beviljas behörigheterna **Managed brand Kit** eller **[!UICONTROL Enable AI assistant]**. [Läs mer](../administration/permissions.md)

+++  Lär dig hur du tilldelar varumärkesrelaterade behörigheter

1. Gå till fliken **Roller** i produkten **Behörigheter** och välj önskad **roll**.

1. Klicka på **Redigera** om du vill ändra behörigheterna.

1. Lägg till resursen **AI Assistant** och välj sedan **Hanterat varumärkespaket** eller **[!UICONTROL Enable Ai assistant]** i listrutan.

   Observera att behörigheten **[!UICONTROL Enable Ai assistant]** endast ger skrivskyddad åtkomst till menyn Varumärke.

   ![](assets/brands-permission.png){zoomable="yes"}

1. Klicka på **Spara** om du vill använda ändringarna.

   Alla användare som redan har tilldelats den här rollen får sina behörigheter automatiskt uppdaterade.

1. Om du vill tilldela den här rollen till nya användare går du till fliken **Användare** på kontrollpanelen **Roller** och klickar på **Lägg till användare**.

1. Ange användarens namn, e-postadress eller välj i listan och klicka sedan på **Spara**.

1. Om användaren inte har skapats tidigare, se [den här dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/users).


+++

## Skapa ditt varumärke {#create-brand-kit}

Om du vill skapa och hantera din varumärkesriktlinje kan du antingen ange detaljerna själv eller överföra ditt varumärkesriktlinjer så att informationen extraheras automatiskt:

1. Klicka på **[!UICONTROL Add brand]** på menyn **[!UICONTROL Brands]**.

   ![](assets/brands-1.png)

1. Ange en **[!UICONTROL Name]** och en **[!UICONTROL Description]** i varumärkesriktlinjerna.

1. Dra och släpp eller markera filen för att ladda upp varumärkesriktlinjerna och extrahera automatiskt relevant varumärkesinformation. Klicka på **[!UICONTROL Add brand]**.

   Processen för informationsextrahering börjar nu. Observera att det kan ta flera minuter att slutföra.

   ![](assets/brands-2.png)

1. Standarderna för att skapa innehåll och visuellt innehåll är nu automatiskt ifyllda. Bläddra bland de olika flikarna för att anpassa informationen efter behov.

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) i **[!UICONTROL Content creation standards]** om du vill lägga till ytterligare en stödlinje, exempel eller undantag.

   ![](assets/brands-3.png)

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) i **[!UICONTROL Visual creation standards]** om du vill lägga till ytterligare en stödlinje, exempel eller undantag.

1. Klicka på **[!UICONTROL Select image]** om du vill lägga till ett bildexempel. Du kan också lägga till felaktiga insikter som identifieras.

   ![](assets/brands-4.png)

1. Klicka på **[!UICONTROL Save]** och sedan **[!UICONTROL Publish]** för att göra dina varumärkesriktlinjer tillgängliga i AI-assistenten.

1. Klicka på **[!UICONTROL Edit brand]** om du vill ändra det publicerade varumärket. Observera att detta skapar en temporär kopia i redigeringsläge och ersätter den publicerade versionen.

   ![](assets/brands-8.png)

1. Öppna den avancerade menyn på din **[!UICONTROL Brands]**-kontrollpanel genom att klicka på ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) för att:

   * Visa varumärke
   * Redigera
   * Duplicera
   * Publicera
   * Avpublicera
   * Ta bort

   ![](assets/brands-6.png)

Riktlinjerna för varumärken finns nu i listrutan Varumärken i AI-assistentmenyn, vilket gör att du kan generera innehåll och resurser som är anpassade efter dina specifikationer. [Läs mer om AI-assistenten](gs-generative.md)

![](assets/brands-7.png)
