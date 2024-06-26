---
title: Kom igång med kodbaserade upplevelser
description: Läs om kodbaserade upplevelser i Journey Optimizer
feature: Code-based Experiences
topic: Content Management
role: User, Developer, Admin
level: Experienced
exl-id: 987de2bf-cebe-4753-98b4-01eb3fded492
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Kom igång med kodbaserad kanal {#get-sarted-code-based}

[!DNL Journey Optimizer] kan ni personalisera och testa de upplevelser ni vill leverera till kunderna via alla kontaktytor, som webbappar, mobilappar, datorprogram, videokonsoler, tv-anslutna enheter, smarta TV-apparater, kioskdatorer, ATM-enheter, röstassistenter, IoT-enheter osv.

Med **kodbaserad upplevelse** kan ni definiera inkommande upplevelser med en enkel och intuitiv icke-visuell redigerare. Det gör att du kan infoga och redigera specifika element på enskilda och mer detaljerade platser i dina program eller webbsidor, oavsett vilken typ av program du har - i stället för att ändra ett helt innehåll.

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound surface in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

>[!IMPORTANT]
>
>Specifika skyddsutkast och rekommendationer för kodbaserade upplevelser finns i [den här sidan](code-based-prerequisites.md).


<!--Discover the detailed steps to create a code-based campaign in this video.-->

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="#how-it-works">
<img alt="Lead" src="../assets/do-not-localize/privacy-audit.jpeg">
</a>
<div><a href="#how-it-works"><strong>Så här fungerar det</strong>
</div>
<p>
</td>
<td>
<a href="code-based-prerequisites.md">
<img alt="Validering" src="../assets/do-not-localize/web-prerequisites.jpg">
</a>
<div>
<a href="code-based-prerequisites.md"><strong>Garantier och krav</strong></a>
</div>
<p>
</td>
<td>
<a href="create-code-based.md#create-code-based-campaign">
<img alt="Sällan" src="../assets/do-not-localize/web-create.jpg">
</a>
<div>
<a href="create-code-based.md#create-code-based-campaign"><strong>Skapa en kodbaserad upplevelse</strong></a>
</div>
<p></td>
<td>
<a href="code-based-implementation-samples.md">
<img alt="Validering" src="../assets/do-not-localize/web-design.jpg">
</a>
<div>
<a href="code-based-implementation-samples.md"><strong>Implementeringsexempel</strong></a>
</div>
<p>
</td>
</tr></table>

<!--[Learn how to create a code-based campaign in this video](#video)-->

## När kodbaserade jämfört med andra kanaler ska användas {#code-based-vs-other-channels}

### Kodbaserade jämfört med andra kanaler

När den kodbaserade kanalen ska användas i stället för den andra [!DNL Journey Optimizer] kanaler?

* Du kan använda kodbaserade upplevelser när som helst när du inte har åtkomst till din digitala egenskap via en webbläsare eller en mobilapp - situationer där du förmodligen kan använda [!DNL Journey Optimizer] [webbkanal](../web/get-started-web.md){target="_blank"} eller [!DNL Journey Optimizer] [meddelanden i appen](../in-app/get-started-in-app.md){target="_blank"} kanal.

* Du kan använda den kodbaserade kanalen som ett alternativ till [!DNL Journey Optimizer] webbkanal om din webbplats inte kan läsas in i [webbdesigner](../web/edit-web-content.md#work-with-web-designer){target="_blank"} den visuella redigeraren eller om du inte kan använda [webbläsartillägg](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"} som gör det möjligt att skapa visuellt material för webbkanaler.

* Du kan också använda den kodbaserade kanalen som ett alternativ till [!DNL Journey Optimizer] webb- eller appkanaler om ni har en API-baserad, headless- eller serversidesimplementering.

### Kodbaserad kontra webbkanal

Om du vill köra webbanvändningsfall kan du använda antingen webbkanalen eller den kodbaserade upplevelsen, men beroende på ditt sammanhang kan ett alternativ vara mer lämpligt än det andra. De viktigaste skillnaderna listas nedan så att du kan fatta ett välgrundat beslut om vad du ska använda när.

**Webb**
* Redigera innehåll med [webbdesigner](../web/edit-web-content.md#work-with-web-designer){target="_blank"} visuell redigerare.
* Du behöver [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} implementering och [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} tillägg som är installerat i webbläsaren. [Läs mer](../web/web-prerequisites.md){target="_blank"}
* Med webbkanalen kan du ändra allt på sidan och ha en fördefinierad lista över åtgärder som du kan använda för att göra ändringar. [Läs mer](../web/edit-web-content.md#work-with-web-designer){target="_blank"}
* Det är enkelt att konfigurera och komma igång snabbt.
* Det är fokuserat på marknadsföring och personalisering.

**Kodbaserad upplevelse**
* Redigera innehåll med [personaliseringsredigerare](create-code-based.md#edit-code).
* Den kodbaserade upplevelsen kräver tidigare utvecklingsarbete med implementeringen för att säkerställa att dina ytor kan tolka och leverera det innehåll som publiceras i utkanten av [!DNL Journey Optimizer] för dessa ytor. [Läs mer](#surface-definition)
* Det kräver mer planering och kan bara ändra det som utvecklarna anger. Därför är det viktigt att identifiera komponenterna (hembanderoll, hjältebild, menyrad osv.) på de ytor som behöver ändras för personalisering eller testning, och samarbeta med ditt utvecklingsteam för att bygga den implementering som krävs för att hantera dessa ändringar.
* Du kan använda JSON-kodinnehåll.
* Det är inriktat på utvecklare och persona.

## Så här fungerar det {#how-it-works}

>[!CAUTION]
>
>Den här funktionen är avsedd för utvecklare och/eller erfarna användare. Den kan användas av marknadsförare med viss kodskrivningskompetens, förutsatt att ytimplementeringarna och den inledande konfigurationen hanteras av utvecklingsteamet.

Så här redigerar du innehåll med [!DNL Journey Optimizer] kodbaserad upplevelsefunktion, dina sidor eller appar måste vara instrumenterade. Om du vill göra det måste du deklarera de specifika enskilda platserna i förväg (kallas &quot;[ytor](#surface-definition)&quot;) där du vill infoga eller ersätta innehåll<!--HOW??-->.

>[!NOTE]
>
>Innehållet som är associerat med en yta kan för närvarande bara vara HTML eller JSON. <!--WILL COME LATER: text, image or another format depending on the application-->

De viktigaste stegen för att implementera en kodbaserad kampanj är följande.

1. Definiera en [yta](#surface-definition), som är den plats där du vill lägga till din kodbaserade upplevelse, och skapa en kampanj i [!DNL Journey Optimizer] med den här ytan. [Lär dig mer](create-code-based.md#create-code-based-campaign)

1. Skapa en upplevelse genom att ange innehåll för den markerade ytan med [!DNL Journey Optimizer] personaliseringsredigerare. [Lär dig mer](create-code-based.md#edit-code)

1. Appimplementeringsteamet gör explicita API- eller SDK-anrop för att hämta innehåll för namngivna ytor, som&quot;Banner Text&quot; eller&quot;Recommendations Tray 1&quot;, eller icke-UI-relaterade beslutspunkter i ett program, som&quot;sökalgoritmparametrar&quot;. I det här fallet är implementeringsteamet ansvarigt för återgivning eller annan tolkning och åtgärd för det returnerade innehållet.<!--TBC with Robert - should link to a new section with API/SDK call samples-->

## Vad är en yta? {#surface-definition}

>[!CONTEXTUALHELP]
>id="ajo_code_based_surface"
>title="Definiera en kodbaserad upplevelseyta"
>abstract="En kodbaserad yta är en enhet som är utformad för användar- eller systeminteraktion, som identifieras unikt av en URI."

A **kodbaserad upplevelseyta** är en enhet som är utformad för användar- eller systeminteraktion<!--ask Robert to explain further-->, som identifieras unikt av en **URI**.

Med andra ord kan en yta ses som en behållare på alla nivåer i hierarkin med en enhet (kontaktyta) som finns.<!--good idea to illustrate how it can be seen, but to clarify-->

* Det kan vara en webbsida, en mobilapp, ett datorprogram, en specifik innehållsplats inom en större enhet (till exempel en `div`) eller ett visningsmönster som inte är standard (till exempel en kioskdator eller en banner för datorprogram).<!--In retail, a kiosk is a digital display or small structure that businesses often place in high-traffic areas to engage customers.-->

* Den kan även omfatta specifika innehållsbehållare för icke-visning eller abstraherad visning (t.ex. JSON-blober som levereras till tjänster).

* Det kan också vara en jokeryta som matchar en mängd olika klientytdefinitioner (en hjältebildsplats på varje sida på webbplatsen kan till exempel översättas i en yt-URI som web://mydomain.com/*#hero_image).

En yt-URI består i princip av flera avsnitt:
1. **Typ**: web, mobileapp, atm, kiosk, tvcd, service etc.
1. **Egenskap**: sidadress eller apppaket
1. **Behållare**: plats i sid-/appaktiviteten

Tabellerna nedan visar några exempel på URI-definitioner för olika enheter.

**Webb och mobiler**

| Typ | URI | Beskrivning |
| --------- | ----------- | ------- | 
| Webb | `web://domain.com/path/page.html#element` | Representerar ett enskilt element på en viss sida i en viss domän, där ett element kan vara en etikett som i följande exempel: hero_banner, top_nav, menu, footer osv. |
| iOS | `mobileapp://com.vendor.bundle/activity#element` | Representerar ett specifikt element i en intern programaktivitet, till exempel en knapp eller ett annat vyelement. |
| Android-app | `mobileapp://com.vendor.bundle/#element` | Representerar ett specifikt element i ett systemspecifikt program. |

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
