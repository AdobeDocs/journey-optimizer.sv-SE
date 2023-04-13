---
solution: Journey Optimizer
product: journey optimizer
title: Dokumentationsuppdateringar
description: Läs om de senaste dokumentationsuppdateringarna
exl-id: 83c8f206-bce3-4cc8-94a3-575ec1d999bc
source-git-commit: 93e3ed9e1a9a437353b800aee58952b86eab9370
workflow-type: tm+mt
source-wordcount: '2570'
ht-degree: 17%

---

# Dokumentationsuppdateringar {#latest-updates}

På den här sidan listas alla dokumentationsuppdateringar för [!DNL Journey Optimizer].

## April 2023 {#apr-2023}

* Adobe Experience Manager Assets Essentials och Adobe Stock har lagts till på integreringssidan för flera lösningar. [Läs mer](../start/ajo-integrations.md)
* Varningen för e-postunderdomäner på flera nivåer som inte tillåts har tagits bort eftersom de nu stöds. [Läs mer](../configuration/delegate-subdomain.md)
* En anteckning har lagts till för att ange att om ändringar görs i ett offertbeslut som används i en resa måste du avpublicera resan och publicera den på nytt. [Läs mer](../building-journeys/publishing-the-journey.md)

## Mars 2023 {#march-2023}

* Journey Optimizer schemaordlista är nu tillgänglig. Du hittar den fullständiga listan med fält och attribut för varje schema.  [Läs mer](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)
* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Mars 23-utgåvan finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Ett steg har lagts till för att aktivera Adobe Analytics-event på dina resor. [Läs mer](../event/about-analytics.md)
* Ett nytt avsnitt har skapats i beslutshanteringshandboken om hur man samlar in feedback från offera decisioningar i Adobe Experience Platform, inklusive vilka erbjudanden som visas och hur användare interagerar med dem. [Läs mer](../offers/data-collection/data-collection.md)
* Ett nytt underavsnitt har lagts till i **Skapa beslut** för att förklara skillnaden mellan att utvärdera kriterier i en sekventiell ordning eller samtidigt. [Läs mer](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* Ett skyddsräcke har lagts till för att läsa segmentresor med stegvis läsning. Du kan inte skapa en ny version, du måste duplicera resan. [Läs mer](../start/guardrails.md#journey-versions-g)

## Februari 2023 {#feb-2023}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version 23 av februari 2003 finns detaljerad i dokumentationen. [Läs mer](release-notes.md)
* En anteckning har lagts till i den API-utlösta kampanjdokumentationen för att ange att kontextattribut som skickas till begäran inte får överstiga 50 kB. [Läs mer](../campaigns/api-triggered-campaigns.md#contextual)
* Information om hur avanmälningsinformation lagras i **Samtycketjänstens datauppsättning** efter att mottagarna har avbeställt prenumerationen via en landningssida. [Läs mer](../landing-pages/lp-use-cases.md#configure-opt-out)

## Januari 2023 {#jan-2023}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version 23 av jan har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Tillgänglighetsfunktioner i [!DNL Journey Optimizer] grupperas nu på en dedikerad sida. [Läs mer](../start/accessibility.md)
* En ny sida om datahantering har lagts till i [!DNL Journey Optimizer]. [Läs mer](../data/gs-data.md)
* En tabell med alla koder som kan returneras i svaret har lagts till när erbjudanden levereras med hjälp av besluts-API:t. [Läs mer](../offers/api-reference/offer-delivery-api/decisioning-api.md)

+++ 2022

## December 2022 {#december-2022}

* Meddelandeguiden har omstrukturerats och delats upp i dedikerade guider för varje kanal:

   * [E-postkanal](../email/get-started-email.md)
   * [Push-meddelandekanal](../push/get-started-push.md)
   * [SMS-kanal](../sms/get-started-sms.md)

* Konfigurationsguiden har omstrukturerats för att bli enklare att läsa. [Läs mer](../configuration/get-started-configuration.md)

## November 2022 {#november-2022}

* En ny sida om Journey Optimizer integreringar har lagts till. [Läs mer](../start/ajo-integrations.md)
* En rekommendation om längden på URL:er för spegelsidor har lagts till. [Läs mer](../email/message-tracking.md)
* Ett nytt underavsnitt i konfigurationen av e-postinställningarna har lagts till i svaret på e-postadressen, inklusive rekommendationer för att säkerställa korrekt svarshantering. [Läs mer](../email/email-settings.md#reply-to-email)
* Ett avsnitt har lagts till om hur du ändrar innehållet i ett meddelande i en direktresa. [Läs mer](../building-journeys/journeys-message.md#update-live-content)

## Oktober 2022 {#october-2022}

* Ett exempel på hur man begränsar genomströmningen med hjälp av externa datakällor och anpassade åtgärder har lagts till. [Läs mer](../building-journeys/limit-throughput.md)
* Fallavsnittet för resans användning har omorganiserats i två kategorier: [Användningsexempel](../building-journeys/journeys-uc.md) och [Tekniska användningsfall](../building-journeys/collections.md).
* The **Enhetsdatauppsättning** -avsnittet har uppdaterats med mer information. [Läs mer](../data/datasets-query-examples.md#entity-dataset)
* Avsnitten för hantering av avanmälan och godkännandepolicyer har omorganiserats. [Läs mer](../privacy/opt-out.md)
* Avsnittet om avancerade parametrar i resemeddelanden har klargjorts och anger nu att åsidosättning av e-postadresser endast ska användas för särskilda användningsfall. Det värde som oftast definieras som den primära adressen i **Körningsfält** är den som bör användas.
* En anteckning har lagts till i **Konfigurera underdomäner för landningssidor** för att ange att versaler inte tillåts i underdomäner för landningssidor. [Läs mer](../landing-pages/lp-subdomains.md)

## September 2022 {#september-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Septemberversionen 22 har detaljerats i dokumentationen. [Läs mer](release-notes.md)
* Lagt till en metodtips som är relaterad till användningen av vänteaktiviteter i återkommande lässegmentsresor. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)
* Frågeexempel för det nya steget har lagts till samt information om skillnaden mellan id, instanceid och profileid. [Läs mer](../reports/query-examples.md).
* Uppdaterade sidor relaterade till [toDateOnly](../building-journeys/functions/functiontodateonly.md) och [toString](../building-journeys/functions/functiontostring.md) funktioner.
* Information om tidsvillkorsparametrar har lagts till. [Läs mer](../building-journeys/condition-activity.md#time_condition)
* Lagt till information om inbyggda datauppsättningar. [Läs mer](../data/get-started-datasets.md#access-datasets)
* Delarna i den globala rapporten och Live-rapporten har förbättrats och omorganiserats. [Läs mer](../reports/global-report.md)
* En lista över alla rapporteringsmått som är tillgängliga i Adobe Journey Optimizer har lagts till.
   [Läs mer](../reports/global-report.md#email-and-sms-metrics)
* BCC-e-postavsnittet har flyttats till den nya sidan Stöd för arkivering. [Läs mer](../configuration/archiving-support.md)

## Augusti 2022 {#august-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version 22 augusti finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Avsnittet Frekvensregler har uppdaterats för att återspegla det nya textbundna meddelandeflödet. [Läs mer](../configuration/frequency-rules.md#apply-frequency-rule)
* En video som visar hur du konfigurerar prenumerationer och skapar landningssidor finns nu i avsnittet Kom igång med landningssidor. [Läs mer](../landing-pages/get-started-lp.md#video)
* En begränsning har lagts till för resor som använder Läs segment-aktiviteter. [Läs mer](../building-journeys/read-segment.md)
* Operatorsidan för uttrycksredigeraren har förbättrats. [Läs mer](../building-journeys/expression/operators.md)
* Ett avsnitt om schemaläggning av en kampanj har lagts till. [Läs mer](../campaigns/create-campaign.md)
* Avsnittet med allmänna syntaxregler för uttrycksredigeraren har uppdaterats för att ta hänsyn till den nya regeln för den omvända snedstreckssymbol som undgår bokstavsfunktioner. De befintliga publicerade meddelandena påverkas inte av den här ändringen. Endast de nya meddelandena eller utkastmeddelandena måste uppdateras. [Läs mer](../personalization/personalization-syntax.md#general-rules)

## Juli 2022 {#july-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version 22 från juli finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* The **Konfigurera kanalytor** -avsnittet har klargjorts och uppdaterats med länkar till sidan som beskriver hur SMS-kanalen konfigureras. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)
* I reseegenskaperna **Tidszon för profil** är nu inaktiverat som standard. [Läs mer](../building-journeys/timezone-management.md#timezone-from-profiles)
* I **Vänta** aktivitet, **Fast datum** är inte längre tillgängligt. [Läs mer](../building-journeys/wait-activity.md)
* Ytterligare information om **Inkrementell läsning** i **Lässegment** aktivitet. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)
* Rekommendationer om **Profilände** villkorstyp. [Läs mer](../building-journeys/condition-activity.md#profile_cap)
* Lagt till en begränsning av affärshändelser. [Läs mer](../start/guardrails.md#events-g)

## Juni 2022 {#june-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version från 22 juni finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Ett nytt avsnitt om sekretessförfrågningar har lagts till i dokumentationen. [Läs mer](../privacy/requests.md)
* Ett nytt avsnitt om granskningsloggar på resurser har lagts till i dokumentationen. [Läs mer](../privacy/audit-logs.md)
* Ett nytt avsnitt om hur du lägger till HTML eller JSON-innehåll som kommer från Adobe Experience Cloud Asset-biblioteket i en offertrepresentation har lagts till i dokumentationen. [Läs mer](../offers/offer-library/add-representations.md#html-json)
* En ny sida om resans livscykel har lagts till. [Läs mer](../building-journeys/journey.md#journey-versions)
* Sidan Vänta aktivitet har uppdaterats. [Läs mer](../building-journeys/wait-activity.md)
* Listan med Adobe Journey Optimizer datauppsättningar har lagts till med frågeexempel. [Läs mer](../data/datasets-query-examples.md)
* Sidan Tillåtelselista har flyttats till avsnittet Konfiguration. [Läs mer](../configuration/allow-list.md)
* Sidan Suppression List har uppdaterats för att förtydliga viss information, inklusive det faktum att alla ASCII-tecken mellan 32 och 126 tillåts i fältet för undertryckning. [Läs mer](../configuration/manage-suppression-list.md)
* Länken till skyddsförslag och statiska gränser för beslutshantering har lagts till. [Läs mer](../start/guardrails.md)
* Tidsoptimering är nu tillgängligt för alla kunder. Betaversionen har tagits bort. [Läs mer](../building-journeys/journeys-message.md#send-time-optimization)
* API:t för gruppbeslut har lagts till i listan över tillgängliga API:er för leverans av personaliserade erbjudanden. [Läs mer](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)

## Maj 2022 {#may-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version från maj 22 finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Nya frågeexempel relaterade till [segmentkvalificering](../reports/query-examples.md#segment-qualification-queries) och [händelser](../reports/query-examples.md#event-based-queries) har lagts till.
* I avsnittet för e-postdesign omnämns nu nya inbyggda mallar som kan användas för att börja innehåll med. Relaterade skärmbilder har uppdaterats. [Läs mer](../email/get-started-email-design.md)
* Länkar till viktiga resurser har uppdaterats på Journey Optimizer dokumentationsstartsida.
* Skärmbilder för landningssidor och prenumerationsrapporter har uppdaterats. [Läs mer](../reports/live-report.md)
* En anteckning om att metoden Delete inte stöds i anpassade åtgärder har lagts till. [Läs mer](../action/about-custom-action-configuration.md)
* Länkar till instruktionsvideor har uppdaterats.
* The [E-postkonfiguration](../configuration/about-subdomain-delegation.md), [Meddelandeförinställningar](../configuration/channel-surfaces.md) och [Konfigurera landningssidor](../landing-pages/lp-subdomains.md) -avsnitten har omstrukturerats för att bli enklare att läsa.
* Avsnittet för URL-spårning har uppdaterats och förbättrats med exempel. [Läs mer](../email/email-settings.md#url-tracking)
* Ett nytt underavsnitt om hur du konfigurerar en e-postadress för vidarebefordran har lagts till. Observera att du inte kan göra det via användargränssnittet. [Läs mer](../email/email-settings.md#forward-email)

## April 2022 {#april-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Versionen från 22 april finns detaljerad i dokumentationen. [Läs mer](release-notes.md)
* The **reaktioner** sidan med händelsedokumentation har uppdaterats. [Läs mer](../building-journeys/reaction-events.md)
* Videoklippen för funktioner för beslutshantering har uppdaterats för att återspegla Journey Optimizer användargränssnitt. [Läs mer](../offers/get-started/starting-offer-decisioning.md)
* The **Kom igång med datauppsättningar** -avsnittet har förbättrats för att ge detaljerad information om hur du får åtkomst till och skapar datauppsättningar. [Läs mer](../data/get-started-datasets.md)
* Länkar till hjälplinjer och versionsinformation om produkten har lagts till i **Adobe Journey Optimizer Documentation** hemsida. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer.html)
* The **Skapa meddelandeförinställningar** anger nu att du inte kan fortsätta med att skapa förinställningar medan den valda IP-poolen är under utgåva (**[!UICONTROL Processing]** status) och har aldrig kopplats till den valda underdomänen. [Läs mer](../configuration/channel-surfaces.md#subdomains-and-ip-pools)
* Meddelandeförinställningarna **URL-spårning** -avsnittet har uppdaterats för att återspegla mindre ändringar i användargränssnittet. [Läs mer](../configuration/channel-surfaces.md#url-tracking)

## Mars 2022 {#march-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Mars 22-utgåvan finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* En ny sida om hur du kommer igång med AI-modeller har lagts till i **Offer decisioning** med en detaljerad beskrivning av [autooptimeringsmodell](../offers/ranking/auto-optimization-model.md), den algoritm som används och mer teknisk information. [Läs mer](../offers/ranking/ai-models.md)
* Sidan där testprofilen skapades har flyttats till  **Segment, profiler och identitet** -avsnitt. [Läs mer](../segment/creating-test-profiles.md)
* Ett exempel har lagts till om hur du lägger till ett uttryck som ett standardvärde i uttrycksredigeraren. [Läs mer](../building-journeys/expression/field-references.md#default-value)
* The **Skapa personaliserade erbjudanden** -avsnittet har omstrukturerats för förbättrad läsbarhet. [Läs mer](../offers/offer-library/creating-personalized-offers.md)
* Ett nytt avsnitt har lagts till för att beskriva den påverkan som ett byte av ett erbjudandes start- och/eller slutdatum kan ha på det här erbjudandets frekvensbegränsning. [Läs mer](../offers/offer-library/add-constraints.md#capping-change-date)
* The **Ändra de primära e-postadresserna** -avsnittet har uppdaterats för att återspegla ändringar i användargränssnittet. [Läs mer](../configuration/primary-email-addresses.md)

## Februari 2022 {#feb-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] 22 februari-utgåvan finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Dokumentationssidorna för funktionerna [replace](../building-journeys/functions/functionreplace.md#example_2) och [replaceAll](../building-journeys/functions/functionreplaceall.md#example) har uppdaterats med ytterligare information och exempel angående målparametern.
* Bästa praxis har lagts till på sidan [Operatorer](../building-journeys/expression/operators.md#important-notes).

## Januari 2022 {#january-2022}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version 22 av jan finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* The **Offer decisioning AI-rankningar** -avsnittet har uppdaterats med en mer detaljerad beskrivning av den automatiska optimeringsmodellen. [Läs mer](../offers/ranking/auto-optimization-model.md)
* Ett nytt avsnitt om schemakraven som behövs för att kunna skicka in händelsetyper när en rankningsstrategi används har lagts till. [Läs mer](../offers/data-collection/schema-requirement.md)
* Avsnittet som är relaterat till [!DNL Journey Optimizer] personaliseringsfunktionerna har omstrukturerats för att bli lättare att läsa. [Läs mer](../personalization/personalize.md)
* The **Skapa meddelandeförinställningar** har delats upp i flera avsnitt för att bli tydligare. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)
* The **Hantering av avanmälan** har klargjorts och omorganiserats något. [Läs mer](../privacy/opt-out.md#opt-out-management)
* The **Infoga länkar** -avsnittet har uppdaterats för att återspegla de senaste ändringarna i användargränssnittet. [Läs mer](../email/message-tracking.md#insert-links)

+++

+++ 2021

## November 2021 {#november-2021}

* En fullständig beskrivning av **avancerad uttrycksredigerare** som används i resor finns nu tillgängliga. [Läs mer](../building-journeys/expression/expressionadvanced.md)
* Ett nytt avsnitt om **Delegeringsmetod för CNAME-underdomän** har lagts till. [Läs mer](../configuration/delegate-subdomain.md#cname-subdomain-delegation)

## Oktober 2021 {#october-2021}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Okt &#39;21-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Tillagd **Funktionen Datum och tid** lista. [Läs mer](../personalization/functions/dates.md)
* Nytt **Komma igång-avsnitt per användarprofil**. Ta din egen väg för att nå dina mål snabbare! [Läs mer](../start/quick-start.md)
* Nytt **Redigera en meddelandeförinställning** -avsnitt. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface)
* Nytt **Redigera en PTR-post** -avsnitt. [Läs mer](../configuration/ptr-records.md#edit-ptr-record)
* Nytt **Inaktivera en meddelandeförinställning** -avsnitt. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface#deactivate-a-surface)
* Nya begränsningar i **Utvecklarhandbok för API för beslutshantering** begränsningar för erbjudandet som inte stöds av mobilen [!DNL Experience Edge] arbetsflöden. [Läs mer](../offers/api-reference/offers-api/personalized-offers/create.md#limitations)
* Nytt **Skapa simuleringar** -avsnitt. [Läs mer](../offers/offer-activities/simulation.md)
* Uppdaterat **Lägg till beslutsomfattningar** -avsnitt. [Läs mer](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)
* Uppdaterat **Definiera innehåll för dina representationer** avsnitt, inklusive ett nytt [undersektion](../offers/offer-library/creating-personalized-offers.md#custom-text) om hur man definierar och personaliserar egen text. [Läs mer](../offers/offer-library/creating-personalized-offers.md#content)

## September 2021 {#september-2021}

* Följande funktionssidor har uppdaterats: [sethours](../building-journeys/functions/functionsethours.md), [getListItem](../building-journeys/functions/functiongetlistitem.md), [inSegment](../building-journeys/functions/functioninsegment.md)

* Följande funktioner har lagts till: [filter](../building-journeys/functions/functionfilter.md), [intersect](../building-journeys/functions/functionintersect.md), [toDateOnly](../building-journeys/functions/functiontodateonly.md)

* Datumtypen dateOnly har lagts till i dokumentationen för utrycksredigering. [Läs mer](../building-journeys/expression/data-types.md)

* Tillagda uppgifter om anpassad cachelängd på åtgärd. [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode)

* Tillagd information om standardportar för anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)

* Lagt till information om flera användningsfall för affärshändelser. [Läs mer](../event/about-creating-business.md#multiple-business-events)

* Tillagda vanligt förekommande exempel till frågor om Journey Step Events i Data Lake. [Läs mer](../reports/query-examples.md)

* Lagt till en ny **Begränsningar** sida. [Läs mer](../start/guardrails.md)

* Förbättrade **Snabbstart** sida med steg för olika profiler. [Läs mer](../start/quick-start.md)

* Nu gäller alla funktioner för beslutshantering som beskrivs i det särskilda avsnittet även för Adobe Experience Platform-användare som använder Offera decisioningens programtjänst. [Läs mer](../offers/get-started/starting-offer-decisioning.md)

* Ett underavsnitt lades till för att förtydliga skillnaderna mellan att använda segment kontra beslutsregler när en begränsning tillämpas för att begränsa urvalet av erbjudanden för en viss placering. [Läs mer](../offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* Specifika exempel på rankningsformler har lagts till för att illustrera exempel på verkliga användningsområden. [Läs mer](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)

* Ett underavsnitt om hur du redigerar IP-pooler har lagts till. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)

## Augusti 2021 {#august-2021}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Versionen från 21 augusti finns detaljerad i dokumentationen. [Läs mer](release-notes.md)
* Uppdaterade behörigheter för beslutshantering. [Läs mer](../administration/ootb-product-profiles.md)
* Uppdaterade skärmbilder för e-postdesigner med det senaste användargränssnittet.
* Konfigurationsproceduren för anpassade åtgärder med dynamiska URL-sökvägar och dynamiska huvuden har uppdaterats. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* Ett avsnitt om tillgänglighetsfunktioner och genvägar har lagts till. [Läs mer](../start/user-interface.md#accessibility)
* Ett avsnitt om metoder för segmentutvärdering har lagts till. [Läs mer](../segment/about-segments.md#evaluation-method-in-journey-optimizer)
* Anteckningar har lagts till i avsnitten om Suppression-listan, Tillåtelselista och e-post, global/liverapport, för att ange att profiler med statusen Inaktiverad och Inte tillåten ska uteslutas från e-postrapporten Skickade mått. [Läs mer](../reports/global-report.md)
* Ett nytt avsnitt har lagts till som beskriver hur du hämtar e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. [Läs mer](../configuration/allow-list.md#reporting)
* Avsnittet Aktivera tillåtelselista har uppdaterats. [Läs mer](../configuration/allow-list.md#enable-allow-list)
* Avsnittet Monitor-meddelandets förinställningar har uppdaterats med orsaker till att förinställningarna inte kunde skapas och information om sådana fel. [Läs mer](../configuration/channel-surfaces.md#monitor-channel-surfaces)
* Uppdaterat och ändrat namn på avsnittet för återförsöksperiod för att återspegla det faktum att du nu kan ändra inställningen för återförsök via e-post i meddelandeförinställningarna. [Läs mer](../configuration/retries.md#retry-duration)
* Ett nytt avsnitt har lagts till som beskriver hur du infogar en länk för att välja bort ett enstaka klick i e-postinnehåll. [Läs mer](../privacy/opt-out.md#one-click-opt-out-link)
* Uppdaterade avsnittet Delegera en underdomän med mer detaljerad information om valideringsprocessen som utfördes av Adobe. [Läs mer](../configuration/delegate-subdomain.md#subdomain-validation)
* Ett avsnitt har lagts till som beskriver hur du manuellt lägger till e-postadresser och domäner i listan över inaktiveringar. [Läs mer](../configuration/manage-suppression-list.md#add-addresses-and-domains)
* Uppdaterade [Åtkomst till listan över inaktiveringar](../configuration/manage-suppression-list.md#access-suppression-list) och [Försök igen](../configuration/retries.md) -avsnitt som återspeglar det nya användargränssnittet.
* Det nya flödet för att lägga till och konfigurera representationer när ett erbjudande skapas har dokumenterats. [Läs mer](../offers/offer-library/creating-personalized-offers.md#representations)

## Juli 2021 {#july-2021}

* Alla nya funktioner och förbättringar som ingår [!DNL Journey Optimizer] Version från juli 210 finns utförlig i dokumentationen. [Läs mer](release-notes.md)
* Lagt till direktlänkar till Experience Platform-tjänstdokumentation i [!DNL Journey Optimizer] hemsida och innehållsförteckning
* Nya landningssidor för Experience Platform-tjänster finns tillgängliga på [!DNL Journey Optimizer]
* Lagt till länkar till [!DNL Journey Optimizer] produktbeskrivning på startsidan
* Lagt till självstudievideor på flera sidor
* Optimerade startsidesbilder
* Avsnittet&quot;Meddelandespårning&quot; har flyttats, förbättrats och bytt namn till&quot;Lägg till länkar och spåra meddelanden&quot;. [Läs mer](../email/message-tracking.md)
* Ett underavsnitt har lagts till på spegelsidor. [Läs mer](../email/message-tracking.md#mirror-page)
* Namnet på&quot;erbjudandeaktiviteter&quot; har ändrats till&quot;beslut&quot; och&quot;beslut&quot; till&quot;beslutsomfattningar&quot; i dokumentation och skärmar. [Läs mer](../offers/get-started/starting-offer-decisioning.md)
* Nytt användningsfall: [personalisera ett meddelande med hjälpfunktioner](../personalization/personalization-use-case-helper-functions.md)
* Dokumentationen för Läs segment har uppdaterats för att återspegla materialiserad segmentpåverkan. [Läs mer](../building-journeys/read-segment.md)
* Uppdaterade begränsningar för resan. [Läs mer](../start/guardrails.md)
* Markeringen Konfigurera erbjudanden uppdaterades i avsnittet Beslut. [Läs mer](../offers/offer-activities/configure-offer-selection.md)
* En varning har lagts till som anger att händelsebaserade erbjudanden för närvarande inte stöds. [Läs mer](../offers/offer-library/creating-personalized-offers.md#eligibility)
* Dokumenterade beslutsledningens nya **[!UICONTROL Overview]** -fliken. [Läs mer](../offers/get-started/user-interface.md#overview)
* Nya avsnitt har lagts till för att beskriva de åtgärder som är tillgängliga från erbjudandet och beslutslistorna: [Erbjudandelista](../offers/offer-library/creating-personalized-offers.md#offer-list) och [Beslutslista](../offers/offer-activities/create-offer-activities.md#decision-list).

+++
