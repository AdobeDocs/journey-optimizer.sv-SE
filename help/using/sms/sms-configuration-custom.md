---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera din anpassade leverantör
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer via en anpassad leverantör
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%

---

# Konfigurera en anpassad provider {#sms-configuration-custom}

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

Med den här funktionen kan du integrera och konfigurera dina egna meddelandeleverantörer och erbjuda flexibilitet utöver standardalternativen (Sinch, Twilio och Infobip). Detta möjliggör smidig redigering, leverans, rapportering och samtyckeshantering för både SMS- och RCS-meddelanden.

Med anpassad leverantörskonfiguration kan du ansluta tredjepartstjänster direkt inifrån Journey Optimizer, anpassa meddelandenyttolaster för dynamiskt innehåll och hantera inställningar för anmälan/avanmälan för att säkerställa regelefterlevnad i både SMS- och RCS-kanaler.

Följ stegen nedan för att konfigurera din anpassade leverantör:

1. [Skapa API-autentiseringsuppgifter](#api-credential)
1. [Skapa webkrok](#webhook)
1. [Skapa kanalkonfiguration](sms-configuration-surface.md)
1. [Skapa resa eller kampanj med SMS-kanalsåtgärd](create-sms.md)

## Skapa API-autentiseringsuppgifter {#api-credential}

Följ de här stegen för att skicka SMS- och RCS-meddelanden i Journey Optimizer med en anpassad leverantör som inte är tillgänglig direkt från Adobe (t.ex. Sinch, Infobip, Twilio):

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL API Credentials]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create new API credentials]**.

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

   För RCS-meddelanden används den här nyttolasten senare under [innehållsdesign](create-sms.md#sms-content).

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på ![bin-ikonen](assets/do-not-localize/Smock_Delete_18_N.svg) på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

   ![](assets/sms_byo_3.png)

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

   ![](assets/sms_byo_4.png)

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu konfigurera [inställningarna för inkommande trafik för Webkrok](#webhook) för SMS-meddelanden.

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

## Skapa webkrok {#webhook}

>[!BEGINSHADEBOX]

Om nyckelord för anmälan eller avanmälan inte anges används standardmeddelanden för godkännande för att respektera användarens integritet. Om du lägger till anpassade nyckelord åsidosätts standardvärdena automatiskt.

**Standardnyckelord:**

* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN
* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO
* **Hjälp**: HJÄLP

>[!ENDSHADEBOX]

När API-autentiseringsuppgifterna har skapats är nästa steg att skapa en webkrok och konfigurera dina inkommande inställningar. Den här konfigurationen ser till att systemet kan ta emot och bearbeta inkommande data eller meddelanden på rätt sätt.

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL SMS Webhooks]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create Webhook]**.

   ![](assets/sms_byo_5.png)

1. Konfigurera webkrosinställningarna enligt anvisningarna nedan:

   * **[!UICONTROL Name]**: Ange ett namn för din webkrok.

   * **[!UICONTROL Select SMS vendor]**: Anpassad.

   * **[!UICONTROL Select API credentials]**: Välj i listrutan [tidigare konfigurerade API-autentiseringsuppgifter](#api-credential).

   * **[!UICONTROL Opt-in Keywords]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande om anmälan. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-in Message]**: Ange det anpassade svar som automatiskt skickas som ditt meddelande.

   * **[!UICONTROL Opt-out Keywords]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt avanmälningsmeddelande. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-out Message]**: Ange det anpassade svar som automatiskt skickas som ditt avanmälan.

   ![](assets/sms_byo_6.png)

1. Klicka på **[!UICONTROL View payload editor]** för att validera och anpassa dina begärandataströmmar.

   Du kan dynamiskt anpassa din nyttolast med hjälp av profilattribut och säkerställa att korrekta data skickas för bearbetning och svarsgenerering med hjälp av inbyggda hjälpfunktioner.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av din webkrok.

1. Klicka på ikonen ![bin](assets/do-not-localize/Smock_Delete_18_N.svg) på menyn **[!UICONTROL Webhooks]** för att ta bort webkroken.

1. Om du vill ändra den befintliga konfigurationen letar du reda på önskad webbkrok och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

1. Få åtkomst till och kopiera din nya **[!UICONTROL Webhook URL]** från din tidigare inskickade **[!UICONTROL Webhook]**.

   ![](assets/sms_byo_7.png)

När du har skapat och konfigurerat inställningarna för inkommande trafik för webkroken måste du nu skapa en [kanalkonfiguration](sms-configuration-surface.md) för SMS-meddelanden.

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)

