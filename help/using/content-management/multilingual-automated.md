---
solution: Journey Optimizer
product: journey optimizer
title: Skapa flerspråkigt innehåll med automatiserad översättning
description: Läs mer om flerspråkigt innehåll i Journey Optimizer
feature: Multilingual Content
topic: Content Management
role: User
level: Beginner
keywords: komma igång, börja, innehåll, experimentera
exl-id: 38e82eb2-67d9-4a7d-8c1f-77dab20bcec4
badge: label="Begränsad tillgänglighet" type="Informative"
source-git-commit: a190b5547c2d8e13563391bd9d784add75c55fd4
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 1%

---

# Skapa flerspråkigt innehåll med automatiserad översättning {#multilingual-automated}

>[!CONTEXTUALHELP]
>id="ajo_multi_add_provider"
>title="Lägg till provider"
>abstract="Lägg till översättningsleverantörer och språkområden efter behov. På så sätt kan ni hantera vilka leverantörer och språkområden som är aktiva i projektet, vilket ger er flexibilitet att justera resurser och inrikta er på målgrupper baserat på era aktuella krav och projektomfattning."

>[!CONTEXTUALHELP]
>id="ajo_multi_edit_provider"
>title="Redigera provider"
>abstract="Ändra befintliga översättningsleverantörer och lägg till språkområden efter behov. Med den här funktionen kan du styra vilka leverantörer och språkområden som är aktiva i ditt projekt, vilket ger dig flexibilitet att justera resurser och inrikta dig på specifika målgrupper utifrån dina aktuella behov och projektmål."

>[!AVAILABILITY]
>
>Flerspråkigt innehåll är för närvarande endast tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

Med hjälp av det automatiserade flödet kan du helt enkelt välja målspråk och språkleverantör. Ditt innehåll skickas sedan direkt till översättningen, klart för slutgranskning när det är klart.

Följ de här stegen för att skapa flerspråkigt innehåll med hjälp av automatiserad översättning:

1. [Skapa din språkinställning](#create-locale).

1. [Skapa ett språkprojekt](#create-translation-project).

1. [Skapa språkinställningar](#create-language-settings).

1. [Skapa ett flerspråkigt innehåll](#create-a-multilingual-campaign).

1. [Granska översättningsaktiviteten (valfritt)](#review-translation-project).

## Skapa nationella inställningar {#create-locale}

>[!CONTEXTUALHELP]
>id="ajo_multi_add_locale"
>title="Lägg till nationella inställningar"
>abstract="När du konfigurerar språkinställningarna kan du skapa ytterligare språkområden om det önskade inte är tillgängligt för ditt flerspråkiga innehåll."

När du konfigurerar språkinställningarna, enligt beskrivningen i avsnittet [Skapa språkinställningar](#language-settings) , kan du skapa så många nya språkinställningar som behövs på menyn **[!UICONTROL Translation]** om det inte finns någon tillgänglig språkinställning för det flerspråkiga innehållet.

1. Gå till **[!UICONTROL Translation]** på menyn **[!UICONTROL Content management]**.

1. Klicka på **[!UICONTROL Add locale]** på fliken **[!UICONTROL Locale dictionary]**.

   ![](assets/locale_1.png)

1. Välj din språkkod i listan **[!UICONTROL Language]** och tillhörande **[!UICONTROL Region]**.

1. Klicka på **[!UICONTROL Save]** för att skapa din språkinställning.

   ![](assets/locale_2.png)

## Skapa översättningsprojekt {#translation-project}

>[!CONTEXTUALHELP]
>id="ajo_multi_create_project"
>title="Skapa projekt"
>abstract="Om du vill börja skapa flerspråkigt innehåll börjar du med att identifiera målspråkinställningen och väljer språk eller regional dialekt för målgruppen. Därefter väljer du en översättningsleverantör som passar ditt projekts behov."

>[!CONTEXTUALHELP]
>id="ajo_multi_edit_project"
>title="Redigera projekt"
>abstract="Uppdatera översättningsprojektet så att det innehåller fler språkområden, så att innehållet kan nå en större publik."

Starta översättningsprojektet genom att ange språkområdet som mål, vilket anger det specifika språket eller den specifika regionen för innehållet. Du kan sedan välja översättningsleverantör.

1. Klicka på **[!UICONTROL Create project]** på fliken **[!UICONTROL Projects]** på menyn **[!UICONTROL Translation]** under **[!UICONTROL Content management]**.

   ![](assets/translation_project_1.png)

1. Ange ett **[!UICONTROL Name]** och **[!UICONTROL Description]**.

1. Markera **[!UICONTROL Source locale]**.

   ![](assets/translation_project_2.png)

1. Välj om du vill aktivera följande alternativ:

   * **[!UICONTROL Automatically publish approved translations]**: När översättningar har godkänts integreras de automatiskt i kampanjen utan att något manuellt behöver göras.
   * **[!UICONTROL Enable Review workflow]**: Gäller endast för översatta språkinställningar. På så sätt kan en intern granskare effektivt utvärdera och antingen godkänna eller avvisa översatt innehåll. [Läs mer](#review-translation-project)

1. Klicka på **[!UICONTROL Add locale]** för att komma åt menyn och definiera språken för översättningsprojektet.

   Om **[!UICONTROL Locale]** saknas kan du skapa den manuellt på menyn **[!UICONTROL Translation]** eller via API. Se [Skapa en ny språkinställning](#create-locale).

   ![](assets/translation_project_3.png)

1. Välj i listan din **[!UICONTROL Target locale(s)]** och välj vilken **[!UICONTROL Translation provider]** du vill använda för varje språkinställning.

   **[!UICONTROL Translation provider]**-inställningar kan nås från menyn **[!UICONTROL Translation]** i menyavsnittet **[!UICONTROL Administration]**.

   >[!NOTE]
   >
   >Kontraktshantering med översättningsprovidern ligger utanför den här funktionens räckvidd. Kontrollera att du har ett giltigt och aktivt kontrakt med den utsedda översättningspartnern.
   >
   ></br>Översättningsprovidern äger det översatta innehållets kvalitet.

1. Klicka på **[!UICONTROL Add a locale]** när du har länkat målspråket till rätt översättningsleverantör. Klicka sedan på **[!UICONTROL Save]**.

   Observera, att om en provider är nedtonad för ett målland innebär det att providern inte stöder det aktuella språkområdet.

   ![](assets/translation_project_4.png)

1. Klicka på **[!UICONTROL Save]** när ditt översättningsprojekt har konfigurerats.

Ditt översättningsprojekt har skapats och kan användas i en flerspråkig kampanj.

## Skapa språkinställningar {#language-settings}

I det här avsnittet kan du ange ditt primära språk och tillhörande språk för hantering av ditt flerspråkiga innehåll. Du kan också välja det attribut som du vill använda för att söka efter information om profilspråket.

1. Gå till **[!UICONTROL Channel]** > **[!UICONTROL General settings]** på menyn **[!UICONTROL Administration]**.

1. Klicka på **[!UICONTROL Create language settings]** på menyn **[!UICONTROL Language settings]**.

   ![](assets/language_settings_1.png)

1. Ange namnet på din **[!UICONTROL Language settings]**.

1. Välj alternativet **[!UICONTROL Translation project]**.

1. Klicka på **[!UICONTROL Edit]** i fältet **[!UICONTROL Translation project]** och välj den **[!UICONTROL Translation project]** som du skapade tidigare.

   De tidigare konfigurerade språkinställningarna importeras automatiskt.

   ![](assets/language_settings_2.png)

1. På menyn **[!UICONTROL Sending preference]** väljer du det attribut du vill söka efter för att hitta information om profilspråk.

1. Klicka på **[!UICONTROL Edit]** bredvid din **[!UICONTROL Locale]** om du vill anpassa den ytterligare och lägga till **[!UICONTROL Profile preferences]**.

   ![](assets/language_settings_3.png)

1. Om **[!UICONTROL Translation project]** har uppdaterats klickar du på **[!UICONTROL Refresh]** för att spegla dessa ändringar i **[!UICONTROL Language settings]**.

   ![](assets/language_settings_4.png)

1. Klicka på **[!UICONTROL Submit]** för att skapa din **[!UICONTROL Language settings]**.

<!--
1. Access the **[!UICONTROL channel configurations]** menu and create a new channel configuration or select an existing one.

1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.


1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## Skapa flerspråkigt innehåll {#create-multilingual-campaign}

När du har konfigurerat översättningsprojektet och språkinställningarna är du redo att skapa en kampanj eller resa och anpassa innehållet för olika språkområden.

1. Börja med att skapa och konfigurera e-post, SMS eller push-meddelanden [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journeys-message.md) enligt dina krav.

1. När det primära innehållet har skapats klickar du på **[!UICONTROL Save]** och går tillbaka till kampanjkonfigurationsskärmen.

1. Klicka på **[!UICONTROL Add languages]**.  [Läs mer](#create-language-settings)

   ![](assets/multilingual-campaign-automated-1.png)

1. Välj den **[!UICONTROL Language settings]** som du skapade tidigare.

   ![](assets/multilingual-campaign-automated-2.png)

1. Nu när språkinställningarna har importerats klickar du på **[!UICONTROL Send to translate]** för att vidarebefordra innehållet till den tidigare valda översättningsleverantören.

   ![](assets/multilingual-campaign-automated-3.png)

1. När innehållet har skickats för översättning går det inte längre att redigera. Klicka på låsikonen om du vill ändra det ursprungliga innehållet.

   Observera att om du vill göra några ändringar i det här innehållet måste du skapa ett nytt översättningsprojekt och skicka om det för översättning.

   ![](assets/multilingual-campaign-automated-4.png)

1. Klicka på **[!UICONTROL Open translation]** för att komma åt översättningsprojektet och granska det.

   ![](assets/multilingual-campaign-automated-5.png)

1. På den här sidan följer du översättningsprojektets status:

   * **[!UICONTROL Translation in progress]**: Din tjänstleverantör arbetar aktivt med översättningen.

     Om du valde **Insourcing** när du konfigurerade dina **språkinställningar** kan du översätta ditt innehåll direkt i översättningsprojektet. [Läs mer](#manage-ht-project)

   * **[!UICONTROL Ready for review]**: Granskningsprocessen är klar att börja, vilket ger dig möjlighet att komma åt översättningen och antingen avvisa eller godkänna den.

     Om du har markerat **[!UICONTROL Enable review worflow]** i din **[!UICONTROL Translation project]** kan du granska översättningen direkt i Journey Optimizer när den har slutförts av den valda översättningsleverantören. [Läs mer](#review-translation-project)

   * **[!UICONTROL Reviewed]**: Översättningen har godkänts och kan skickas till kampanjen.

   * **[!UICONTROL Ready to publish]**: Maskinöversättning har slutförts och kan nu skickas till din kampanj.

   * **[!UICONTROL Completed]**: Översättning är nu tillgänglig i din kampanj.

   ![](assets/multilingual-campaign-automated-6.png)

1. När översättningen är klar kan det flerspråkiga innehållet skickas.

   ![](assets/translation_review_9.png)

1. Klicka på **[!UICONTROL Review to activate]** om du vill visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

1. Bläddra igenom det flerspråkiga innehållet för att se återgivningen på varje språk.

   ![](assets/multilingual-campaign-automated-7.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

Nu kan ni aktivera kampanjen eller resan. När ni har skickat dem kan ni mäta effekten av er flerspråkiga resa eller kampanj i rapporter.

## Hantera översättningsprojekt från Insourcing {#manage-ht-project}

>[!CONTEXTUALHELP]
>id="ajo_multi_insourcing_project"
>title="Översättningsprojekt läggs in"
>abstract="Genom att lägga in översättningsprojekt kan ni hantera och utföra översättningar direkt i översättningsprojektet, effektivisera processen och behålla större kontroll över översättningskvalitet och konsekvens."

Om du valde Insourcing när du konfigurerade språkinställningarna kan du översätta innehållet direkt i översättningsprojektet.

1. Gå till menyn **[!UICONTROL More actions]** från din **[!UICONTROL Translation project]** och välj **[!UICONTROL Insourcing]**.

   ![](assets/inhouse-translation-1.png)

1. Du kan exportera din CSV-fil för översättning med hjälp av ett externt översättningsprogram. Du kan också importera CSV-filen tillbaka till ditt översättningsprojekt genom att klicka på knappen **[!UICONTROL Import CSV]**.

   ![](assets/inhouse-translation-3.png)

1. Klicka på **[!UICONTROL Edit]** om du vill lägga till översättningsinnehållet.

   ![](assets/inhouse-translation-2.png)

1. Om du är redo att publicera den översatta texten klickar du på **[!UICONTROL Finalize]**.

## Granska ditt översättningsprojekt {#review-translation-project}

>[!CONTEXTUALHELP]
>id="ajo_multi_review_project"
>title="Granska ditt översättningsprojekt"
>abstract="När översättningsleverantören är klar med översättningen kan du granska resultatet direkt i Journey Optimizer. På så sätt kan du bedöma översättningens exakthet och kvalitet och säkerställa att den överensstämmer med dina förväntningar och projektkrav innan du slutför den."

>[!CONTEXTUALHELP]
>id="ajo_multi_preview_project"
>title="Förhandsgranska översättningsprojektet"
>abstract="I förhandsgranskningsfönstret kan du visa hur det översatta innehållet visas på varje språk. Med den här funktionen kan du granska återgivningen och se till att innehållet visas korrekt och effektivt på alla valda språk."

Om du har markerat **[!UICONTROL Enable review worflow]** i din **[!UICONTROL Translation project]** kan du granska översättningen direkt i Journey Optimizer när den har slutförts av den valda översättningsleverantören.

Observera att om det här alternativet är inaktiverat, när översättningen är klar av din leverantör, ställs översättningsaktivitetens status automatiskt in på **[!UICONTROL Reviewed]**, vilket gör att du snabbt kan fortsätta genom att klicka på **[!UICONTROL Publish]**.

1. När översättningen har slutförts från tjänsteleverantören kan du komma åt översättningen för granskning från **[!UICONTROL Translation project]** eller direkt från **[!UICONTROL Campaign]**.

   Klicka på **[!UICONTROL Review]** på menyn **[!UICONTROL More actions]**.

   ![](assets/translation_review_1.png)

1. I granskningsfönstret bläddrar du igenom det översatta innehållet och godkänner eller avvisar alla översättningssträngar.

   ![](assets/translation_review_3.png)

1. Klicka på **[!UICONTROL Edit]** om du vill ändra innehållet i översättningssträngen.

   ![](assets/translation_review_2.png)

1. Ange den uppdaterade översättningen och klicka på **[!UICONTROL Confirm]** när du är klar.

   ![](assets/translation_review_4.png)

1. Du kan också välja att **[!UICONTROL Reject all]** eller **[!UICONTROL Approve all]** direkt.

   När du väljer **[!UICONTROL Reject all]** lägger du till en kommentar och klickar på **[!UICONTROL Reject]**.

1. Klicka på **[!UICONTROL Preview]** för att kontrollera återgivningen av det översatta innehållet på varje språk.

1. Om du är redo att publicera den översatta texten klickar du på **[!UICONTROL Finalize]**.

   ![](assets/translation_review_5.png)

1. Välj ett av dina projekt i **[!UICONTROL Translation project]** om du vill ha mer information. Om du avvisade översättningen kan du välja att skicka tillbaka den till översättningen.

   ![](assets/translation_review_6.png)

1. När din **[!UICONTROL Translation project]**-status har angetts till Granskad kan du skicka den till din kampanj.

   Klicka på **[!UICONTROL Publish]** på menyn **[!UICONTROL More actions]**.

   ![](assets/translation_review_7.png)

1. Kontrollera att din översättningsstatus har ändrats till **[!UICONTROL Translation complete]** i din kampanj. Du kan nu skicka ditt flerspråkiga innehåll, se steg 10 i [det här avsnittet](#create-multilingual-campaign).

   ![](assets/translation_review_9.png)

<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.


-->
