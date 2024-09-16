---
title: Konfiguration av innehållskort
description: Kanalkonfiguration för innehållskort
feature: Channel Configuration
topic: Content Management
role: Admin
level: Experienced
badge: label="Begränsad tillgänglighet" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: 8a902298bbbac5689b4f84266dd9c9027e45fad5
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 1%

---

# Konfigurera innehållskort {#content-card-configuration}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med innehållskort](get-started-content-card.md)
* [Krav för innehållskort](content-card-configuration-prereq.md)
* **Konfigurera innehållskortskanal**
* [Skapa innehållskort](create-content-card.md)
* [Utforma innehållskort](design-content-card.md)
* [Rapport om innehållskort](content-card-report.md)

>[!ENDSHADEBOX]

## Vad är en konfiguration? {#surface-definition}

En **konfiguration för innehållskortupplevelse** är en entitet som är utformad för användar- eller systeminteraktion, som identifieras unikt av en **URI**.

Med andra ord kan en yta ses som en behållare på alla nivåer i hierarkin med en enhet (kontaktyta) som finns.

* Det kan vara en webbsida, en mobilapp, en skrivbordsapp, en specifik innehållsplats inom en större enhet (till exempel en `div`) eller ett visningsmönster som inte är standard (till exempel en kioskdator eller en banner för datorprogram).

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

## Skapa en konfiguration för innehållskort {#create-config}

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/content_card_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj **[!UICONTROL Content card]**-kanal.

   ![](assets/content_card_config_2.png)

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Välj den plattform som innehållskortsupplevelsen ska användas för.

   ![](assets/content_card_config_3.png)

1. För webben:

   * Ange en **[!UICONTROL Page URL]** om du endast vill tillämpa ändringar på en enda sida.

   * Eller skapa en **[!UICONTROL Pages matching rule]** som mål för flera URL:er som matchar den angivna regeln. Detta kan till exempel användas för att göra ändringar på en webbplats, till exempel uppdatera en hjältebanderoll på alla sidor eller lägga till en översta bild som ska visas på varje produktsida. [Läs mer](../web/web-configuration.md)

1. För iOS och Android:

   * Ange eller välj din **[!UICONTROL App id]**, **[!UICONTROL Location or path inside the app]** och **[!UICONTROL Preview URL]**.

1. Skicka in ändringarna.

Nu kan du välja din konfiguration när du skapar en upplevelse av ditt innehållskort.

