---
solution: Journey Optimizer
product: journey optimizer
title: Skapa innehållsmallar
description: Lär dig skapa mallar för återanvändning av innehåll i Journey Optimizer kampanjer och resor
feature: Templates
topic: Content Management
role: User
level: Beginner
source-git-commit: 59c675dd2ac94b6967cfb3a93f74b2016a090190
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 2%

---


# Skapa innehållsmallar {#create-content-templates}

>[!CONTEXTUALHELP]
>id="ajo_create_template"
>title="Definiera en egen innehållsmall"
>abstract="Skapa en egen mall från scratch för att göra innehållet återanvändbart på flera resor och i flera kampanjer."

Det finns två sätt att skapa innehållsmallar:

* Skapa en innehållsmall från grunden med hjälp av menyn **[!UICONTROL Content Templates]** i den vänstra listen. [Lär dig hur](#create-template-from-scratch)

* Spara innehållet som en mall när du utformar innehållet i en kampanj eller resa. [Lär dig hur](#save-as-template)

När du har sparat din innehållsmall är den tillgänglig för användning i en kampanj eller på en resa. Oavsett om du har skapat från grunden eller från ett tidigare innehåll kan du nu använda den här mallen när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig hur](#use-content-templates)

>[!NOTE]
>
>* Ändringar som görs i innehållsmallar sprids inte till kampanjer eller resor, vare sig de är live eller utkast.
>
>* När mallar används i en kampanj eller en resa påverkas inte heller den tidigare använda innehållsmallen av ändringar som du gör i kampanj- och reseinnehåll.

## Skapa mall från grunden {#create-template-from-scratch}

Följ stegen nedan för att skapa en innehållsmall från grunden.

1. Öppna innehållsmalllistan via den vänstra menyn **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]**.

1. Välj **[!UICONTROL Create template]**.

1. Fyll i mallinformationen och välj önskad kanal.

   ![](assets/content-template-channels.png)

   >[!NOTE]
   >
   >För närvarande är alla kanaler tillgängliga utom webben.

1. Välj en **[!UICONTROL Type]** för den valda kanalen.

   ![](assets/content-template-type.png)

   * Om du väljer **[!UICONTROL Content]** för **[!UICONTROL Email]** kan du definiera [Ämnesraden](../email/create-email.md#define-email-content) som en del av mallen. Om du väljer **[!UICONTROL HTML]** kan du bara definiera innehållet i e-postbrödtexten.

   * För **[!UICONTROL SMS]**, **[!UICONTROL Push]**, **[!UICONTROL In-App]** och **[!UICONTROL Direct Mail]** är endast standardtypen tillgänglig för den aktuella kanalen. Du måste fortfarande markera den.

1. Välj eller skapa Adobe Experience Platform-taggar från fältet **[!UICONTROL Tags]** för att kategorisera mallen för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Om du vill tilldela etiketter för anpassad eller viktig dataanvändning till mallen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Klicka på **[!UICONTROL Create]** och utforma ditt innehåll efter behov, på samma sätt som du gör för innehåll inuti en resa eller en kampanj - enligt den kanal du valt.

   ![](assets/content-template-edition.png)

   Lär dig hur du skapar innehåll för de olika kanalerna i följande avsnitt:
   * [Definiera e-postinnehåll](../email/get-started-email-design.md)
   * [Definiera push-innehåll](../push/design-push.md)
   * [Definiera SMS-innehåll](../sms/create-sms.md#sms-content)
   * [Definiera innehåll för direktreklam](../direct-mail/create-direct-mail.md)
   * [Definiera innehåll i appen](../in-app/design-in-app.md)

1. Om du skapar en **[!UICONTROL Email]**-mall med typen **[!UICONTROL HTML]** kan du testa ditt innehåll. [Lär dig hur](#test-template)

1. När mallen är klar klickar du på **[!UICONTROL Save]**.

1. Klicka på pilen bredvid mallnamnet för att gå tillbaka till skärmen **[!UICONTROL Details]**.

   ![](assets/content-template-back.png)

Den här mallen kan nu användas när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig hur](#use-content-templates)

## Spara innehåll som innehållsmall {#save-as-template}

>[!CONTEXTUALHELP]
>id="ajo_messages_depecrated_inventory"
>title="Lär dig hur du migrerar meddelanden"
>abstract="Den 25 juli 2022 försvann menyn Meddelanden och meddelanden skrivs nu direkt från en resa. Om du vill återanvända dina gamla meddelanden under resor måste du spara dem som mallar."

När du utformar innehåll i en kampanj eller resa kan du spara det för framtida återanvändning. Följ stegen nedan för att göra detta.

1. Klicka på knappen **[!UICONTROL Content template]** på skärmen **[!UICONTROL Edit content]**.

1. Välj **[!UICONTROL Save as content template]** i listrutan.

   ![](assets/content-template-button-save.png)

   Om du befinner dig i [e-post-Designer](../email/get-started-email-design.md) kan du även välja det här alternativet i listrutan **[!UICONTROL More]** längst upp till höger på skärmen.

   ![](assets/content-template-more-button-save.png)

1. Lägg till ett namn och en beskrivning för mallen.

   ![](assets/content-template-name.png)

   >[!NOTE]
   >
   >Den aktuella kanalen och typen fylls i automatiskt och kan inte redigeras. För e-postmallar som skapas från [e-post-Designer](../email/get-started-email-design.md) väljs typen **[!UICONTROL HTML]** automatiskt.

1. Markera eller skapa en Adobe Experience Platform-tagg från fältet **Taggar** för att kategorisera mallen. [Läs mer](../start/search-filter-categorize.md#tags)

1. Om du vill tilldela etiketter för anpassad eller viktig dataanvändning till mallen kan du välja **[!UICONTROL Manage access]**. [Läs mer](../administration/object-based-access.md).

1. Klicka på **[!UICONTROL Save]**.

1. Mallen sparas i listan **[!UICONTROL Content Templates]**, som du kommer åt från den dedikerade menyn [!DNL Journey Optimizer]. Det blir en fristående innehållsmall som du kan komma åt, redigera och ta bort som alla andra objekt i listan. [Läs mer](#access-manage-templates)

Du kan nu använda den här mallen när du skapar innehåll i [!DNL Journey Optimizer]. [Lär dig hur](#use-content-templates)

>[!NOTE]
>
>Ändringar i den nya mallen sprids inte till det innehåll som den kommer från. När det ursprungliga innehållet redigeras i det innehållet ändras inte den nya mallen.
