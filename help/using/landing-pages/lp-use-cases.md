---
title: Användningsexempel för landningssida
description: Upptäck de vanligaste användningsområdena med landningssidor i Journey Optimizer
feature: Landing Pages
topic: Content Management
role: User
level: Intermediate
hidefromtoc: true
hide: true
source-git-commit: 4d564ff89a8cb6c6d76161f2e6cedf39d33e70a0
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# Användningsexempel för landningssida

Nedan finns exempel på hur du kan använda [!DNL Journey Optimizer] landningssidor så att dina kunder kan välja att inte ta emot vissa eller alla meddelanden.

<!--The main use cases are:
* Subscription to a service
* Opt-in
* Opt-out-->

## Prenumeration på en tjänst {#subscription-to-a-service}

De viktigaste stegen för att få mottagarna att prenumerera på en tjänst beskrivs nedan.

![](../assets/lp_subscription-uc.png)

Anta till exempel att du ordnar ett event nästa månad och vill starta en kampanj för att registrera event så att dina kunder som är intresserade av det evenemanget hålls uppdaterade.

1. Skapa händelseregistreringens prenumerationslista. Läs mer på [prenumerationslistor](subscription-list.md)

1. [Skapa en landningssida](create-lp.md), som gör det möjligt för mottagarna att registrera sig för evenemanget.

1. Konfigurera och utforma landningssidan för registrering, inklusive länken till prenumerationslistan. Läs mer om hur du bygger [primär landningssida](create-lp.md#configure-primary-page)

1. Skapa en tacksida som visas för mottagarna när de har skickat in registreringsformuläret. Läs mer på [landningsundersidor](create-lp.md#configure-subpages)

1. Skapa ett e-postmeddelande. Läs mer på [skapa meddelanden](../create-message.md)

1. [Infoga en länk](../message-tracking.md#insert-links) i meddelandet. Välj **[!UICONTROL Landing page]** som **[!UICONTROL Link type]** och väljer [landningssida](create-lp.md#configure-primary-page) som du har skapat för registrering.

   ![](../assets/lp_subscription-uc-link.png)

1. Spara innehåll och [publicera meddelandet](../publish-manage-message.md).

1. Skicka ditt meddelande via en [resa](../building-journeys/journey.md) Nu kan du meddela att du har registrerat dig och skicka trafik till landningssidan för registrering.

   När mottagarna har fått e-postmeddelandet och klickar på länken till landningssidan dirigeras de till din tacksida och läggs till i prenumerationslistan.

1. Du kan skicka ett bekräftelsemeddelande via e-post till de mottagare som har registrerat dig för din aktivitet. Om du vill göra det skickar du den genom en annan resa med **[!UICONTROL Segment qualification]** och välj den prenumerationslista som du skapade som segment.

<!--The event registration's subscription list tracks the profiles who registered and you can send them targeted event updates.-->

## Avanmäl dig {#opt-out}

Om du vill att mottagarna ska kunna avbeställa din kommunikation kan du inkludera en länk till en avanmälningssida i dina e-postmeddelanden.

Läs mer om hur du hanterar mottagarnas samtycke och varför detta är viktigt i [det här avsnittet](../consent.md).

### Hantering av avanmälan {#opt-out-management}

Att ge mottagarna möjlighet att avbryta prenumerationen på information från ett varumärke är ett juridiskt krav. Läs mer om gällande lagstiftning i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target=&quot;_blank&quot;}.

Därför måste du alltid inkludera en **avbeställ länk** i varje e-postmeddelande som skickas till mottagarna:

* När du klickar på den här länken dirigeras mottagarna till en landningssida med en knapp som bekräftar att de avanmäler sig.
* När du klickar på avanmälningsknappen uppdateras profildata med den här informationen.

### Konfigurera avanmälan {#configure-opt-out}

Följ stegen nedan om du vill att mottagarna av ett meddelande ska kunna avbeställa från din kommunikation via en landningssida.

1. Bygg [landningssida](create-lp.md). Använd landningssidans specifika **[!UICONTROL Form]** -komponent, definiera **[!UICONTROL Opt-out]** kryssruta och välj att uppdatera **[!UICONTROL Channel (email)]**: profilen som markerar avanmälningsrutan på landningssidan avvisas från all kommunikation. [Läs mer](design-lp.md)

   <!--You can also build your own landing page and host it on the third-party system of your choice. To keep?-->

1. [Skapa ett meddelande](../create-message.md) in [!DNL Journey Optimizer].

1. Markera text i innehållet och [infoga en länk](../message-tracking.md#insert-links) med hjälp av kontextverktygsfältet. Du kan också använda en länk på en knapp.

   ![](../assets/lp_opt-out-insert-link.png)

1. Välj **[!UICONTROL Landing page]** från **[!UICONTROL Link type]** nedrullningsbar lista.

1. Välj [landningssida](create-lp.md#configure-primary-page) som du skapade för att avanmäla dig.

   ![](../assets/lp_opt-out-landing-page.png)

1. Klicka på **[!UICONTROL Save]**.

1. Spara innehåll och [publicera meddelandet](../publish-manage-message.md).

1. Skicka ditt meddelande via en [resa](../building-journeys/journey.md).

1. Om mottagaren klickar på länken för att avbryta prenumerationen visas din startsida när meddelandet har tagits emot.

   <!--![](../assets/lp_opt-out-lp-example.png)-->

1. Om mottagaren klickar på länken för avanmälan på landningssidan uppdateras profildata och kommer inte att få meddelanden från varumärket om han eller hon inte prenumererar igen.

   <!--The opted-out recipient is then redirected to a confirmation message screen indicating that opting out was successful.-->

   <!--![](../assets/lp_opt-out-confirmation-example.png)-->

Om du vill kontrollera att den aktuella profilens val har uppdaterats går du till Experience Platform och öppnar profilen genom att markera ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

![](../assets/lp_opt-out-profile-choice.png)

I **[!UICONTROL Attributes]** kan du se värdet för **[!UICONTROL choice]** har ändrats till **[!UICONTROL no]**.

<!--

### Other ways to opt out

You can also enable your recipients to unsubscribe whithout using landing pages.

* **One-click opt-out**

    You can add a one-click opt-out link into your email content. This will enable your recipients to quickly unsubscribe from your communications, without being redirected to a landing page where they need to confirm opting out. [Learn more](../message-tracking.md#one-click-opt-out-link)

* **Unsubscribe link in header**

    If the recipients' email client supports displaying an unsubscribe link in the email header, emails sent with [!DNL Journey Optimizer] automatically include this link. [Learn more](../consent.md#unsubscribe-email)
-->