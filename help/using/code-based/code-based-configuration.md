---
title: Kodbaserad konfiguration
description: Skapa kodbaserad konfiguration
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 1%

---

# Konfigurera din kodbaserade upplevelse {#code-based-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_app_id"
>title="Program-ID"
>abstract="Tillhandahåll program-ID:t för korrekt identifiering och konfiguration i appens operativmiljö, vilket ger smidig integrering och funktionalitet."

>[!CONTEXTUALHELP]
>id="ajo_admin_location"
>title="Plats på sida"
>abstract="Platsen eller sökvägen i programfältet anger exakt destinationen i programmet som du vill att användarna ska ha tillgång till. Detta kan vara ett visst avsnitt eller en viss sida i programmets navigeringsstruktur."

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="Surface URI"
>abstract="En Surface URI fungerar som en exakt identifierare som dirigerar till distinkta användargränssnittselement eller -komponenter i ett program."

>[!CONTEXTUALHELP]
>id="ajo_admin_default_mobile_url"
>title="URL för standardredigering och förhandsgranskning"
>abstract="Det här fältet ser till att sidorna som genereras eller matchas av regeln har en angiven URL-adress, vilket är nödvändigt för att både skapa och förhandsgranska innehåll effektivt."

## Skapa en kanalkonfiguration {#reatte-code-based-configuration}

Så här skapar du en kanalkonfiguration:

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/code_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Välj **Kodbaserad**-kanal.

   ![](assets/code_config_2.png)

1. Välj plattformen som kodbaserad upplevelse ska användas för.

1. För webben:

   * Ange en **[!UICONTROL Page URL]** om du endast vill tillämpa ändringar på en enda sida.

   * Eller skapa en **[!UICONTROL Pages matching rule]** som mål för flera URL:er som matchar den angivna regeln. Detta kan till exempel användas för att göra ändringar på en webbplats, till exempel uppdatera en hjältebanderoll på alla sidor eller lägga till en översta bild som ska visas på varje produktsida. [Läs mer](../web/web-configuration.md)

1. För iOS och Android:

   * Ange din **[!UICONTROL App id]** och **[!UICONTROL Location or path inside the app]**.

1. Välj Annan som plattform om implementeringen inte är för webben, iOS eller Android, eller om du behöver ange specifika URI:er som mål. När du väljer flera plattformar eller lägger till flera URI:er levereras innehållet till alla valda sidor eller appar.

   * Ange **[!UICONTROL Surface URI]**.

   >[!CAUTION]
   >
   >Kontrollera att den yt-URI som används i din kodbaserade kampanj matchar den som används i din egen implementering. Annars levereras inte ändringarna.

1. Välj det format som programmet förväntar sig på den aktuella platsen. Detta kommer att användas vid utvecklingen av den kodbaserade upplevelsen i kampanjer och resor.

1. Skicka in ändringarna.

Nu kan du välja din konfiguration när du skapar en kodbaserad upplevelse.


## Vad är en yta? {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_code_based_surface"
>title="Definiera en kodbaserad upplevelsekonfiguration"
>abstract="En kodbaserad konfiguration definierar sökvägen och platsen i programmet, som identifieras unikt av en URI i programimplementeringen, där innehållet levereras och förbrukas."

En **kodbaserad upplevelseyta** är en entitet som utformats för användar- eller systeminteraktion, som identifieras unikt av en URI. Ytan anges i programimplementeringen och ska motsvara den som ingår i den kodbaserade upplevelsekanalskonfigurationen.

När du skapar en kodbaserad upplevelsekanalskonfiguration - för webben, iOS och Android måste du ange en sökväg och en plats för att komponera ytan. Om plattformen är Annan måste du ange den fullständiga URI:n, som i exemplen nedan.

En yta kan med andra ord ses som en behållare på vilken hierarkinivå som helst med en entitet (kontaktyta) som finns.<!--good idea to illustrate how it can be seen, but to clarify-->

* Det kan vara en webbsida, en mobilapp, en skrivbordsapp, en specifik innehållsplats inom en större enhet (till exempel en `div`) eller ett visningsmönster som inte är standard (till exempel en kioskdator eller en banner för datorprogram).<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* Den kan även omfatta specifika innehållsbehållare för icke-visning eller abstraherad visning (t.ex. JSON-blober som levereras till tjänster).

* Det kan också vara en jokeryta som matchar en mängd olika klientytdefinitioner (en hjältebildsplats på varje sida på webbplatsen kan till exempel översättas i en yt-URI som web://mydomain.com/*#hero_image).

En yt-URI består i princip av flera avsnitt:
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

