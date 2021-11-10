---
title: Dokumentationsuppdateringar
description: Läs om de senaste dokumentationsuppdateringarna
exl-id: 83c8f206-bce3-4cc8-94a3-575ec1d999bc
source-git-commit: 5e93ccee2056814c25531fc13c3cd433a19077a6
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 23%

---

# Senaste uppdateringarna i den här dokumentationen

På den här sidan listas alla dokumentationsuppdateringar för [!DNL Journey Optimizer].


## Oktober 2021

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Okt &#39;21-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Tillagd **Funktionen Datum och tid** lista. [Läs mer](personalization/functions/dates.md)
* Nytt **Komma igång-avsnitt per användarprofil**. Ta din egen väg för att nå dina mål snabbare! [Läs mer](quick-start.md)
* Nytt **Redigera en meddelandeförinställning** -avsnitt. [Läs mer](configuration/message-presets.md#edit-message-preset)
* Nytt **Redigera en PTR-post** -avsnitt. [Läs mer](configuration/ptr-records.md#edit-ptr-record)
* Nytt **Inaktivera en meddelandeförinställning** -avsnitt. [Läs mer](configuration/message-presets.md#edit-message-preset#deactivate-preset)
* Nya begränsningar i **Utvecklarhandbok för API för beslutshantering** begränsningar för erbjudandet som inte stöds av mobilen [!DNL Experience Edge] arbetsflöden. [Läs mer](offers/api-reference/offers-api/personalized-offers/create.md#limitations)
* Nytt **Skapa simuleringar** -avsnitt. [Läs mer](offers/offer-activities/simulation.md)
* Uppdaterat **Lägg till beslutsomfattningar** -avsnitt. [Läs mer](offers/offer-activities/create-offer-activities.md#add-decision-scopes)
* Uppdaterat **Definiera innehåll för dina representationer** avsnitt, inklusive ett nytt [undersektion](offers/offer-library/creating-personalized-offers.md#custom-text) om hur man definierar och personaliserar egen text. [Läs mer](offers/offer-library/creating-personalized-offers.md#content)

## September 2021

* Följande funktionssidor har uppdaterats: [sethours](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/date/functionsethours.html), [getListItem](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functiongetlistitem.html), [inSegment](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/adobe-experience-platform/functioninsegment.html)

* Följande funktioner har lagts till: [filter](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functionfilter.html), [intersect](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functiontintersect.html), [toDateOnly](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/conversion/functiontodateonly.html)

* Datumtypen dateOnly har lagts till i dokumentationen för utrycksredigering. [Läs mer](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/syntax/data-types.html?lang=en)

* Tillagda uppgifter om anpassad cachelängd på åtgärd. [Läs mer](datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Tillagd information om standardportar för anpassade åtgärder. [Läs mer](action/about-custom-action-configuration.md#url-configuration)

* Lagt till information om flera användningsfall för affärshändelser. [Läs mer](event/about-creating-business.md#multiple-business-events)

* Tillagda vanligt förekommande exempel till frågor om Journey Step Events i Data Lake. [Läs mer](reports/query-examples.md)

* Lagt till en ny **Begränsningar** sida. [Läs mer](limitations.md)

* Förbättrade **Snabbstart** sida med steg för olika profiler. [Läs mer](quick-start.md)

* Nu gäller alla funktioner för beslutshantering som beskrivs i det särskilda avsnittet även för Adobe Experience Platform-användare som använder Offera decisioningens programtjänst. [Läs mer](offers/get-started/starting-offer-decisioning.md)

* Ett underavsnitt lades till för att förtydliga skillnaderna mellan att använda segment kontra beslutsregler när en begränsning tillämpas för att begränsa urvalet av erbjudanden för en viss placering. [Läs mer](offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* Specifika exempel på rankningsformler har lagts till för att illustrera exempel på verkliga användningsområden. [Läs mer](offers/offer-library/create-ranking-formulas.md#ranking-formula-examples)

* Ett underavsnitt om hur du redigerar IP-pooler har lagts till. [Läs mer](configuration/ip-pools.md#edit-ip-pool)

## Augusti 2021

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Versionen från 21 augusti finns detaljerad i dokumentationen. [Läs mer](release-notes.md)
* Uppdaterade behörigheter för beslutshantering. [Läs mer](administration/ootb-product-profiles.md)
* Uppdaterade skärmbilder för e-postdesigner med det senaste användargränssnittet.
* Konfigurationsproceduren för anpassade åtgärder med dynamiska URL-sökvägar och dynamiska huvuden har uppdaterats. [Läs mer](action/about-custom-action-configuration.md#url-configuration)
* Ett avsnitt om tillgänglighetsfunktioner och genvägar har lagts till. [Läs mer](user-interface.md#accessibility)
* Ett avsnitt om metoder för segmentutvärdering har lagts till. [Läs mer](segment/about-segments.md#evaluation-method-in-journey-optimizer)
* Anteckningar har lagts till i avsnitten om Suppression-listan, Tillåtelselista och e-post, global/liverapport, för att ange att profiler med statusen Inaktiverad och Inte tillåten ska uteslutas från e-postrapporten Skickade mått. [Läs mer](reports/email-global-report.md)
* Ett nytt avsnitt har lagts till som beskriver hur du hämtar e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. [Läs mer](allow-list.md#reporting)
* Avsnittet Aktivera tillåtelselista har uppdaterats. [Läs mer](allow-list.md#enable-allow-list)
* Avsnittet Monitor-meddelandets förinställningar har uppdaterats med orsaker till att förinställningarna inte kunde skapas och information om sådana fel. [Läs mer](configuration/message-presets.md#monitor-message-presets)
* Uppdaterat och ändrat namn på avsnittet för återförsöksperiod för att återspegla det faktum att du nu kan ändra inställningen för återförsök via e-post i meddelandeförinställningarna. [Läs mer](configuration/retries.md#retry-duration)
* Ett nytt avsnitt har lagts till som beskriver hur du infogar en länk för att välja bort ett enstaka klick i e-postinnehåll. [Läs mer](message-tracking.md#one-click-opt-out-link)
* Uppdaterade avsnittet Delegera en underdomän med mer detaljerad information om valideringsprocessen som utfördes av Adobe. [Läs mer](configuration/delegate-subdomain.md#subdomain-validation)
* Ett avsnitt har lagts till som beskriver hur du manuellt lägger till e-postadresser och domäner i listan över inaktiveringar. [Läs mer](configuration/manage-suppression-list.md#add-addresses-and-domains)
* Uppdaterade [Åtkomst till listan över inaktiveringar](configuration/manage-suppression-list.md#access-suppression-list) och [Försök igen](configuration/retries.md) -avsnitt som återspeglar det nya användargränssnittet.
* Det nya flödet för att lägga till och konfigurera representationer när ett erbjudande skapas har dokumenterats. [Läs mer](offers/offer-library/creating-personalized-offers.md#representations)


## Juli 2021

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version från juli 210 finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Lagt till direktlänkar till Experience Platform-tjänstdokumentation i [!DNL Journey Optimizer] hemsida och innehållsförteckning
* Nya landningssidor för Experience Platform-tjänster finns tillgängliga på [!DNL Journey Optimizer]
* Lagt till länkar till [!DNL Journey Optimizer] produktbeskrivning på startsidan
* Lagt till självstudievideor på flera sidor
* Optimerade startsidesbilder
* Avsnittet&quot;Meddelandespårning&quot; har flyttats, förbättrats och bytt namn till&quot;Lägg till länkar och spåra meddelanden&quot;. [Läs mer](message-tracking.md)
* Ett underavsnitt har lagts till på spegelsidor. [Läs mer](message-tracking.md#mirror-page)
* Namnet på&quot;erbjudandeaktiviteter&quot; har ändrats till&quot;beslut&quot; och&quot;beslut&quot; till&quot;beslutsomfattningar&quot; i dokumentation och skärmar. [Läs mer](offers/get-started/starting-offer-decisioning.md)
* Nytt användningsfall: [personalisera ett meddelande med hjälpfunktioner](personalization/personalization-use-case-helper-functions.md)
* Dokumentationen för Läs segment har uppdaterats för att återspegla materialiserad segmentpåverkan. [Läs mer](building-journeys/read-segment.md)
* Uppdaterade begränsningar för resan. [Läs mer](limitations.md)
* Markeringen Konfigurera erbjudanden uppdaterades i avsnittet Beslut. [Läs mer](offers/offer-activities/configure-offer-selection.md)
* En varning har lagts till som anger att händelsebaserade erbjudanden för närvarande inte stöds. [Läs mer](offers/offer-library/creating-personalized-offers.md#eligibility)
* Dokumenterade beslutsledningens nya **[!UICONTROL Overview]** -fliken. [Läs mer](offers/get-started/user-interface.md#overview)
* Nya avsnitt har lagts till för att beskriva de åtgärder som är tillgängliga från erbjudandet och beslutslistorna: [Erbjudandelista](offers/offer-library/creating-personalized-offers.md#offer-list) och [Beslutslista](offers/offer-activities/create-offer-activities.md#decision-list).
