---
solution: Journey Optimizer
product: journey optimizer
title: Hantera avanmälan
description: Lär dig hur du hanterar avanmälan och sekretess
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: b35ae530ec23da1ecb0ae99c4d9659481d296f09
workflow-type: tm+mt
source-wordcount: '1667'
ht-degree: 1%

---

# Hantera avanmälan {#consent}

Använd [!DNL Journey Optimizer] för att spåra mottagarnas samtycke till kommunikation och förstå hur de vill interagera med ert varumärke genom att hantera sina preferenser och prenumerationer.

I bestämmelser som GDPR anges att du måste uppfylla specifika krav innan du kan använda information från registrerade. Dessutom bör registrerade kunna ändra sitt samtycke när som helst.

**Varför är det viktigt?**

* Om ni inte följer dessa regler medför detta juridiska risker för ert varumärke.
* Det hjälper er att undvika att skicka oombedda meddelanden till era mottagare, vilket kan få dem att märka era meddelanden som skräppost och skada ert rykte.

Läs mer om hur du hanterar sekretess och tillämpliga regler i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=&quot;_blank&quot;}.

>[!NOTE]
>
>I [!DNL Journey Optimizer], samtycke hanteras av Experience Platform [Samtyckesschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target=&quot;_blank&quot;}. Som standard är värdet för medgivandefältet tomt och behandlas som samtycke för att ta emot dina meddelanden. Du kan ändra det här standardvärdet när du går vidare till något av de möjliga värdena som anges [här](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html#choice-values){target=&quot;_blank&quot;}.

## Hantering av avanmälan via e-post {#opt-out-management}

Att ge mottagarna möjlighet att avbryta prenumerationen på information från ett varumärke är ett juridiskt krav. Läs mer om gällande lagstiftning i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target=&quot;_blank&quot;}.

Därför måste du alltid inkludera en **avbeställ länk** i varje e-postmeddelande som skickas till mottagarna:

* När du klickar på den här länken dirigeras mottagarna till en landningssida där de kan bekräfta att de vill avanmäla sig.
* När profilens val har bekräftats uppdateras profilens data med den här informationen.

>[!NOTE]
>
>E-postmeddelanden av marknadsföringstyp måste innehålla en länk för avanmälan, vilket inte krävs för transaktionsmeddelanden. Meddelandekategorin (**[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]**) definieras i [kanalyta](../configuration/channel-surfaces.md#email-type) (t.ex. meddelandeförinställning) nivå och när [skapar meddelandet](../messages/get-started-content.md#create-new-message).

### Extern avanmälan {#opt-out-external-lp}

För att göra detta kan du infoga en länk till en extern landningssida i ett e-postmeddelande så att användarna kan avbryta prenumerationen på information från ert varumärke.

#### Lägg till en länk för att avbryta prenumerationen {#add-unsubscribe-link}

Du måste först lägga till en länk för att avbryta prenumerationen i ett meddelande. Följ stegen nedan för att göra detta:

1. Bygg en egen landningssida utan prenumeration.

1. Lägg det på valfritt tredjepartssystem.

1. [Skapa ett meddelande](../messages/get-started-content.md) på en resa.

1. Markera text i innehållet och [infoga en länk](../design/message-tracking.md#insert-links) med hjälp av kontextverktygsfältet.

   ![](assets/opt-out-insert-link.png)

1. Välj **[!UICONTROL External Opt-out/Unsubscription]** från **[!UICONTROL Link type]** nedrullningsbar lista.

   ![](assets/opt-out-link-type.png)

1. I **[!UICONTROL Link]** klistra in länken till tredjepartssidan.

   ![](assets/opt-out-link-url.png)

1. Klicka på **[!UICONTROL Save]**.

#### Implementera ett API-anrop för avanmälan {#opt-out-api}

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

#### Skicka meddelandet med en länk för att avbryta prenumerationen {#send-message-unsubscribe-link}

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

### Avanmäl dig med ett klick {#one-click-opt-out}

Eftersom många kunder vill ha en enklare process för att avbryta prenumerationen kan du även lägga till en länk för att avanmäla dig med ett enda klick i ditt e-postinnehåll. Med den här länken kan dina mottagare snabbt avbeställa din kommunikation utan att omdirigeras till en landningssida där de måste bekräfta sitt val, vilket snabbar upp avanmälningsprocessen.

Följ stegen nedan om du vill lägga till en länk för att avanmäla dig i ditt e-postmeddelande.

1. [Infoga en länk](../design/message-tracking.md#insert-links) och markera **[!UICONTROL One click Opt-out]** som typ av länk.

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

### Avbeställ länk i e-posthuvud {#unsubscribe-header}

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

## Hantering av avanmälan {#push-opt-out-management}

Push-mottagare kan avbeställa prenumerationen via sina enheter själva.

När du till exempel hämtar eller använder programmet kan de välja att stoppa meddelanden. På samma sätt kan de ändra meddelandeinställningarna via det mobila operativsystemet.

## Hantering av SMS-avanmälan {#sms-opt-out-management}

I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. När prenumerationen har avbrutits tas profilerna automatiskt bort från målgruppen för framtida marknadsföringsmeddelanden.

Som standard hanterar Adobe Journey Optimizer engelskspråkiga svarsmeddelanden som STOP, UNSTOP och START för avgiftsfria och långa kodmeddelanden, i enlighet med branschstandarder för inbyggd integrering som Sinch och Twilio. Dessa nyckelord utlöser vanligtvis ett automatiskt standardsvar från din tredje part (t.ex. Twilio, Sinch osv.). Du kan bekräfta detta direkt hos leverantören eller via deras dokumentationswebbplats.

Inga steg krävs för att säkerställa att SMS-avanmälningsfunktioner fungerar i Adobe Journey Optimizer när nyckelordssvaren STOP, UNSTOP och START identifieras automatiskt.

Förutom att Adobe Journey Optimizer stoppar sändningen baserat på avanmälningsstatus (för direktintegrering med Twilio eller Sinch) har de flesta SMS-gatewayleverantörer också ett blockeringslista som säkerställer att du inte får något SMS-meddelande till en person som har valt att avanmäla sig. Om du använder en annan leverantör än Sinch eller Twilio och skickar ett SMS via [anpassad kanal](../building-journeys/using-custom-actions.md)måste du bekräfta detta med din leverantör.

>[!IMPORTANT]
>
>Textmeddelandekampanjer kan följa olika lagkrav beroende på vilken typ av SMS-kampanj du använder, var du skickar textmeddelanden och var mottagarna finns. <br>Även om Adobe Journey Optimizer kommer att hantera meddelandena om långa koder och avgiftsfria nummer enligt ovan, bör du rådfråga ditt juridiska ombud för att försäkra dig om att din SMS-kampanj uppfyller alla gällande lagkrav.

### Korta koder {#short-codes}

Som standard hanterar inte Adobe Journey Optimizer avanmälnings-, avanmälnings- eller hjälpnyckelord för korta kodnummer.

Ni måste se till att er korta kod följer alla branschregler och regler för hantering av avanmälan.

### Avsändarens alfanumeriska ID {#alphanumeric}

De alfanumeriska avsändar-ID:n är endast avsedda för envägsmeddelanden och kan inte ta emot inkommande meddelanden. Därför gäller inte Adobe Journey Optimizer nyckelord SMS STOP, START och HELP för Alpha Sender ID. Du måste ange andra instruktioner, till exempel skriva till supportteamet, ringa en telefonlinje till supporten eller skicka ett annat telefonnummer eller en annan kod så att användarna kan välja bort meddelanden som skickas via ett alfanumeriskt avsändar-ID.

#### Video {#video-sms}

Mer information om hur inbyggt stöd för inkommande nyckelord (START, STOP och UNSTOP) fungerar för SMS finns i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)