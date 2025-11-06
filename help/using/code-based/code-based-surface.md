---
title: Kodbaserad yta
description: Lär dig vad en kodbaserad upplevelseyta är
feature: Code-based Experiences, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 07ec74fb-7fbc-48c6-a8fc-f58f24a60723
source-git-commit: d3f15c09194a50b95107fb84d680606a468f8644
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---

# Kodbaserade upplevelseytor {#code-based-surface}

## Vad är en yta? {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="Lägg till yt-URI för komponenten"
>abstract="Om implementeringen inte är för webben, iOS eller Android, eller om du behöver ange specifika URI:er, anger du en yt-URI, som är en unik identifierare som dirigerar till enheten där du vill leverera upplevelsen. Se till att du anger en yt-URI som matchar den som används i din egen implementering."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/code-based-experience/configure-code-based-channel/code-based-configuration#other" text="Skapa en kodbaserad upplevelsekonfiguration för andra plattformar"

En kodbaserad upplevelse **surface** är en entitet som är utformad för användar- eller systeminteraktion, unikt identifierad av en [URI](#surface-uri). Ytan anges i [programimplementeringen](code-based-prerequisites.md#implementation-prerequisites) och måste matcha ytan som refereras i din [kodbaserade upplevelsekanalskonfiguration](code-based-configuration.md).

En yta kan ses som en behållare på vilken hierarkinivå som helst med en entitet (kontaktyta) som finns.

* Det kan vara en webbsida, en mobilapp, en skrivbordsapp, en specifik innehållsplats inom en större enhet (till exempel en `div`) eller ett visningsmönster som inte är standard (till exempel en kioskdator eller en banner för datorprogram).<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* Den kan även omfatta specifika innehållsbehållare för icke-visning eller abstraherad visning (t.ex. JSON-blober som levereras till tjänster).

* Det kan också vara en jokeryta som matchar en mängd olika klientytdefinitioner (en hjältebildsplats på varje sida på webbplatsen kan till exempel översättas i en yt-URI som web://mydomain.com/*#hero_image).

>[!NOTE]
>
>När du har flera kodbaserade upplevelseåtgärder som körs på samma yta avgör kampanjen eller resan **[!UICONTROL Priority score]** vad som levereras till slutanvändaren om de kvalificerar sig för mer än en åtgärd. [Läs mer om prioritetspoäng](../conflict-prioritization/priority-scores.md)

## Ytidentifierare {#surface-uri}

En **yt-URI** fungerar som en exakt identifierare som dirigerar till distinkta användargränssnittselement eller -komponenter i ett program. En yts-URI består i princip av flera avsnitt:

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

## URI-disposition {#uri-composition}

I [!DNL Journey Optimizer] har den kodbaserade upplevelsekanalen stöd för två typer av kundimplementeringar:

* Baserat på [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} för dina webbplatser eller på [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} för dina mobilappar.
* Server-side eller hybrid med [AEP Edge Network Server-API:er](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"}.

>[!NOTE]
>
>Läs mer om implementeringskraven i [det här avsnittet](code-based-prerequisites.md#implementation-prerequisites).

Med kodbaserade upplevelser kan du ändra innehåll på detaljerade platser <!--(such as a specific location on a page, or inside a mobile native app)--> som identifieras unikt av [!DNL Journey Optimizer] med [yt-URI:er](#surface-uri).

Dessa yt-URI:er disponeras och hanteras beroende på implementeringsmetoden:

* **Webb/mobil-SDK**: Din webb-/mobilutvecklare måste definiera dessa detaljerade platser som enkla strängar, eftersom webb-/mobil-SDK automatiskt kan disponera yt-URI baserat på aktuell URL/app-ID och platssträngen.

* **Edge Network-API:er**: App-/sidutvecklaren måste definiera URI:er med fullständig yta som innehåller den fullständiga sökvägen och platsen där innehållet ska användas, eftersom fullständiga URI:er krävs för den här typen av implementering.

Det är därför som du kan ange ytan enligt den valda plattformen på två sätt när du skapar en [kodbaserad upplevelsekanalskonfiguration](code-based-configuration.md):

* För plattformarna **[!UICONTROL Web]**, **[!UICONTROL iOS]** och **[!UICONTROL Android]** måste du ange **URL/program-ID** och en **plats eller sökväg** för att skapa ytan. Läs mer om hur du konfigurerar kodbaserade upplevelser för plattformarna [web](code-based-configuration.md#web) och [mobile](code-based-configuration.md#mobile)

* Om plattformen är **[!UICONTROL Other]** måste du ange den fullständiga **yt-URI**, som i exemplen [&#x200B; ovan](#surface-uri). Läs mer om hur du konfigurerar kodbaserade upplevelser för [andra](code-based-configuration.md#other)-plattformar
