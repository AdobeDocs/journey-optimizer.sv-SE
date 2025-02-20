---
solution: Journey Optimizer
product: journey optimizer
title: Hantera varumärke
description: Lär dig skapa och hantera riktlinjer för ert varumärke
badge: label="Beta" type="Informative"
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 6c99d733b973efd790f8727bf867fbf0a952f6d9
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Skapa och hantera varumärken {#brands}

>[!AVAILABILITY]
>
>Den här funktionen är en privat betaversion. Den kommer att finnas tillgänglig successivt för alla kunder i framtida versioner.

Varumärkesriktlinjerna är en detaljerad uppsättning regler och standarder som bygger upp ett varumärkes visuella och verbala identitet. De fungerar som referenser för att upprätthålla en enhetlig varumärkesrepresentation på alla marknadsförings- och kommunikationsplattformar.

<!--Upload feature currently behind feature flag--

In [!DNL Journey Optimizer], you now have the option to manually input and organize your brand details or upload brand guideline documents for automatic information extraction.-->

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

Följ stegen nedan om du vill skapa och hantera riktlinjer för ditt varumärke.

<!--Upload feature currently behind feature flag--

To create and manage your Brand guideline, you can either enter the details yourself, or upload your brand guidelines document to have the information extracted automatically:-->

1. Klicka på **[!UICONTROL Create brand]** på menyn **[!UICONTROL Brands]**.

   ![](assets/brands-1.png)

1. Ange en **[!UICONTROL Name]** för ditt varumärke <!--and a **[!UICONTROL Description]** to your brand guideline-->.

   ![](assets/brands-2-temp.png)

<!--Upload feature currently behind feature flag so hidden from doc - should be available again by EOM (Feb)--

1. Drag and drop or select your file to upload your brand guidelines and extract automatically relevant brand information. Click **[!UICONTROL Create brand]**.

    The information extraction process now begins. Note that it may take several minutes to complete.

    ![](assets/brands-2.png)

1. Your Content and visual creation standards are now automatically populated. Browse through the different tabs to adapt the information as needed.

-->

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) på fliken **[!UICONTROL Writing Style]** om du vill lägga till en stödlinje eller ett undantag, inklusive exempel.

   ![](assets/brands-3.png)

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) på fliken **[!UICONTROL Visual content]** om du vill lägga till ytterligare en stödlinje eller ett undantag.

1. Om du vill lägga till en bild som visar korrekt användning väljer du **[!UICONTROL Example]** och klickar på **[!UICONTROL Select image]**. Du kan också lägga till en bild som visar felaktig användning som ett exkluderingsexempel.

   ![](assets/brands-4.png)

1. När konfigurationen är klar klickar du på **[!UICONTROL Save]** och sedan på **[!UICONTROL Publish]** för att göra din varumärkesriktlinje tillgänglig i AI-assistenten.

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

Riktlinjerna för ditt varumärke är nu tillgängliga från listrutan **[!UICONTROL Brand]** i AI-assistentmenyn, vilket gör att det kan generera innehåll och resurser som är anpassade till dina specifikationer. [Läs mer om AI-assistenten](gs-generative.md)

![](assets/brands-7.png)
