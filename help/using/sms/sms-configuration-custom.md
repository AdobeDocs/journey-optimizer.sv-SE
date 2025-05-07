---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera din anpassade leverantör
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer via en anpassad leverantör
feature: SMS, Channel Configuration
badge: label="Beta" type="Informative"
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: fc78fcfb0f2ce3616cb8b1df44dda2cfd66262fe
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Konfigurera en anpassad SMS-provider {#sms-configuration-custom}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_url"
>title="Provider-URL"
>abstract="Ange URL:en för det externa API som du vill ansluta till. Den här URL:en fungerar som slutpunkt för åtkomst till API:ns funktioner."

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_header_parameters"
>title="Huvudparametrar"
>abstract="Ange etikett, typ och värde för ytterligare rubriker för att aktivera korrekt autentisering, innehållsformatering och effektiv API-kommunikation. "

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_provider_payload"
>title="Leverantörsnyttolast"
>abstract="Ange nyttolasten för begäran för att säkerställa att rätt data skickas för bearbetning och svarsgenerering."

>[!AVAILABILITY]
>
>Anpassade leverantörer är för närvarande endast tillgängliga som betaversioner för vissa användare. Kontakta Adobe om du vill vara med i Beta.
>Observera att denna Beta inte stöder inkommande meddelanden för hantering av anmälan/avanmälan och leveransrapportering.


Med den här funktionen kan du integrera och konfigurera dina egna SMS-leverantörer och erbjuda flexibilitet utöver standardleverantörerna (Sinch, Twilio och Infobip). Detta möjliggör smidig framtagning av SMS, leverans, rapportering och hantering av samtycke.

Med den anpassade providerkonfigurationen för SMS kan du:

* Konfigurera anpassade SMS-leverantörer direkt i Journey Optimizer.
* Använd avancerad anpassning av nyttolasten för dynamiska meddelanden.
* Hantera medgivandeinställningar (anmälan/avanmälan) för att säkerställa regelefterlevnad.

## Skapa API-autentiseringsuppgifter {#api-credential}

Följ de här stegen för att skicka meddelanden i Journey Optimizer med en anpassad leverantör som inte är tillgänglig från Adobe (t.ex. Sinch, Infobip, Twilio):

1. Gå till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL API Credentials]** och klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_byo_1.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Anpassad.

   * **[!UICONTROL Name]**: Ange ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Provider AppId]**: Ange det program-ID som din SMS-leverantör har angett.

   * **[!UICONTROL Provider Name]**: Ange namnet på SMS-providern.

   * **[!UICONTROL Provider URL]**: Ange URL:en till din SMS-leverantör.

   * **[!UICONTROL Auth Type&#x200B;]**: Välj auktoriseringstyp och [fyll i motsvarande fält](#auth-options) baserat på den valda autentiseringsmetoden.

     ![](assets/sms-byop.png)

1. I avsnittet **[!UICONTROL Headers]** klickar du på **[!UICONTROL Add new parameter]** för att ange HTTP-rubriker för det begärandemeddelande som ska skickas till den externa tjänsten.

   Rubrikfälten **Content-Type** och **Charset** är inställda som standard och kan inte tas bort.

   ![](assets/sms_byo_2.png)

1. Lägg till din **[!UICONTROL Provider Payload]** för att validera och anpassa dina begärda nyttolaster.

   Du kan dynamiskt anpassa din nyttolast med hjälp av profilattribut och säkerställa att korrekta data skickas för bearbetning och svarsgenerering med hjälp av inbyggda hjälpfunktioner.
<!--
1. Add your **Inbound settings** to determine how your system handles incoming messages and subscriber preferences: 

    * **[!UICONTROL Inbound Webhook URL]**: Specify the endpoint URL where inbound messages (e.g. replies or new messages from users) are sent.
    * **[!UICONTROL Opt-in Keywords]**: Enter the default or custom keywords that will automatically trigger your Opt-In Message. For multiple keywords, use comma-separated values.
    * **[!UICONTROL Opt-in Message]**: Enter the custom response that is automatically sent as your Opt-In Message.
    * **[!UICONTROL Opt-out Keywords]**: Enter the default or custom keywords that will automatically trigger your Opt-Out Message. For multiple keywords, use comma-separated values.
    * **[!UICONTROL Opt-out Message]**: Enter the custom response that is automatically sent as your Opt-Out Message.
-->

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

   ![](assets/sms_byo_3.png)

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

   ![](assets/sms_byo_4.png)

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

### Autentiseringsalternativ för anpassade SMS-providers {#auth-options}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_byop_auth_type"
>title="Autentiseringstyp"
>abstract="Ange den autentiseringsmetod som krävs för att få åtkomst till API:t, vilket garanterar säker och auktoriserad kommunikation med den externa tjänsten."

>[!BEGINTABS]

>[!TAB API-nyckel]

När API-autentiseringsuppgifterna har skapats fyller du i de fält som krävs för API-nyckelautentisering:

* **[!UICONTROL Name]** &#x200B;: Ange ett namn för API-nyckelkonfigurationen.
* **[!UICONTROL API Token]** &#x200B;: Ange den API-token som din SMS-leverantör tillhandahåller.

![](assets/sms-byop-api-key.png)

>[!TAB MAC-autentisering]

När API-autentiseringsuppgifterna har skapats fyller du i de fält som krävs för MAC-autentisering:

* **[!UICONTROL Name]** &#x200B;: Ange ett namn för din MAC-autentiseringskonfiguration.
* **[!UICONTROL API Token]** &#x200B;: Ange den API-token som din SMS-leverantör tillhandahåller.
* **[!UICONTROL API Secret Key]**: Ange API-hemlig nyckel från din SMS-leverantör. Den här nyckeln används för att generera MAC (Message Authentication Code) för säker kommunikation.
* **[!UICONTROL Mac Authorization Hash Format]**: Välj hash-format för MAC-autentiseringen.

![](assets/sms-byop-mac.png)

>[!TAB OAuth-autentisering]

När API-autentiseringsuppgifterna har skapats fyller du i fälten som krävs för OAuth-autentisering:

* **[!UICONTROL Name]** &#x200B;: Ange ett namn för OAuth-autentiseringskonfigurationen.

* **[!UICONTROL API Token]** &#x200B;: Ange den API-token som din SMS-leverantör tillhandahåller.

* **[!UICONTROL OAuth URL]** &#x200B;: Ange URL:en för att hämta OAuth-token.

* **[!UICONTROL OAuth Body]** &#x200B;: Ange OAuth-begärandetexten i JSON-format, inklusive parametrar som `grant_type`, `client_id` och `client_secret`.

![](assets/sms-byop-oauth.png)

>[!TAB JWT-autentisering]

När API-autentiseringsuppgifterna har skapats fyller du i fälten som krävs för JWT-autentisering:

* **[!UICONTROL Name]** &#x200B;: Ange ett namn för JWT-autentiseringskonfigurationen.

* **[!UICONTROL API Token]** &#x200B;: Ange den API-token som din SMS-leverantör tillhandahåller.

* **[!UICONTROL JWT Payload]** &#x200B;: Ange JSON-nyttolasten som innehåller de anspråk som krävs för JWT, till exempel utfärdare, ämne, målgrupp och utgångsdatum.

![](assets/sms-byop-jwt.png)

>[!ENDTABS]

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3443610?captions=swe)
