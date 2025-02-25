---
solution: Journey Optimizer
product: journey optimizer
title: Dokumentationsuppdateringar
description: Läs om de senaste dokumentationsuppdateringarna
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 83c8f206-bce3-4cc8-94a3-575ec1d999bc
source-git-commit: 99099cb6b705cb5a7b97652154c42f0565fdfdb9
workflow-type: tm+mt
source-wordcount: '6144'
ht-degree: 12%

---

# Dokumentationsuppdateringar {#latest-updates}

På den här sidan visas alla de senaste uppdateringarna i [!DNL Journey Optimizer]-dokumentationen.


## Februari 2025 {#feb-2025}

* Stegen för att skapa dina första resor har beskrivits och länkar till dokumentationsavsnitt har lagts till. [Läs mer](../building-journeys/journey-gs.md)
* En ny sida finns nu tillgänglig för att beskriva resorna i användargränssnittet för resehantering. [Läs mer](../building-journeys/journey-ui.md)
* Dokumentationen för **[!UICONTROL Send-Time optimization]** och dess relaterade vanliga frågor har uppdaterats, förbättrats och flyttats till en ny dedikerad sida. [Läs mer](../building-journeys/send-time-optimization.md)
* Nya skyddsutkast har lagts till för resehändelser. [Läs mer](../start/guardrails.md#events-g)
* Den inbyggda sidan för kanalåtgärder har omstrukturerats. [Läs mer](../building-journeys/journeys-message.md)
* Garantier och begränsningar har lagts till i avsnitten om beslutsfattande och beslutshantering.
   * [Avgörande av skyddsräcken och begränsningar](../experience-decisioning/decisioning-guardrails.md)
   * [Garantier och begränsningar för beslutshantering](../offers/decision-management-guardrails.md)
* Ett nytt avsnitt om kontextdata har lagts till i dokumentationen för beslutshanteringen. Där finns information om hur man utnyttjar kontextdata i beslutsmotorn, t.ex. för att utforma en beslutsregel som kräver att det aktuella vädret ska vara minst 80 grader vid den tidpunkt då beslutsbegäran görs. [Läs mer](../offers/context-data.md)

## Januari 2025 {#jan-2025}

* Ett nytt avsnitt om alternativet **[!UICONTROL Execution address]** i e-postkonfigurationen har lagts till. Den primära adressen definieras på sandlådenivå, men standardinställningen kan åsidosättas för en viss e-postkonfiguration. [Läs mer](../email/email-settings.md#execution-address)

* Sidan **Kom igång med leverans** har uppdaterats med möjligheten att skapa arbetsflöden för IP-värmare direkt från användargränssnittet. [Läs mer](../reports/deliverability.md#reputation)

* Avsnittet **Huvudparametrar** har uppdaterats för att återspegla de nya etiketterna och ändringarna i användargränssnittet. [Läs mer](../email/email-settings.md#email-header)

* Avsnittet **Vidarebefordra e-post** har uppdaterats för att ange att alla e-postmeddelanden som skickas till adressen **Från e-post** vidarebefordras till e-postadressen för vidarebefordran. Om inget vidarebefordrande e-postmeddelande anges, ignoreras dessa e-postmeddelanden. [Läs mer](../email/email-settings.md#forward-email)

* Den maximala storleken på kontextuella attribut som skickas till en API-utlöst kampanjbegäran har uppdaterats till 200 kB. [Läs mer](../campaigns/api-triggered-campaigns.md#contextual)

* Ett nytt avsnitt har lagts till på sidan **Hantera fragment** som beskriver hur du lägger till nya attribut i ett live-fragment. Hela sidan har också förbättrats. [Läs mer](../content-management/manage-fragments.md#adding-new-attributes)

* Ett avsnitt,&quot;Guardsändningar &amp; begränsningar&quot;, har lagts till i dokumentationen för verktygen för konflikthantering och prioritering. [Läs mer](../conflict-prioritization/gs-conflict-prioritization.md)

* Ett nytt heltäckande användningsexempel har lagts till för att presentera alla steg som behövs för att använda Decisionering i innehållsexperiment med den kodbaserade [!DNL Journey Optimizer]-upplevelsekanalen. [Läs mer](../experience-decisioning/experience-decisioning-uc.md)

* Sidan **Konfigurera e-postinställningar** har delats upp i flera undersidor för förbättrad läsbarhet, inklusive nya fristående sidor som är dedikerade till [Avsluta prenumeration](../email/list-unsubscribe.md), [Huvudparametrar](../email/header-parameters.md) och [URL-spårning](../email/url-tracking.md).

## December 2024 {#nov-2024}

* En anteckning har lagts till för att hjälpa till att felsöka ett eventuellt felmeddelande när du gör ett API-anrop för att aktivera datauppsättningar för personalisering med hjälp av Adobe Experience Platform-data. [Läs mer](../personalization/lookup-aep-data.md)

## Oktober 2024 {#oct-2024}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] oktoberversionen 24 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Alla kommunikationskanaler som är tillgängliga i [!DNL Journey Optimizer] grupperas nu i ett dedikerat avsnitt i dokumentationen. [Läs mer](../channels/gs-channels.md)
* Sidan **Konfigurera din kodbaserade upplevelse** har förbättrats för att göra processen tydligare, inklusive avsnittet som förklarar vad en yt-URI är. [Läs mer](../code-based/code-based-configuration.md)
* Sidan **Skapa webbkanalskonfiguration** har uppdaterats för att klargöra stegen när du skapar en sidmatchningsregel, som även gäller för kodbaserad upplevelsekonfiguration. [Läs mer](../web/web-configuration.md#web-page-matching-rule)
* En anteckning om det kommande TTL-skyddsutkastet (time-to-live) för systemgenererade datauppsättningar har lagts till. [Läs mer](../data/get-started-datasets.md)
* Ett nytt avsnitt har lagts till som beskriver hur du förhandsgranskar dina kodbaserade, personaliserade upplevelser direkt i webbläsaren eller på dina mobila enheter, med alternativet **Förhandsgranska på enhet** när du simulerar innehåll under en resa eller en kampanj. [Läs mer](../code-based/test-code-based.md#preview-on-device)
* En ny sida har lagts till om hur du använder anpassade uppladdningsmålgrupper för beslut. [Läs mer](../offers/custom-upload-decisioning.md)
* En ny sida har lagts till för att presentera beslutsmöjligheterna i Journey Optimizer. [Läs mer](../experience-decisioning/gs-decision.md)
* Garantier och begränsningar har lagts till i beslutsdokumentationen. [Läs mer](../experience-decisioning/gs-experience-decisioning.md#guardrails)

## September 2024 {#sept-2024}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer], avsnitt 24, har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Lagt till ett avsnitt om hantering av reseåterförsök. [Läs mer](../building-journeys/read-audience.md#read-audience-retry)
* Vanliga frågor om begränsning/begränsning av begränsning för anpassade åtgärder har uppdaterats för att ange standardregel för begränsning. [Läs mer](../configuration/external-systems.md#faq)
* Avsnittet Kontroll av åtkomst har uppdaterats med behörigheter för innehållsgeneratorn i AI Assistant. [Läs mer](../administration/high-low-permissions.md#ai-permission)
* En video om AI Assistant Content Generator för e-postgenerering har lagts till. [Läs mer](../content-management/generative-email.md#video)


## Augusti 2024 {#aug-2024}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] augusti 24 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Prestandaskyddsutkast för Beslutshantering har uppdaterats för att omnämna leveranshastigheter med eller utan Edge Segmentation. [Läs mer](../start/guardrails.md#decision-management)
* Resegarantierna har uppdaterats. [Läs mer](../start/guardrails.md#journeys-guardrails-journeys)


## Juli 2024 {#july-2024}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] juliversionen 24 har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Ett exempel på hur man personaliserar ett e-postmeddelande med information om hälsoplaner och recept har lagts till. [Läs mer](../personalization/perso-uc-plan-prescriptions.md)

## Juni 2024 {#june-2024}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 24 juni har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* En anteckning om användningen av sammanfogningsprinciper i resor har lagts till på [den här sidan](../building-journeys/journey-properties.md#merge-policies).
* Sidan om hur du konfigurerar en **Wait**-aktivitet i en resa har organiserats om och förbättrats. [Läs mer](../building-journeys/wait-activity.md)
* En ny sida har skapats för att beskriva resans egenskaper. [Läs mer](../building-journeys/journey-properties.md)

## Maj 2024 {#may-2024}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] maj 24-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Avsnittet om utsädeslistor har uppdaterats när det gäller återkommande resor. [Läs mer](../configuration/seed-lists.md#use-seed-list)
* Avsnittet om externa datakällor har uppdaterats. [Läs mer](../datasource/external-data-sources.md#custom-authentication-access-token)
* Tidsgränsen för den globala resan på 30 dagar har lagts till på sidan Guardrail och prefix. [Läs mer](../start/guardrails.md#journeys-guardrails-journeys)
* Avsnittet om integreringen av Adobe Campaign v7/v8 har uppdaterats med information om etablering. [Läs mer](../action/acc-action.md#access)
* Uttrycksredigeraren som används för att anpassa innehåll har bytt namn i dokumentationen till&quot;personaliseringsredigerare&quot; för att tydligt skilja det från [reseuttrycksredigeraren](../building-journeys/expression/expressionadvanced.md). [Läs mer](../personalization/personalization-build-expressions.md)

## April 2024 {#april-2024}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 24 april finns detaljerade i dokumentationen. [Läs mer](release-notes.md#apr-2024)
* Konfigurationsstegen för meddelanden i programmet har beskrivits. [Läs mer](../in-app/inapp-configuration.md)
* Dokumentationen för [API:er för offertbeslut](../offers/api-reference/offer-delivery-api/decisioning-api.md) och [API:er för gruppbeslut](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md) har uppdaterats.
* Information om hantering av edge- och navregioner har lagts till i beslutsdokumentationen när frekvenscappning används med Edge Decisioning API. [Läs mer](../offers/offer-library/add-constraints.md#frequency-capping)
* Information har lagts till om att skapa en identitet med anpassade namnutrymmen när du arbetar med API-utlösta kampanjer. [Läs mer](../campaigns/api-triggered-campaigns.md)
* Skärmfotona har uppdaterats för att återspegla den förbättrade arbetsytan på resan.
* Namnbegränsningar har uppdaterats på följande sida: [Konfigurera en enhetshändelse](../event/about-creating.md), [Konfigurera en affärshändelse](../event/about-creating-business.md#gs-business-events), [Konfigurera en anpassad åtgärd](../action/about-custom-action-configuration.md#configuration-steps), [Externa datakällor](../datasource/external-data-sources.md)
* En anteckning har lagts till om tillgängligheten för tidsoptimering för sändning. [Läs mer](../building-journeys/send-time-optimization.md)
* Ett nytt exempel på teknisk användning har lagts till om hur du skapar en anpassad åtgärd för att skicka data till Experience Platform. [Läs mer](../building-journeys/custom-action-aep.md)

## Mars 2024 {#march-2024}

* Ett avsnitt med vanliga frågor och svar har lagts till som åtgärdar vanliga frågor om användningen av målgruppssammansättning och anpassade målgrupper för uppladdning i Journey Optimizer. [Läs mer](../audience/about-audiences.md#faq)
* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] mars 24-utgåvan finns detaljerade i dokumentationen. [Läs mer](release-notes.md#mar-2024)
* Sidan om profilingångshantering har förbättrats. [Läs mer](../building-journeys/entry-management.md)
* Felsökningsinformation har lagts till på sidan Varningar. [Läs mer](../reports/alerts.md#alert-troubleshooting)
* Information om aktiviteten Vänta har lagts till på sidan om reserapporter. [Läs mer](../reports/sharing-overview.md)
* För Resor i testläge har följande genvägar inaktiverats:
   * T: Kortkommando för att aktivera eller inaktivera testläget.
   * E: Kortkommando som används för att utlösa en händelse i en händelsebaserad resa.
   * P: Kortkommando för att utlösa en händelse i en målgruppsbaserad resa där alternativet Enstaka profil i taget är aktiverat.
   * L: Kortkommando för att visa testloggarna.
* Regelsidan för meddelandefrekvens har uppdaterats med ett nytt underavsnitt om dagligt frekvenstak, som är tillgängligt på begäran utöver vecko- eller månadsvisa capping.
* Sidan Arbeta med profiler för samtycke har förbättrats och uppdaterats med användbara länkar till Experience Platform-dokumentationen. [Läs mer](../action/consent.md)
* Ett nytt avsnitt har lagts till för att återspegla att du kan visa HTML mallar för e-postinnehåll som miniatyrbilder i stödrastervisningsläget (begränsad tillgänglighet). [Läs mer](../content-management/content-templates.md#template-thumbnails)
* Ett nytt avsnitt har lagts till på sidan Leverans för att förklara vilka feedback-slingor som är och hur de kan användas. [Läs mer](../reports/deliverability.md#feedback-loops)
* En anteckning har lagts till i avsnittet Skapa anpassade erbjudanden för att ange att storleken på ett erbjudande inklusive alla dess representationer inte får överstiga 300 kB. [Läs mer](../offers/offer-library/creating-personalized-offers.md#create-offer)

## Februari 2024 {#feb-2024}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] februari 24-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md#feb-2024)
* Integrationen mellan Journey Optimizer och Workfront har lagts till på integreringssidan. [Läs mer](../integrations/ajo-integrations.md)
* Information har lagts till om hur man personaliserar offerternas representationer baserat på kontextdata. [Läs mer](../offers/offer-library/add-representations.md#context-data)
* Sidan med skyddsförslag har uppdaterats med en anteckning om anpassade åtgärder som endast stöder JSON-format när nyttolasterna för begäran eller svar används. [Läs mer](../start/guardrails.md#custom-actions-g)
* Ytterligare information har lagts till om den grundläggande autentiseringstypen i externa datakällor. [Läs mer](../datasource/external-data-sources.md)
* En anteckning har lagts till för att tydligt skilja [reseuttrycksredigeraren](../building-journeys/expression/expressionadvanced.md) från [personaliseringsredigeraren](../personalization/functions/functions.md).
* Listan med funktioner i den avancerade uttrycksredigeraren har uppdaterats. [Läs mer](../building-journeys/expression/functions.md)
* Sidan i funktionen Dela har uppdaterats. [Läs mer](../building-journeys/functions/functioninaudience.md)
* Information har lagts till om effekten av push-meddelanden för anmälan eller avanmälan av meddelanden i appen. [Läs mer](../in-app/create-in-app.md)
* Regelsidan för meddelandefrekvens har uppdaterats för att återspegla de varaktighetsalternativ som är tillgängliga i användargränssnittet (varje vecka eller månad).
* Avsnittet Redigera en PTR-post har uppdaterats för att klargöra att PTR-poster inte kan skapas manuellt och att du måste redigera PTR-poster för att tilldela dem nya underdomäner. [Läs mer](../configuration/ptr-records.md#edit-ptr-record)

## Januari 2024 {#jan-2024}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 24 januari finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Ett skyddsräcke om resestorleken har lagts till. [Läs mer](../start/guardrails.md#journeys-guardrails-journeys)
* Resetimeout-hantering har beskrivits [i följande avsnitt](../building-journeys/journey-properties.md#global_timeout).
* Journey Optimizer [dokumentationsstartsida](../../ajo-home.md) har gjorts om.
* Rekommendationer om aktiviteten Uppdatera profiler har lagts till. [Läs mer](../building-journeys/update-profiles.md)
* Information har lagts till om beteendet för tidsgränser för händelseaktiviteter under resor. Om ingen händelse tas emot under den angivna tidsgränsen fortsätter den enskilda personen resan om ingen tidsgräns anges. [Läs mer](../building-journeys/general-events.md#events-specific-time)
* Krav för kanalkonfiguration i programmet har uppdaterats med en anteckning om användningen av en anpassad sammanfogningsprincip för datauppsättning. [Läs mer](../in-app/inapp-configuration.md)
* Mer information om hur du hanterar samlingar i en anpassad åtgärd har lagts till. [Läs mer](../action/action-response.md#exp-syntax).
* En länk till [schemaordlistan för Adobe Journey Optimizer](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html) har lagts till på startsidan.
* En inaktuell referens till AJO Message-resursen har tagits bort från listan över tillgängliga resurser i granskningsloggen. När en uppdatering görs av ett meddelande under en resa skapas en **Resa**-logg. [Läs mer](../privacy/audit-logs.md)
* Ytterligare rekommendationer har lagts till om användningen av aktiviteten **Läs målgrupp**. [Läs mer](../building-journeys/read-audience.md#must-read)
* Sidan Kom igång med Adobe Experience Platform målgrupper har förbättrats med en lista över metoder för målgruppsgenerering. [Läs mer](../audience/about-audiences.md)
* Bästa metoder har lagts till när du väljer en slutpunkt att rikta in dig på med en anpassad åtgärd. [Läs mer](../action/about-custom-action-configuration.md)
* En anteckning har lagts till för att meddela användare att händelser inte kan utlösas från externa system med ett API. [Läs mer](../building-journeys/testing-the-journey.md#important-notes)
* Information om funktionen **currentActionField** har lagts till i listan med [samlingshanteringsfunktioner](../building-journeys/expression/collection-management-functions.md). Ett uttrycksexempel som utnyttjar funktionen har lagts till på sidan [Använd API-anropssvar i anpassade åtgärder](../action/action-response.md).
* Uppdatera anpassat autentiseringsdokument med avseende på cachevaraktighet. [Läs mer] (../datasource/external-data-sources.md)
* Stöd för `<listObject>` har ändrats i flera funktioner.
* Uppdatera parametern **duration** i funktionen `toString`. [Läs mer](../building-journeys/functions/functiontostring.md)
* För vissa externa datakällor bör du använda anpassade åtgärder.
* Syntaxen för händelsefältet har uppdaterats. Följande syntax är inaktuell `@(my_event.myfield}` och ersatt med `@event{my_event.myfield}`. [Läs mer](../building-journeys/expression/field-references.md)

+++ 2023

## November 2023 {#nov-2023}

* Skyddsplanen som begränsar alla anpassade åtgärder har ändrats från 150 000 anrop över 30 sekunder till 300 000 anrop över en minut. Dessutom gäller inte längre standardfästningen för varje slutpunkt. Den utförs nu per värd och per sandlåda. Om du till exempel har två slutpunkter med samma värd (till exempel: `https://www.adobe.com/endpoint1` och `https://www.adobe.com/endpoint2`) i en sandlåda, gäller det för alla slutpunkter under adobe.com. &quot;endpoint1&quot; och &quot;endpoint2&quot; har samma begränsningskonfiguration och om en slutpunkt når gränsen påverkas den andra slutpunkten. [Läs mer](../action/about-custom-action-configuration.md)
* En ny status för e-postkampanjer har lagts till i listan över kampanjstatus. [Läs mer](../campaigns/modify-stop-campaign.md#campaign-statuses-and-alerts-statuses)
* Avsnittet Kom igång med Adobe Experience Platform målgrupper har uppdaterats för att återspegla tillgängliga metoder för målgruppsutvärdering och hur du väljer dem. [Läs mer](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)
* Ett nytt underavsnitt har lagts till för att specificera vilka händelser som ska undvikas när du skapar en målgrupp om du använder utvärderingsmetoden för direktuppspelningssegmentering. [Läs mer](../audience/about-audiences.md#streaming-segmentation-events-guardrails)

## Oktober 2023 {#oct-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 23 oktober finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* GIF-filer har lagts till för att illustrera vissa nyckelfunktioner, som: [Innehållsmallar](../content-management/content-templates.md), [Fragment](../content-management/fragments.md), [Beräknade attribut](../audience/computed-attributes.md), [Direktutskick](../direct-mail/get-started-direct-mail.md), [Taggar](../start/search-filter-categorize.md#tags), [Optimeringsmodeller för beslutshantering](../offers/ranking/personalized-optimization-model.md), [API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md) och [ 4}Experimentera med innehåll](../content-management/content-experiment.md).
* Processen för att skapa scheman har uppdaterats för att återspegla de senaste uppdateringarna i användargränssnittet, som följer med Adobe Experience Platform-ändringar. [Läs mer](../audience/creating-test-profiles.md)
* Garantier för beslutshantering har lagts till på sidan Guardsutkast och begränsningar. [Läs mer](../start/guardrails.md#decision-management)
* Avsnittet med rubrikparametrar har uppdaterats för att återspegla hur utomstående meddelanden och utmaningssvar hanteras (de tas emot på **[!UICONTROL Error email]**). [Läs mer](../email/email-settings.md#email-header)
* Ett nytt avsnitt om hur du förhandsgranskar och testar innehåll har skapats. [Läs mer](../content-management/preview-test.md)
* Sidan Implementera enkelsidiga program har flyttats till dokumentationen för Adobe Experience Platform Web SDK. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-spa-implementation.html){target="_blank"}
* Facksektionen har uppdaterats för att återspegla de etikettändringar som har att göra med begränsningen av erbjudanden i beslutsgränssnittet. [Läs mer](../offers/offer-library/add-constraints.md#capping)
* Alternativet Lägg till dynamiskt innehåll i e-postmeddelanden har uppdaterats med information om hur du tar bort en variant. [Läs mer](../personalization/dynamic-content.md#emails)
* Exemplet för capping &amp; Throttling-konfigurationer har uppdaterats. [Läs mer](../configuration/external-systems.md)
* Begränsningen för skalära arrayer har tagits bort från avsnittet för externa datakällor. [Läs mer](../datasource/external-data-sources.md)
* Flerkanalsanvändningen har uppdaterats. [Läs mer](../building-journeys/journeys-uc.md)
* Dokumentationsuppsättningen för Journey Optimizer har uppdaterats för att återspegla den nya processen för att skapa Experience Platform-scheman.

## September 2023 {#september-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 23 september har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* En ny sida har lagts till med bästa praxis för skalning och vägledning om hur du sammanfogar bilder i realtid. [Läs mer](../start/best-practices.md)

  <!--  * The maximum wait duration has been changed from 30 to 29 days. [Read more](../building-journeys/wait-management.md) -->

* Ett avsnitt med vanliga frågor och svar har lagts till för optimering av sändningstid. [Läs mer](../building-journeys/journeys-message.md#faq-send-time)
* En anteckning har lagts till för målgruppsklassificeringsaktiviteten. Det kan ta upp till 10 minuter att vara aktiv och lyssna på profiler som kommer in eller lämnar publiken. [Läs mer](../building-journeys/audience-qualification-events.md#important-notes-segment-qualification)
* En lista över begränsningar som ska vara medveten om när man skapar beslutsregler har lagts till i dokumentationen för beslutshantering. [Läs mer](../offers/offer-library/creating-decision-rules.md)
* Länkar till åtkomstkontrollsdokumentation har uppdaterats. [Läs mer](../administration/permissions.md)
* Förutsättningar för kanaler i appen har uppdaterats med information om Adobe Experience Platform Data Collection. [Läs mer](../in-app/inapp-configuration.md)
* Vissa uttryck som presenteras i rankningsformelexempel har uppdaterats för att undvika valideringsfel. [Läs mer](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)
* En varning har lagts till i avsnittet Definiera beslutsomfattningar för att ange att om AI-modellen används i en utvärderingskriteriegrupp måste alla utvärderingskriterier i den gruppen använda AI-rangordningsmetoden med samma specifika AI-modell. Dessutom kan endast en grupp av utvärderingskriterier använda AI-modellen. [Läs mer](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

## Augusti 2023 {#august-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] augusti 23 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Anteckningen om **hantering av autentiseringscache** under resan har uppdaterats för att visa i detalj att token inte delas mellan olika resor. [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode)
* Sidan om resan **hantering av inträde** har uppdaterats för att förtydliga beteendet. [Läs mer](../building-journeys/entry-management.md)
* Erbjudandebeslut för **exportdatamängder** är nu aktiverat som standard. Anteckningen om det tidigare beteendet har tagits bort.  [Läs mer](../offers/export-catalog/get-started-export.md)
* Olika **kampanjrapportmått** har bytt namn i både Live- och Global-rapporter. [Läs mer](../reports/campaign-live-report.md)
* Ett nytt avsnitt har lagts till om krav för innehållsexperiment för webbkanalen. [Läs mer](../web/web-prerequisites.md#experiment-prerequisites)
* En varning har lagts till på sidan **Arbeta med innehållsmallar** för att ange att spårning inte stöds när du testar mallar för e-postinnehåll. Om du vill testa spårning måste du använda innehållsmallen i ett e-postmeddelande och skicka ett korrektur. [Läs mer](../content-management/content-templates.md#test-template)
* Flera varningar har lagts till i avsnittet **Skapa och publicera landningssidor** för att ange att du inte kan komma åt din landningssida genom att kopiera och klistra in URL-adressen som angavs när sidan skapades i en webbläsare, även om den publicerades. I stället kan du testa den med förhandsvisningsfunktionen. [Läs mer](../landing-pages/create-lp.md)
* Ett nytt avsnitt har lagts till om hur du **hanterar samtycke** för direktpostkanalen. [Läs mer](../direct-mail/test-send-direct-mail.md)

## Juli 2023 {#july-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 23 juli har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Dokumentationssidan för vänteaktivitet har förbättrats med ytterligare information och bästa praxis för global tidsgräns och återinträde. [Läs mer](../building-journeys/wait-activity.md)
* Sidan om hantering av inträde har förbättrats. [Läs mer](../building-journeys/entry-management.md)
* Ytterligare information om begränsningsgraden finns i dokumentationen om målgruppsaktivitet. [Läs mer](../building-journeys/read-audience.md)
* Ytterligare information om återförsök har lagts till. [Läs mer](../start/guardrails.md#general-actions-g)
* Avsnittet **Implementera personaliseringsmedgivande** har uppdaterats för att beskriva hur du manuellt framtvingar personaliseringsmedgivande i kampanjer: du kan använda segmentregelbyggaren för att skapa en målgrupp som innehåller avanmälningsprofiler eller lägga till en delad aktivitet i ett dispositionsarbetsflöde. [Läs mer](../privacy/opt-out.md#opt-out-expression-editor)

## Juni 2023 {#june-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 23 juni har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Information har lagts till om förhållandet för ignoreringsfrekvens i fönstret Resursöversikt. [Läs mer](../building-journeys/journey-gs.md#journey-access)
* En anteckning har lagts till med de steg som ska följas om du ändrar schemat med nya uppräkningsvärden efter att ha skapat händelsen [Läs mer](../event/about-creating.md)
* En rekommendation har lagts till att använda travelVersionID i stället för travelVersionName när resor efterfrågas. [Läs mer](../reports/sharing-common-fields.md#journeyversionid-field)
* Ytterligare exempel på ordningen för utvärderingskriterier har lagts till i avsnittet **Skapa beslut** för att illustrera fall där flera kriterier och flera beslutsomfattningar används. [Läs mer](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* Dokumentationen för beslutshantering har klargjorts med en anteckning som anger att åtkomstkontrollen på objektnivå inte är tillgänglig för dynamiska samlingar. [Läs mer](../offers/offer-library/creating-collections.md)

## Maj 2023 {#may-2023}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] maj 23-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* En ny sida har lagts till som beskriver hur du konfigurerar den underdomän som ska användas för att publicera innehåll från Adobe Experience Manager Assets Essentials i dina webbupplevelser. [Läs mer](../web/web-delegated-subdomains.md)
* Ett nytt underavsnitt har lagts till som förklarar hur du lägger till personaliserade spårningsparametrar i URL:er i e-post-Designer. [Läs mer](../email/message-tracking.md#url-tracking)
* Ett nytt avsnitt har lagts till som beskriver hur du kan säkerställa att valet av de kunder som avstår från att använda sina profildata för personalisering respekteras. [Läs mer](../privacy/opt-out.md#opt-out-personalization)
* En anteckning har lagts till om hur du använder internationella specialtecken i URL:er som ingår i e-postinnehållet. [Läs mer](../email/message-tracking.md#insert-links)
* Behörigheten som krävs för att testa och publicera landningssidor har lagts till. [Läs mer](../landing-pages/create-lp.md)
* En anteckning har lagts till om Adobe Experience Platform-slutpunkter som behövs för att dina anpassade händelser ska kunna räknas med i frekvensbegränsningen för beslutshantering. [Läs mer](../offers/data-collection/schema-requirement.md#track-custom-events)

## April 2023 {#apr-2023}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 23 april finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* En anteckning har lagts till som anger att inbyggda åtgärder inte kan tas bort. [Läs mer](../start/guardrails.md#custom-actions-g)
* Information har lagts till om serviceEvents och ett frågeexempel för att kontrollera informationen om en serviceEvent. [Läs mer](../reports/query-examples.md#common-queries)
* En anteckning har lagts till som anger att du inte kan utföra frågor i tidsserier. [Läs mer](../building-journeys/condition-activity.md)
* Adobe Experience Manager Assets Essentials och Adobe Stock har lagts till på integreringssidan för flera lösningar. [Läs mer](../integrations/ajo-integrations.md)
* Varningen för e-postunderdomäner på flera nivåer som inte tillåts har tagits bort eftersom de nu stöds. [Läs mer](../configuration/delegate-subdomain.md)
* En anteckning har lagts till för att ange att om ändringar görs i ett erbjudandebeslut som används i en resa måste du avpublicera resan och publicera den på nytt. [Läs mer](../building-journeys/publishing-the-journey.md)
* Förklaring om hur du ser till att händelser räknas på rätt sätt i appningsräknaren har klargjorts i avsnittet för beslutshantering **Capping-händelse**. [Läs mer](../offers/offer-library/add-constraints.md#capping-event)
* Ett nytt avsnitt har lagts till på sidan **Ändra körningsadresser**. Det anger att det är möjligt att åsidosätta körningsfältet som angetts globalt i de avancerade parametrarna för resan, men åsidosättningen av e-postadressen ska bara användas för särskilda användningsfall. För det mesta är det värde som definieras som den primära adressen i **körningsfälten** det som ska användas. [Läs mer](../configuration/primary-email-addresses.md#journey-parameters)
* Avsnittet **URL-spårning** innehåller nu en lista och beskrivning av alla kontextattribut som kan anges för URL-spårning i en e-postkanalskonfiguration. [Läs mer](../email/email-settings.md#url-tracking)

## Mars 2023 {#march-2023}

* Journey Optimizer schemaordlista är nu tillgänglig. Du hittar den fullständiga listan med fält och attribut för varje schema.  [Läs mer](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)
* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] mars 23-utgåvan finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Ett steg har lagts till för att aktivera Adobe Analytics-event på dina resor. [Läs mer](../event/about-analytics.md)
* Ett nytt avsnitt har skapats i beslutshanteringshandboken om hur man samlar in feedback om beslut om erbjudanden i Adobe Experience Platform, inklusive vilka erbjudanden som visas och hur användare interagerar med dem. [Läs mer](../offers/data-collection/data-collection.md)
* Ett nytt underavsnitt har lagts till i avsnittet **Skapa beslut** för att förklara skillnaden mellan att utvärdera villkor i en sekventiell ordning eller samtidigt. [Läs mer](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* Ett skyddsräcke har lagts till för läsning av målgruppsresor med stegvis läsning. Du kan inte skapa en ny version, du måste duplicera resan. [Läs mer](../start/guardrails.md#journey-versions-g)
* Användningsexemplet om hur man begränsar genomströmningen har uppdaterats med information om begränsningsfunktioner. [Läs mer](../building-journeys/limit-throughput.md)
* En anteckning har lagts till för att ange att skalära arrayer inte stöds i svarsnyttolastdefinitionen. [Läs mer](../datasource/external-data-sources.md)
* Avsnittet om villkor för profiloblock har uppdaterats. [Läs mer](../building-journeys/condition-activity.md#profile_cap)

## Februari 2023 {#feb-2023}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] februari 23 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Information om verktygsfältet Arbetsyta har lagts till. [Läs mer](../building-journeys/using-the-journey-designer.md#gs-journey-design)
* Information har lagts till om att interna Adobe-adresser inte tillåts i URL:er och API:er. [Läs mer](../start/guardrails.md)
* En anteckning har lagts till i den API-utlösta kampanjdokumentationen för att ange att kontextattribut som skickas till begäran inte får överstiga 50 kB. [Läs mer](../campaigns/api-triggered-campaigns.md#contextual)
* Information lades till om hur avanmälningsinformation lagras i **datamängden för tillståndstjänst** efter att mottagarna har avbeställt prenumerationen via en landningssida. [Läs mer](../landing-pages/lp-use-cases.md#configure-opt-out)

## Januari 2023 {#jan-2023}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] Jan 23-versionen har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Information har lagts till om anpassade slutpunkter för autentisering i capping-dokumentationen. [Läs mer](../configuration/external-systems.md)
* Ett nytt exempel på anpassad autentisering har lagts till i avsnittet externa datakällor. [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode)
* En anteckning har lagts till om datainsamlingens bastjänst (DCCS) för händelseutlösta resor. [Läs mer](../start/guardrails.md#events-g)
* En anteckning om hämtning av identitetsnamnrymder har lagts till i avsnitten [Läsa målgrupp](../building-journeys/read-audience.md), [Målgruppskvalifikation](../building-journeys/audience-qualification-events.md) och [Skapa händelse](../event/about-creating.md).
* Hjälpmedelsfunktionerna i [!DNL Journey Optimizer] grupperas nu på en dedikerad sida. [Läs mer](../start/accessibility.md)
* Exemplen har uppdaterats i avsnittet Operatorer i dokumentationen för den avancerade uttrycksredigeraren. [Läs mer](../building-journeys/expression/operators.md)
* En anteckning har lagts till om begränsningen för sökning med objektmatris. [Läs mer](../event/experience-event-schema.md#relationships_limitations)
* En ny sida om datahantering har lagts till i [!DNL Journey Optimizer]. [Läs mer](../data/gs-data.md)
* En tabell med alla koder som kan returneras i svaret har lagts till när erbjudanden levereras med hjälp av besluts-API:t. [Läs mer](../offers/api-reference/offer-delivery-api/decisioning-api.md)

+++

+++ 2022

## December 2022 {#december-2022}

* Guiden Meddelanden har omorganiserats och delats upp i dedikerade guider för varje kanal:

   * [E-postkanal](../email/get-started-email.md)
   * [Push-meddelandekanal](../push/get-started-push.md)
   * [SMS-kanal](../sms/get-started-sms.md)

* Konfigurationsguiden har omstrukturerats för att bli enklare att läsa. [Läs mer](../configuration/get-started-configuration.md)

## November 2022 {#november-2022}

* En ny sida om Journey Optimizer integreringar har lagts till. [Läs mer](../integrations/ajo-integrations.md)
* En rekommendation om längden på URL:er för spegelsidor har lagts till. [Läs mer](../email/message-tracking.md)
* Ett nytt underavsnitt i konfigurationen av e-postinställningarna har lagts till i svaret på e-postadressen, inklusive rekommendationer för att säkerställa korrekt svarshantering. [Läs mer](../email/email-settings.md#reply-to-email)
* Ett avsnitt har lagts till om hur du ändrar innehållet i ett meddelande i en direktresa. [Läs mer](../building-journeys/journeys-message.md#update-live-content)

## Oktober 2022 {#october-2022}

* Ett exempel på hur man begränsar genomströmningen med hjälp av externa datakällor och anpassade åtgärder har lagts till för resan. [Läs mer](../building-journeys/limit-throughput.md)
* Fallavsnittet för resans användning har omorganiserats i två kategorier: [Affärsfall](../building-journeys/journeys-uc.md) och [Tekniska användningsfall](../building-journeys/collections.md).
* Avsnittet **Entitetsdatauppsättning** har uppdaterats med mer information. [Läs mer](../data/datasets-query-examples.md#entity-dataset)
* Avsnitten för hantering av avanmälan och godkännandepolicyer har omorganiserats. [Läs mer](../privacy/opt-out.md)
* Avsnittet om avancerade parametrar i resemeddelanden har klargjorts och anger nu att åsidosättning av e-postadresser endast ska användas för särskilda användningsfall. För det mesta är det värde som definieras som den primära adressen i **körningsfälten** det som ska användas.
* En anteckning har lagts till i avsnittet **Konfigurera underdomäner för landningssidor** för att ange att versaler inte tillåts i underdomäner för landningssidor. [Läs mer](../landing-pages/lp-subdomains.md)

## September 2022 {#september-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 22 september har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Lagt till en metodtips som rör användningen av vänteaktiviteter i återkommande läsningar. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* Frågeexempel för det nya steget har lagts till samt information om skillnaden mellan id, instanceid och profileid. [Läs mer](../reports/query-examples.md).
* Uppdaterade sidor relaterade till funktionerna [toDateOnly](../building-journeys/functions/functiontodateonly.md) och [toString](../building-journeys/functions/functiontostring.md).
* Information om tidsvillkorsparametrar har lagts till. [Läs mer](../building-journeys/condition-activity.md#time_condition)
* Ytterligare information om inbyggda datauppsättningar. [Läs mer](../data/get-started-datasets.md#access-datasets)
* Delarna i den globala rapporten och Live-rapporten har förbättrats och omorganiserats. [Läs mer](../reports/report-gs-cja.md)
* En lista över alla rapporteringsmått som är tillgängliga i Adobe Journey Optimizer har lagts till.
  [Läs mer](../reports/report-gs-cja.md#email-and-sms-metrics)
* BCC-e-postavsnittet har flyttats till den nya sidan Stöd för arkivering. [Läs mer](../configuration/archiving-support.md)

## Augusti 2022 {#august-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] augusti 22 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Avsnittet Frekvensregler har uppdaterats för att återspegla det nya textbundna meddelandeflödet.
* En video som visar hur du konfigurerar prenumerationer och skapar landningssidor finns nu i avsnittet Kom igång med landningssidor. [Läs mer](../landing-pages/get-started-lp.md#video)
* En begränsning har lagts till för resor med hjälp av Läs publik-aktiviteter. [Läs mer](../building-journeys/read-audience.md)
* Operatorsidan för uttrycksredigeraren har förbättrats. [Läs mer](../building-journeys/expression/operators.md)
* Ett avsnitt om schemaläggning av en kampanj har lagts till. [Läs mer](../campaigns/create-campaign.md)
* Avsnittet med allmänna syntaxregler för uttrycksredigeraren har uppdaterats för att ta hänsyn till den nya regeln för den omvända snedstreckssymbol som undgår bokstavsfunktioner. De befintliga publicerade meddelandena påverkas inte av den här ändringen. Endast de nya meddelandena eller utkastmeddelandena måste uppdateras. [Läs mer](../personalization/personalization-syntax.md#general-rules)

## Juli 2022 {#july-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 22 juli har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Avsnittet **Konfigurera kanalkonfigurationer** har klargjorts och uppdaterats med länkar till sidan som beskriver hur du konfigurerar SMS-kanalen. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)
* Alternativet **Tidszon för profil** är nu inaktiverat som standard i reseegenskaperna. [Läs mer](../building-journeys/timezone-management.md#timezone-from-profiles)
* Alternativet **Fast datum** är inte längre tillgängligt i aktiviteten **Vänta**. [Läs mer](../building-journeys/wait-activity.md)
* Mer information om alternativet **Inkrementell läsning** har lagts till i aktiviteten **Läs målgrupp**. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* Rekommendationer för villkorstypen **Profilbegränsning** har lagts till. [Läs mer](../building-journeys/condition-activity.md#profile_cap)
* Lagt till en begränsning av affärshändelser. [Läs mer](../start/guardrails.md#events-g)

## Juni 2022 {#june-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 22 juni finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Ett nytt avsnitt om sekretessförfrågningar har lagts till i dokumentationen. [Läs mer](../privacy/requests.md)
* Ett nytt avsnitt om granskningsloggar på resurser har lagts till i dokumentationen. [Läs mer](../privacy/audit-logs.md)
* Ett nytt avsnitt om hur du lägger till HTML- eller JSON-innehåll från Adobe Experience Cloud Asset-biblioteket i en offertrepresentation har lagts till i dokumentationen. [Läs mer](../offers/offer-library/add-representations.md#html-json)
* En ny sida om resans livscykel har lagts till. [Läs mer](../building-journeys/journey.md#journey-versions)
* Sidan Vänta aktivitet har uppdaterats. [Läs mer](../building-journeys/wait-activity.md)
* Listan med Adobe Journey Optimizer-datauppsättningar har lagts till med frågeexempel. [Läs mer](../data/datasets-query-examples.md)
* Sidan Tillåtelselista har flyttats till avsnittet Konfiguration. [Läs mer](../configuration/allow-list.md)
* Sidan Suppression List har uppdaterats för att förtydliga viss information, inklusive det faktum att alla ASCII-tecken som finns mellan 32 och 126 tillåts i fältet för undertryckning. [Läs mer](../configuration/manage-suppression-list.md)
* Länken till skyddsförslag och statiska gränser för beslutshantering har lagts till. [Läs mer](../start/guardrails.md)
* Tidsoptimering är nu tillgängligt för alla kunder. Betafältet har tagits bort. [Läs mer](../building-journeys/send-time-optimization.md)
* API:t för gruppbeslut har lagts till i listan över tillgängliga API:er för leverans av personaliserade erbjudanden. [Läs mer](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)

## Maj 2022 {#may-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] maj 22 har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Nya frågeexempel som rör [målgruppskvalifikation](../reports/query-examples.md#segment-qualification-queries) och [händelser](../reports/query-examples.md#event-based-queries) har lagts till.
* I avsnittet för e-postdesign omnämns nu nya inbyggda mallar som kan användas för att börja innehåll med. Relaterade skärmbilder har uppdaterats. [Läs mer](../email/get-started-email-design.md)
* Länkar till viktiga resurser har uppdaterats på Journey Optimizer dokumentationsstartsida.
* Skärmbilder för landningssidor och prenumerationsrapporter har uppdaterats. [Läs mer](../reports/live-report.md)
* En anteckning om att metoden Delete inte stöds i anpassade åtgärder har lagts till. [Läs mer](../action/about-custom-action-configuration.md)
* Länkar till instruktionsvideor har uppdaterats.
* Avsnitten [E-postkonfiguration](../configuration/about-subdomain-delegation.md), [Meddelandeförinställningar](../configuration/channel-surfaces.md) och [Konfigurera landningssidor](../landing-pages/lp-subdomains.md) har organiserats om för förbättrad läsbarhet.
* Avsnittet för URL-spårning har uppdaterats och förbättrats med exempel. [Läs mer](../email/email-settings.md#url-tracking)
* Ett nytt underavsnitt om hur du konfigurerar en e-postadress för vidarebefordran har lagts till. Observera att du inte kan göra det via användargränssnittet. [Läs mer](../email/email-settings.md#forward-email)

## April 2022 {#april-2022}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 22 april finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Dokumentationssidan för **reaktion**-händelser har uppdaterats. [Läs mer](../building-journeys/reaction-events.md)
* Videoklippen för funktioner för beslutshantering har uppdaterats för att återspegla Journey Optimizer användargränssnitt. [Läs mer](../offers/get-started/starting-offer-decisioning.md)
* Avsnittet **Kom igång med datauppsättningar** har förbättrats så att du får en mer detaljerad beskrivning av hur du får åtkomst till och skapar datauppsättningar. [Läs mer](../data/get-started-datasets.md)
* Länkar till hjälpguider och versionsinformation för produkten har lagts till på startsidan för **Adobe Journey Optimizer Documentation** . [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer.html)
* Avsnittet **Skapa meddelandeförinställningar** anger nu att du inte kan fortsätta med att skapa förinställningar när den valda IP-poolen är under utgåva (**[!UICONTROL Processing]** status) och aldrig har associerats med den valda underdomänen. [Läs mer](../configuration/channel-surfaces.md#subdomains-and-ip-pools)
* Avsnittet **URL-spårning** har uppdaterats för att återspegla mindre ändringar i användargränssnittet. [Läs mer](../configuration/channel-surfaces.md#url-tracking)

## Mars 2022 {#march-2022}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] mars 22-utgåvan finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* En ny sida om hur du kommer igång med AI-modeller har lagts till i avsnittet **Erbjudandebeslut**, inklusive en detaljerad beskrivning av [automatisk optimeringsmodell](../offers/ranking/auto-optimization-model.md), algoritmen som används och mer teknisk information. [Läs mer](../offers/ranking/ai-models.md)
* Sidan där du skapade testprofilen har flyttats till avsnittet **Målgrupp, profiler och identitet**. [Läs mer](../audience/creating-test-profiles.md)
* Ett exempel har lagts till om hur du lägger till ett uttryck som ett standardvärde i uttrycksredigeraren. [Läs mer](../building-journeys/expression/field-references.md#default-value)
* Avsnittet **Skapa anpassade erbjudanden** har organiserats om för förbättrad läsbarhet. [Läs mer](../offers/offer-library/creating-personalized-offers.md)
* Ett nytt avsnitt har lagts till för att beskriva den påverkan som ett byte av ett erbjudandes start- och/eller slutdatum kan ha på det här erbjudandets frekvensbegränsning. [Läs mer](../offers/offer-library/add-constraints.md#capping-change-date)
* Avsnittet **Ändra de primära e-postadresserna** har uppdaterats för att återspegla ändringar i användargränssnittet. [Läs mer](../configuration/primary-email-addresses.md)

## Februari 2022 {#feb-2022}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] februari 22 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Dokumentationssidorna för funktionerna [replace](../building-journeys/functions/functionreplace.md#example_2) och [replaceAll](../building-journeys/functions/functionreplaceall.md#example) har uppdaterats med ytterligare information och exempel angående målparametern.
* Bästa praxis har lagts till på sidan [Operatorer](../building-journeys/expression/operators.md#important-notes).

## Januari 2022 {#january-2022}

* Alla nya funktioner och förbättringar som kommer med [!DNL Journey Optimizer] Jan 22-utgåvan finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Avsnittet **Erbjudandet om AI-rankningar** har uppdaterats med en mer detaljerad beskrivning av den automatiska optimeringsmodellen. [Läs mer](../offers/ranking/auto-optimization-model.md)
* Ett nytt avsnitt om schemakraven som behövs för att kunna skicka in händelsetyper när en AI-modell används har lagts till. [Läs mer](../offers/data-collection/schema-requirement.md)
* Avsnittet om [!DNL Journey Optimizer]-personaliseringsfunktioner har organiserats om för att bli lättare att läsa. [Läs mer](../personalization/personalize.md)
* Avsnittet **Skapa meddelandeförinställningar** har delats upp i flera avsnitt för att bli tydligare. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)
* Avsnittet **Avanvisningshantering** har klargjorts och omorganiserats något. [Läs mer](../privacy/opt-out.md#opt-out-management)
* Avsnittet **Infoga länkar** har uppdaterats för att återspegla de senaste ändringarna i användargränssnittet. [Läs mer](../email/message-tracking.md#insert-links)

+++

+++ 2021

## November 2021 {#november-2021}

* Nu finns en fullständig beskrivning av den **avancerade uttrycksredigeraren** som används i resor. [Läs mer](../building-journeys/expression/expressionadvanced.md)
* Ett nytt avsnitt om **delegeringsmetoden för CNAME-underdomäner** har lagts till. [Läs mer](../configuration/delegate-subdomain.md#cname-subdomain-delegation)

## Oktober 2021 {#october-2021}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] okt 21 har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Listan med **Date time function** har lagts till. [Läs mer](../personalization/functions/dates.md)
* Nya **Get Started-avsnitt per användarprofil**. Ta din egen väg för att nå dina mål snabbare! [Läs mer](../start/quick-start.md)
* Nytt avsnitt i **Redigera en meddelandeförinställning**. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface)
* Nytt avsnitt i **Redigera en PTR-post**. [Läs mer](../configuration/ptr-records.md#edit-ptr-record)
* Nytt avsnitt i **Inaktivera en meddelandeförinställning**. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface#deactivate-a-surface)
* Nya begränsningar har lagts till i **Utvecklarhandboken för API:t för beslutshantering** för begränsningar för erbjudanden som inte stöds i arbetsflödena för mobila enheter [!DNL Experience Edge]. [Läs mer](../offers/api-reference/offers-api/personalized-offers/create.md#limitations)
* Nytt avsnitt i **Skapa simuleringar**. [Läs mer](../offers/offer-activities/simulation.md)
* Uppdaterade avsnittet **Lägg till beslutsomfattningar**. [Läs mer](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)
* **Definiera innehåll för dina representationer** har uppdaterats, inklusive ett nytt [underavsnitt](../offers/offer-library/creating-personalized-offers.md#custom-text) om hur du definierar och anpassar anpassad text. [Läs mer](../offers/offer-library/creating-personalized-offers.md#content)

## September 2021 {#september-2021}

* Följande funktionssidor har uppdaterats: [sethours](../building-journeys/functions/functionsethours.md), [getListItem](../building-journeys/functions/functiongetlistitem.md), [inSegment](../building-journeys/functions/functioninaudience.md)

* Följande funktioner har lagts till: [filter](../building-journeys/functions/functionfilter.md), [intersect](../building-journeys/functions/functionintersect.md), [toDateOnly](../building-journeys/functions/functiontodateonly.md)

* Datumtypen dateOnly har lagts till i dokumentationen för utrycksredigering. [Läs mer](../building-journeys/expression/data-types.md)

* Tillagda uppgifter om anpassad cachelängd på åtgärd. [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode)

* Tillagd information om standardportar för anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)

* Lagt till information om flera användningsfall för affärshändelser. [Läs mer](../event/about-creating-business.md#multiple-business-events)

* Tillagda vanligt förekommande exempel till frågor om Journey Step Events i Data Lake. [Läs mer](../reports/query-examples.md)

* En ny sida med **begränsningar** har lagts till. [Läs mer](../start/guardrails.md)

* Förbättrade sidan **Snabbstart** med steg för olika profiler. [Läs mer](../start/quick-start.md)

* Nu gäller alla beslutsfunktioner som beskrivs i det särskilda avsnittet även för Adobe Experience Platform-användare som använder Offer Decisioning-programmet. [Läs mer](../offers/get-started/starting-offer-decisioning.md)

* Lagt till ett underavsnitt för att förtydliga skillnaderna mellan att använda målgrupper jämfört med beslutsregler när en begränsning tillämpas för att begränsa urvalet av erbjudanden för en viss placering. [Läs mer](../offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* Specifika exempel på rankningsformler har lagts till för att illustrera exempel på verkliga användningsområden. [Läs mer](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)

* Ett underavsnitt om hur du redigerar IP-pooler har lagts till. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)

## Augusti 2021 {#august-2021}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] augusti 21 finns detaljerade i dokumentationen. [Läs mer](release-notes.md)
* Uppdaterade behörigheter för beslutshantering. [Läs mer](../administration/ootb-product-profiles.md)
* Uppdaterade skärmbilder för e-postdesigner med det senaste användargränssnittet.
* Konfigurationsproceduren för anpassade åtgärder med dynamiska URL-sökvägar och dynamiska huvuden har uppdaterats. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* Ett avsnitt om tillgänglighetsfunktioner och genvägar har lagts till. [Läs mer](../start/user-interface.md#accessibility)
* Ett avsnitt om metoder för målgruppsutvärdering har lagts till. [Läs mer](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)
* Anteckningar har lagts till i avsnitten om Suppression-listan, Tillåtelselista och e-post, global/liverapport, för att ange att profiler med statusen Inaktiverad och Inte tillåten ska uteslutas från e-postrapporten Skickade mått. [Läs mer](../reports/report-gs-cja.md)
* Ett nytt avsnitt har lagts till som beskriver hur du hämtar e-postadresser eller domäner som har uteslutits från en sändning eftersom de inte fanns på tillåtelselista. [Läs mer](../configuration/allow-list.md#reporting)
* Avsnittet Aktivera tillåtelselista har uppdaterats. [Läs mer](../configuration/allow-list.md#enable-allow-list)
* Avsnittet Monitor-meddelandets förinställningar har uppdaterats med orsaker till att förinställningarna inte kunde skapas och information om sådana fel. [Läs mer](../configuration/channel-surfaces.md#monitor-channel-surfaces)
* Uppdaterat och ändrat namn på avsnittet för återförsöksperiod för att återspegla det faktum att du nu kan ändra inställningen för återförsök via e-post i meddelandeförinställningarna. [Läs mer](../configuration/retries.md#retry-duration)
* Uppdaterade avsnittet Delegera en underdomän med mer detaljerad information om valideringsprocessen som utförs av Adobe. [Läs mer](../configuration/delegate-subdomain.md#subdomain-validation)
* Ett avsnitt har lagts till som beskriver hur du manuellt lägger till e-postadresser och domäner i listan över inaktiveringar. [Läs mer](../configuration/manage-suppression-list.md#add-addresses-and-domains)
* [Åtkomst till avsnittet ](../configuration/manage-suppression-list.md#access-suppression-list) med undertryckningslistan och avsnitten [Försök igen](../configuration/retries.md) har uppdaterats för att återspegla det nya användargränssnittet.
* Det nya flödet för att lägga till och konfigurera representationer när ett erbjudande skapas har dokumenterats. [Läs mer](../offers/offer-library/creating-personalized-offers.md#representations)

## Juli 2021 {#july-2021}

* Alla nya funktioner och förbättringar som kommer med versionen [!DNL Journey Optimizer] den 21 juli har beskrivits i dokumentationen. [Läs mer](release-notes.md)
* Direktlänkar har lagts till i dokumentationen för Experience Platform-tjänster på startsidan för [!DNL Journey Optimizer] och i innehållsförteckningen
* Nya landningssidor för Experience Platform-tjänster är tillgängliga i [!DNL Journey Optimizer]
* Länkar har lagts till i produktbeskrivningen för [!DNL Journey Optimizer] på startsidan
* Lagt till självstudievideor på flera sidor
* Optimerade startsidesbilder
* Avsnittet&quot;Meddelandespårning&quot; har flyttats, förbättrats och bytt namn till&quot;Lägg till länkar och spåra meddelanden&quot;. [Läs mer](../email/message-tracking.md)
* Ett underavsnitt har lagts till på spegelsidor. [Läs mer](../email/message-tracking.md#mirror-page)
* Namnet på&quot;erbjudandeaktiviteter&quot; har ändrats till&quot;beslut&quot; och&quot;beslut&quot; till&quot;beslutsomfattningar&quot; i dokumentation och skärmar. [Läs mer](../offers/get-started/starting-offer-decisioning.md)
* Nytt användningsexempel: [Anpassa ett meddelande med hjälpfunktioner](../personalization/personalization-use-case-helper-functions.md)
* Uppdaterade läsningsdokumentationen för att spegla segmentets faktiska påverkan. [Läs mer](../building-journeys/read-audience.md)
* Uppdaterade begränsningar för resan. [Läs mer](../start/guardrails.md)
* Markeringen Konfigurera erbjudanden uppdaterades i avsnittet Beslut. [Läs mer](../offers/offer-activities/configure-offer-selection.md)
* En varning har lagts till som anger att händelsebaserade erbjudanden för närvarande inte stöds. [Läs mer](../offers/offer-library/creating-personalized-offers.md#eligibility)
* Dokumenterade den nya fliken **[!UICONTROL Overview]** för beslutshantering. [Läs mer](../offers/get-started/user-interface.md#overview)
* Nya avsnitt har lagts till för att beskriva de åtgärder som är tillgängliga från erbjudandet och beslutslistorna: [Erbjudandelista](../offers/offer-library/creating-personalized-offers.md#offer-list) och [Beslutslista](../offers/offer-activities/create-offer-activities.md#decision-list).

+++
