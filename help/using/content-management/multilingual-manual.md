---
solution: Journey Optimizer
product: journey optimizer
title: Skapa flerspråkigt innehåll med manuell översättning
description: Lär dig skapa flerspråkigt innehåll med manuell översättning i Journey Optimizer
feature: Multilingual Content
topic: Content Management
role: User
level: Beginner
keywords: komma igång, börja, innehåll, experimentera
exl-id: 6244d717-fbd6-468e-9164-60451d0d62f0
badge: label="Begränsad tillgänglighet" type="Informative"
source-git-commit: 59dee15d2952438a074db57a94b3d896b38cd4f3
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 1%

---

# Skapa flerspråkigt innehåll med manuell översättning {#multilingual-manual}

>[!AVAILABILITY]
>
>Flerspråkigt innehåll är för närvarande endast tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

Med det manuella flödet kan ni enkelt översätta ert innehåll direkt i kampanjen och resan för e-post, push-meddelanden eller SMS, vilket ger er precis kontroll och anpassningsbara alternativ för flerspråkiga meddelanden. Dessutom kan du enkelt importera redan befintligt flerspråkigt innehåll med alternativet Importera HTML.

Följ de här stegen för att skapa flerspråkigt innehåll med hjälp av manuell översättning:

1. [Skapa din språkinställning](#create-locale).

1. [Skapa språkinställningar](#create-language-settings).

1. [Skapa flerspråkigt innehåll](#create-a-multilingual-campaign).

## Skapa nationella inställningar {#create-locale}

När du konfigurerar språkinställningarna enligt beskrivningen i [Skapa språkinställningar](#language-settings) om det inte finns någon specifik språkinställning för ditt flerspråkiga innehåll kan du skapa så många nya språkinställningar som behövs med **[!UICONTROL Translation]** -menyn.

1. Från **[!UICONTROL Content management]** meny, åtkomst **[!UICONTROL Translation]**.

1. Klicka på **[!UICONTROL Add locale]** på fliken **[!UICONTROL Locale dictionary]**.

   ![](assets/locale_1.png)

1. Välj din språkinställningskod på menyn **[!UICONTROL Language]** lista och associerade **[!UICONTROL Region]**.

1. Klicka **[!UICONTROL Save]** för att skapa din språkinställning.

   ![](assets/locale_2.png)

## Skapa språkinställningar {#language-settings}

I det här avsnittet kan du ange ditt primära språk och tillhörande språk för hantering av ditt flerspråkiga innehåll. Du kan också välja det attribut som du vill använda för att söka efter information om profilspråket

1. Från **[!UICONTROL Administration]** meny, åtkomst **[!UICONTROL Channel]**.

1. I **[!UICONTROL Language settings]** meny, klicka **[!UICONTROL Create language settings]**.

   ![](assets/multilingual-settings-1.png)

1. Ange ditt namn **[!UICONTROL Language settings]**.

1. Välj **[!UICONTROL Locales]** som är kopplade till dessa inställningar. Du kan lägga till högst 50 språkområden.

   Om en **[!UICONTROL Locale]** saknas kan du skapa den manuellt i förväg från **[!UICONTROL Translation]** eller av API. Se [Skapa en ny språkinställning](#create-locale).

   ![](assets/multilingual-settings-2.png)

1. Från **[!UICONTROL Sending preference]** väljer du det attribut du vill söka efter för att hitta information om profilspråk.

   ![](assets/multilingual-settings-3.png)

1. Klicka **[!UICONTROL Edit]** bredvid **[!UICONTROL Locale]** för att ytterligare personalisera den och lägga till **[!UICONTROL Profile preferences]**.

   ![](assets/multilingual-settings-4.png)

1. Välj andra **[!UICONTROL Locales]** från listrutan Profilinställningar och klicka på **[!UICONTROL Add profiles]**.

1. Gå till den avancerade menyn i **[!UICONTROL Locale]** för att definiera **[!UICONTROL Primary locale]**, dvs. standardspråket om profilattributet inte anges.

   Du kan även ta bort språkområdet från den här avancerade menyn.

   ![](assets/multilingual-settings-5.png)

1. Klicka **[!UICONTROL Submit]** för att skapa **[!UICONTROL Language settings]**.

<!--
1. Access the **[!UICONTROL Channel surfaces]** menu and create a new channel surface or select an existing one.


1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.

1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## Skapa flerspråkigt innehåll {#create-multilingual-campaign}

När du har konfigurerat ditt flerspråkiga innehåll är du redo att skapa en kampanj eller resa och anpassa innehållet för alla valda språkområden.

1. Börja med att skapa och konfigurera e-post, SMS eller push-meddelanden [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journeys-message.md) enligt dina krav.

   >[!AVAILABILITY]
   >
   >Vi rekommenderar att du endast inkluderar ett översättningsprojekt per resa.

1. Skapa eller importera ditt ursprungliga innehåll och anpassa det efter behov.

1. När det primära innehållet har skapats klickar du på **[!UICONTROL Save]** och gå tillbaka till kampanjkonfigurationsskärmen.

   ![](assets/multilingual-campaign-2.png)

1. Klicka **[!UICONTROL Add languages]** och markera dina tidigare skapade **[!UICONTROL Language settings]**. [Läs mer](#create-language-settings)

   ![](assets/multilingual-campaign-3.png)

1. Få åtkomst till de avancerade inställningarna i **[!UICONTROL Locales]** meny och välj **[!UICONTROL Copy primary to all locales]**.

   ![](assets/multilingual-campaign-4.png)

1. Nu när det primära innehållet dupliceras i hela det markerade  **[!UICONTROL Locales]**, komma åt de olika språkinställningarna och klicka **[!UICONTROL Edit email body]** att översätta innehållet.

   ![](assets/multilingual-campaign-5.png)

1. Du kan välja att inaktivera eller aktivera språkområden med **[!UICONTROL More action]** menyn för det valda språkområdet.

   ![](assets/multilingual-campaign-6.png)

1. Om du vill inaktivera flerspråkig konfiguration klickar du på **[!UICONTROL Add languages]** och välj det språk du vill behålla som lokalt språk.

   ![](assets/multilingual-campaign-7.png)

1. Klicka **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

1. Bläddra igenom det flerspråkiga innehållet för att se återgivningen på varje språk.

   ![](assets/multilingual-campaign-8.png)

Nu kan ni aktivera kampanjen eller resan. När ni har skickat dem kan ni mäta effekten av er flerspråkiga resa eller kampanj i rapporter.

<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.

-->
