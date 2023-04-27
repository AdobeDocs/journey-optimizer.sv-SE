---
product: Journey Optimizer
audience: end-user
user-guide-title: Användarhandbok om Journey Optimizer
user-guide-description: Använd Journey Optimizer för att skapa och leverera sammankopplade, kontextuella och personanpassade upplevelser till kunderna
type: Documentation
solution: Journey Optimizer
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '1371'
ht-degree: 33%

---

# Hjälp om Adobe Journey Optimizer {#using}

+ [Journey Optimizer-dokumentation](ajo-home.md)
+ Nyheter? {#whats-new}
   + [Senaste versionsinformation](using/rn/release-notes.md)
   + Tidigare versionsinformation {#previous-rn-new}
      + [Versionsinformation 2022](using/rn/release-notes-2022.md)
      + [Versionsinformation 2021](using/rn/release-notes-2021.md)
   + [Dokumentationsuppdateringar](using/rn/documentation-updates.md)
+ Kom igång{#get-started}
   + [Vad är Journey Optimizer?](using/start/get-started.md)
   + Snabbstartguider{#quick-start}
      + [Översikt](using/start/quick-start.md)
      + [Kom igång som marknadsförare](using/start/path/marketer.md)
      + [Kom igång som datatekniker](using/start/path/data-engineer.md)
      + [Kom igång som administratör](using/start/path/administrator.md)
      + [Kom igång som utvecklare](using/start/path/developer.md)
   + [Användargränssnitt](using/start/user-interface.md)
   + [Tillgänglighet](using/start/accessibility.md)
   + [Integreringar](using/start/ajo-integrations.md)
   + [Guardrails](using/start/guardrails.md)
+ Resor {#orchestrate-journeys}
   + [Kom igång med resor](using/building-journeys/journey.md)
   + Skapa en resa{#create-journey}
      + [Skapa den första resan](using/building-journeys/journey-gs.md)
      + [Utforma din resa](using/building-journeys/using-the-journey-designer.md)
      + [Testa din resa](using/building-journeys/testing-the-journey.md)
      + [Publicera din resa](using/building-journeys/publishing-the-journey.md)
   + Hantera dina resor{#manage-journey}
      + [Avsluta din resa](using/building-journeys/end-journey.md)
      + [Hantering av tidszoner](using/building-journeys/timezone-management.md)
      + [Profilingångshantering](using/building-journeys/entry-management.md)
      + [Kopiera en resa till en annan sandlåda](using/building-journeys/copy-to-sandbox.md)
      + [Felsök din resa](using/building-journeys/troubleshooting.md)
      + [Integrera med intelligenta tjänster](using/building-journeys/ai-services-overview.md)
      + [Hantera taggar under resor](using/building-journeys/tags.md)
   + Aktiviteter {#about-journey-building}
      + [Kom igång med reseaktiviteter](using/building-journeys/about-journey-activities.md)
      + [Allmänna händelser](using/building-journeys/general-events.md)
      + [Reaktion](using/building-journeys/reaction-events.md)
      + [Segmentkvalificering](using/building-journeys/segment-qualification-events.md)
      + [Villkor](using/building-journeys/condition-activity.md)
      + [Vänta](using/building-journeys/wait-activity.md)
      + [Lässegment](using/building-journeys/read-segment.md)
      + [E-post, i appen, push, SMS](using/building-journeys/journeys-message.md)
      + [Anpassade åtgärder](using/building-journeys/using-custom-actions.md)
      + [Adobe Campaign Standard-åtgärder](using/building-journeys/using-adobe-campaign-standard.md)
      + [Adobe Campaign v7/v8-åtgärder](using/building-journeys/using-adobe-campaign-classic.md)
      + [Hoppa](using/building-journeys/jump.md)
      + [Uppdatera profil](using/building-journeys/update-profiles.md)
   + Bygga uttryck {#building-advanced-conditions-journeys}
      + [Översikt](using/building-journeys/expression/expressionadvanced.md)
      + Syntax {#syntax}
         + [Allmänt](using/building-journeys/expression/generalities.md)
         + [Villkorlig instruktion](using/building-journeys/expression/conditional-instruction.md)
         + [Datatyper](using/building-journeys/expression/data-types.md)
         + [Fältreferenser](using/building-journeys/expression/field-references.md)
         + [Funktioner för att hantera samlingar](using/building-journeys/expression/collection-management-functions.md)
         + [Operatorer](using/building-journeys/expression/operators.md)
         + [Resans egenskaper](using/building-journeys/expression/journey-properties.md)
         + [Exempel](using/building-journeys/expression/advanced-editor-use-cases.md)
      + Funktioner {#main-functions-journey}
         + [Huvudfunktioner](using/building-journeys/expression/functions.md)
         + Adobe Experience Platform {#adobe-experience-platform}
            + [inSegment](using/building-journeys/functions/functioninsegment.md)
         + Aggregera {#aggregation}
            + [avg](using/building-journeys/functions/functionavg.md)
            + [count](using/building-journeys/functions/functioncount.md)
            + [countOnlyNull](using/building-journeys/functions/functioncountonlynull.md)
            + [countWithNull](using/building-journeys/functions/functioncountwithnull.md)
            + [distinctCount](using/building-journeys/functions/functiondistinctcount.md)
            + [distinctCountWithNull](using/building-journeys/functions/functiondistinctcountwithnull.md)
            + [max](using/building-journeys/functions/functionmax.md)
            + [min](using/building-journeys/functions/functionmin.md)
            + [sum](using/building-journeys/functions/functionsum.md)
         + Konvertering {#conversion}
            + [toBool](using/building-journeys/functions/functiontobool.md)
            + [toDateOnly](using/building-journeys/functions/functiontodateonly.md)
            + [toDateTime](using/building-journeys/functions/functiontodatetime.md)
            + [toDateTimeOnly](using/building-journeys/functions/functiontodatetimeonly.md)
            + [toDecimal](using/building-journeys/functions/functiontodecimal.md)
            + [toDuration](using/building-journeys/functions/functiontoduration.md)
            + [toInteger](using/building-journeys/functions/functiontointeger.md)
            + [toString](using/building-journeys/functions/functiontostring.md)
         + Datum {#date}
            + [currentTimeInMillis](using/building-journeys/functions/functioncurrenttimeinmillis.md)
            + [inLastDays](using/building-journeys/functions/functioninlastdays.md)
            + [inLastHours](using/building-journeys/functions/functioninlasthours.md)
            + [inLastMonths](using/building-journeys/functions/functioninlastmonths.md)
            + [inLastYears](using/building-journeys/functions/functioninlastyears.md)
            + [inNextDays](using/building-journeys/functions/functioninnextdays.md)
            + [inNextHours](using/building-journeys/functions/functioninnexthours.md)
            + [inNextMonths](using/building-journeys/functions/functioninnextmonths.md)
            + [inNextYears](using/building-journeys/functions/functioninnextyears.md)
            + [now](using/building-journeys/functions/functionnow.md)
            + [nowWithDelta](using/building-journeys/functions/functionnowwithdelta.md)
            + [setHours](using/building-journeys/functions/functionsethours.md)
            + [setDays](using/building-journeys/functions/functionsetdays.md)
            + [updateTimeZone](using/building-journeys/functions/functionupdatetimezone.md)
         + Lista {#list}
            + [distinct](using/building-journeys/functions/functiondistinct.md)
            + [distinctWithNull](using/building-journeys/functions/functiondistinctwithnull.md)
            + [filter](using/building-journeys/functions/functionfilter.md)
            + [getListItem](using/building-journeys/functions/functiongetlistitem.md)
            + [in](using/building-journeys/functions/functionin.md)
            + [korsa](using/building-journeys/functions/functionintersect.md)
            + [gräns](using/building-journeys/functions/functionlimit.md)
            + [listSize](using/building-journeys/functions/functionlistsize.md)
            + [serializeList](using/building-journeys/functions/functionserializelist.md)
            + [sort](using/building-journeys/functions/functionsort.md)
         + Matematik {#math}
            + [random](using/building-journeys/functions/functionrandom.md)
            + [round](using/building-journeys/functions/functionround.md)
         + Sträng {#string}
            + [concat](using/building-journeys/functions/functionconcat.md)
            + [contain](using/building-journeys/functions/functioncontain.md)
            + [containIgnoreCase](using/building-journeys/functions/functioncontainwithignorecase.md)
            + [endWith](using/building-journeys/functions/functionendwith.md)
            + [endWithIgnorecase](using/building-journeys/functions/functionendwithignorecase.md)
            + [equalIgnoreCase](using/building-journeys/functions/functionequalignorecase.md)
            + [indexOf](using/building-journeys/functions/functionindexof.md)
            + [isEmpty](using/building-journeys/functions/functionisempty.md)
            + [isNotEmpty](using/building-journeys/functions/functionisnotempty.md)
            + [lastIndexOf](using/building-journeys/functions/functionlastindexof.md)
            + [längd](using/building-journeys/functions/functionlength.md)
            + [nedre](using/building-journeys/functions/functionlower.md)
            + [matchRegExp](using/building-journeys/functions/functionmatchregexp.md)
            + [notequalIgnoreCase](using/building-journeys/functions/functionnotequalignorecase.md)
            + [ersätta](using/building-journeys/functions/functionreplace.md)
            + [replaceAll](using/building-journeys/functions/functionreplaceall.md)
            + [dela](using/building-journeys/functions/functionsplit.md)
            + [startWith](using/building-journeys/functions/functionstartwith.md)
            + [startWithIgnoreCase](using/building-journeys/functions/functionstartwithignorecase.md)
            + [substr](using/building-journeys/functions/functionsubstr.md)
            + [trim](using/building-journeys/functions/functiontrim.md)
            + [övre](using/building-journeys/functions/functionupper.md)
            + [uuid](using/building-journeys/functions/functionuuid.md)
   + Användningsfall {#journey-use-cases}
      + Användningsexempel {#business-use-cases}
         + [Skicka flerkanalsmeddelanden](using/building-journeys/journeys-uc.md)
         + [Skicka ett meddelande med Campaign v7/v8](using/building-journeys/ajo-ac.md)
         + [Skicka ett meddelande till prenumeranter](using/building-journeys/message-to-subscribers-uc.md)
      + Tekniska användningsfall {#technical-use-cases}
         + [Skicka samlingar dynamiskt med anpassade åtgärder](using/building-journeys/collections.md)
         + [Rita upp leveranser](using/building-journeys/ramp-up-deliveries-uc.md)
         + [Begränsa genomströmning med externa datakällor och anpassade åtgärder](using/building-journeys/limit-throughput.md)
+ Kampanjer{#campaigns}
   + [Kom igång med kampanjer](using/campaigns/get-started-with-campaigns.md)
   + [Skapa en kampanj](using/campaigns/create-campaign.md)
   + [Granska och aktivera en kampanj](using/campaigns/review-activate-campaign.md)
   + [Hantera kampanjer](using/campaigns/modify-stop-campaign.md)
   + Innehållsexperiment {#content-experiment}
      + [Kom igång med innehållsexperiment](using/campaigns/get-started-experiment.md)
      + [Skapa ett innehållsexperiment](using/campaigns/content-experiment.md)
      + [Förstå statistiska beräkningar](using/campaigns/experiment-calculations.md)
      + [Konfigurera experimentrapporter](using/campaigns/reporting-configuration.md)
      + [Statistiska beräkningar i experimentrapporten](using/campaigns/experiment-report-calculations.md)
   + [Utlösa kampanjer med API:er](using/campaigns/api-triggered-campaigns.md)
+ E-postkanal {#email}
   + [Kom igång med e-post](using/email/get-started-email.md)
   + [Skapa ett e-postmeddelande](using/email/create-email.md)
   + Designa e-postinnehåll {#design-email}
      + [Kom igång med e-postdesign](using/email/get-started-email-design.md)
      + Börja skapa innehåll {#start-creating-content}
         + [Designa innehåll från grunden](using/email/content-from-scratch.md)
         + [Importera innehåll](using/email/existing-content.md)
         + [Koda eget innehåll](using/email/code-content.md)
         + [Arbeta med mallar](using/email/email-templates.md)
      + Designa innehåll {#add-content}
         + [Använda innehållskomponenter](using/email/content-components.md)
         + [Lägga till länkar och spåra meddelanden](using/email/message-tracking.md)
         + Hantera resurser {#manage-asset}
            + [Arbeta med Assets Essentials](using/email/assets-essentials.md)
            + [Arbeta med Adobe Stock](using/email/stock.md)
         + [Infoga personaliserade erbjudanden](using/email/add-offers-email.md)
         + [Generera textversionen](using/email/text-version-email.md)
         + [Lägga till en förrubrik](using/email/preheader.md)
      + Redigera stil {#edit-style}
         + [Kom igång med e-postformat](using/email/get-started-email-style.md)
         + [Redigera bakgrundsinställningar](using/email/backgrounds.md)
         + [Justera lodrät justering och utfyllnad](using/email/alignment-and-padding.md)
         + [Definiera ett format för länkar](using/email/styling-links.md)
         + [Lägg till textbundna formatattribut](using/email/inline-styling.md)
   + [Förhandsgranska och testa din e-post](using/email/preview.md)
   + [Skapa innehållsmallar](using/email/content-templates.md)
   + [Använd Experience Manager-mallar](using/email/aem-templates.md)
   + [Hantera e-postavanmälan](using/email/email-opt-out.md)
   + Konfigurera e-postkanal {#configure-email}
      + [Kom igång med e-postkonfiguration](using/email/get-started-email-config.md)
      + [Konfigurera inställningar för e-postyta](using/email/email-settings.md)
+ Kanal i appen{#in-app}
   + [Kom igång med kanalen i appen](using/in-app/get-started-in-app.md)
   + [Skapa ett meddelande i appen](using/in-app/create-in-app.md)
   + [Skapa ett meddelande i appen på en resa](using/in-app/create-in-app-journey.md)
   + [Designa ditt innehåll i appen](using/in-app/design-in-app.md)
   + [Testa och skicka meddelanden i appen](using/in-app/send-in-app.md)
   + [Konfigurera kanal i appen](using/in-app/inapp-configuration.md)
+ Push-meddelandekanal{#push}
   + [Kom igång med push-meddelanden](using/push/get-started-push.md)
   + [Skapa ett push-meddelande](using/push/create-push.md)
   + [Utforma ett push-meddelande](using/push/design-push.md)
   + [Skicka push-meddelanden](using/push/send-push.md)
   + Konfigurera push-meddelanden{#push-config}
      + [Push-meddelandeflöde](using/push/push-gs.md)
      + [Konfigurera kanal för push-meddelanden](using/push/push-configuration.md)
      + [Arbetsflöde för snabb start av mobil introduktion](using/push/mobile-onboarding-wf.md)
+ SMS-kanal{#sms}
   + [Kom igång med SMS](using/sms/get-started-sms.md)
   + [Skapa ett SMS-meddelande](using/sms/create-sms.md)
   + [Förhandsgranska och testa ditt SMS](using/sms/send-sms.md)
   + [Hantera SMS-avanmälan](using/sms/sms-opt-out.md)
   + [Konfigurera SMS-kanal](using/sms/sms-configuration.md)
   + [Konfigurera SMS-underdomäner](using/sms/sms-subdomains.md)
+ Direktutskick {#direct-mail}
   + [Skapa direktreklam](using/direct-mail/create-direct-mail.md)
   + [Konfigurera direktreklam](using/direct-mail/direct-mail-configuration.md)
+ Webbkanal{#web}
   + [Kom igång med webbkanalen](using/web/get-started-web.md)
   + [Förutsättningar för webbkanaler](using/web/web-prerequisites.md)
   + [Skapa webbupplevelser](using/web/create-web.md)
   + [Skapa webbsidor](using/web/author-web.md)
   + [Konfigurera webbunderdomäner](using/web/web-delegated-subdomains.md)
+ Landningssidor {#landing-pages}
   + [Kom igång med landningssidor](using/landing-pages/get-started-lp.md)
   + [Skapa en landningssida](using/landing-pages/create-lp.md)
   + Designinnehåll {#landing-pages-design}
      + [Om landningssidans design](using/landing-pages/design-lp.md)
      + [Skapa innehållet på landningssidan](using/landing-pages/lp-content.md)
      + [Skapa mallar](using/landing-pages/lp-templates.md)
      + [Lägg till anpassat JavaScript](using/landing-pages/lp-custom-js.md)
   + [Skapa en prenumerationslista](using/landing-pages/subscription-list.md)
   + [Lär dig mer om användningsexempel](using/landing-pages/lp-use-cases.md)
   + Konfigurera landningssidor {#lp-configuration}
      + [Konfigurera underdomäner för landningssidor](using/landing-pages/lp-subdomains.md)
      + [Definiera förinställningar för landningssidor](using/landing-pages/lp-presets.md)
+ Personalisering och dynamiskt innehåll {#personalized-dynamic-content}
   + Personalisering {#personalization}
      + [Kom igång med personalisering](using/personalization/personalize.md)
      + [Anpassningssammanhang](using/personalization/personalization-contexts.md)
      + Bygga uttryck {#build-expressions}
         + [Anpassningssyntax](using/personalization/personalization-syntax.md)
         + Arbeta med uttrycksredigeraren {#expression-editor}
            + [Om uttrycksredigeraren](using/personalization/personalization-build-expressions.md)
            + [Lägg till attribut i favoriter](using/personalization/personalization-favorites.md)
            + [Arbeta med sparade uttryck](using/personalization/personalization-library.md)
            + [Validering av personalisering](using/personalization/personalization-validation.md)
         + Hjälpfunktioner{#functions}
            + [Kom igång med hjälpfunktioner](using/personalization/functions/functions.md)
            + [Sammanställningsfunktioner](using/personalization/functions/aggregation.md)
            + [Aritmetiska funktioner](using/personalization/functions/arithmetic-functions.md)
            + [Arrayer och listfunktioner](using/personalization/functions/arrays-list.md)
            + [Datumfunktioner](using/personalization/functions/dates.md)
            + [Boolean- och jämförelsefunktioner](using/personalization/functions/operators.md)
            + [Hjälpmedel](using/personalization/functions/helpers.md)
            + [Kartfunktioner](using/personalization/functions/maps.md)
            + [Matematiska funktioner](using/personalization/functions/math.md)
            + [Objektfunktioner](using/personalization/functions/objects.md)
            + [Strängfunktioner](using/personalization/functions/string.md)
      + Användningsfall{#personalization-use-cases}
         + [Meddelande om orderstatus](using/personalization/personalization-use-case.md)
         + [E-post om att kunden överger en kundvagn](using/personalization/personalization-use-case-helper-functions.md)
   + Dynamiskt innehåll {#dynamic}
      + [Kom igång med dynamiskt innehåll](using/personalization/get-started-dynamic-content.md)
      + [Skapa villkorsregler](using/personalization/create-conditions.md)
      + [Skapa dynamiskt innehåll](using/personalization/dynamic-content.md)
+ Segment, profiler och identitet{#segment}
   + Segment {#segments}
      + [Kom igång med segment](using/segment/about-segments.md)
      + [Skapa segment](using/segment/creating-a-segment.md)
   + Profiler{#profiles}
      + [Kom igång med profiler](using/segment/get-started-profiles.md)
      + [Skapa testprofiler](using/segment/creating-test-profiles.md)
   + [Identiteter](using/segment/get-started-identity.md)
   + Disponera målgrupper {#audience-orchestration}
      + [Kom igång med målgruppsmaterial](using/segment/get-started-audience-orchestration.md)
      + [Skapa kompositionsarbetsflöden](using/segment/create-compositions.md)
      + [Arbeta med arbetsytan](using/segment/composition-canvas.md)
      + [Få åtkomst till och hantera målgrupper](using/segment/access-audiences.md)
   + [Licensanvändning](using/segment/license-usage.md)
+ Spåra och övervaka {#reporting}
   + Live-rapport {#live-report}
      + [Kom igång med Live Report](using/reports/live-report.md)
      + [Lista över komponenter](using/reports/live-report-components.md)
      + [Journey Live-rapport](using/reports/journey-live-report.md)
      + [Campaign Live-rapport](using/reports/campaign-live-report.md)
      + [Live-rapport för landningssida](using/reports/lp-report-live.md)
      + [Live-rapport om prenumerationslista](using/reports/subscription-report-live.md)
   + Global rapport {#global-report}
      + [Kom igång med global rapport](using/reports/global-report.md)
      + [Lista över komponenter](using/reports/global-report-components.md)
      + [Rapport om global resa](using/reports/journey-global-report.md)
      + [Global kampanjrapport](using/reports/campaign-global-report.md)
      + [Global rapport för landningssida](using/reports/lp-report-global.md)
      + [Global rapport om prenumerationslista](using/reports/subscription-report-global.md)
   + Reserapporter {#reports}
      + [Skapa reserapporter](using/reports/sharing-overview.md)
      + [Lista över steghändelsefält](using/reports/sharing-field-list.md)
      + Äldre steghändelsefält {#legacy-step-event-fields}
         + [Om äldre fält](using/reports/sharing-legacy-fields.md)
         + [Resefält](using/reports/sharing-journey-fields.md)
         + [Vanliga fält](using/reports/sharing-common-fields.md)
         + [Körningsfält för åtgärd](using/reports/sharing-execution-fields.md)
         + [Fält för datahämtning](using/reports/sharing-fetch-fields.md)
         + [Identitetsfält](using/reports/sharing-identity-fields.md)
      + [Exempel på frågor](using/reports/query-examples.md)
   + levererbarhet {#deliverability}
      + [Kom igång med leverans](using/reports/deliverability.md)
      + [Förstå listan över inaktiveringar](using/reports/suppression-list.md)
   + [Larm](using/reports/alerts.md)
   + [Arbeta med Customer Journey Analytics](using/reports/cja-ajo.md)
+ Beslutshantering {#offer-decisioning}
   + Kom igång med beslutshantering {#get-started-decision}
      + [Om beslutshantering](using/offers/get-started/starting-offer-decisioning.md)
      + [Användargränssnitt](using/offers/get-started/user-interface.md)
      + [Viktiga steg för att skapa och hantera erbjudanden](using/offers/offer-library/key-steps.md)
      + [Användningsfall: infoga erbjudanden i ett e-postmeddelande](using/offers/offers-e2e.md)
   + Skapa komponenter {#create-components}
      + [Skapa placeringar](using/offers/offer-library/creating-placements.md)
      + [Skapa beslutsregler](using/offers/offer-library/creating-decision-rules.md)
      + [Skapa samlingskvalificerare](using/offers/offer-library/creating-tags.md)
   + Skapa rankningar {#rankings}
      + [Kom igång med rankningar](using/offers/ranking/get-started-rankings.md)
      + [Rankningsformler](using/offers/ranking/create-ranking-formulas.md)
      + AI-modeller {#ai-models}
         + [Om AI-modeller](using/offers/ranking/ai-models.md)
         + AI-modelltyper {#ai-model-types}
            + [Automatisk optimeringsmodell](using/offers/ranking/auto-optimization-model.md)
            + [Anpassad optimeringsmodell](using/offers/ranking/personalized-optimization-model.md)
         + [Skapa AI-modeller](using/offers/ranking/create-ranking-strategies.md)
   + Skapa och hantera erbjudanden {#managing-offers-in-the-offer-library}
      + Konfigurera erbjudanden {#configure-offers}
         + [Skapa personaliserade erbjudanden](using/offers/offer-library/creating-personalized-offers.md)
         + [Lägg till representationer](using/offers/offer-library/add-representations.md)
         + [Lägg till begränsningar](using/offers/offer-library/add-constraints.md)
      + [Skapa reserverbjudanden](using/offers/offer-library/creating-fallback-offers.md)
      + [Skapa samlingar](using/offers/offer-library/creating-collections.md)
   + Skapa och hantera beslut {#create-manage-activities}
      + [Skapa beslut](using/offers/offer-activities/create-offer-activities.md)
      + [Konfigurera urval av erbjudanden i beslut](using/offers/offer-activities/configure-offer-selection.md)
      + [Skapa simuleringar](using/offers/offer-activities/simulation.md)
   + [Använd batchbeslut](using/offers/batch-delivery.md)
   + Samla in händelsedata {#collect-event-data}
      + [Komma igång med datainsamling](using/offers/data-collection/data-collection.md)
      + [Skapa en datauppsättning för att samla in händelser](using/offers/data-collection/create-dataset.md)
      + [Konfigurera händelsehämtning](using/offers/data-collection/schema-requirement.md)
   + Skapa rapporter om beslutshantering {#create-reports}
      + [Arbeta med beslutsledningshändelser](using/offers/reports/get-started-events.md)
      + [Åtkomst till XDM-fält för händelser](using/offers/reports/xdm-fields.md)
   + Exportera din erbjudandekatalog {#export-catalog}
      + [Kom igång med export av din erbjudandekatalog ](using/offers/export-catalog/get-started-export.md)
      + [Åtkomst till den exporterade erbjudandekatalogen](using/offers/export-catalog/access-dataset.md)
      + [Datauppsättning med personaliserade erbjudanden](using/offers/export-catalog/export-offers.md)
      + [Datauppsättning med beslut](using/offers/export-catalog/export-decisions.md)
      + [Datauppsättning med placeringar](using/offers/export-catalog/export-placements.md)
      + [Datauppsättning med reserverbjudanden](using/offers/export-catalog/export-fallback.md)
   + API-referens {#api-reference}
      + [Komma igång](using/offers/api-reference/getting-started.md)
      + Skapa och hantera erbjudanden med API:er {#offers-api}
         + Placeringar {#placements}
            + [Lista placeringar](using/offers/api-reference/offers-api/placements/placements-list.md)
            + [Söka efter en placering](using/offers/api-reference/offers-api/placements/lookup.md)
            + [Skapa en placering](using/offers/api-reference/offers-api/placements/create.md)
            + [Uppdatera en placering](using/offers/api-reference/offers-api/placements/update.md)
            + [Ta bort en placering](using/offers/api-reference/offers-api/placements/delete.md)
         + Beslutsregler {#decision-rules}
            + [Lista beslutsregler](using/offers/api-reference/offers-api/decision-rules/rules-list.md)
            + [Söka efter en beslutsregel](using/offers/api-reference/offers-api/decision-rules/lookup.md)
            + [Skapa en beslutsregel](using/offers/api-reference/offers-api/decision-rules/create.md)
            + [Uppdatera en beslutsregel](using/offers/api-reference/offers-api/decision-rules/update.md)
            + [Ta bort en beslutsregel](using/offers/api-reference/offers-api/decision-rules/delete.md)
         + Samlingskvalificerare {#tags}
            + [Kvalificerare för listsamling](using/offers/api-reference/offers-api/tags/tags-list.md)
            + [Söka efter en samlingskvalificerare](using/offers/api-reference/offers-api/tags/lookup.md)
            + [Skapa en samlingskvalificerare](using/offers/api-reference/offers-api/tags/create.md)
            + [Uppdatera en samlingskvalificerare](using/offers/api-reference/offers-api/tags/update.md)
            + [Ta bort en samlingskvalificerare](using/offers/api-reference/offers-api/tags/delete.md)
         + Personaliserade erbjudanden {#personalized-offers}
            + [Lista personaliserade erbjudanden](using/offers/api-reference/offers-api/personalized-offers/offers-list.md)
            + [Söka efter ett personaliserat erbjudande](using/offers/api-reference/offers-api/personalized-offers/lookup.md)
            + [Skapa ett personaliserat erbjudande](using/offers/api-reference/offers-api/personalized-offers/create.md)
            + [Uppdatera ett personaliserat erbjudande](using/offers/api-reference/offers-api/personalized-offers/update.md)
            + [Ta bort ett personaliserat erbjudande](using/offers/api-reference/offers-api/personalized-offers/delete.md)
         + Samlingar {#collections}
            + [Lista samlingar](using/offers/api-reference/offers-api/collections/collections-list.md)
            + [Söka efter en samling](using/offers/api-reference/offers-api/collections/lookup.md)
            + [Skapa en samling](using/offers/api-reference/offers-api/collections/create.md)
            + [Uppdatera en samling](using/offers/api-reference/offers-api/collections/update.md)
            + [Ta bort en samling](using/offers/api-reference/offers-api/collections/delete.md)
         + Reserverbjudanden {#fallback-offers}
            + [Lista reserverbjudanden](using/offers/api-reference/offers-api/fallback-offers/fallback-list.md)
            + [Söka efter ett reserverbjudande](using/offers/api-reference/offers-api/fallback-offers/lookup.md)
            + [Skapa ett reserverbjudande](using/offers/api-reference/offers-api/fallback-offers/create.md)
            + [Uppdatera ett reserverbjudande](using/offers/api-reference/offers-api/fallback-offers/update.md)
            + [Ta bort ett reserverbjudande](using/offers/api-reference/offers-api/fallback-offers/delete.md)
      + Skapa och hantera beslut med API:er {#activities-api}
         + [Lista beslut](using/offers/api-reference/activities-api/activities/activities-list.md)
         + [Söka efter ett beslut](using/offers/api-reference/activities-api/activities/lookup.md)
         + [Skapa ett beslut](using/offers/api-reference/activities-api/activities/create.md)
         + [Uppdatera ett beslut](using/offers/api-reference/activities-api/activities/update.md)
         + [Ta bort ett beslut](using/offers/api-reference/activities-api/activities/delete.md)
      + Leverera erbjudanden med API:er {#offer-delivery-api}
         + [Kom igång med API:er för erbjudanden](using/offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
         + [Besluts-API](using/offers/api-reference/offer-delivery-api/decisioning-api.md)
         + [API för Edge Decisioning](using/offers/api-reference/offer-delivery-api/edge-decisioning-api.md)
         + [API för gruppbeslut](using/offers/api-reference/offer-delivery-api/batch-decisioning-api.md)
+ Datahantering {#data-management}
   + [Kom igång med datahantering](using/data/gs-data.md)
   + [Arbeta med scheman](using/data/get-started-schemas.md)
   + Journey Optimizer dataset {#datasets}
      + [Kom igång med datauppsättningar](using/data/get-started-datasets.md)
      + [Exportera Journey Optimizer-datauppsättningar](using/data/export-datasets.md)
      + [Frågeexempel](using/data/datasets-query-examples.md)
      + [Inbyggda scheman > ](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)
   + [Frågor](using/data/get-started-queries.md)
+ Konfiguration{#configuration}
   + [Kom igång med Journey Optimizer](using/configuration/get-started-configuration.md)
   + Delegera e-postunderdomäner {#delegate-subdomains}
      + [Kom igång med delegering till underdomäner](using/configuration/about-subdomain-delegation.md)
      + [Delegera en underdomän](using/configuration/delegate-subdomain.md)
      + [Lägg till en Google TXT-post](using/configuration/google-txt.md)
      + [Få åtkomst till och redigera PTR-poster](using/configuration/ptr-records.md)
      + [Skapa IP-pooler](using/configuration/ip-pools.md)
   + [Konfigurera kanalytor](using/configuration/channel-surfaces.md)
   + Övervaka e-postadresser {#monitor-reputation}
      + [Undertryckningslista](using/configuration/manage-suppression-list.md)
      + [Återförsök](using/configuration/retries.md)
      + [Tillåtelselista](using/configuration/allow-list.md)
   + [Stöd för arkivering](using/configuration/archiving-support.md)
   + [Konfigurera frekvensregler](using/configuration/frequency-rules.md)
   + [Hantera körningsadresser](using/configuration/primary-email-addresses.md)
   + Konfigurera resor {#configure-journeys}
      + [Om datakällor, händelser och åtgärder](using/configuration/about-data-sources-events-actions.md)
      + Integrera med externa system {#external-systems}
         + [Integrering av resor med externa system](using/configuration/external-systems.md)
         + [API för reglering](using/configuration/capping.md)
         + [API för begränsning](using/configuration/throttling.md)
      + Händelsekonfiguration {#events-journeys}
         + [Allmän princip](using/event/about-events.md)
         + Konfigurera en enhetshändelse {#unitary-events}
            + [Kom igång med Unitary Events](using/event/about-creating.md)
            + [Om scheman i ExperienceEvent](using/event/experience-event-schema.md)
            + [Arbeta med Adobe Analytics](using/event/about-analytics.md)
         + [Konfigurera en affärshändelse](using/event/about-creating-business.md)
         + [Ytterligare steg för att skicka händelser](using/event/additional-steps-to-send-events-to-journey.md)
      + Datakällans konfiguration{#data-source-journeys}
         + [Om datakällor](using/datasource/about-data-sources.md)
         + [Konfigurera en datakälla](using/datasource/configure-data-sources.md)
         + [Datakällan i Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
         + [Externa datakällor](using/datasource/external-data-sources.md)
      + Åtgärdskonfiguration {#action-journeys}
         + [Om åtgärder](using/action/action.md)
         + [Konfigurera en åtgärd](using/action/about-custom-action-configuration.md)
         + [Integrera med Adobe Campaign Standard](using/action/acs-action.md)
         + [Integrera med Adobe Campaign v7/v8](using/action/acc-action.md)
   + [Källor](using/start/get-started-sources.md)
+ Åtkomstkontroll {#access-control}
   + [Översikt över åtkomstkontroll](using/administration/permissions-overview.md)
   + [Inbyggda produktprofiler](using/administration/ootb-product-profiles.md)
   + [Hantera användare och produktprofiler](using/administration/permissions.md)
   + [Behörighetsnivåer](using/administration/high-low-permissions.md)
   + [Hantering av sandlådor](using/administration/sandboxes.md)
   + [Attributbaserad åtkomstkontroll](using/administration/attribute-based-access.md)
   + [Åtkomstkontroll på objektnivå](using/administration/object-based-access.md)
+ Sekretess {#privacy}
   + [Kom igång med sekretess](using/privacy/get-started-privacy.md)
   + [Förfrågningar om användarens information](using/privacy/requests.md)
   + [Granskningsåtgärder för resurser](using/privacy/audit-logs.md)
   + [Utför datahygien](using/privacy/data-hygiene.md)
   + Hantera medgivande {#consent}
      + [Hantera avanmälan](using/privacy/opt-out.md)
      + [Arbeta med policyer för samtycke](using/action/consent.md)
   + [Datastyrning](using/action/action-privacy.md)
