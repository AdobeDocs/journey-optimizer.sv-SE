---
solution: Journey Optimizer
product: journey optimizer
title: Skapa innehållsmallar
description: Lär dig skapa mallar för återanvändning av innehåll i Journey Optimizer kampanjer och resor
feature: Templates
topic: Content Management
role: User
level: Beginner
exl-id: 327de13a-1c99-4d5e-86cf-8180fb7aaf23
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---

# Arbeta med innehållsmallar {#content-templates}

För en snabbare och förbättrad designprocess kan du skapa fristående mallar för att enkelt återanvända anpassat innehåll i [!DNL Journey Optimizer] kampanjer och resor.

Med den här funktionen kan innehållsorienterade användare arbeta med mallar utanför kampanjer eller resor. Marknadsförare kan sedan återanvända och anpassa dessa fristående innehållsmallar på sina egna resor eller i sina egna kampanjer.

<!--![](../rn/assets/do-not-localize/content-template.gif)-->

>[!NOTE]
>
>Innehållsmallar är för närvarande inte tillgängliga för webbkanalen.

En användare i företaget ansvarar t.ex. bara för innehållet och har därför inte tillgång till kampanjer eller resor. Den här användaren kan dock skapa en e-postmall som organisationens marknadsförare kan välja att använda i alla e-postmeddelanden som utgångspunkt.

Du kan också skapa och hantera innehållsmallar med API:er. Mer information finns i [Dokumentation för Journey Optimizer API:er](https://developer.adobe.com/journey-optimizer-apis/references/content/){target="_blank"}.

➡️ [Lär dig hur du skapar och använder mallar i den här videon](#video-templates)

>[!CAUTION]
>
>Om du vill skapa, redigera och ta bort innehållsmallar måste du ha **[!DNL Manage library items]** behörighet som ingår i **[!DNL Content Library Manager]** produktprofil. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)

## Få åtkomst till och hantera mallar {#access-manage-templates}

Om du vill komma åt innehållsmalllistan väljer du **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** från den vänstra menyn.

![](../email/assets/content-template-list.png)

Alla mallar som skapades i den aktuella sandlådan - antingen från en resa eller en kampanj med **[!UICONTROL Save as template]** alternativ, antingen från **[!UICONTROL Content Templates]** -menyn visas. [Lär dig hur du skapar mallar](#create-content-templates)

Du kan sortera innehållsmallar efter:
* Typ
* Kanal
* Skapad eller ändrad den
* Taggar - [Läs mer om taggar](../start/search-filter-categorize.md#tags)

Du kan också välja att bara visa de objekt som du själv har skapat eller ändrat.

![](assets/content-template-list-filters.png)

<!--Select the **[!UICONTROL Grid view]** mode to display each template as a thumbnail. 

>[!NOTE]
>
>Currently proper thumbnails can only be generated for HTML-type email content templates.

When you update a content, you may have to wait a few seconds before the changes are reflected in the thumbnail.

![](assets/content-template-grid-view.png)-->

* Om du vill redigera ett mallinnehåll klickar du på önskat objekt i listan och väljer **[!UICONTROL Edit content]**.

  ![](../email/assets/content-template-edit.png)

* Om du vill ta bort en mall väljer du **[!UICONTROL More actions]** intill önskad mall och välj **[!UICONTROL Delete]**.

  ![](assets/content-template-list-delete.png)

>[!NOTE]
>
>När en mall redigeras eller tas bort påverkas inte kampanjer eller resor inklusive innehåll som skapats med den här mallen.

## Skapa innehållsmallar {#create-content-templates}

>[!CONTEXTUALHELP]
>id="ajo_create_template"
>title="Definiera en egen innehållsmall"
>abstract="Skapa en egen mall från scratch för att göra innehållet återanvändbart på flera resor och i flera kampanjer."

Det finns två sätt att skapa innehållsmallar:

* Skapa en innehållsmall från grunden med den vänstra listen **[!UICONTROL Content Templates]** -menyn. [Lär dig mer](#create-template-from-scratch)

* Spara innehållet som en mall när du utformar innehållet i en kampanj eller resa. [Lär dig mer](#save-as-template)

När du har sparat din innehållsmall är den tillgänglig för användning i en kampanj eller på en resa. Oavsett om du har skapat från grunden eller från ett tidigare innehåll kan du nu använda den här mallen när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig mer](#use-content-templates)

>[!NOTE]
>
>* Ändringar som görs i innehållsmallar sprids inte till kampanjer eller resor, vare sig de är live eller utkast.
>
>* När mallar används i en kampanj eller en resa påverkas inte heller den tidigare använda innehållsmallen av ändringar som du gör i kampanj- och reseinnehåll.

### Skapa mall från grunden {#create-template-from-scratch}

Följ stegen nedan för att skapa en innehållsmall från grunden.

1. Få åtkomst till innehållsmalllistan via **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** vänster meny.

1. Välj **[!UICONTROL Create template]**.

1. Fyll i mallinformationen och välj önskad kanal.

   ![](assets/content-template-channels.png)

   >[!NOTE]
   >
   >För närvarande är alla kanaler tillgängliga utom webben.

1. Välj en **[!UICONTROL Type]** för den valda kanalen.

   ![](assets/content-template-type.png)

   * För **[!UICONTROL Email]** om du väljer **[!UICONTROL Content]** kan du definiera [Subject line](../email/create-email.md#define-email-content) som en del av din mall. Om du väljer **[!UICONTROL HTML]** kan du bara definiera innehållet i e-postbrödtexten.

   * För **[!UICONTROL SMS]**, **[!UICONTROL Push]**, **[!UICONTROL In-App]** och **[!UICONTROL Direct Mail]**&#x200B;är bara standardtypen tillgänglig för den aktuella kanalen. Du måste fortfarande markera den.

1. Markera eller skapa Adobe Experience Platform-taggar från **[!UICONTROL Tags]** fält för att kategorisera mallen för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till mallen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Klicka **[!UICONTROL Create]** och utforma innehållet efter behov, på samma sätt som du gör för allt innehåll i en resa eller kampanj - enligt den kanal du valt.

   ![](assets/content-template-edition.png)

   Lär dig hur du skapar innehåll för de olika kanalerna i följande avsnitt:
   * [Definiera e-postinnehåll](../email/get-started-email-design.md)
   * [Definiera push-innehåll](../push/design-push.md)
   * [Definiera SMS-innehåll](../sms/create-sms.md#sms-content)
   * [Definiera innehåll för direktreklam](../direct-mail/create-direct-mail.md)
   * [Definiera innehåll i appen](../in-app/design-in-app.md)

1. Om du skapar en **[!UICONTROL Email]** mall med **[!UICONTROL HTML]** kan du testa ditt innehåll. [Lär dig mer](#test-template)

1. När mallen är klar klickar du **[!UICONTROL Save]**.

1. Klicka på pilen bredvid mallnamnet för att gå tillbaka till **[!UICONTROL Details]** skärm.

   ![](assets/content-template-back.png)

Den här mallen kan nu användas när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig mer](#use-content-templates)

### Spara som mall {#save-as-template}

>[!CONTEXTUALHELP]
>id="ajo_messages_depecrated_inventory"
>title="Lär dig hur du migrerar meddelanden"
>abstract="Den 25 juli 2022 försvann menyn Meddelanden och meddelanden skrivs nu direkt från en resa. Om du vill återanvända dina gamla meddelanden under resor måste du spara dem som mallar."

När du utformar innehåll i en kampanj eller resa kan du spara det för framtida återanvändning. Följ stegen nedan för att göra detta.

1. Från meddelandet **[!UICONTROL Edit content]** klickar du på **[!UICONTROL Content template]** -knappen.

1. Välj **[!UICONTROL Save as content template]** i listrutan.

   ![](assets/content-template-button-save.png)

   Om du är i [E-postdesigner](../email/get-started-email-design.md)kan du också välja det här alternativet på **[!UICONTROL More]** nedrullningsbar lista längst upp till höger på skärmen.

   ![](assets/content-template-more-button-save.png)

1. Lägg till ett namn och en beskrivning för mallen.

   ![](assets/content-template-name.png)

   >[!NOTE]
   >
   >Den aktuella kanalen och typen fylls i automatiskt och kan inte redigeras. För e-postmallar som skapats från [E-postdesigner](../email/get-started-email-design.md), **[!UICONTROL HTML]** text väljs automatiskt.

1. Markera eller skapa en Adobe Experience Platform-tagg från **Taggar** fält för att kategorisera mallen. [Läs mer](../start/search-filter-categorize.md#tags)

1. Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till mallen kan du välja **[!UICONTROL Manage access]**. [Läs mer](../administration/object-based-access.md).

1. Klicka på **[!UICONTROL Save]**.

1. Mallen sparas i **[!UICONTROL Content Templates]** lista, tillgänglig från [!DNL Journey Optimizer] egen meny. Det blir en fristående innehållsmall som du kan komma åt, redigera och ta bort som alla andra objekt i listan. [Läs mer](#access-manage-templates)

Du kan nu använda den här mallen när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig mer](#use-content-templates)

>[!NOTE]
>
>Ändringar i den nya mallen sprids inte till det innehåll som den kommer från. När det ursprungliga innehållet redigeras i det innehållet ändras inte den nya mallen.

## Testa mallar för e-postinnehåll {#test-template}

Du kan testa återgivningen av vissa e-postmallar, oavsett om de har skapats från grunden eller från ett befintligt innehåll. Följ stegen nedan för att göra det.

>[!CAUTION]
>
>För närvarande är testning av innehållsmallar bara tillgängligt för **[!UICONTROL Email]** mallar med **[!UICONTROL HTML]** typ.

1. Få åtkomst till innehållsmalllistan via **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** och välj en e-postmall.

1. Klicka **[!UICONTROL Edit content]** från **[!UICONTROL Template properties]**.

1. Klicka **[!UICONTROL Simulate Content]** och välj en testprofil för att kontrollera återgivningen. [Läs mer](../content-management/preview-test.md)

   ![](../email/assets/content-template-stimulate.png)

1. Du kan skicka ett bevis för att testa ditt innehåll och få det godkänt av vissa interna användare innan du använder det under en resa eller i en kampanj.

   * Klicka på **[!UICONTROL Send proof]** och följer stegen som beskrivs i [det här avsnittet](../content-management/proofs.md).

   * Innan du skickar korrekturet måste du välja [e-postyta](../configuration/channel-surfaces.md) som kommer att användas för att testa ditt innehåll.

     ![](../email/assets/content-template-stimulate-proof-surface.png)

>[!CAUTION]
>
>Spårning stöds för närvarande inte vid testning av mallar för e-postinnehåll, vilket innebär att spårningshändelser, UTM-parametrar och länkar på landningssidor inte kommer att vara effektiva i korrektur som skickas från en mall. Testa spårning [använda innehållsmallen](../email/use-email-templates.md) i ett mejl och [skicka ett bevis](../content-management/preview-test.md#send-proofs).

## Använda innehållsmallar {#use-content-templates}

När du skapar innehåll för valfri kanal (utom webben) i [!DNL Journey Optimizer]kan du använda en anpassad mall som du antingen:

* Skapat från grunden med **[!UICONTROL Content templates]** -menyn. [Läs mer](#create-template-from-scratch)

* Sparas från ett befintligt innehåll på en resa eller en kampanj med hjälp av **[!UICONTROL Save as content template]** alternativ. [Läs mer](#save-as-template)

Följ stegen nedan när du vill börja skapa innehåll med någon av dessa mallar.

1. Oavsett om det gäller en kampanj eller resa, efter att du har valt **[!UICONTROL Edit content]** klickar du på **[!UICONTROL Content template]** -knappen.

1. Välj **[!UICONTROL Apply content template]**.

   ![](assets/content-template-button.png)

1. Välj önskad mall i listan. Endast mallar som är kompatibla med den valda kanalen och/eller typen visas.

   ![](assets/content-template-select.png)

   >[!NOTE]
   >
   >Från den här skärmen kan du även skapa en ny mall med den dedikerade knappen som öppnar en ny flik.

1. Klicka på **[!UICONTROL Confirm]**. Mallen används för ditt innehåll.

1. Fortsätt redigera ditt innehåll efter behov.

>[!NOTE]
>
>Börja utforma ett e-postmeddelande från en innehållsmall med [E-postdesigner](../email/get-started-email-design.md)följer du de steg som beskrivs i [det här avsnittet](../email/use-email-templates.md).

## Instruktionsvideo {#video-templates}

Lär dig hur du skapar, redigerar och använder innehållsmallar i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3413743/?quality=12)
