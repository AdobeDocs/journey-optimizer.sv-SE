---
title: Kodbaserad konfiguration
description: Skapa kodbaserad konfiguration
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 1aff2f6f-914c-4088-afd8-58bd9edfe07d
source-git-commit: c3300b240bd0dc0563ed6d4e6de40bd9fa36a92e
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 1%

---

# Konfigurera din kodbaserade upplevelse {#code-based-configuration}

>[!CONTEXTUALHELP]
>id="ajo_code_based_surface"
>title="Definiera en kodbaserad upplevelsekonfiguration"
>abstract="En kodbaserad konfiguration definierar sökvägen och platsen i programmet, som identifieras unikt av en URI i programimplementeringen, där innehållet levereras och förbrukas."

Innan du [skapar din upplevelse](create-code-based.md) måste du skapa en kodbaserad upplevelsekonfiguration där du anger var innehållet ska levereras och användas i programmet.

En kodbaserad upplevelsekonfiguration måste referera till ytan, som i princip är den plats där du vill återge ändringarna. Enligt den valda plattformen måste du ange en plats/sökväg eller en URI för hela ytan. [Läs mer](#surface-definition)

## Skapa en kodbaserad upplevelsekonfiguration {#create-code-based-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_location"
>title="Ange den specifika platsen på sidan eller i appen"
>abstract="I det här fältet anges det exakta målet på en sida eller i det program som du vill att användarna ska ha tillgång till. Det kan vara ett visst avsnitt på en webbsida, eller en sida som är djup i programmets navigeringsstruktur."

>[!CONTEXTUALHELP]
>id="ajo_admin_default_mobile_url"
>title="Definiera en URL för att skapa och förhandsgranska innehåll"
>abstract="Det här fältet ser till att sidorna som genereras eller matchas av regeln har en angiven URL-adress, vilket är nödvändigt för att både skapa och förhandsgranska innehåll effektivt."

Så här skapar du en kodbaserad upplevelsekanalkonfiguration:

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/code_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Välj kanalen **Kodbaserad upplevelse**.

   ![](assets/code_config_2.png)

1. Välj den plattform som kodbaserad upplevelse ska användas för:

   * [Webb](#web)
   * [iOS och/eller Android](#mobile)
   * [Övriga](#other)

   >[!NOTE]
   >
   >Du kan välja flera plattformar. När du väljer flera plattformar levereras innehållet till alla valda sidor eller appar.

1. Välj det format som programmet förväntar sig för den här platsen. Detta kommer att användas vid utvecklingen av den kodbaserade upplevelsen i kampanjer och resor.

   ![](assets/code_config_4.png)

1. Klicka på **[!UICONTROL Submit]** om du vill spara ändringarna.

Du kan nu välja den här konfigurationen när du [skapar en kodbaserad upplevelse](create-code-based.md) i dina kampanjer och resor.

>[!NOTE]
>
>Appimplementeringsteamet ansvarar för att göra explicita API- eller SDK-anrop för att hämta innehåll för de ytor som definieras i den valda kodbaserade upplevelsekonfigurationen. Läs mer om olika kundimplementeringar i [det här avsnittet](code-based-implementation-samples.md).

### Webbplattformar {#web}

>[!CONTEXTUALHELP]
>id="ajo_admin_default_web_url"
>title="Definiera en URL för redigering och förhandsgranskning av innehåll"
>abstract="Det här fältet ser till att sidorna som genereras eller matchas av regeln har en angiven URL-adress, vilket är nödvändigt för att både skapa och förhandsgranska innehåll effektivt."

Följ stegen nedan för att definiera de kodbaserade inställningarna för upplevelsekonfiguration för webbplattformar.

1. Välj något av följande alternativ:

   * **[!UICONTROL Single page]** - Om du vill använda ändringarna på en enda sida enbart anger du **[!UICONTROL Page URL]**.

     ![](assets/code_config_single_page.png)

   * **[!UICONTROL Pages matching rule]** - Om du vill ha flera URL:er som matchar samma regel som mål ska du skapa en eller flera regler. [Läs mer](../web/web-configuration.md#web-page-matching-rule)

     <!--This could be used to apply changes universally across a website, such as updating a hero banner across all pages or adding a top image to display on every product page.-->

     Om du till exempel vill redigera element som visas på alla sidor med produkter för kvinnor på din Luma-webbplats väljer du **[!UICONTROL Domain]** > **[!UICONTROL Starts with]** > `luma` och **[!UICONTROL Page]** > **[!UICONTROL Contains]** > `women`.

     ![](assets/code_config_matching_rules.png)

1. Följande gäller för förhandsvisnings-URL:en:

   * Om du anger en URL för en sida används den URL:en för förhandsgranskningen - du behöver inte ange en annan URL.
   * Om du väljer en [sida som matchar regeln ](../web/web-configuration.md#web-page-matching-rule) måste du ange en **[!UICONTROL Default authoring and preview URL]** som ska användas för att förhandsgranska upplevelsen i webbläsaren. [Läs mer](../code-based/create-code-based.md#preview-on-device)

     ![](assets/code_config_matching_rules_preview.png)

1. Fältet **[!UICONTROL Location on page]** anger det exakta målet på sidan som du vill att användarna ska få åtkomst till. Det kan vara ett visst avsnitt på en sida i webbplatsens navigeringsstruktur, till exempel&quot;hjälte-banner&quot; eller&quot;product-rail&quot;.

   ![](assets/code_config_location_on_page.png)

### Mobila plattformar (iOS och Android) {#mobile}

>[!CONTEXTUALHELP]
>id="ajo_admin_app_id"
>title="Ange ditt program-ID"
>abstract="Ange program-ID:t för korrekt identifiering och konfiguration i programmets driftsmiljö, vilket ger smidig integrering och funktionalitet."

>[!CONTEXTUALHELP]
>id="ajo_admin_mobile_url_preview"
>title="Ange URL-adressen för förhandsgranskning av innehåll"
>abstract="Det här fältet är viktigt för att du ska kunna simulera och förhandsgranska ditt innehåll direkt på enheten i programmet."

Följ stegen nedan för att definiera de kodbaserade upplevelsekonfigurationsinställningarna för mobila plattformar.

1. Ange din **[!UICONTROL App id]**. Detta gör att programmet kan identifieras och konfigureras korrekt i dess operativmiljö och säkerställer smidig integrering och funktionalitet.

1. Ange **[!UICONTROL Location or path inside the app]**. I det här fältet anges det exakta målet i programmet som du vill att användarna ska ha tillgång till. Det kan vara ett visst avsnitt eller en viss sida i programmets navigeringsstruktur, till exempel&quot;hero-banner&quot; eller&quot;product-rail&quot;.

   ![](assets/code_config_3.png){width="500"}

1. Fyll i fältet **[!UICONTROL Preview URL]** om du vill aktivera förhandsvisningar på enheten. Den här URL:en informerar förhandsgranskningstjänsten om den specifika URL:en som ska användas när förhandsgranskning aktiveras på enheten. [Läs mer](../code-based/create-code-based.md#preview-on-device)

   Förhandsgransknings-URL:en är en djup länk som konfigureras av apputvecklaren i din app. Detta garanterar att alla URL:er som matchar djuplänksschemat öppnas i appen i stället för i en mobilwebbläsare. Kontakta din apputvecklare för att få tillgång till det djuplänksschema som konfigurerats för din app.

+++  Följande resurser kan hjälpa dig att konfigurera djupa länkar för appimplementeringen

   * För Android:

      * [Skapa djupa länkar till appkontext](https://developer.android.com/training/app-links/deep-linking)

   * För iOS:

      * [Definiera ett anpassat URL-schema för din app](https://developer.apple.com/documentation/xcode/defining-a-custom-url-scheme-for-your-app)

      * [Supporting Universal Links in your app](https://developer.apple.com/documentation/xcode/supporting-universal-links-in-your-app)

+++

   >[!NOTE]
   >
   >Om du stöter på problem när du förhandsgranskar upplevelsen kan du läsa [den här dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/troubleshooting#app-does-not-open-link).

### Andra plattformar {#other}

Följ stegen nedan för att definiera de kodbaserade inställningarna för upplevelsekonfiguration för andra plattformar (t.ex. videokonsoler, tv-anslutna enheter, smarta tv-apparater, kioskdatorer, ATM-enheter, röstassistenter, IoT-enheter).

1. Välj **[!UICONTROL Other]** som plattform om din implementering inte är för webben, iOS eller Android, eller om du behöver ange specifika URI:er som mål.

1. Ange **[!UICONTROL Surface URI]**. En yt-URI är en unik identifierare som motsvarar den enhet där du vill leverera din upplevelse. [Läs mer](#surface-definition)

   ![](assets/code_config_5.png)

   >[!CAUTION]
   >
   >Se till att du anger en yt-URI som matchar den som används i din egen implementering. Annars kan ändringarna inte levereras.

1. **[!UICONTROL Add another surface URI]** om det behövs. Du kan lägga till upp till 10 URI:er.

   >[!NOTE]
   >
   >När du lägger till flera URI:er levereras innehållet till alla de angivna komponenterna.

## Vad är en yta? {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="Lägg till yt-URI för komponenten"
>abstract="Om implementeringen inte är för webben, iOS eller Android, eller om du behöver ange specifika URI:er, anger du en yt-URI, som är en unik identifierare som dirigerar till enheten där du vill leverera upplevelsen. Se till att du anger en yt-URI som matchar den som används i din egen implementering."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/code-based-experience/code-based-configuration#other" text="Skapa en kodbaserad upplevelsekonfiguration för andra plattformar"

En kodbaserad upplevelse **surface** är en entitet som utformats för användar- eller systeminteraktion, som identifieras unikt av en **URI**. Ytan anges i programimplementeringen och måste matcha den yta som refereras i den kodbaserade upplevelsekanalskonfigurationen.

En yta kan ses som en behållare på vilken hierarkinivå som helst med en entitet (kontaktyta) som finns.

* Det kan vara en webbsida, en mobilapp, en skrivbordsapp, en specifik innehållsplats inom en större enhet (till exempel en `div`) eller ett visningsmönster som inte är standard (till exempel en kioskdator eller en banner för datorprogram).<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* Den kan även omfatta specifika innehållsbehållare för icke-visning eller abstraherad visning (t.ex. JSON-blober som levereras till tjänster).

* Det kan också vara en jokeryta som matchar en mängd olika klientytdefinitioner (en hjältebildsplats på varje sida på webbplatsen kan till exempel översättas i en yt-URI som web://mydomain.com/*#hero_image).

När du skapar en kodbaserad upplevelsekanalskonfiguration kan du ange ytan på två sätt enligt den valda plattformen:

* För plattformarna **[!UICONTROL Web]**, **[!UICONTROL iOS]** och **[!UICONTROL Android]** måste du ange en **plats eller sökväg** för att skapa ytan.

* Om plattformen är **[!UICONTROL Other]** måste du ange den fullständiga **yt-URI**, som i exemplen nedan.

En yt-URI fungerar som en exakt identifierare som dirigerar till distinkta användargränssnittselement eller -komponenter i ett program. En yts-URI består i princip av flera avsnitt:

1. **Typ**: webb, mobilapp, atm, kiosk, tvcd, service osv.
1. **Egenskap**: sid-URL eller apppaket
1. **Behållare**: plats i sid-/appaktiviteten

Tabellerna nedan visar några exempel på URI-definitioner för olika enheter.

**Webb och mobil**

| Typ | URI | Beskrivning |
| --------- | ----------- | ------- | 
| Webb | `web://domain.com/path/page.html#element` | Representerar ett enskilt element på en viss sida i en viss domän, där ett element kan vara en etikett som i följande exempel: hero_banner, top_nav, menu, footer osv. |
| iOS | `mobileapp://com.vendor.bundle/activity#element` | Representerar ett specifikt element i en intern programaktivitet, till exempel en knapp eller ett annat vyelement. |
| Android | `mobileapp://com.vendor.bundle/#element` | Representerar ett specifikt element i ett systemspecifikt program. |

**Andra enhetstyper**

| Typ | URI | Beskrivning |
| --------- | ----------- | ------- | 
| Skrivbord | `desktop://com.vendor.bundle/#element` | Representerar ett specifikt element i ett program, t.ex. en knapp, en meny, en hjältebanderoll. |
| TV-app | `tvcd://com.vendor.bundle/#element` | Representerar ett specifikt element i en app som är ansluten till en smart TV eller TV - paket-ID. |
| Tjänst | `service://servicename/#element` | Representerar en process på serversidan eller en annan manuell enhet. |
| Kiosk | `kiosk://location/screen#element` | Exempel på möjliga ytterligare yttyper som enkelt kan läggas till. |
| ATM | `atm://location/screen#element` | Exempel på möjliga ytterligare yttyper som enkelt kan läggas till. |

**Ytor med jokertecken**

| Typ | URI | Beskrivning |
| --------- | ----------- | ------- | 
| Webben med jokertecken | `wildcard:web://domain.com/*#element` | Jokertecknets yta - representerar ett enskilt element på varje sida under en specifik domän. |
| Webben med jokertecken | `wildcard:web://*domain.com/*#element` | Jokerteckenyta - representerar ett enskilt element på varje sida under alla domäner som slutar med &quot;domain.com&quot;. |
