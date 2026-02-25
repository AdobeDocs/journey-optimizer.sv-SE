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
source-git-commit: 97fa287d94efb7fb95817fc15268e736517cb629
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 1%

---

# Skapa flerspråkigt innehåll med manuell översättning {#multilingual-manual}

>[!IMPORTANT]
>
>För manuellt flöde måste användare beviljas behörigheten **[!UICONTROL Manage Language settings]**.

Med det manuella flödet kan ni enkelt översätta ert innehåll direkt i era kampanjer och resor, vilket ger er precis kontroll och anpassningsbara alternativ för flerspråkiga meddelanden. Dessutom kan du enkelt importera redan befintligt flerspråkigt innehåll med alternativet Importera HTML.

Följ de här stegen för att skapa flerspråkigt innehåll med hjälp av manuell översättning:

1. [Lägg till din leverantör (valfritt)](multilingual-provider.md)

1. [Lägg till nationella inställningar (valfritt)](multilingual-locale.md)

1. [Skapa språkinställningar](#language-settings)

1. [Skapa flerspråkigt innehåll](#create-multilingual-campaign)

## Skapa språkinställningar {#language-settings}

I det här avsnittet kan du ange olika språkområden för hantering av ditt flerspråkiga innehåll. Du kan också välja det attribut som du vill använda för att söka efter information om profilspråket

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channel]** på menyn **[!UICONTROL General settings]**.

1. Klicka på **[!UICONTROL Language settings]** på menyn **[!UICONTROL Create language settings]**.

   ![](assets/language_settings_1.png)

1. Ange namnet på din **[!UICONTROL Language settings]** och välj **[!UICONTROL Manual Translation]**.

1. Välj **[!UICONTROL Locales]** som är associerad med de här inställningarna. Du kan lägga till högst 50 språkområden.

   Om **[!UICONTROL Locale]** saknas kan du skapa den manuellt på menyn **[!UICONTROL Translation]** eller via API. Se [Skapa en ny språkinställning](multilingual-locale.md).

   ![](assets/multilingual-settings-2.png)

1. Välj en **[!UICONTROL Fallback preferences]** som du vill definiera ett säkerhetskopieringsalternativ för när en profil inte uppfyller de nödvändiga villkoren för innehållsleverans.

   Observera att kampanjen eller resan inte skickas om inget reservalternativ väljs.

1. Välj sändningsinställning bland följande alternativ:

   * **[!UICONTROL Select profile language preference attributes]**
   * **[!UICONTROL Create custom conditional rules]**

1. Om du väljer **[!UICONTROL Select profile language preference attributes]** väljer du det relevanta attributet på menyn **[!UICONTROL Profile language preference attributes]** för att söka efter profilspråksinformation.

   ![](assets/multilingual-settings-3.png)

1. Om du väljer **[!UICONTROL Create custom conditional rules]** väljer du den språkinställning som du vill skapa villkor för. Bygg sedan regler baserat på faktorer som användarplats, språkinställningar eller andra sammanhangsberoende element.

   ![](assets/multilingual-settings-4.png)

1. Börja skapa villkor genom att lägga till ett attribut, en händelse eller en målgrupp för att definiera målgruppen.

   >[!IMPORTANT]
   >
   >Sammanhangsbaserade data är tillgängliga exklusivt för kanalerna Web, In-App, Code-based Experience och Content Card. Om den används för e-post, SMS, push-meddelanden eller direktreklam, utan ytterligare attribut, skickas kampanjen eller resan på det språk som används för det första alternativet i listan.

   ![](assets/multilingual-settings-6.png)

   +++Förutsättningar för att använda sammanhangsberoende händelser i dina förhållanden

   När användarna visar ditt innehåll skickas en personaliseringsbegäran tillsammans med upplevelsehändelsen. Om du vill utnyttja sammanhangsbaserade data i dina villkor måste du bifoga ytterligare data till nyttolasten för personaliseringsbegäran. För att göra detta måste du skapa en regel i Adobe Experience Platform Data Collection som anger: Om en personaliseringsbegäran skickas, bifogar SEDAN extra data till begäran och definierar vilket attribut som ska matcha språkfältet i ditt schema.

   >[!NOTE]
   >
   >Dessa krav är endast obligatoriska för kanalerna In-App och Content Card.

   1. Gå till menyn **[!UICONTROL Rules]** i Adobe Experience Platform Data Collection och skapa en ny regel. Detaljerad information om hur du skapar regler finns i [!DNL Adobe Experience Platform] [dokumentationen för datainsamling](https://experienceleague.adobe.com/en/docs/experience-platform/collection/e2e#create-a-rule){target="_blank"}

   2. Lägg till en händelse som konfigurerats enligt nedan i regelns **[!UICONTROL IF]**-avsnitt:

      ![](assets/multilingual-experience-events-rule-if.png)

      * Välj den **[!UICONTROL Extension]** du arbetar med.
      * I fältet **[!UICONTROL Event type]** väljer du&quot;AEP Request Event&quot;.
      * Välj &quot;XDM Event Type equals personalization.request&quot; i den högra rutan
      * Bekräfta genom att klicka på knappen **[!UICONTROL Keep changes]**.

   3. Lägg till en åtgärd som konfigurerats enligt nedan i regelns **[!UICONTROL THEN]**-avsnitt:

      ![](assets/multilingual-experience-events-rule-then.png)

      * Välj den **[!UICONTROL Extension]** du arbetar med.
      * Välj Bifoga data i fältet **[!UICONTROL Action Type]**.
      * I avsnittet JSON-nyttolast kontrollerar du att attributet som används för att hämta språket som ska användas (i exemplet nedan &quot;språk&quot;) matchar namnet på attributet som anges i schemat där datainsamlingsdataströmmen flödar in.

        ```JSON
        {
            "xdm":{
                "application":{
                    "_dc":{
                        "language":"{%%Language%%}"
                    }
                }
            }
        }
        ```

      * Klicka på knappen **[!UICONTROL Keep changes]** för att bekräfta och spara regeln.

   +++

1. Dra och släpp språkinställningarna för att ordna om dem och hantera deras prioritet i listan.

1. Om du vill ta bort en språkinställning klickar du på behållarikonen.

   ![](assets/multilingual-settings-5.png)

1. Klicka på **[!UICONTROL Submit]** för att skapa din **[!UICONTROL Language settings]**.

Observera att när du har konfigurerat språkinställningarna kan du inte längre redigera dem.

<!--
1. Access the **[!UICONTROL channel configurations]** menu and create a new channel configuration or select an existing one.


1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.

1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## Skapa flerspråkigt innehåll {#create-multilingual-campaign}

När du har konfigurerat ditt flerspråkiga innehåll är du redo att skapa en kampanj eller resa och anpassa innehållet för alla valda språkområden.

1. Börja med att skapa och konfigurera e-post, SMS eller push-meddelanden [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journey-action.md) enligt dina krav.

   >[!IMPORTANT]
   >
   >Vi rekommenderar att du endast inkluderar ett översättningsprojekt per resa.

1. Skapa eller importera ditt ursprungliga innehåll och anpassa det efter behov.

1. När innehållet har skapats klickar du på **[!UICONTROL Save]** och går tillbaka till konfigurationsskärmen för kampanjen.

   ![](assets/multilingual-campaign-2.png)

1. Klicka på **[!UICONTROL Add languages]** och markera **[!UICONTROL Language settings]** som du skapat tidigare. [Läs mer](#language-settings)

   ![](assets/multilingual-campaign-3.png)

1. Välj önskad språkinställning på den nedrullningsbara menyn som du vill använda för det befintliga redigerade innehållet.

1. Gå till de avancerade inställningarna på menyn **[!UICONTROL Locales]** och välj **[!UICONTROL Copy to all locales]**.

   ![](assets/multilingual-campaign-4.png)

1. Nu när ditt innehåll är duplicerat i hela den valda **[!UICONTROL Locales]** kan du komma åt varje språkinställning och klicka på **[!UICONTROL Edit email body]** för att översätta ditt innehåll.

   ![](assets/multilingual-campaign-5.png)

1. Du kan välja att inaktivera eller aktivera språkinställningar med menyn **[!UICONTROL More action]** för den valda språkinställningen.

   ![](assets/multilingual-campaign-6.png)

1. Om du vill inaktivera den flerspråkiga konfigurationen klickar du på **[!UICONTROL Add languages]** och väljer det språk som du vill behålla som lokalt språk.

   ![](assets/multilingual-campaign-7.png)

1. Klicka på **[!UICONTROL Review to activate]** om du vill visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

1. Bläddra igenom det flerspråkiga innehållet för att se återgivningen på varje språk.

   ![](assets/multilingual-campaign-8.png)

Nu kan ni aktivera kampanjen eller resan. När ni har skickat dem kan ni mäta effekten av er flerspråkiga resa eller kampanj i rapporter.

>[!IMPORTANT]
>
> Om din kampanj omfattas av en policy för godkännande måste du begära godkännande för att kunna skicka din flerspråkiga kampanj eller resa. [Läs mer](../test-approve/gs-approval.md)

<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.

-->
