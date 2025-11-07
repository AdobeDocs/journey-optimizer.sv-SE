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
source-git-commit: 1349da209bc90dd8ebad0bd309f89039aa6ea3f2
workflow-type: tm+mt
source-wordcount: '2814'
ht-degree: 9%

---

# Dokumentationsuppdateringar {#latest-updates}

På den här sidan visas alla de senaste ändringarna i [!DNL Journey Optimizer]-dokumentationen, förutom de uppdateringar som rör månadsreleasefunktionerna och förbättringarna.

## November 2025 {#november-2025}

* Det som nu finns i kanalerna App och LINE för Action-kampanjer. [Läs mer](../campaigns/campaign-content.md)

* Ett nytt omfattande avsnitt om hur snabbt resorna behandlas har lagts till i dokumentationen för hantering av bidrag, som omfattar antal deltagare, antal event och målgruppskvalifikationer inomresorna, effekt av vänteaktiviteter och påverkan av aktivitetsaktiviteter. [Läs mer](../building-journeys/entry-management.md#journey-processing-rate)

* När du utformar e-postmeddelanden söker systemet nu efter nyckelinställningar och visar varningar för varningar och fel. Information om e-postaviseringar och valideringskrav har lagts till på sidan Guardrails. [Läs mer](../email/create-email.md#check-email-alerts)

* Observera att frekvensbegränsning inte kan aktiveras eller inaktiveras för tidigare skapade erbjudanden har tagits bort från sidan Lägg till begränsningar till ett erbjudande. [Läs mer](../offers/offer-library/add-constraints.md#capping)

* Nu finns dokumentation om hur du arbetar med steg för kundresan. [Läs mer](../reports/journey-step-events-overview.md)

* Det finns nu tre nya varningsmeddelanden om resan: utlöst resa, färd klar och utlöst anpassad åtgärd. [Läs mer](../reports/alerts.md#journey-alerts)

## Oktober 2025 {#october-2025}

* Nu kan du konvertera bilder till HTML-mallar med hjälp av bilden till HTML Converter. [Läs mer](../email/image-to-html.md)

* Information om Adobe Journey Optimizer lanseringscykel finns nu tillgänglig. [Läs mer](releases.md)

* Nu finns en ny sida med frågor och svar om Journeys. [Läs mer](../building-journeys/journey-faq.md)

* Nu finns funktionen för övervakning av anpassade åtgärder tillgänglig. [Läs mer](../action/reporting.md)

* Det finns nu ett avancerat genomströmningsläge för API-utlösta kampanjer. [Läs mer](../campaigns/api-triggered-high-throughput.md)

* Det finns nu en felkodsreferens för resor. [Läs mer](../building-journeys/error-codes-reference.md)

* Journey Optimizer Experimentation Accelerator-dokumentation finns nu tillgänglig. [Läs mer](../content-management/experiment-accelerator-gs.md)

* Ett nytt avsnitt har lagts till i hjälpfunktionens dokumentation **formatDate**. I det här avsnittet klargörs betydelsen av nyckelmönstersymboler som y, Y, M, d och D. [Läs mer](../personalization/functions/dates.md#pattern-characters)

* Ett PQL-exempel har lagts till i avsnittet för rangordningsformel för beslut, för att visa hur man kan öka antalet erbjudanden baserat på en profils postnummer och årsinkomst. [Läs mer](../experience-decisioning/ranking/ranking-formulas.md#ranking-formula-examples)

* En begränsning lades till i avsnittet om testläge för resan för att nämna att testläget inte stöder anrikning av anpassade attribut för uppladdningsmottagare. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)

* Ett nytt avsnitt har lagts till på sidorna [Beslutshanteringsgarantier och -begränsningar](../offers/decision-management-guardrails.md#configurations) och [Beslutsfattare och -begränsningar](../experience-decisioning/decisioning-guardrails.md#configurations) för att ange det maximala antalet konfigurationer som stöds (20 000), vilket motsvarar det totala antalet regler för att fästa objekt som finns i sandlådan.

* En anteckning har lagts till i avsnittet Villkorsaktivitet för resan i dokumentet om att villkorsutvärderingen kommer att misslyckas för profiler som innehåller mer än två enhetsidentiteter. [Läs mer](../building-journeys/condition-activity.md)

* En ny sida lades till för att beskriva hur ni kan använda samtyckespolicyer för att uppfylla kundernas önskemål utifrån deras val, samtidigt som de respekterar deras samtycke. [Läs mer](../action/preference-center.md)

* En anteckning har lagts till på sidorna Kom igång med profiler och Guardrails för att ange att e-postmeddelanden är skiftlägeskänsliga när data importeras, vilket innebär att dubblettprofiler kan skapas och användas när målmottagaren anges. [Läs mer](../audience/get-started-profiles.md)

* Ett nytt `render`-attribut introducerades i personaliseringsredigeraren. Ange det till `false` om du vill dölja innehållet i ett uttrycksfragment. [Läs mer](../personalization/use-expression-fragments.md#use-expression-fragment)

* En lista med skyddsförslag lades till i avsnittet med information om hur fragment som kopplats till beslutsposter inom beslutspolicyer kan utnyttjas. [Läs mer](../experience-decisioning/create-decision.md#fragments-guardrails)

* Lagt till metodtips för datasökningar: Aktivera för att undvika indexeringsproblem och förstå hur gruppborttagningar påverkar sökdata. [Läs mer](../data/lookup-aep-data.md#guardrails--guidelines-guidelines)

* Lagt till en begränsning som säger att endast enhetliga profiltjänstmålgrupper stöds när målgruppsresor med extra identifierare används. [Läs mer](../building-journeys/supplemental-identifier.md#guardrails--limitations-guardrails)

* Dokumentationen för Experimentation Accelerator har flyttats till en separat samling. [Läs mer](https://experienceleague.adobe.com/en/docs/experimentation-accelerator/using/overview)

## September 2025 {#september-2025}

* Ett nytt avsnitt om inkommande kanaler har lagts till på sidan Guardrails and limits för att samla in alla begränsningar som gäller för webben, appar, kodbaserade upplevelser och innehållskortskanaler. Den högsta volymen på 5 000 inkommande begäranden per sekund för alla inkommande begäranden och maximalt 500 aktiva inkommande åtgärder. [Läs mer](../start/guardrails.md#inbound-guardrails)

* En sida med vanliga frågor och svar har släppts för orkestrerade kampanjer. [Läs mer](../orchestrated/orchestrated-campaigns-faq.md)

* Ett felsökningsavsnitt har lagts till i dokumentationen för steg för resa med definitioner, vanliga orsaker och felsökningssteg för de vanligaste händelsetyperna för ignorering. [Läs mer](../reports/sharing-field-list.md#troubleshoot-discarded-event-types-in-journey_step_events)

* Dokumentationen om hur man använder tilläggsidentifierare under resor innehåller nu en tabell som beskriver hur profiler beter sig när utträdeskriterier tillämpas under resor med kompletterande ID:n. [Läs mer](../building-journeys/supplemental-identifier.md#exit-criteria)

* Ett felsökningsavsnitt har lagts till för att underhålla profiler som tas bort under pausade resor. [Läs mer](../building-journeys/journey-pause.md#troubleshoot-profile-discards-in-paused-journeys)

* Information har lagts till i översiktsdokumentationen för scheman för att skilja mellan standard- och relationsscheman som används för Orchestrated-kampanjer. [Läs mer](../data/gs-data.md)

* Information har lagts till i dokumentationen för beslutsfattande och beslutshantering om kraven för att kunna utbilda modellerna [automatisk optimering](../experience-decisioning/ranking/auto-optimization-model.md) och [personaliserad optimering](../experience-decisioning/ranking/personalized-optimization-model.md).

* Det klargörs att API-anrop för REST för interaktiv meddelandekörning har en 60-sekunders timeout, med interna försök att säkerställa leveransen. [Läs mer](../campaigns/trigger-campaigns.md)

* Sidan för beslutsobjektsamlingar uppdaterades för att förtydliga beteendet hos operatorn **CONTAINS** när regler definierades. [Läs mer](../experience-decisioning/collections.md)

* Sidan Tilldela prioritetspoäng uppdaterades med de specifika stegen för att definiera en prioritetspoäng för inkommande kanalåtgärder inom aktiviteten **Åtgärd**. [Läs mer](../conflict-prioritization/priority-scores.md#priority-action)

## Augusti 2025 {#august-2025}

* En ny sida med en lista över de bästa sätten att utforma hjälpmedelsanpassat innehåll för e-post och landningssidor med [!DNL Journey Optimizer] har lagts till. [Läs mer](../email/accessible-content.md)

* Dokumentationen för kompletterande identifierare under resor har uppdaterats med följande förtydliganden:

   * När du har lagt till en tilläggsidentifierare till ett schema måste en ny händelse (för händelseutlösta resor) eller en ny fältgrupp (för läsmålgruppsresor) skapas. Befintliga enheter uppdateras inte automatiskt och känner inte igen den nya identifieraren.

   * Ytterligare identifierare valideras inte mot policyer för märkning och verkställighet av dataanvändning (DULE) och beaktas inte vid kontroller av datastyrning under resor.

[Läs mer](../building-journeys/supplemental-identifier.md)

* Optimeringen på kampanjsidan uppdaterades för att återspegla det faktum att optimering nu även är tillgängligt på resorna. [Läs mer](../campaigns/campaigns-message-optimization.md)

* En länk till självstudievideon med en beskrivning av hur man utnyttjar meddelandeoptimering i en kampanj lades till. [Läs mer](../campaigns/campaigns-message-optimization.md)

## Juli 2025 {#july-2025}

* Kampanjgränssnittet har nu två separata flikar: **Åtgärd** och **API utlöst**. Dokumentationen har uppdaterats i enlighet med detta, med information för varje kampanjtyp ordnad i dedikerade avsnitt för att förbättra tydligheten och användbarheten. [Läs mer](../campaigns/get-started-with-campaigns.md)

* Sidorna [Kom igång med delegering via underdomän](../configuration/about-subdomain-delegation.md) och [Delegera en underdomän](../configuration/delegate-subdomain.md) har uppdaterats för att ge en bättre presentation av de olika delegeringsmetoderna och stegen för att konfigurera dem.

* En anteckning har lagts till i avsnittet Fragment, som anger att när spårning är aktiverat i en resa eller kampanj, om det finns länkar i ett fragment och om det här fragmentet används i ett meddelande, spåras dessa länkar, t.ex. alla andra länkar i meddelandet. [Läs mer](../content-management/create-fragments.md#content)

* Skyddsutkast och begränsningar som gäller delegering av underdomäner i Journey Optimizer har berikats och konsoliderats i ett dedikerat avsnitt. [Läs mer](../configuration/delegate-subdomain.md#guardrails)

* En anteckning har lagts till i Skapa reserverbjudanden och Skapa beslutssidor för att ange att reserverbjudanden ska innehålla alla representationer som används i ett beslut. [Läs mer](../offers/offer-library/creating-fallback-offers.md)

* Skyddsritningarna som gäller för fragment har berikats. [Läs mer](../start/guardrails.md#fragments-guardrails).

* En anteckning har lagts till som anger att länkar som lagts till i meddelanden upphör att gälla efter 25 månader och länkar till spegelsidor efter 90 dagar. [Läs mer](../email/message-tracking.md)

<!--* The possible email error types that could happen upon sending email deliveries with are now listed in a dedicated section. [Read more](../configuration/email-error-types.md)-->

## Juni 2025 {#june-2025}

* Ett nytt avsnitt om hur du lägger till och använder formaterad text som radbrytningar, fet stil, kursiv stil etc. i anpassningsbara fragment med hjälp av HTML-komponenter har lagts till. [Läs mer](../content-management/customizable-fragments.md#rich-text)

* Beslutsdelen har uppdaterats med ett särskilt avsnitt som handlar om att skapa AI-modeller. [Läs mer](../experience-decisioning/ranking/ai-models.md)

* En rekommendation om användningen av fältet `actionExecutionTime` har lagts till i åtgärden travelStep-händelser. [Läs mer](../reports/sharing-execution-fields.md#actionexecutiontime-actionexecutiontime-field)

* En anteckning om `messageID` har lagts till som kanske inte är unik för varje enskild leverans. [Läs mer](../data/datasets-query-examples.md)

* En rekommendation om hantering av historiska händelser har lagts till i datahygien. [Läs mer](../privacy/data-hygiene.md#recommendations-data-hygiene-recommendations)

* Ett skyddsräcke om landningssidor som inte stöds för migrering mellan sandlådor har lagts till. [Läs mer](../configuration/copy-objects-to-sandbox.md#general-best-practices-global)

* En varning om kapslade JSON-objekt som inte stöds i anpassad autentisering för anpassade åtgärder har lagts till. [Läs mer](../datasource/external-data-sources.md)

* En varning om villkorsstyrd innehållsvariantnamngivning har lagts till i e-postdesignern. [Läs mer](../personalization/create-conditions.md)

* Uppdaterade avsnittet &quot;Avdelegera en underdomän till en landningssida&quot;. [Läs mer](../landing-pages/lp-subdomains.md#undelegate-subdomain)

* Tydligare regler för återinträde på resan när kompletterande identifierare används. [Läs mer](../building-journeys/supplemental-identifier.md#guardrails--limitations)

* En ny anteckning har lagts till för att klargöra att du måste använda uttrycksredigeraren i avancerat läge när du väljer attributet för tilläggsidentifierare under händelsekonfigurationen. [Läs mer](../building-journeys/supplemental-identifier.md#add)

* Förtydligande av hur återinträde på resan fungerar med kompletterande identifierare. [Läs mer](../building-journeys/supplemental-identifier.md#guardrails)

## Maj 2025 {#may-2025}

* Adobe-integreringar som finns med Journey Optimizer listas nu i avsnittet&quot;Koppla samman dina system och miljöer&quot;. [Läs mer](../integrations/ajo-integrations.md)

* Innehållsintegreringarna grupperas nu i avsnittet Innehållshantering. [Läs mer](../integrations/content-integrations.md)

* Arkitekturdiagram för Adobe Experience Platform och Journey Optimizer har uppdaterats. [Läs mer](../start/get-started.md#architecture-architecture)

* En video om hur personaliseringsredigeraren fungerar har lagts till för att hjälpa dig att lära dig hur du skriver och testar personaliseringskod med exempeldata. [Läs mer](../personalization/personalize.md#how-to-videosvideo-perso)

* Det högsta antalet adresser i en utsädeslista har ökats från 50 till 300. [Läs mer](../configuration/seed-lists.md#create-seed-list)

* Ett nytt steg som beskriver hur du radbryter kod när du använder beslutsprinciper i den kodbaserade upplevelseredigeraren har lagts till på sidan Skapa beslutspolicyer. [Läs mer](../experience-decisioning/create-decision.md#use-decision-policy)

* En anteckning har lagts till i den kodbaserade upplevelsedokumentationen för att ange att när du har flera kodbaserade upplevelseåtgärder som körs på samma yta, avgör kampanjens eller kundens prioritetspoäng vad som skickas till slutanvändaren om de kvalificerar för mer än en åtgärd. [Läs mer](../code-based/code-based-surface.md#surface-definition)

* En ny sida om felsökning av inkommande åtgärder under resor ger stegvis hjälp för att identifiera och lösa problem oberoende av varandra innan man kontaktar supporten. [Läs mer](../building-journeys/troubleshooting-inbound.md)

* En ny [sida](../code-based/code-based-decisioning-implementations.md) har lagts till som beskriver hur du lägger till följande flaggor i din klientimplementering när du använder beslut i kodbaserade upplevelser:

   * Lägger till flaggan `dryRun` för att testa beslut i kodbaserade upplevelser. [Läs mer](../code-based/code-based-decisioning-implementations.md#code-based-test-decisions)

   * Använd borttagning av dubbletter för att fatta beslut i kodbaserade upplevelser. [Läs mer](../code-based/code-based-decisioning-implementations.md#code-based-decisioning-deduplication)

## April 2025 {#apr-2025}

* Kapitlet Konfiguration har nu delats upp i tre kapitel: [Kanalkonfiguration](../configuration/get-started-configuration.md), [Resurskonfiguration](../configuration/about-data-sources-events-actions.md) och [Anslut dina system](../configuration/ajo-apis.md).
* En varning om att använda upplevelsehändelser i reseuttryck och villkor har lagts till. [Läs mer](../building-journeys/expression/expressionadvanced.md#discovering-the-interface)
* En anteckning om tillfällig lagring av utdatafilen har lagts till på konfigurationssidan för direktreklam. [Läs mer](../direct-mail/direct-mail-configuration.md)
* Ett tips har lagts till i avsnittet avancerad uttrycksredigerare om riktlinjerna för villkorsformat. [Läs mer](../building-journeys/expression/expressionadvanced.md)
* En varningsanteckning har lagts till i funktionsavsnittet `inAudience` om påverkan och bästa praxis när en målgrupp ska namnges. [Läs mer](../building-journeys/functions/functioninaudience.md)
* En rekommendation om användning av inbyggda nyckelord har lagts till när tvåvägs-SMS används. [Läs mer](../sms/sms-opt-out.md)
* Uppdaterade testsidan för resan med en anteckning om behovet av att inkludera ett identitetsnamn i händelsen som används. [Läs mer](../building-journeys/testing-the-journey.md)
* Du kan för närvarande inte avdelegera underdomäner via användargränssnittet [!UICONTROL Journey Optimizer]. Du måste kontakta din Adobe-representant. Steg för att avdelegera en underdomän finns nu detaljerade för [e-postmeddelanden](../configuration/delegate-subdomain.md#undelegate-subdomain), [SMS](../sms/sms-subdomains.md#undelegate-a-subdomain-undelegate-subdomain), [webbupplevelser](../web/web-delegated-subdomains.md#undelegate-a-subdomain-undelegate-subdomain) och [landningssidor](../landing-pages/lp-subdomains.md#undelegate-subdomain).<!--[Read more](../configuration/delegate-subdomain.md#undelegate-subdomain)-->
* Ett förtydligande har lagts till om den valfria parametern `maxHttpConnections` i Resor Capping API, inklusive vägledning om hur den ska användas tillsammans med begränsningskonfigurationer för samma slutpunkt. [Läs mer](../configuration/throttling.md)
* I avsnittet Experience Decision (Upplevelsebeslut) finns en vägledning som förklarar att godkända erbjudandeposter inte kan tas bort om de används i en samling eller ett beslut. Inkluderade steg för att ändra deras status till Utkast med alternativet **[!UICONTROL Undo approve]**. [Läs mer](../experience-decisioning/items.md#manage)
* Information om sandlådor har grupperats tillsammans i ett nytt avsnitt,&quot;Hantering av sandlådor&quot;. Det här nya avsnittet innehåller information om hur du använder och tilldelar sandlådor och hur du använder export- och importfunktioner för paket för att kopiera objekt som resor, innehållsmallar eller fragment över flera sandlådor. [Läs mer](../administration/sandboxes.md)

## Mars 2025 {#mar-2025}

* Sidan om Audience Qualification-händelser har uppdaterats med nya rekommendationer. [Läs mer](../building-journeys/audience-qualification-events.md)
* Funktionen för felsökning av anpassade åtgärder är nu tillgänglig för alla kunder (GA). [Läs mer](../action/troubleshoot-custom-action.md)
* Datahygien är nu Data Lifecycle i produktanvändargränssnittet. Dokumentationen har uppdaterats för att återspegla den här ändringen. [Läs mer](../privacy/data-hygiene.md)
* De inbyggda behörigheterna för Landing Page som saknas har lagts till i dokumentationen. [Läs mer](../administration/ootb-permissions.md)
* En anteckning har lagts till om schemaläggning av återkommande kampanjer. [Läs mer](../campaigns/create-campaign.md)
* Avsnittet om att infoga länkar och aktivera spårning i ett e-postmeddelande har uppdaterats och omorganiserats. [Läs mer](../email/message-tracking.md)
* Avsnittet om personaliseringsfunktioner i Adobe Journey Optimizer har omstrukturerats och förbättrats. [Läs mer](../personalization/personalize.md)
* API:t för beslutshantering för att lista personaliserade erbjudanden har uppdaterats med ett exempel för att utföra paginering om flera personaliserade erbjudanden saknas i svaret. [Läs mer](../offers/api-reference/offers-api/personalized-offers/offers-list.md)
* En ny sida med all information om funktionen för att avbryta prenumerationen i List har skapats för att bli tydligare. [Läs mer](../email/list-unsubscribe.md)
* Avsnittet Frequency capping har uppdaterats med information om hur frekvenscapping-räknaren har uppdaterats för API:erna för beslut och gruppbeslut, utöver Edge Decisioning API. [Läs mer](../offers/offer-library/add-constraints.md#frequency-capping)

## Februari 2025 {#feb-2025}

* Åtgärdsprofilerna för läsning av målgrupp har uppdaterats för att ange att endast en aktivitet kan användas under en resa och att endast en målgrupp kan nås. [Läs mer](../building-journeys/read-audience.md)
* Reservoarerna för resan när Adobe Campaign används har uppdaterats. [Läs mer](../start/guardrails.md#ac-g)
* Stegen för att skapa dina första resor har beskrivits och länkar till dokumentationsavsnitt har lagts till. [Läs mer](../building-journeys/journey-gs.md)
* Det finns nu en ny sida med information om kontrollpanelen för resan och användargränssnittet för filtrering. [Läs mer](../building-journeys/journey-ui.md)
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

* En anteckning har lagts till för att hjälpa till att felsöka ett eventuellt felmeddelande när du gör ett API-anrop för att aktivera datauppsättningar för personalisering med hjälp av Adobe Experience Platform-data. [Läs mer](../personalization/aep-data-perso.md)

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
* En video om hur AI Assistant Content Generator genererar e-postmeddelanden har lagts till. [Läs mer](../content-management/generative-email.md#video)

<!--

## August 2024 {#aug-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] August '24 release have been detailed in the documentation. [Read more](release-notes.md)
* Performance guardrails for Decision Management have been updated to mention Decisioning APIs delivery throughputs with/without Edge Segmentation. [Read more](../start/guardrails.md#decision-management)
* Journey guardrails have been updated. [Read more](../start/guardrails.md#journeys-guardrails-journeys)


## July 2024 {#july-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] July '24 release have been detailed in the documentation. [Read more](release-notes.md)
* A personalization use case has been added on how to personalize an email with information related health plans and prescriptions. [Read more](../personalization/perso-uc-plan-prescriptions.md)

## June 2024 {#june-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] June '24 release have been detailed in the documentation. [Read more](release-notes.md)
* A note about the usage of merge policies in journeys has been added on [this page](../building-journeys/journey-properties.md#merge-policies).
* The page about how to configure a **Wait** activity in a journey has been reorganized and improved. [Read more](../building-journeys/wait-activity.md)
* A new page has been created to detail journey's properties. [Read more](../building-journeys/journey-properties.md)

## May 2024 {#may-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] May '24 release have been detailed in the documentation. [Read more](release-notes.md)
* The section on seed lists has been updated regarding recurring journeys. [Read more](../configuration/seed-lists.md#use-seed-list)
* The setion on external data sources has been updated. [Read more](../datasource/external-data-sources.md#custom-authentication-access-token)
* The global journey timeout of 30 days has been added to the Guardrail and limitation page. [Read more](../start/guardrails.md#journeys-guardrails-journeys)
* The section on the Adobe Campaign v7/v8 integration has been updated with information on provisionning. [Read more](../action/acc-action.md#access)
* The expression editor used to personalize content has been renamed in the documentation to "personalization editor" to clearly differenciate it from the [Journey expression editor](../building-journeys/expression/expressionadvanced.md). [Read more](../personalization/personalization-build-expressions.md)

## April 2024 {#april-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] April '24 release have been detailed in the documentation. [Read more](release-notes.md#apr-2024)
* Configuration steps for In-app messaging have been detailed. [Read more](../in-app/inapp-configuration.md)
* Documentation for [Offer decisioning APIs](../offers/api-reference/offer-delivery-api/decisioning-api.md) and [Batch decisioning APIs](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md) have been updated.
* Information has been added in the Decision Management documentation regarding edge and hub regions management when using frequency capping with the Edge Decisioning API. [Read more](../offers/offer-library/add-constraints.md#frequency-capping)
* Information has been added on identity creation with custom namespaces when working with API-triggered campaigns. [Read more](../campaigns/api-triggered-campaigns.md)
* Screeshots have been updated to reflect the improved Journey canvas.
* Naming constraints has been updated in the following page: [Configure a unitary event](../event/about-creating.md), [Configure a business event](../event/about-creating-business.md#gs-business-events), [Configure a custom action](../action/about-custom-action-configuration.md#configuration-steps), [External data sources](../datasource/external-data-sources.md)
* A note has been added on Send Time Optimization availability. [Read more](../building-journeys/send-time-optimization.md)
* A new technical use case has been added on how to create a custom action to send data to Experience Platform. [Read more](../building-journeys/custom-action-aep.md)

## March 2024 {#march-2024}
 
* A Frequently Asked Questions section has been added to address common questions regarding the use of audience composition and custom upload audiences in Journey Optimizer. [Read more](../audience/about-audiences.md#faq)
* All new features and improvements coming with [!DNL Journey Optimizer] March '24 release have been detailed in the documentation. [Read more](release-notes.md#mar-2024)
* The page on profile entrance management has been improved. [Read more](../building-journeys/entry-management.md)
* Troubleshooting information has been added to the Alerts page. [Read more](../reports/alerts.md#alert-troubleshooting)
* Information on the Wait activity has been added to the page on journey reports. [Read more](../reports/sharing-overview.md)
* For Journeys in test mode, following shortcuts have been disabled:
    * T: Shortcut to toggle the test mode on or off.
    * E: Shortcut used to trigger an event in an event-based journey.
    * P: Shortcut to trigger an event in an audience-based journey for which the Single profile at a time option is turned on.
    * L: Shortcut designated to display the test logs.
* The Message frequency rules page has been updated with a new subsection on daily frequency cap, which is available on demand in addition to weekly or monthly capping.
* The Work with consent policies page has been improved and updated with useful links to the Experience Platform documentation. [Read more](../action/consent.md)
* A new section has been added to reflect the fact that you can display HTML email content templates as thumbnails with the Grid view mode (Limited Availability). [Read more](../content-management/content-templates.md#template-thumbnails)
* A new section has been added to the Deliverability page to explain what feedback loops are and how to leverage them. [Read more](../reports/deliverability.md#feedback-loops)
* A note has been added to the Create personalized offers section to specify that the size of an offer including all its representations cannot exceed 300KB. [Read more](../offers/offer-library/creating-personalized-offers.md#create-offer)

## February 2024 {#feb-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] February '24 release have been detailed in the documentation. [Read more](release-notes.md#feb-2024)
* The Journey Optimizer + Workfront integration has been added to the integrations page. [Read more](../integrations/ajo-integrations.md)
* Information has been added on how to personalize offers' representations based on context data. [Read more](../offers/offer-library/add-representations.md#context-data)
* The guardrails page has ben updated with a note on custom actions which support JSON format only when using request or response payloads. [Read more](../start/guardrails.md#custom-actions-g)
* Additional information has been added about the basic authentication type in external datasources. [Read more](../datasource/external-data-sources.md)
* A note has been added to clearly differenciate the [Journey expression editor](../building-journeys/expression/expressionadvanced.md) from the [personalization editor](../personalization/functions/functions.md).
* The list of functions available in the advanced expression editor has been updated. [Read more](../building-journeys/expression/functions.md)
* The page on the Split function has been updated. [Read more](../building-journeys/functions/functioninaudience.md)
* Information has been added regarding the impact of the opt-in or opt-out of push notifications on In-app messages. [Read more](../in-app/create-in-app.md)
* The Message frequency rules page has been updated to reflect the Duration options available in the user interface (weekly or monthly).
* The Edit a PTR record section has been updated to clarify the fact that PTR records cannot be created manually and that you need to edit PTR records to assign them new subdomains. [Read more](../configuration/ptr-records.md#edit-ptr-record)

## January 2024 {#jan-2024}

* All new features and improvements coming with [!DNL Journey Optimizer] January '24 release have been detailed in the documentation. [Read more](release-notes.md)
* A guardrail about the journey size has been added. [Read more](../start/guardrails.md#journeys-guardrails-journeys)
* Journey timeout management has been detailed [in the following section](../building-journeys/journey-properties.md#global_timeout).
* Journey Optimizer [documentation home](../../ajo-home.md) page has been redesigned.
* Recommendations about the Update Profiles activity have been added. [Read more](../building-journeys/update-profiles.md) 
* Information has been added regarding the behaviour of timeouts on event activities in journeys. When no event is received during the specified timeout period, individuals will continue the journey if no timeout path is defined. [Read more](../building-journeys/general-events.md#events-specific-time)
* In-app channel configuration prerequisites have been updated with a note about the usage of a custom Dataset preference merge policy. [Read more](../in-app/inapp-configuration.md)
* More details have been added about how to manipulate collections in a custom action response. [Read more](../action/action-response.md#exp-syntax).
* A link to the [Schema Dictionary for Adobe Journey Optimizer](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html) has been added to the home page.
* An outdated reference to the AJO Message resource has been removed from the list of resources available in the Audit Log. When an update is done on a message in a journey, a **Journey** log is created. [Read more](../privacy/audit-logs.md)
* Additional recommendations have been added about the usage of the **Read Audience** activity. [Read more](../building-journeys/read-audience.md#must-read)
* The Get started with Adobe Experience Platform audiences page has been improved with a list of audience generation methods. [Read more](../audience/about-audiences.md)
* Best practices have been added when choosing an endpoint to target using a custom action. [Read more](../action/about-custom-action-configuration.md)
* An note has been added to notify users that events cannot be fired from external systems using an API. [Read more](../building-journeys/testing-the-journey.md#important-notes)
* Information on the **currentActionField** function has been added to the list of [collection management functions](../building-journeys/expression/collection-management-functions.md). An expression sample leveraging the function has been added in the [Use API call reponses in custom actions](../action/action-response.md) page.
* Update custom authentication doc regarding cache duration. [Read more] (../datasource/external-data-sources.md)
* Support of `<listObject>` has been modified in multiple functions.
* Update the **duration** parameter in the `toString` function. [Read more](../building-journeys/functions/conversion-functions.md#toString)
* For some external data sources use-cases, usage of custom actions is recommended.
* Event field syntax has been updated. The following syntax is deprecated `@(my_event.myfield}` and replaced by `@event{my_event.myfield}`. [Read more](../building-journeys/expression/field-references.md)

+++ 2023

## November 2023 {#nov-2023}

* The guardrail that limits all custom actions has been changed from 150,000 calls over 30 seconds to 300,000 calls over one minute. In addition, the default capping no longer applies to each endpoint. It is now performed per host and per sandbox. For example, on a sandbox, if you have two endpoints with the same host (eg: `https://www.adobe.com/endpoint1` and `https://www.adobe.com/endpoint2`), the capping will apply for all endpoints under the adobe.com host. "endpoint1" and "endpoint2" will share the same capping configuration and having one endpoint reach the limit will have an impact on the other endpoint. [Read more](../action/about-custom-action-configuration.md)
* A new status for email campaigns has been added to the list of campaigns' statuses. [Read more](../campaigns/manage-campaigns.md#campaign-statuses-and-alerts-statuses)
* The Get started with Adobe Experience Platform audiences section has been updated to reflect the audience evaluation methods available and how to select them. [Read more](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)
* A new subsection has been added to specify which events should be avoided when building your audience if you are using the streaming segmentation evaluation method. [Read more](../audience/about-audiences.md#streaming-segmentation-events-guardrails)

## October 2023 {#oct-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] October '23 release have been detailed in the documentation. [Read more](release-notes.md)
* Added GIFs to illustrate some key capabilities, such as: [Content templates](../content-management/content-templates.md), [Fragments](../content-management/fragments.md), [Computed attributes](../audience/computed-attributes.md), [Direct mail](../direct-mail/get-started-direct-mail.md), [Tags](../start/search-filter-categorize.md#tags), [Decision management optimization models](../offers/ranking/personalized-optimization-model.md), [API-triggered campaigns](../campaigns/api-triggered-campaigns.md), and [Content experiment](../content-management/content-experiment.md).
* The Schema creation process has been updated to reflect latest updates in the user interface, coming with Adobe Experience Platform changes. [Read more](../audience/creating-test-profiles.md) 
* Decision Management guardrails have been added to the Guardrails and limitations page. [Read more](../start/guardrails.md#decision-management)
* The Header parameters section has been updated to reflect how out-of-office notifications and challenge responses are handled (they are received on the **[!UICONTROL Error email]**). [Read more](../email/email-settings.md#email-header)
* A new section on how to preview and test your content has been created. [Read more](../content-management/preview-test.md)
* The Implement single-page applications page has been moved to the Adobe Experience Paltform Web SDK documentation. [Read more](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-spa-implementation.html){target="_blank"}
* The Capping section has been updated to reflect the label changes relating to offer capping in the decision management interface. [Read more](../offers/offer-library/add-constraints.md#capping)
* The Add dynamic content into emails has been updated with details on how to delete a variant. [Read more](../personalization/dynamic-content.md#emails)
* The example for capping & throttling configurations has been updated. [Read more](../configuration/external-systems.md)
* The limitation regarding scalar arrays has been removed from the external data source section. [Read more](../datasource/external-data-sources.md)
* The multi-channel journey use case has been updated. [Read more](../building-journeys/journeys-uc.md)
* The Journey Optimizer documentation set has been updated to reflect the new Experience Platform schema creation process. 

## September 2023 {#september-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] September '23 release have been detailed in the documentation. [Read more](release-notes.md)
* A new page has been added with scaling best practices and real-time stitching guidance. [Read more](../start/best-practices.md)
* A Frequently-Asked-Questions section has been added for Send-Time Optimization. [Read more](../building-journeys/journeys-message.md#faq-send-time)
* A note has been added for the audience qualification activity. It may take up to 10 minutes to be active and listen to profiles entering or exiting the audience. [Read more](../building-journeys/audience-qualification-events.md#important-notes-segment-qualification)
* A list of limitations to be aware of when creating decision rules has been added to the decision management documentation. [Read more](../offers/offer-library/creating-decision-rules.md)
* Links to access control documentation have been updated. [Read more](../administration/permissions.md)
* In-app channel prerequisites have been updated with Adobe Experience Platform Data Collection details. [Read more](../in-app/inapp-configuration.md)
* Some expressions presented in ranking formula examples have been updated to avoid validation errors. [Read more](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)
* A warning has been added to the Define decision scopes section to specify that if AI model is used in an evaluation criteria group, all the evaluation criteria in that group must use the AI ranking method, with the same specific AI model. Moreover, only one evaluation criteria group can use AI model. [Read more](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

## August 2023 {#august-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] August '23 release have been detailed in the documentation. [Read more](release-notes.md)
* The note about **authentication cache management** in journey has been updated to detail that the token is not shared between different journeys. [Read more](../datasource/external-data-sources.md#custom-authentication-mode)
* The page about journey **entry management** has been updated to clarify behaviour. [Read more](../building-journeys/entry-management.md)
* Offer decisioning **export datasets** are now enabled by default. The note about the previous behavior has been removed.  [Read more](../offers/export-catalog/get-started-export.md)
* Various **campaign report metrics** have been renamed, in both Live and Global reports. [Read more](../reports/campaign-live-report.md)
* A new section has been added on content experiment prerequisites for the web channel. [Read more](../web/web-prerequisites.md#experiment-prerequisites)
* A warning has been added on the **Work with content templates** page to indicate that currently tracking is not supported when testing email content templates. To test tracking, you must use the content template in an email and send a proof. [Read more](../content-management/content-templates.md#test-template)
* Several warnings have been added in the **Create and publish landing pages** section to specify that you cannot access your landing page by simply copy-pasting into a web browser the URL defined when creating the page, even if published. Instead you can test it using the preview function. [Read more](../landing-pages/create-lp.md)
* A new section has been added on how to **manage consent** for the direct mail channel. [Read more](../direct-mail/test-send-direct-mail.md)

## July 2023 {#july-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] July '23 release have been detailed in the documentation. [Read more](release-notes.md)
* The wait activity documentation page has been improved with additional information and best practices related to the global timeout and reentrance usage. [Read more](../building-journeys/wait-activity.md)
* The page on entry management has been improved. [Read more](../building-journeys/entry-management.md)
* Additional information has been added about the throttling rate in the Read audience activity documentation. [Read more](../building-journeys/read-audience.md)
* Additional information has been added about retries. [Read more](../start/guardrails.md#general-actions-g)
* The **Implement personalization consent** section has been updated to describe how to manually enforce personalization consent in campaigns: you can use the segment rule builder to create an audience containing opt-out profiles or add a split activity to a composition workflow. [Read more](../privacy/opt-out.md#opt-out-expression-editor)

## June 2023 {#june-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] June '23 release have been detailed in the documentation. [Read more](release-notes.md)
* Information has been added about the discard rate ratio in the Journeys overview screen. [Read more](../building-journeys/journey-gs.md#journey-access)
* A note has been added with the steps to follow if you modify your schema with new enumeration values after creating an event [Read more](../event/about-creating.md)
* A recommendation has been added to use journeyVersionID instead of journeyVersionName when querying journeys. [Read more](../reports/sharing-common-fields.md#journeyversionid-field)
* Additional examples on the evaluation criteria order have been added to the **Create decisions** section to illustrate cases where multiple criteria and multiple decision scopes are used. [Read more](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* Decision Management documentation has been clarified with a note specifying that the use of Object Level Access Control is not available for dynamic collections. [Read more](../offers/offer-library/creating-collections.md)

## May 2023 {#may-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] May '23 release have been detailed in the documentation. [Read more](release-notes.md)
* A new page has been added to describe how to set up the subdomain that will be used to publish content coming from the Adobe Experience Manager Assets Essentials in your web experiences. [Read more](../web/web-delegated-subdomains.md)
* A new subsection has been added to explain how to add personalized tracking parameters to URLs in the Email Designer. [Read more](../email/message-tracking.md#url-tracking)
* A new section has been added to describe how to ensure that the choice of your customers who opt out from having their profile data used for personalization is honored. [Read more](../privacy/opt-out.md#opt-out-personalization)
* A note has been added about using special international characters in URLs included in email contents. [Read more](../email/message-tracking.md#insert-links)
* The permission needed to test and publish landing pages has been added. [Read more](../landing-pages/create-lp.md)
* A note has been added about the Adobe Experience Platform endpoints needed to have your custom events accounted for in Decision Management frequency capping. [Read more](../offers/data-collection/schema-requirement.md#track-custom-events)

## April 2023 {#apr-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] April '23 release have been detailed in the documentation. [Read more](release-notes.md)
* A note has been added to specify that built-in actions cannot be removed. [Read more](../start/guardrails.md#custom-actions-g)
* Information has been added on serviceEvents as well as a query example to check the details of a serviceEvent. [Read more](../reports/query-examples.md#common-queries) 
* A note has been added to specify that you cannot perform queries on time series. [Read more](../building-journeys/condition-activity.md)
* Adobe Experience Manager Assets Essentials and Adobe Stock have been added to the multi-solution integration page. [Read more](../integrations/ajo-integrations.md)
* The warning on multi-level email subdomains not being allowed has been removed as they are now supported. [Read more](../configuration/delegate-subdomain.md)
* A note has been added to specify that, if changes are made to an offer decision which is being used in a journey's message, you need to unpublish the journey and republish it. [Read more](../building-journeys/publish-journey.md)
* Explanation on how to make sure events are correctly accounted for in the capping counter has been clarified in the decision management **Capping event** section. [Read more](../offers/offer-library/add-constraints.md#capping-event)
* A new section has been added to the **Change execution addresses** page. It specifies that it is possible to override the execution field set globally in the journey advanced parameters, but the email address override should only be used for specific use cases. Most of the time, the value defined as the primary address in the **Execution fields** is the one that should be used. [Read more](../configuration/primary-email-addresses.md#journey-parameters)
* The **URL tracking** section now provides the list and description of all contextual attributes that can be set for URL tracking in an email channel configuration. [Read more](../email/email-settings.md#url-tracking)

## March 2023 {#march-2023}

* The Journey Optimizer schema dictionary is now available. You will find the complete list of fields and attributes for each schema.  [Read more](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)
* All new features and improvements coming with [!DNL Journey Optimizer] March '23 release have been detailed in the documentation. [Read more](release-notes.md)
* Added a step to enable Adobe Analytics events in your journeys. [Read more](../event/about-analytics.md)
* A new section has been created in the Decision management guide on how to collect offer decisioning feedback in Adobe Experience Platform, including which offers are displayed and how users interact with them. [Read more](../offers/data-collection/data-collection.md)
* A new subsection has been added to the **Create decision** section to explain the difference between evaluating criteria in a sequential order or at the same time. [Read more](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* A guardrail has been added for read audience journeys with incremental read. You cannot create a new version, you need to duplicate the journey. [Read more](../start/guardrails.md#journey-versions-g)
* The use case on how to limit throughput put has been updated with information on throttling capabilities. [Read more](../building-journeys/limit-throughput.md)
* A note has been added to specify that scalar arrays are not supported in response payload definition. [Read more](../datasource/external-data-sources.md)
* The section on profile cap conditions has been updated. [Read more](../building-journeys/condition-activity.md#profile_cap)

## February 2023 {#feb-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] Feb '23 release have been detailed in the documentation. [Read more](release-notes.md)
* Information has been added about the canvas toolbar. [Read more](../building-journeys/using-the-journey-designer.md#gs-journey-design)
* Information has been added to state that internal Adobe addresses are not allowed in URLs and APIs. [Read more](../start/guardrails.md)
* A note has been added in the API-triggered campaigns documentation to specify that contextual attributes passed into the request cannot exceed 50kb. [Read more](../campaigns/api-triggered-campaigns.md#contextual)
* Information was added on how opt-out information is stored in the **Consent Service Dataset** after recipients are unsubscribed through a landing page. [Read more](../landing-pages/lp-use-cases.md#configure-opt-out)

## January 2023 {#jan-2023}

* All new features and improvements coming with [!DNL Journey Optimizer] Jan '23 release have been detailed in the documentation. [Read more](release-notes.md)
* Information has been added on custom authentication endpoints in the capping documentation. [Read more](../configuration/external-systems.md)
* A new custom authentication example has been added in the external datasources section. [Read more](../datasource/external-data-sources.md#custom-authentication-mode)
* A note has been added about Data Collection Core Service (DCCS) for event-triggered journeys. [Read more](../start/guardrails.md#events-g)
* A note on identity namespace retrieval has been added in the [Read audience](../building-journeys/read-audience.md), [Audience qualification](../building-journeys/audience-qualification-events.md) and [Event creation](../event/about-creating.md) sections.
* Accessibility features in [!DNL Journey Optimizer] are now grouped in a dedicated page. [Read more](../start/accessibility.md)
* The examples have been updated in the Operators section of the advanced expression editor documentation. [Read more](../building-journeys/expression/operators.md)
* A note has been added about the limitation on lookup with array of objects. [Read more](../event/experience-event-schema.md#relationships_limitations)
* Added a new page about data management in [!DNL Journey Optimizer]. [Read more](../data/gs-data.md)
* Added a table listing all codes that can be returned in the response when delivering offers using the Decisioning API. [Read more](../offers/api-reference/offer-delivery-api/decisioning-api.md)

+++

+++ 2022

## December 2022 {#december-2022}

* The Messages guide has been reorganized and split into dedicated guides for each channel:

    * [Email channel](../email/get-started-email.md)
    * [Push notification channel](../../rp_landing_pages/push-landing-page.md)
    * [SMS channel](../sms/get-started-sms.md)

* The Configuration guide has been reorganized for improved readability. [Read more](../configuration/get-started-configuration.md)

## November 2022 {#november-2022}

* Added a new page about Journey Optimizer integrations. [Read more](../integrations/ajo-integrations.md)
* Added a recommendation about the length of mirror pages URLs. [Read more](../email/message-tracking.md)
* A new subsection in the email settings configuration has been added on the reply to email address, including recommendations to ensure proper reply management. [Read more](../email/email-settings.md#reply-to-email)
* Added a section on how to modify the content of a message in a live journey. [Read more](../building-journeys/journeys-message.md#update-live-content)

## October 2022 {#october-2022}

* Added a journey use case on how to limit throughput using External Data Sources and Custom Actions. [Read more](../building-journeys/limit-throughput.md)
* The journey use case section has been reorganized into two categories: [Business use cases](../building-journeys/journeys-uc.md) and [Technical use cases](../building-journeys/collections.md).
* The **Entity Dataset** section has been updated with more details. [Read more](../data/datasets-query-examples.md#entity-dataset)
* The opt-out management and consent policies sections have been reorganized. [Read more](../privacy/opt-out.md)
* The section on advanced parameters in journey messages has been clarified and now specifies that email address override should only be used for specific use cases. Most of the time, the value defined as the primary address in the **Execution fields** is the one that should be used. 
* Added a note to the **Configure landing page subdomains** section to specify that capital letters are not allowed in landing page subdomains. [Read more](../landing-pages/lp-subdomains.md)

## September 2022 {#september-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] September '22 release have been detailed in the documentation. [Read more](release-notes.md)
* Added a best practice related to the use of wait activities in recurring read audience journeys. [Read more](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* Added new step event query examples as well as information on the difference between id, instanceid and profileid. [Read more](../reports/query-examples.md).
* Updated the pages related to the [toDateOnly](../building-journeys/functions/conversion-functions.md#toDateOnly) and [toString](../building-journeys/functions/conversion-functions.md#toString) functions.
* Added details on the time condition parameters. [Read more](../building-journeys/condition-activity.md#time_condition)
* Added information on built-in datasets. [Read more](../data/get-started-datasets.md#access-datasets)
* The Global report and Live report sections have been improved and reorganized. [Read more](../reports/report-gs-cja.md)
* A list of every reporting metric available in Adobe Journey Optimizer has been added.
[Read more](../reports/report-gs-cja.md#email-and-sms-metrics)
* The BCC email section has been moved to the new Support for archiving page. [Read more](../configuration/archiving-support.md)

## August 2022 {#august-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] August '22 release have been detailed in the documentation. [Read more](release-notes.md)
* The Frequency rules section has been updated to reflect the new in-line messaging flow.
* A video showing how to configure subscriptions and create landing pages is now referenced in the Get started with landing pages section. [Read more](../landing-pages/get-started-lp.md#video)
* A limitation has been added for journeys using Read Audience activities. [Read more](../building-journeys/read-audience.md)
* The expression editor operators page has been improved. [Read more](../building-journeys/expression/operators.md)
* A section on how to schedule a campaign has been added. [Read more](../campaigns/create-campaign.md)
* General syntax rules section for expression editor has been updated to take into account the new rule regarding the backslash symbol escaping in literal functions. The existing published messages are not impacted by this change. Only the new or draft messages must be updated. [Read more](../personalization/personalization-syntax.md#general-rules)

## July 2022 {#july-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] July '22 release have been detailed in the documentation. [Read more](release-notes.md)
* The **Set up channel configurations** section has been clarified and updated with links to the page describing how to configure the SMS channel. [Read more](../configuration/channel-surfaces.md#create-channel-surface)
* In the journey properties, the **Profile Time zone** option is now disabled by default. [Read more](../building-journeys/timezone-management.md#timezone-from-profiles)
* In the **Wait** activity, the **Fixed date** option is no longer available. [Read more](../building-journeys/wait-activity.md)
* Added more information on the **Incremental read** option in the **Read audience** activity. [Read more](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* Added recommendations on the **Profile cap** condition type. [Read more](../building-journeys/condition-activity.md#profile_cap)
* Added a limitation on business events. [Read more](../start/guardrails.md#events-g)

## June 2022 {#june-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] June '22 release have been detailed in the documentation. [Read more](release-notes.md)
* A new section about Privacy requests has been added to the documentation. [Read more](../privacy/requests.md)
* A new section about Audit logs on resources has been added to the documentation. [Read more](../privacy/audit-logs.md)
* A new section about how to add HTML or JSON content coming from Adobe Experience Cloud Asset library to an offer representation has been added to the documentation. [Read more](../offers/offer-library/add-representations.md#html-json)
* Added a new page on journey lifecyle. [Read more](../building-journeys/journey.md#journey-versions)
* Updated the Wait activity page. [Read more](../building-journeys/wait-activity.md)
* Added the list of Adobe Journey Optimizer datasets with query examples. [Read more](../data/datasets-query-examples.md)
* The Allowed list page has been moved to the Configuration section. [Read more](../configuration/allow-list.md)
* The Suppression list page has been updated to clarify some information, including the fact that all ASCII characters comprised between 32 and 126 are allowed in the reason for suppression field. [Read more](../configuration/manage-suppression-list.md)
* The link to guardrails and static limits for Decision management has been added. [Read more](../start/guardrails.md)
* Send-Time Optimization is now available for all customers. The beta mention has been removed. [Read more](../building-journeys/send-time-optimization.md)
* The Batch Decisioning API has been added to the list of available APIs to delivery personalized offers. [Read more](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)

## May 2022 {#may-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] May '22 release have been detailed in the documentation. [Read more](release-notes.md)
* New query examples related to [audience qualification](../reports/query-examples.md#segment-qualification-queries) and [events](../reports/query-examples.md#event-based-queries) have been added.
* The email design section now mentions new built-in templates available to start content with. Related screenshots have been updated. [Read more](../email/get-started-email-design.md)
* Links to key resources have been updated in Journey Optimizer documentation home page.
* Screenshots for landing page and subscription reporting have been updated. [Read more](../reports/live-report.md)
* A note has been added stating that the Delete method is not supported in custom actions. [Read more](../action/about-custom-action-configuration.md)
* Links to how-to videos have been updated.
* The [Email configuration](../configuration/about-subdomain-delegation.md), [Message presets](../configuration/channel-surfaces.md) and [Configure landing pages](../landing-pages/lp-subdomains.md) sections have been reorganized for improved readability.
* The URL tracking section has been updated and improved with examples. [Read more](../email/email-settings.md#url-tracking)
* A new subsection on setting up a forward email address has been added. Note that you cannot do it through the user interface. [Read more](../email/email-settings.md#forward-email)

## April 2022 {#april-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] April '22 release have been detailed in the documentation. [Read more](release-notes.md)
* The **reactions** event documentation page has been updated. [Read more](../building-journeys/reaction-events.md)
* Videos for Decision Management capabilities have been updated to reflect Journey Optimizer user interface. [Read more](../offers/get-started/starting-offer-decisioning.md)
* The **Get Started with Datasets** section has been improved to detail how to access and create datasets. [Read more](../data/get-started-datasets.md)
* Links to help guides and product release notes have been added to the **Adobe Journey Optimizer Documentation** home page. [Read more](https://experienceleague.adobe.com/docs/journey-optimizer.html)
* The **Create message presets** section now specifies that you cannot proceed with preset creation while the selected IP pool is under edition (**[!UICONTROL Processing]** status) and has never been associated with the selected subdomain. [Read more](../configuration/channel-surfaces.md#subdomains-and-ip-pools)
* The message presets **URL tracking** section has been updated to reflect minor changes in the user interface. [Read more](../configuration/channel-surfaces.md#url-tracking)

## March 2022 {#march-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] March '22 release have been detailed in the documentation. [Read more](release-notes.md)
* A new page on getting started with AI models has been added to the **Offer decisioning** section, including a thorough description of the [auto-optimization model](../offers/ranking/auto-optimization-model.md), the algorithm it uses and more technical details. [Read more](../offers/ranking/ai-models.md)
* The test profile creation page has been moved to the  **Audience, profiles and identity** section. [Read more](../audience/creating-test-profiles.md)
* Added an example on how to add an expression as a default value in the expression editor. [Read more](../building-journeys/expression/field-references.md#default-value)
* The **Create personalized offers** section has been reorganized for improved readability. [Read more](../offers/offer-library/creating-personalized-offers.md)
* A new section has been added to describe the impacts that changing an offer's start and/or end dates may have on this offer's frequency capping. [Read more](../offers/offer-library/add-constraints.md#capping-change-date)
* The **Change the primary email addresses** section has been updated to reflect the user interface changes. [Read more](../configuration/primary-email-addresses.md)

## February 2022 {#feb-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] Feb '22 release have been detailed in the documentation. [Read more](release-notes.md)
* The [replace](../building-journeys/functions/string-functions.md#replace) and [replaceAll](../building-journeys/functions/string-functions.md#replaceAll) function documentation pages have been updated with additional information and examples regarding the target parameter.
* Best practices have been added to the [Operators](../building-journeys/expression/operators.md#important-notes) page.

## January 2022 {#january-2022}

* All new features and improvements coming with [!DNL Journey Optimizer] Jan '22 release have been detailed in the documentation. [Read more](release-notes.md)
* The **Offer decisioning AI rankings** section has been updated with a more detailed description of the auto-optimization model. [Read more](../offers/ranking/auto-optimization-model.md)
* A new section on the schema requirements needed to be able to send in event types when using an AI model has been added. [Read more](../offers/data-collection/schema-requirement.md)
* The section related to [!DNL Journey Optimizer] personalization capabilities has been reorganized for better readability. [Read more](../personalization/personalize.md)
* The **Create message presets** section has been divided into several sections for improved clarity. [Read more](../configuration/channel-surfaces.md#create-channel-surface)
* The **Opt-out management** section has been clarified and slightly reorganized. [Read more](../privacy/opt-out.md#opt-out-management)
* The **Insert links** section has been updated to reflect the recent user interface changes. [Read more](../email/message-tracking.md#insert-links)

+++

+++ 2021

## November 2021 {#november-2021}

* A full description of the **advanced expression editor** used in journeys is now available. [Read more](../building-journeys/expression/expressionadvanced.md)
* A new section about **CNAME subdomain delegation method** has been added. [Read more](../configuration/delegate-subdomain.md#cname-subdomain-setup)

## October 2021 {#october-2021}

* All new features and improvements coming with [!DNL Journey Optimizer] Oct '21 release have been detailed in the documentation. [Read more](release-notes.md)
* Added **Date time function** list. [Read more](../personalization/functions/dates.md)
* New **Get Started sections per user persona**. Take your own path to get to your goals faster! [Read more](../start/quick-start.md)
* New **Edit a message preset** section. [Read more](../configuration/channel-surfaces.md#edit-channel-surface)
* New **Edit a PTR record** section. [Read more](../configuration/ptr-records.md#edit-ptr-record)
* New **Deactivate a message preset** section. [Read more](../configuration/channel-surfaces.md#edit-channel-surface#deactivate-a-surface)
* New limitations added to the **Decision Management API developer guide** on offer constraints not supported with the mobile [!DNL Experience Edge] workflows. [Read more](../offers/api-reference/offers-api/personalized-offers/create.md#limitations)
* New **Create simulations** section. [Read more](../offers/offer-activities/simulation.md)
* Updated **Add decision scopes** section. [Read more](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)
* Updated **Define content for your representations** section, including a new [subsection](../offers/offer-library/creating-personalized-offers.md#custom-text) on how to define and personalize custom text. [Read more](../offers/offer-library/creating-personalized-offers.md#content)

## September 2021 {#september-2021}

* The following function pages have been updated: [sethours](../building-journeys/functions/date-functions.md#setHours), [getListItem](../building-journeys/functions/list-functions.md#getListItem), [inSegment](../building-journeys/functions/functioninaudience.md)

* The following functions have been added: [filter](../building-journeys/functions/list-functions.md#filter), [intersect](../building-journeys/functions/list-functions.md#intersect), [toDateOnly](../building-journeys/functions/conversion-functions.md#toDateOnly)

* The dateOnly date type has been added in the expression editor documentation. [Read more](../building-journeys/expression/data-types.md)

* Added details on custom action cache duration. [Read more](../datasource/external-data-sources.md#custom-authentication-mode)

* Added information on custom action default ports. [Read more](../action/about-custom-action-configuration.md#url-configuration)

* Added information on multiple business event use cases. [Read more](../event/about-creating-business.md#multiple-business-events)

* Added commonly used examples to query Journey Step Events in Data Lake. [Read more](../reports/query-examples.md)

* Added a new **Limitations** page. [Read more](../start/guardrails.md)

* Improved the **Quick start** page with steps for different personas. [Read more](../start/quick-start.md)

* Now all the Decision Management features described in the dedicated section also apply to the Adobe Experience Platform users leveraging the Offer Decisioning application. [Read more](../offers/get-started/starting-offer-decisioning.md)

* Added a subsection to clarify the differences between using audiences versus decision rules when applying a constraint to restrict the selection of offers for a given placement. [Read more](../offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* Added specific ranking formula examples to illustrate some real-life use cases. [Read more](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)

* Added a subsection on how to edit IP pools. [Read more](../configuration/ip-pools.md#edit-ip-pool)

## August 2021 {#august-2021}

* All new features and improvements coming with [!DNL Journey Optimizer] August '21 release have been detailed in the documentation. [Read more](release-notes.md)
* Updated Decision management permissions. [Read more](../administration/ootb-product-profiles.md)
* Updated Email Designer screenshots with latest UI.
* Updated the configuration procedure for custom actions with dynamic URL paths and dynamic headers. [Read more](../action/about-custom-action-configuration.md#url-configuration)
* Added a section about accessibility features and shortcuts. [Read more](../start/user-interface.md#accessibility)
* Added a section about audience evaluation methods. [Read more](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)
* Added notes to the Suppression list, Allowed list and Email global/live report sections to specify that profiles with Suppressed and Not allowed statuses are excluded from the Email report Sent metrics. [Read more](../reports/report-gs-cja.md)
* Added a new section to describe how to retrieve email addresses or domains that were excluded from a sending because they were not on the allowed list. [Read more](../configuration/allow-list.md#reporting)
* Updated the Enable the allow list section. [Learn more](../configuration/allow-list.md#enable-allow-list)
* Updated the Monitor message presets section with the possible preset creation failure reasons and details on such errors. [Read more](../configuration/channel-surfaces.md#monitor-channel-surfaces)
* Updated and renamed the Retry time period section to reflect the fact that you can now adjust the email retry setting in the message presets. [Read more](../configuration/retries.md#retry-duration)
* Updated the Delegate a subdomain section with more detailed information on the validation process performed by Adobe. [Read more](../configuration/delegate-subdomain.md#subdomain-validation)
* Added a section to describe how to manually add email addresses and domains to the suppression list. [Read more](../configuration/manage-suppression-list.md#add-addresses-and-domains)
* Updated the [Access the suppression list](../configuration/manage-suppression-list.md#access-suppression-list) section and [Retries](../configuration/retries.md) sections to reflect the new user interface.
* The new flow to add and configure representations when creating an offer has been documented. [Read more](../offers/offer-library/creating-personalized-offers.md#representations)

## July 2021 {#july-2021}

* All new features and improvements coming with [!DNL Journey Optimizer] July '21 release have been detailed in the documentation. [Read more](release-notes.md)
* Added direct links to Experience Platform services documentation in [!DNL Journey Optimizer] home page and table of contents
* New landing pages for Experience Platform services available in [!DNL Journey Optimizer] 
* Added links to [!DNL Journey Optimizer] product description in the home page
* Added tutorial videos in multiple pages
* Optimized home page imagery
* Moved, improved and renamed 'Message tracking' section to 'Add links and track messages'. [Read more](../email/message-tracking.md)
* Added a subsection on mirror pages. [Read more](../email/message-tracking.md#mirror-page)
* Renamed 'offer activities' as 'decisions' and 'decisions' as 'decision scopes' in documentation and screens. [Read more](../offers/get-started/starting-offer-decisioning.md)
* New use case: [personalize a message with helper functions](../personalization/personalization-use-case-helper-functions.md)
* Updated the Read audience documentation to reflect materialized segment impacts. [Read more](../building-journeys/read-audience.md)
* Updated the Journey limitations. [Read more](../start/guardrails.md)
* Updated the Configure offers selection in decisions section. [Read more](../offers/offer-activities/configure-offer-selection.md)
* Added a warning to mention that event-based offers are not currently supported. [Read more](../offers/offer-library/creating-personalized-offers.md#eligibility)
* Documented the Decision Management new **[!UICONTROL Overview]** tab. [Read more](../offers/get-started/user-interface.md#overview)
* Added new sections to describe the actions available from the offer and decision lists: [Offer list](../offers/offer-library/creating-personalized-offers.md#offer-list) and [Decision list](../offers/offer-activities/create-offer-activities.md#decision-list).

+++
-->
