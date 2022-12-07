---
solution: Journey Optimizer
product: journey optimizer
title: Hantering av avanmälan via e-post
description: Lär dig hur du hanterar avanmälan med e-post
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 1%

---

# Hantering av avanmälan via e-post {#email-opt-out}

För att mottagarna ska kunna avbeställa mejl måste du alltid inkludera en **avbeställ länk** i alla e-postmeddelanden som skickas till mottagarna. [Läs mer om sekretess- och avanmälningshantering](../privacy/opt-out.md)

Om du vill göra det kan du:

* Infoga en **länk till en extern landningssida** via e-post så att användarna kan avbryta prenumerationen på information från ert varumärke. [Lär dig hur du lägger till en extern avanmälningslänk](#opt-out-external-lp)

* Lägg till en **länk för avanmälan med ett klick** i ert e-postinnehåll. Med den här länken kan dina mottagare snabbt avbeställa din kommunikation utan att omdirigeras till en landningssida där de måste bekräfta sitt val, vilket snabbar upp avanmälningsprocessen. [Lär dig hur du lägger till en länk för avanmälan med ett enda klick](#one-click-opt-out)

Om **[!UICONTROL List-Unsubscribe]** om alternativet är aktiverat på kanalytnivå kommer motsvarande e-postmeddelanden som skickas med Journey Optimizer att innehålla en länk för att avbryta prenumerationen i e-posthuvudet. [Läs mer om avanmälan i e-postrubriken](#unsubscribe-header)

>[!NOTE]
>
>E-postmeddelanden av marknadsföringstyp måste innehålla en länk för avanmälan, vilket inte krävs för transaktionsmeddelanden. Meddelandekategorin (**[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]**) definieras i [kanalyta](../configuration/channel-surfaces.md#email-type) (dvs. meddelandeförinställning) nivå och när meddelandet skapas).

## Extern avanmälan {#opt-out-external-lp}

### Lägg till en länk för att avbryta prenumerationen {#add-unsubscribe-link}

Du måste först lägga till en länk för att avbryta prenumerationen i ett meddelande. Följ stegen nedan för att göra detta:

1. Bygg en egen landningssida utan prenumeration.

1. Lägg det på valfritt tredjepartssystem.

1. Skapa ett meddelande under en resa.

1. Markera text i innehållet och [infoga en länk](../email/message-tracking.md#insert-links) med hjälp av kontextverktygsfältet.

   ![](assets/opt-out-insert-link.png)

1. Välj **[!UICONTROL External Opt-out/Unsubscription]** från **[!UICONTROL Link type]** nedrullningsbar lista.

   ![](assets/opt-out-link-type.png)

1. I **[!UICONTROL Link]** klistra in länken till tredjepartssidan.

   ![](assets/opt-out-link-url.png)

1. Klicka på **[!UICONTROL Save]**.

### Implementera ett API-anrop för avanmälan {#opt-out-api}

Om du vill att mottagarna ska avanmäla sig när de skickar in sitt val från landningssidan måste du implementera en **Prenumerations-API-anrop** via [Adobe Developer](https://developer.adobe.com){target=&quot;_blank&quot;} om du vill uppdatera motsvarande profilers inställningar.

Det här anropet till POSTEN är som följer:

Slutpunkt: platform.adobe.io/journey/imp/consent/preferences

Frågeparametrar:

* **parametrar**: innehåller den krypterade nyttolasten
* **sig**: signatur
* **pid**: krypterat profil-ID

Dessa tre parametrar kommer att ingå i den URL till landningssidan som skickas till mottagaren:

![](assets/opt-out-parameters.png)

Huvudkrav:

* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* behörighet (användartoken från ditt tekniska konto)

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

[!DNL Journey Optimizer] använder de här parametrarna för att uppdatera motsvarande profils val via [Adobe Developer](https://developer.adobe.com){target=&quot;_blank&quot;} API-anrop.

### Skicka meddelandet med en länk för att avbryta prenumerationen {#send-message-unsubscribe-link}

När du har konfigurerat länken för att avbryta prenumerationen på din landningssida och implementerat API-anropet är ditt meddelande klart att skickas.

1. Skicka meddelandet inklusive länken via en [resa](../building-journeys/journey.md).

1. Om mottagaren klickar på länken för att avbryta prenumerationen visas din startsida när meddelandet har tagits emot.

   ![](assets/opt-out-lp-example.png)

1. Om mottagaren skickar in formuläret (här, genom att klicka på **Avbeställ** på landningssidan) uppdateras profildata via [API-anrop](#opt-out-api).

1. Mottagaren omdirigeras sedan till ett bekräftelsemeddelande som anger att avanmälan lyckades.

   ![](assets/opt-out-confirmation-example.png)

   Därför får den här användaren inte information från ert varumärke om han eller hon inte prenumererar igen.

1. Om du vill kontrollera att den aktuella profilens val har uppdaterats går du till Experience Platform och öppnar profilen genom att markera ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.

   ![](assets/opt-out-profile-choice.png)

   I **[!UICONTROL Attributes]** kan du se värdet för **[!UICONTROL choice]** har ändrats till **[!UICONTROL no]**.

## Avanmäl dig med ett klick {#one-click-opt-out}

Följ stegen nedan om du vill lägga till en länk för att avanmäla dig i ditt e-postmeddelande.

1. [Infoga en länk](../email/message-tracking.md#insert-links) och markera **[!UICONTROL One click Opt-out]** som typ av länk.

   ![](assets/message-tracking-opt-out.png)

1. Välj hur du vill använda avanmälningen: på kanal-, identitet- eller prenumerationsnivå.

   ![](assets/message-tracking-opt-out-level.png)

   * **[!UICONTROL Channel]**: Avanmälningen gäller för framtida meddelanden som skickas till profilens mål (dvs. e-postadress) för den aktuella kanalen. Om flera mål är kopplade till en profil gäller avanmälan alla mål (t.ex. e-postadresser) i profilen för den kanalen.
   * **[!UICONTROL Identity]**: Avanmälningen gäller för framtida meddelanden som skickas till det specifika målet (dvs. e-postadressen) som används för det aktuella meddelandet.
   * **[!UICONTROL Subscription]**: Avanmälningen gäller för framtida meddelanden som är kopplade till en viss prenumerationslista. Det här alternativet kan bara väljas om det aktuella meddelandet är kopplat till en prenumerationslista.

1. Ange URL-adressen till landningssidan där användaren omdirigeras när prenumerationen har upphört. Den här sidan är bara här för att bekräfta att avanmälan lyckades.

   >[!NOTE]
   >
   >Om du har aktiverat **List-Unsubscribe** på kanalytnivå kommer denna URL också att användas när användarna klickar på länken för att avbryta prenumerationen i e-posthuvudet. [Läs mer](#unsubscribe-header)

   ![](assets/message-tracking-opt-out-confirmation.png)

   Du kan anpassa länkarna. Läs mer om personaliserade URL:er i [det här avsnittet](../personalization/personalization-syntax.md).

1. Spara ändringarna.

När ditt meddelande har skickats via en [resa](../building-journeys/journey.md), om en mottagare klickar på länken för att avanmäla sig, avvisas deras profil omedelbart.

## Avbeställ länk i e-posthuvud {#unsubscribe-header}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_unsubscribe"
>title="Lägg till länken för att avbryta prenumerationen i e-posthuvudet"
>abstract="Aktivera List-Unsubscribe om du vill lägga till en länk för att avbryta prenumerationen i e-posthuvudet. Om du vill ange en avanmälnings-URL infogar du en länk för avanmälan med ett klick i e-postinnehållet."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html#one-click-opt-out" text="Avanmäl dig med ett klick"

Om [Alternativet List-Unsubscribe](../configuration/channel-surfaces.md#list-unsubscribe) är aktiverat på kanalytnivå, motsvarande e-postmeddelanden som skickas med [!DNL Journey Optimizer] kommer att innehålla en länk för att avbryta prenumerationen i e-posthuvudet.

Länken för att avbryta prenumerationen visas så här i Gmail:

![](assets/unsubscribe-header.png)

>[!NOTE]
>
>Om du vill visa länken för att avbryta prenumerationen i e-posthuvudet måste mottagarens e-postklient ha stöd för den här funktionen.

Avbeställningsadressen är standard **[!UICONTROL Mailto (unsubscribe)]** som visas i motsvarande kanalyta. [Läs mer](../configuration/channel-surfaces.md#list-unsubscribe).

Om du vill ange en personlig avanmälnings-URL infogar du en länk för att välja bort en anmälan med ett klick i e-postmeddelandets innehåll och anger den URL du vill använda. [Läs mer](#one-click-opt-out)

Beroende på e-postklienten kan du klicka på länken för att avbryta prenumerationen från rubriken få följande effekter:

* Begäran om att avbryta prenumerationen skickas till standardadressen för att avbryta prenumerationen.

* Mottagaren dirigeras till den URL för landningssidan som du angav när du lade till länken för avanmälan i meddelandet.

   >[!NOTE]
   >
   >Om du inte lägger till en länk för avanmälan med ett enda klick i ditt meddelandeinnehåll visas ingen startsida.

* Motsvarande profil väljs omedelbart och det här alternativet uppdateras i Experience Platform. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}.
