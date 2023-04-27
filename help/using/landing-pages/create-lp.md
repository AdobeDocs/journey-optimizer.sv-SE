---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en landningssida
description: Lär dig konfigurera och publicera en landningssida i Journey Optimizer
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
keywords: landning, landningssida, skapande, publicering
exl-id: 18f9bdff-f5c6-4601-919d-4f3124e484b5
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 1%

---

# Skapa och publicera landningssidor {#create-lp}

## Åtkomst till landningssidor {#access-landing-pages}

Om du vill få åtkomst till landningssidans lista väljer du **[!UICONTROL Journey Management]** > **[!UICONTROL Landing pages]** från den vänstra menyn.

![](assets/lp_access-list.png)

The **[!UICONTROL Landing Pages]** visas alla objekt som har skapats. Du kan filtrera dem baserat på deras status eller ändringsdatum.

![](assets/lp_access-list-filter.png)

I den här listan kan du komma åt [landningssida Live-rapport](../reports/lp-report-live.md) eller [Global rapport för landningssida](../reports/lp-report-global.md) för publicerade objekt.

Du kan också ta bort, duplicera och avpublicera en landningssida.

>[!CAUTION]
>
>Om du avpublicerar en landningssida som det refereras till i ett meddelande bryts länken till landningssidan och en felsida visas.

Klicka på de tre punkterna bredvid en landningssida för att välja önskad åtgärd.

![](assets/lp_access-list-actions.png)

>[!NOTE]
>
>Du kan inte ta bort en [publicerad](#publish-landing-page) landningssida. Om du vill ta bort den måste du först avpublicera den.

## Skapa en landningssida {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo_lp_create"
>title="Definiera och konfigurera landningssidan"
>abstract="Om du vill skapa en landningssida måste du välja en förinställning, konfigurera den primära sidan och underordnade sidor och slutligen testa sidan innan du publicerar den."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-presets.html#lp-create-preset" text="Skapa förinställningar för landningssidor"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/create-lp.html#publish-landing-page" text="Publicera landningssidan"

>[!CONTEXTUALHELP]
>id="ajo_lp_access_management_labels"
>title="Tilldela etiketter till landningssidan"
>abstract="För att skydda känsliga digitala resurser kan du definiera auktoriseringar för att hantera dataåtkomst till din landningssida med hjälp av etiketter."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/access-control/object-based-access.html" text="Åtkomstkontroll på objektnivå"

De viktigaste stegen för att skapa landningssidor är följande:

![](assets/lp-creation-process.png)

1. I listan över landningssidor klickar du på **[!UICONTROL Create landing page]**.

   ![](assets/lp_create-lp.png)

1. Lägg till en titel. Du kan lägga till en beskrivning om det behövs.

   ![](assets/lp_create-lp-details.png)

1. Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till landningssidan väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

   <!--You can add a tag. See AEP documentation?-->

1. Välj en förinställning. Lär dig hur du skapar förinställningar för landningssidor i [det här avsnittet](../landing-pages/lp-presets.md#lp-create-preset).

   ![](assets/lp_create-lp-presets.png)

1. Klicka på **[!UICONTROL Create]**.

1. Den primära sidan och dess egenskaper visas. Lär dig hur du konfigurerar inställningarna för den primära sidan [här](#configure-primary-page).

   ![](assets/lp_primary-page.png)

1. Klicka på ikonen + för att lägga till en undersida. Lär dig hur du konfigurerar inställningarna för undersidan [här](#configure-subpages).

   ![](assets/lp_add-subpage.png)

När du har konfigurerat och utformat [primär sida](#configure-primary-page)och [undersidor](#configure-subpages) om det finns något, kan du [test](#test-landing-page) och [publicera](#publish-landing-page) din landningssida.

## Konfigurera den primära sidan {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo_lp_primary_page"
>title="Ange inställningar för den primära sidan"
>abstract="Den primära sidan visas omedelbart för användarna när de klickar på länken till din landningssida, till exempel från ett e-postmeddelande eller en webbplats."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/landing-pages-design/design-lp.html" text="Utforma innehållet på landningssidan"

>[!CONTEXTUALHELP]
>id="ajo_lp_access_settings"
>title="Ange URL-adress för landningssida"
>abstract="I det här avsnittet definierar du en unik URL för landningssidan. Den första delen av URL:en kräver att du tidigare har konfigurerat en underdomän för landningssidan som en del av den förinställning du valde."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-subdomains.html" text="Konfigurera underdomäner för landningssidor"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-presets.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

Den primära sidan är den sida som visas omedelbart för användarna efter att de har klickat på länken till din landningssida, till exempel från ett e-postmeddelande eller en webbplats.

Följ stegen nedan för att definiera inställningarna för den primära sidan.

1. Du kan ändra sidnamnet, vilket är **[!UICONTROL Primary page]** som standard.

1. Redigera innehållet på sidan med hjälp av innehållsdesignern. Lär dig definiera innehåll för landningssidor [här](design-lp.md).

   ![](assets/lp_open-designer.png)

1. Definiera URL-adressen till landningssidan. Den första delen av URL:en kräver att du tidigare har konfigurerat en underdomän för landningssidan som en del av [förinställning](../landing-pages/lp-presets.md#lp-create-preset) du markerade. [Läs mer](../landing-pages/lp-subdomains.md)

   >[!CAUTION]
   >
   >Landningssidans URL måste vara unik.

   ![](assets/lp_access-url.png)

   >[!NOTE]
   >
   >Du kan inte komma åt din landningssida genom att kopiera och klistra in URL-adressen i en webbläsare, även om den publicerats. I stället kan du testa den med förhandsvisningsfunktionen som beskrivs i [det här avsnittet](#test-landing-page).

1. Om du vill att landningssidan ska förhandsladda formulärdata som redan är tillgängliga väljer du **[!UICONTROL Pre-fill form fields with profile information]**.

   ![](assets/lp_prefill-form-fields.png)

   Om det här alternativet är aktiverat och en profil redan har valt in/ut eller redan har lagts till i en prenumerationslista, återspeglas deras val när landningssidan visas.

   Om en profil till exempel har valt att ta emot meddelanden om framtida händelser, kommer motsvarande kryssruta redan att vara markerad nästa gång landningssidan visas för den profilen.

   ![](assets/lp_prefill-form-ex.png)

1. Du kan ange ett förfallodatum för sidan. I så fall måste du välja en åtgärd när sidan förfaller:

   * **[!UICONTROL Redirect URL]**: Ange URL-adressen till sidan som användarna ska omdirigeras till när sidan förfaller.
   * **[!UICONTROL Custom page]**: [Konfigurera en undersida](#configure-subpages) och välj den i listrutan som visas.
   * **[!UICONTROL Browser error]**: Skriv den feltext som ska visas i stället för sidan.

   ![](assets/lp_expiry-date.png)

1. I **[!UICONTROL Additional data]** definierar du en eller flera nycklar och deras motsvarande parametervärden. Du kan använda dessa tangenter i innehållet på din primära sida och dina underordnade sidor med [Uttrycksredigerare](../personalization/personalization-build-expressions.md). Läs mer i [det här avsnittet](lp-content.md#use-form-component#use-additional-data).

   ![](assets/lp_create-lp-additional-data.png)

1. Om du valde en eller flera prenumerationer visas [utforma den primära sidan](design-lp.md)visas de i **[!UICONTROL Subscription list]** -avsnitt.

   ![](assets/lp_subscription-list.png)

1. Från landningssidan kan du [skapa en resa](../building-journeys/journey-gs.md#jo-build) som skickar ett bekräftelsemeddelande till användarna när de skickar formuläret. Lär dig hur du skapar en sådan resa i slutet av detta [användningsfall](lp-use-cases.md#subscription-to-a-service).

   ![](assets/lp_create-journey.png)

   Klicka **[!UICONTROL Create journey]** omdirigeras till **[!UICONTROL Journey Management]** > **[!UICONTROL Journeys]** lista.

## Konfigurera undersidor {#configure-subpages}

>[!CONTEXTUALHELP]
>id="ajo_lp_subpage"
>title="Definiera inställningar för undersidan"
>abstract="Du kan lägga till upp till två undersidor. Du kan till exempel skapa en&quot;tack&quot;-sida som visas när användarna skickar in formuläret, och du kan definiera en felsida som anropas om ett problem uppstår med landningssidan."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/landing-pages-design/design-lp.html" text="Utforma innehållet på landningssidan"

>[!CONTEXTUALHELP]
>id="ajo_lp_access_settings-subpage"
>title="Ange URL-adress för landningssida"
>abstract="I det här avsnittet definierar du en unik URL för landningssidan. Den första delen av URL:en kräver att du tidigare har konfigurerat en underdomän för landningssidan som en del av den förinställning du valde."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-subdomains.html" text="Konfigurera underdomäner för landningssidor"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-presets.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

Du kan lägga till upp till två undersidor. Du kan till exempel skapa en&quot;tack&quot;-sida som visas när användarna skickar in formuläret, och du kan definiera en felsida som anropas om ett problem uppstår med landningssidan.

Följ stegen nedan för att definiera inställningar för undersidan.

1. Du kan ändra sidnamnet, vilket är **[!UICONTROL Subpage 1]** som standard.

1. Redigera innehållet på sidan med hjälp av innehållsdesignern. Lär dig definiera innehåll för landningssidor [här](design-lp.md).

   >[!NOTE]
   >
   >Du kan infoga en länk till den primära sidan från en undersida till samma landningssida. Om du till exempel vill dirigera om användare som har gjort ett misstag och vill prenumerera igen, kan du lägga till en länk från bekräftelseundersidan till den primära prenumerationssidan. Lär dig hur du infogar länkar i [det här avsnittet](../email/message-tracking.md#insert-links).

1. Definiera URL-adressen till landningssidan. Den första delen av URL:en kräver att du tidigare har konfigurerat en underdomän för landningssidan. [Läs mer](../landing-pages/lp-subdomains.md)

   >[!CAUTION]
   >
   >Landningssidans URL måste vara unik.

![](assets/lp_subpage-settings.png)

## Testa landningssidan {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ac_preview_lp_profiles"
>title="Förhandsgranska och testa landningssidan"
>abstract="När du har definierat inställningarna för landningssidan och innehållet kan du använda testprofiler för att förhandsgranska den."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/segment/profiles/creating-test-profiles.html" text="Välj testprofiler"

När inställningarna för landningssidan och innehållet har definierats kan du använda testprofiler för att förhandsgranska den. Om du infogade [personaliserat innehåll](../personalization/personalize.md)kan du med hjälp av testprofildata kontrollera hur det här innehållet visas på landningssidan.

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att kunna förhandsgranska dina meddelanden och skicka korrektur. Lär dig hur [skapa testprofiler](../segment/creating-test-profiles.md).

1. I landningssidans gränssnitt klickar du på **[!UICONTROL Simulate content]** för att komma åt valet av testprofil.

   ![](assets/lp_simulate-button.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Simulate content]** kan även användas av innehållsdesignern.

1. Från **[!UICONTROL Simulate ]** väljer du en eller flera testprofiler.

   ![](assets/lp_test-profiles.png)

   Stegen för att välja testprofiler är desamma som när du testar ett meddelande. De beskrivs i [det här avsnittet](../email/preview.md#select-test-profiles).

1. Välj **[!UICONTROL Open preview]** för att testa landningssidan.

   ![](assets/lp_open-preview.png)

1. Förhandsgranskningen av landningssidan öppnas på en ny flik. Personaliserade element ersätts med valda testprofildata.

   <!--![](assets/lp_preview.png)-->

1. Välj andra testprofiler om du vill förhandsgranska återgivningen för varje variant av landningssidan.

## Kontrollera aviseringar {#check-alerts}

När du skapar en landningssida varnar du om när du måste vidta viktiga åtgärder innan du publicerar.

Varningar visas högst upp till höger på skärmen, som visas nedan:

![](assets/lp_alerts.png)

>[!NOTE]
>
>Om knappen inte visas har ingen varning identifierats.

Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis. <!--For example, a message will display if -->

* **Fel** hindra dig från att publicera landningssidan så länge som de inte är lösta. Du får till exempel en varning om den primära sidans URL saknas.

<!--All possible warnings and errors are detailed [below](#alerts-and-warnings).-->

>[!CAUTION]
>
> Du måste lösa alla **fel** aviseringar före publicering.

<!--The settings and elements checked by the system are listed below. You will also find information on how to adapt your configuration to resolve the corresponding issues.

**Warnings**:

* 

**Errors**:

* 

>[!CAUTION]
>
> To be able to publish your message, you must resolve all **error** alerts.
-->

## Publicera landningssidan {#publish-landing-page}

När landningssidan är klar kan du publicera den för att göra den tillgänglig för användning i ett meddelande.

![](assets/lp_publish.png)

>[!CAUTION]
>
>Kontrollera och åtgärda varningar innan du publicerar. [Läs mer](#check-alerts)

När landningssidan har publicerats läggs den till i listan över landningssidor med **[!UICONTROL Published]** status.

Den är nu klar att användas i en [!DNL Journey Optimizer] som skickas via en [resa](../building-journeys/journey.md).

>[!NOTE]
>
>Ni kan övervaka hur landningssidan påverkas genom specifika rapporter. [Läs mer](../reports/lp-report-live.md)

