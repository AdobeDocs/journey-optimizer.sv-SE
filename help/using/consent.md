---
title: Hantera avanmälan
description: Lär dig hur du hanterar avanmälan och sekretess
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 3c21d797c85c2dabbec77f109b160fbd77170da5
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Hantera avanmälan {#consent}

Använd [!DNL Journey Optimizer] för att spåra mottagarnas samtycke till kommunikation och förstå hur de vill interagera med ert varumärke genom att hantera sina preferenser och prenumerationer. <!--Their preferences and subscriptions are handled through Consent management.-->

I bestämmelser som GDPR anges att du måste uppfylla specifika krav innan du kan använda information från registrerade. Dessutom bör registrerade kunna ändra sitt samtycke när som helst.

**Varför är det viktigt?**

* Om ni inte följer dessa regler medför detta juridiska risker för ert varumärke.
* Det hjälper er att undvika att skicka oombedda meddelanden till era mottagare, vilket kan få dem att märka era meddelanden som skräppost och skada ert rykte.

Läs mer om hur du hanterar sekretess och tillämpliga regler i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=&quot;_blank&quot;}.

<!--* Recipients should be able to opt-in/opt-out from receiving electronic communication through one or more channel
* Recipients expect the brand to offer preference centre capability that controls how brand should engage with them (example: channel of communication, invasive and non-invasive tracking etc). This helps to fulfil regulatory obligations and also facilitates quality engagement with recipient. 
* The third category is the capability to offer subscription to recipients (newsletter, etc)-->

## Hantering av avanmälan {#opt-out-management}

Att ge mottagarna möjlighet att avbryta prenumerationen på information från ett varumärke är ett juridiskt krav. Läs mer om gällande lagstiftning i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target=&quot;_blank&quot;}.

Därför måste du alltid inkludera en **avbeställ länk** i varje e-postmeddelande som skickas till mottagarna:

* När du klickar på den här länken dirigeras mottagarna till en landningssida med en knapp som bekräftar att de avanmäler sig.
* När du klickar på avanmälningsknappen kommer ett Adobe I/O-anrop att göras för att uppdatera profildata med den här informationen. [Läs mer om detta](#consent-service-api).

### Lägg till en länk för att avbryta prenumerationen {#add-unsubscribe-link}

Följ stegen nedan om du vill lägga till en länk för att avbryta prenumerationen:

1. Bygg en startsida för din prenumeration.
1. Lägg landningssidan på valfritt tredjepartssystem.
1. [Skapa ett meddelande](../../help/using/create-message.md) in [!DNL Journey Optimizer].

   <!--The link to your landing page should contain a static URL and the profile ID.-->

1. Markera text i innehållet och infoga en länk med hjälp av det sammanhangsberoende verktygsfältet.

   ![](assets/opt-out-insert-link.png)

1. Välj **[!UICONTROL Unsubscription link]** från **[!UICONTROL Link type]** nedrullningsbar lista.

   ![](assets/opt-out-link-type.png)

1. I **[!UICONTROL Link]** klistra in länken till landningssidan.

   ![](assets/opt-out-link-url.png)

1. Klicka på **[!UICONTROL Save]**.

1. Spara innehåll och [publicera meddelandet](../../help/using/publish-manage-message.md).

   >[!NOTE]
   >
   >URL:en till din startsida från tredje part kommer att innehålla tre parametrar som kommer att användas för att uppdatera profilernas inställningar via ett Adobe I/O-samtal. &#x200B; [Läs mer i det här avsnittet](#consent-service-api).

1. Skicka meddelandet med en länk till landningssidan via en [resa](building-journeys/journey.md).

1. Om mottagaren klickar på länken för att avbryta prenumerationen visas din startsida när meddelandet har tagits emot.

   ![](assets/opt-out-lp-example.png)

1. Om mottagaren klickar på avanmälningsknappen på landningssidan (här, **Avbeställ** ) uppdateras profildata via en [Adobe I/O call](#opt-out-api).

   Mottagaren omdirigeras sedan till ett bekräftelsemeddelande som anger att avanmälan lyckades.

   ![](assets/opt-out-confirmation-example.png)

   Därför får den här användaren inte information från ert varumärke om han eller hon inte prenumererar igen.

Om du vill kontrollera att den aktuella profilens val har uppdaterats går du till Experience Platform och öppnar profilen genom att markera ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

![](assets/opt-out-profile-choice.png)

I **[!UICONTROL Attributes]** kan du se värdet för **[!UICONTROL choice]** har ändrats till **[!UICONTROL no]**.

<!--The opt-out URL is resolved upon each recipient receiving the message. It is then personalized with the relevant encrypted parameters (profile ID, profile name, journey ID, sandbox ID, and message execution ID).-->

### Avanmäl API-anrop {#opt-out-api}

När mottagaren har avanmält sig genom att klicka på länken för att avbryta prenumerationen visas ett Adobe I/O-API <!--Consent service API to capture the encrypted data and-->anropas för att uppdatera motsvarande profils inställning.

Detta samtal till POSTEN i Adobe I/O är följande:

Slutpunkt: cjm.adobe.io/imp/consent/preferences

Frågeparametrar:

* **parametrar**: innehåller den krypterade nyttolasten
* **sig**: signatur <!--which signature?-->
* **pid**: krypterat profil-ID

De här parametrarna finns på den länk för att avbryta prenumerationen som skickas till mottagaren, dvs. den URL som öppnar din tredjepartsstartsida för en viss mottagare:

![](assets/opt-out-parameters.png)

<!--QUESTION: How do you get the URL built for each recipient? Do you have to wait until each targeted recipient receives the unsubscribe link or can you deduce it in advance? Is it done automatically upon the API call or do you have to do something manually for each profile? In other words will the LP automatically include the 3 parameters or do you have to insert something manually? Still not completely clear-->

Huvudkrav:

* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* behörighet (användartoken från ditt tekniska konto) <!--How do you find this information? And other header elements?-->

Begärandetext:

```
{
   "marketing": [
       {
            "type": "email",           
            "choice": "no",          
            "scope": "channel"       
        }
    ],
 
}
```

<!--The Consent service /-->[!DNL Journey Optimizer] will <!--decrypt and-->use these parameters to update the corresponding profile's choice.
<!--and provide an answer back to the landing page.-->

## Avanmäl dig med ett klick {#one-click-opt-out}

Eftersom många kunder vill ha en enklare process för att avbryta prenumerationen kan du även lägga till en länk för att avanmäla dig med ett enda klick i ditt e-postinnehåll. Med den här länken kan dina mottagare snabbt avbeställa din kommunikation utan att omdirigeras till en landningssida där de måste bekräfta att de vill avanmäla sig.

Lär dig hur du lägger till en länk för avanmälan i ditt meddelandeinnehåll i [det här avsnittet](message-tracking.md#one-click-opt-out-link).

När ditt meddelande har skickats via en [resa](building-journeys/journey.md), om en mottagare klickar på länken för att avanmäla sig, avvisas deras profil omedelbart.

## Avbeställ länk i rubrik {#unsubscribe-email}

Om mottagarnas e-postklient har stöd för att visa en länk för att avbryta prenumerationen i e-posthuvudet, skickas e-postmeddelanden med [!DNL Journey Optimizer] infogar automatiskt den här länken.

Länken för att avbryta prenumerationen visas så här i Gmail:

![](assets/unsubscribe-email.png)

Beroende på e-postklienten kan du klicka på länken för att avbryta prenumerationen från rubriken på något av följande sätt:

* Motsvarande profil väljs omedelbart och det här alternativet uppdateras i Experience Platform. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

* Det har samma effekt som att klicka på länken för att avbryta prenumerationen från e-postinnehållet: Mottagaren omdirigeras till en landningssida med en knapp som bekräftar att han eller hon avanmäler sig. Läs mer om avanmälningshantering i [det här avsnittet](#opt-out-management).

## Hantering av avanmälan {#push-opt-out-management}

Push-mottagare kan avbeställa prenumerationen via sina enheter själva.

När du till exempel hämtar eller använder programmet kan de välja att stoppa meddelanden. På samma sätt kan de ändra meddelandeinställningarna via det mobila operativsystemet.
