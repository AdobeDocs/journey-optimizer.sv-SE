---
solution: Journey Optimizer
product: journey optimizer
title: Användningsexempel för landningssida
description: Upptäck de vanligaste användningsområdena med landningssidor i Journey Optimizer
feature: Landing Pages, Subscriptions
topic: Content Management
role: User
level: Intermediate
keywords: landning, landningssida, fallstudie
exl-id: 8c00d783-54a3-45d9-bd8f-4dc58804d922
source-git-commit: 436507ea3ea76eb7a42cbcb3747ad236685e3f13
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 1%

---

# Användningsexempel för landningssida {#lp-use-cases}

Nedan finns några exempel på hur du kan använda [!DNL Journey Optimizer] landningssidor så att dina kunder kan välja att inte ta emot vissa eller alla meddelanden.

## Prenumeration på en tjänst {#subscription-to-a-service}

Ett av de vanligaste användningsområdena är att bjuda in kunderna till [prenumerera på en tjänst](subscription-list.md) (till exempel ett nyhetsbrev eller ett evenemang) via en landningssida. De viktigaste stegen visas i diagrammet nedan:

![](assets/lp_subscription-uc.png)

Anta till exempel att du ordnar ett event nästa månad och vill starta en kampanj för att registrera event<!--to keep your customers that are interested updated on that event-->. För att göra detta ska du skicka ett e-postmeddelande med en länk till en landningssida där mottagarna kan registrera sig för evenemanget. De användare som registrerar sig läggs till i prenumerationslistan som du har skapat för detta ändamål.

### Konfigurera en landningssida {#set-up-lp}

1. Skapa händelseregistreringens prenumerationslista, som lagrar registrerade användare. Lär dig hur du skapar en prenumerationslista [här](subscription-list.md#define-subscription-list).

   ![](assets/lp_subscription-uc-list.png)

1. [Skapa en landningssida](create-lp.md) för att göra det möjligt för mottagarna att registrera sig för evenemanget.

   ![](assets/lp_create-lp-details.png)

1. Konfigurera registreringen [primär landningssida](create-lp.md#configure-primary-page).

1. När du utformar [innehåll på landningssidan](design-lp.md)markerar du den prenumerationslista som du skapade för att uppdatera den med de profiler som markerar kryssrutan för registrering.

   ![](assets/lp_subscription-uc-lp-list.png)

1. Skapa en&quot;tack&quot;-sida som visas för mottagarna när de har skickat in registreringsformuläret. Lär dig konfigurera delsidor för landning [här](create-lp.md#configure-subpages).

   ![](assets/lp_subscription-uc-thanks.png)

1. [Publicera](create-lp.md#publish) landningssidan.

1. I en [resa](../building-journeys/journey.md), lägga till **E-post** verksamhet för att köra trafik till landningssidan för registrering.

   ![](assets/lp_subscription-uc-journey.png)

1. [Designa e-postmeddelandet](../email/get-started-email-design.md) för att meddela att registreringen nu är öppen för ditt event.

1. [Infoga en länk](../email/message-tracking.md#insert-links) i ert meddelandeinnehåll. Välj **[!UICONTROL Landing page]** som **[!UICONTROL Link type]** och väljer [landningssida](create-lp.md#configure-primary-page) som du har skapat för registrering.

   ![](assets/lp_subscription-uc-link.png)

   >[!NOTE]
   >
   >Om du vill kunna skicka ditt meddelande kontrollerar du att landningssidan du valt inte har gått ut ännu. Lär dig hur du uppdaterar förfallodatumet [i det här avsnittet](create-lp.md#configure-primary-page).

   När mottagarna har fått e-postmeddelandet och klickar på länken till landningssidan dirigeras de till&quot;tack&quot;-sidan och läggs till i prenumerationslistan.

### Skicka en bekräftelse via e-post {#send-confirmation-email}

Dessutom kan du skicka ett bekräftelsemeddelande via e-post till de mottagare som har registrerat sig för din aktivitet. Följ stegen nedan för att göra det.

1. Skapa en till [resa](../building-journeys/journey.md). Du kan göra det direkt från landningssidan genom att klicka på **[!UICONTROL Create journey]** -knappen. [Läs mer](create-lp.md#configure-primary-page)

   ![](assets/lp_subscription-uc-create-journey.png)

1. Ta fram **[!UICONTROL Events]** kategori och släpp en **[!UICONTROL Audience Qualification]** på arbetsytan. [Läs mer](../building-journeys/audience-qualification-events.md)

1. Klicka på **[!UICONTROL Audience]** och välj den prenumerationslista som du har skapat.

   ![](assets/lp_subscription-uc-confirm-journey.png)

1. Lägg till ett bekräftelsemeddelande som du väljer och skicka det genom resan.

   ![](assets/lp_subscription-uc-confirm-email.png)

Alla användare som har registrerat sig för din aktivitet får bekräftelsemeddelandet via e-post.

<!--The event registration's subscription list tracks the profiles who registered and you can send them targeted event updates.-->

## Välj ut {#opt-out}

Om du vill att mottagarna ska kunna avbeställa din kommunikation kan du inkludera en länk till en avanmälningssida i dina e-postmeddelanden.

>[!NOTE]
>
>Läs mer om hur du hanterar mottagarnas samtycke och varför detta är viktigt i [det här avsnittet](../privacy/opt-out.md).

### Hantering av avanmälan {#opt-out-management}

Att ge mottagarna möjlighet att avbryta prenumerationen på information från ett varumärke är ett juridiskt krav. Läs mer om gällande lagstiftning i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target="_blank"}.

Därför måste du alltid inkludera en **avbeställ länk** i varje e-postmeddelande som skickas till mottagarna:

* När du klickar på den här länken dirigeras mottagarna till en landningssida med en knapp som bekräftar att de avanmäler sig.
* När du klickar på avanmälningsknappen uppdateras profildata med den här informationen.

### Konfigurera e-postavanmälan {#configure-opt-out}

Följ stegen nedan om du vill att mottagarna av ett e-postmeddelande ska kunna avbeställa från din kommunikation via en landningssida.

1. Skapa en landningssida. [Läs mer](create-lp.md)

1. Definiera den primära sidan. [Läs mer](create-lp.md#configure-primary-page)

1. [Design](design-lp.md) det primära sidinnehållet: använd landningssidans specifika **[!UICONTROL Form]** -komponent, definiera **[!UICONTROL Opt-out]** kryssruta och välj att uppdatera **[!UICONTROL Channel (email)]**: den profil som kontrollerar avanmälningsrutan på din landningssida avvisas från all kommunikation.

   ![](assets/lp_opt-out-primary-lp.png)

   <!--You can also build your own landing page and host it on the third-party system of your choice.-->

1. Lägg till en bekräftelse [undersida](create-lp.md#configure-subpages) som visas för de användare som skickar formuläret.

   ![](assets/lp_opt-out-subpage.png)

   >[!NOTE]
   >
   >Se till att du refererar till undersidan på den primära sidans **[!UICONTROL Call to action]** i **[!UICONTROL Form]** -komponenten. [Läs mer](design-lp.md)

1. När du har konfigurerat och definierat innehållet på dina sidor [publicera](create-lp.md#publish) landningssidan.

1. [Skapa ett e-postmeddelande](../email/get-started-email-design.md) på en resa.

1. Markera text i innehållet och [infoga en länk](../email/message-tracking.md#insert-links) med hjälp av kontextverktygsfältet. Du kan också använda en länk på en knapp.

1. Välj **[!UICONTROL Landing page]** från **[!UICONTROL Link type]** nedrullningsbar lista och välj [landningssida](create-lp.md#configure-primary-page) som du skapade för att avanmäla dig.

   ![](assets/lp_opt-out-landing-page.png)

   >[!NOTE]
   >
   >Om du vill kunna skicka ditt meddelande kontrollerar du att landningssidan du valt inte har gått ut ännu. Lär dig hur du uppdaterar förfallodatumet [i det här avsnittet](create-lp.md#configure-primary-page).

1. Publicera och kör resan. [Läs mer](../building-journeys/journey.md).

1. När meddelandet har tagits emot visas din startsida om en mottagare klickar på länken för att avbryta prenumerationen i e-postmeddelandet.

   ![](assets/lp_opt-out-submit-form.png)

   Om mottagaren markerar rutan och skickar formuläret:

   * Mottagaren omdirigeras till bekräftelsemeddelandeskärmen.

   * Profildata uppdateras och kommer inte att få information från ert varumärke om ni inte prenumererar igen.

Om du vill kontrollera att den aktuella profilens val har uppdaterats går du till Experience Platform och öppnar profilen genom att markera ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target="_blank"}.

![](assets/lp_opt-out-profile-choice.png)

I **[!UICONTROL Attributes]** kan du se att värdet för **[!UICONTROL choice]** har ändrats till **[!UICONTROL no]**.

Information om avanmälan finns i **Samtycketjänstens datauppsättning**. [Läs mer om datauppsättningar](../data/get-started-datasets.md)

>[!NOTE]
>
>Om sammanfogningsmetoden är standard [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"} **[!UICONTROL Profiles]** merge policy is **[!UICONTROL Dataset Precedence]**, make sure to enable the **[!UICONTROL AJO Consent Service Dataset]** and to prioritize it in the merge policy. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#dataset-precedence-profile){target="_blank"}
>
>Även om inga batchar har lagts till i den här datauppsättningen kommer den fortfarande att innehålla information om anmälan/avanmälan.


<!--

### Other ways to opt out

You can also enable your recipients to unsubscribe whithout using landing pages.

* **One-click opt-out**

    You can add a one-click opt-out link into your email content. This will enable your recipients to quickly unsubscribe from your communications, without being redirected to a landing page where they need to confirm opting out. [Learn more](../privacy/opt-out.md#one-click-opt-out-link)

* **Unsubscribe link in header**

    If the recipients' email client supports displaying an unsubscribe link in the email header, emails sent with [!DNL Journey Optimizer] automatically include this link. [Learn more](../privacy/opt-out.md#unsubscribe-header)

////////


## Leverage landing page submission event {#leverage-lp-event}

You can use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.

To do this, you need to create an event containing the landing page submission information and use it in a journey. Follow the steps below.

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Configurations]**, and in the **[!UICONTROL Events]** section, select **[!UICONTROL Manage]**.

    ![](assets/lp_subscription-uc-configurations.png)

1. The list of events displays. Select **[!UICONTROL Create Event]**.

    ![](assets/lp_subscription-uc-create-event.png)

1. The event configuration pane opens on the right side of the screen. Configure a rule-based unitary event. [Learn more](../event/about-creating.md)

1. Define the schema: select **[!UICONTROL AJO Email Tracking Experience Event Schema v.1]** (available by default in [!DNL Journey Optimizer]).

    ![](assets/lp_subscription-uc-event-schema.png)

1. In the **[!UICONTROL Fields]** section, select the following elements:

    * **[!UICONTROL _experience]** > **[!UICONTROL customerJourneyManagement]** > **[!UICONTROL messageInteraction]** > **[!UICONTROL Interaction Type]**
    
    * **[!UICONTROL _experience]** > **[!UICONTROL customerJourneyManagement]** > **[!UICONTROL messageInteraction]** > **[!UICONTROL Landing Page Details]** > **[!UICONTROL Landing Page ID]**

    ![](assets/lp_subscription-uc-event-fields.png)

1. Click inside the **[!UICONTROL Event ID condition]** field. Using the simple expression editor, define the condition for the **[!UICONTROL Interaction Type]** and **[!UICONTROL Landing Page ID]** fields. This will be used by the system to identify the events that will trigger your journey.

    ![](assets/lp_subscription-uc-event-id-condition.png)

    >[!NOTE]
    >
    >To find the landing page ID, you can insert the landing page as a link into an email and select the source code from the contextual toolbar to display the landing page information.
    >
    >![](assets/lp_subscription-uc-lp-id.png)

1. Save your changes.

1. Create a [journey](../building-journeys/journey.md). You can do it directly from the landing page by clicking the **[!UICONTROL Create journey]** button. Learn more [here](create-lp.md#configure-primary-page)

    ![](assets/lp_subscription-uc-event-create-journey.png)

1. In the journey, unfold the **[!UICONTROL Events]** category and drop the event that you created into the canvas. Learn more [here](../building-journeys/audience-qualification-events.md)

    ![](assets/lp_subscription-uc-journey-event.png)

1. Unfold the **[!UICONTROL Actions]** category and drop an email action into the canvas.

    ![](assets/lp_subscription-uc-journey-email.png)

///How do you use the information from the event to send an email to the users? -->
