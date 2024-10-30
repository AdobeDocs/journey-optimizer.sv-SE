---
product: Journey Optimizer
audience: end-user
user-guide-title: Användarhandbok om Journey Optimizer
user-guide-description: Använd Journey Optimizer för att skapa och leverera sammankopplade, kontextuella och personanpassade upplevelser till kunderna
type: Documentation
solution: Journey Optimizer
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '2156'
ht-degree: 24%

---

# Hjälp om Adobe Journey Optimizer {#using}

+ [Journey Optimizer documentation](ajo-home.md)
+ Nyheter? {#whats-new}
   + [Tidig versionsinformation](using/rn/e-release-notes.md)
   + [Latest release notes](using/rn/release-notes.md)
   + {#previous-rn-new}
      + [2024](using/rn/release-notes-2024.md)
      + [2023](using/rn/release-notes-2023.md)
      + [2022](using/rn/release-notes-2022.md)
      + [2021](using/rn/release-notes-2021.md)
   + [Dokumentationsuppdateringar](using/rn/documentation-updates.md)
   + [Förbättrad arbetsyta](using/rn/new-canvas.md)
+ Komma igång{#get-started}
   + [Vad är Journey Optimizer?](using/start/get-started.md)
   + Snabbstartguider{#quick-start}
      + [Översikt](using/start/quick-start.md)
      + [Kom igång som marknadsförare](using/start/path/marketer.md)
      + [Get started as a Data engineer](using/start/path/data-engineer.md)
      + [Get started as an Administrator](using/start/path/administrator.md)
      + [Get started as a Developer](using/start/path/developer.md)
   + [Användargränssnitt](using/start/user-interface.md)
   + [Search, filter, categorize](using/start/search-filter-categorize.md)
   + [Tillgänglighet](using/start/accessibility.md)
   + [Use Case Playbooks](using/start/playbooks.md)
   + [Work with the AI Assistant](using/start/ai-assistant.md)
   + [Integreringar](using/start/ajo-integrations.md)
   + [Guardrails](using/start/guardrails.md)
   + [Bästa praxis](using/start/best-practices.md)
+ {#orchestrate-journeys}
   + [Get started with journeys](using/building-journeys/journey.md)
   + {#create-journey}
      + [Skapa den första resan](using/building-journeys/journey-gs.md)
      + [Set your journey properties](using/building-journeys/journey-properties.md)
      + [Design your journey](using/building-journeys/using-the-journey-designer.md)
      + [Test your journey](using/building-journeys/testing-the-journey.md)
      + [Simulate your journey](using/building-journeys/journey-simulation.md)
      + [Publish your journey](using/building-journeys/publishing-the-journey.md)
      + [Live report in your journey](using/building-journeys/report-journey.md)
   + {#manage-journey}
      + [Profilingångshantering](using/building-journeys/entry-management.md)
      + [Hantering av tidszoner](using/building-journeys/timezone-management.md)
      + [Avsluta din resa](using/building-journeys/end-journey.md)
      + [Kopiera en resa till en annan sandlåda](using/building-journeys/copy-to-sandbox.md)
      + [Felsök din resa](using/building-journeys/troubleshooting.md)
      + [](using/building-journeys/ai-services-overview.md)
   + Aktiviteter {#about-journey-building}
      + [Get started with journey activities](using/building-journeys/about-journey-activities.md)
      + [Allmänna händelser](using/building-journeys/general-events.md)
      + [Reaction](using/building-journeys/reaction-events.md)
      + [Audience qualification](using/building-journeys/audience-qualification-events.md)
      + [Villkor](using/building-journeys/condition-activity.md)
      + [Vänta](using/building-journeys/wait-activity.md)
      + [Läs målgrupp](using/building-journeys/read-audience.md)
      + [Inbyggda kanalåtgärder](using/building-journeys/journeys-message.md)
      + [Anpassade åtgärder](using/building-journeys/using-custom-actions.md)
      + [Adobe Campaign Standard-åtgärder](using/building-journeys/using-adobe-campaign-standard.md)
      + [Adobe Campaign v7/v8 actions](using/building-journeys/using-adobe-campaign-v7-v8.md)
      + [Jump](using/building-journeys/jump.md)
      + [Uppdatera profil](using/building-journeys/update-profiles.md)
   + Bygga uttryck {#building-advanced-conditions-journeys}
      + [Arbeta med den avancerade uttrycksredigeraren](using/building-journeys/expression/expressionadvanced.md)
      + Syntax {#syntax}
         + [Advanced expression editor syntax](using/building-journeys/expression/generalities.md)
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
            + [inAudience](using/building-journeys/functions/functioninaudience.md)
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
      + {#business-use-cases}
         + [Send multi-channel messages](using/building-journeys/journeys-uc.md)
         + [Send a message using Campaign v7/v8](using/building-journeys/ajo-ac.md)
         + [Skicka ett meddelande till prenumeranter](using/building-journeys/message-to-subscribers-uc.md)
      + {#technical-use-cases}
         + [Pass collections dynamically using custom actions](using/building-journeys/collections.md)
         + [Ramp up deliveries](using/building-journeys/ramp-up-deliveries-uc.md)
         + [Limit throughput with External Data Sources and Custom Actions](using/building-journeys/limit-throughput.md)
         + [Använd anpassade åtgärder för att skriva resehändelser i Experience Platform](using/building-journeys/custom-action-aep.md)
+ Kampanjer{#campaigns}
   + [Kom igång med kampanjer](using/campaigns/get-started-with-campaigns.md)
   + [Skapa en kampanj](using/campaigns/create-campaign.md)
   + [Granska och aktivera en kampanj](using/campaigns/review-activate-campaign.md)
   + [Hantera kampanjer](using/campaigns/modify-stop-campaign.md)
   + [Utlösa kampanjer med API:er](using/campaigns/api-triggered-campaigns.md)
+ Testa och godkänn {#test}
   + [Konflikthantering och -prioritering](using/test-approve/conflict-prioritization.md)
   + Konflikthantering och prioritering {#conflict-prioritization}
      + [Kom igång med konflikthantering och -prioritering](using/test-approve/gs-conflict-prioritization.md)
      + [Identifiera potentiella konflikter](using/test-approve/conflicts.md)
      + [Assign priority scores](using/test-approve/priority-scores.md)
      + [Journey capping &amp; arbitration](using/test-approve/journey-capping.md)
   + {#preview-test}
      + [Test your content using sample input data](using/test-approve/simulate-sample-input.md)
      + [Kom igång med förhandsgranskning och test](using/content-management/preview-test.md)
      + [Välj testprofiler](using/content-management/test-profiles.md)
      + [Förhandsgranska ditt innehåll](using/content-management/preview.md)
      + [Skicka e-postkorrektur](using/content-management/proofs.md)
      + [Testa e-poståtergivning](using/content-management/rendering.md)
      + [Rapport om skräppost](using/content-management/spam-report.md)
   + {#approve}
      + [Get started with approvals](using/test-approve/gs-approval.md)
      + [Create and manage approval policies](using/test-approve/approval-policies.md)
      + [Begär godkännande](using/test-approve/request-approval.md)
      + [Godkänn en begäran](using/test-approve/review-approve-request.md)
+ Kommunikationskanaler {#channels}
   + [Kom igång med kommunikationskanaler](using/channels/gs-channels.md)
   + {#email}
      + [Get started with emails](using/email/get-started-email.md)
      + [Skapa ett e-postmeddelande](using/email/create-email.md)
      + {#design-email}
         + [Kom igång med e-postdesign](using/email/get-started-email-design.md)
         + Börja skapa innehåll {#start-creating-content}
            + [Designa innehåll från grunden](using/email/content-from-scratch.md)
            + [Importera innehåll](using/email/existing-content.md)
            + [Koda eget innehåll](using/email/code-content.md)
            + [Använd e-postmallar](using/email/use-email-templates.md)
         + Designa ditt innehåll {#add-content}
            + [Använda innehållskomponenter](using/email/content-components.md)
            + [Utnyttja visuella fragment](using/email/use-visual-fragments.md)
            + [Lägga till länkar och spåra meddelanden](using/email/message-tracking.md)
            + [Infoga personaliserade erbjudanden](using/email/add-offers-email.md)
            + [Generera textversionen](using/email/text-version-email.md)
            + [Add a preheader](using/email/preheader.md)
         + Redigera stil {#edit-style}
            + [Kom igång med e-postformat](using/email/get-started-email-style.md)
            + [Redigera bakgrundsinställningar](using/email/backgrounds.md)
            + [Justera lodrät justering och utfyllnad](using/email/alignment-and-padding.md)
            + [Add inline styling attributes](using/email/inline-styling.md)
      + [Use Experience Manager templates](using/email/aem-templates.md)
      + [](using/email/email-opt-out.md)
      + {#configure-email}
         + [Get started with email configuration](using/email/get-started-email-config.md)
         + [Konfigurera e-postkonfigurationsinställningar](using/email/email-settings.md)
         + [Anpassa e-postkonfigurationen](using/email/surface-personalization.md)
   + Kanal i appen {#in-app}
      + [Get started with In-app channel](using/in-app/get-started-in-app.md)
      + [In-app channel prerequisites](using/in-app/inapp-configuration.md)
      + [Skapa ett mobilt meddelande i appen](using/in-app/create-in-app.md)
      + [Skapa ett meddelande i appen för webben](using/in-app/create-in-app-web.md)
      + [Designa ditt innehåll i appen](using/in-app/design-in-app.md)
      + [Kontrollera och skicka meddelanden i appen](using/in-app/send-in-app.md)
   + Push-meddelandekanal {#push}
      + [Kom igång med push-meddelanden](using/push/get-started-push.md)
      + [Skapa ett push-meddelande](using/push/create-push.md)
      + [Utforma ett push-meddelande](using/push/design-push.md)
      + [Kontrollera och skicka push-meddelanden](using/push/send-push.md)
      + Konfigurera push-meddelanden {#push-config}
         + [Push-meddelandeflöde](using/push/push-gs.md)
         + [Konfigurera kanal för push-meddelanden](using/push/push-configuration.md)
         + [Mobile onboarding quick start workflow](using/push/mobile-onboarding-wf.md)
   + {#sms}
      + [Get started with text messaging](using/sms/get-started-sms.md)
      + [Create a text message (SMS/MMS)](using/sms/create-sms.md)
      + [Check and send your text messages](using/sms/send-sms.md)
      + [Hantera avanmälan av textmeddelande](using/sms/sms-opt-out.md)
      + [Konfigurera SMS-underdomäner](using/sms/sms-subdomains.md)
      + Konfigurera SMS-/MMS-kanal{#configure-sms}
         + [Kom igång med SMS-konfiguration](using/sms/sms-configuration.md)
         + [Konfigurera Sinch-provider](using/sms/sms-configuration-sinch.md)
         + [Configure Infobip provider](using/sms/sms-configuration-infobip.md)
         + [Configure Twilio provider](using/sms/sms-configuration-twilio.md)
         + [Konfigurera en anpassad leverantör (Beta)](using/sms/sms-configuration-custom.md)
         + [Skapa en SMS-konfiguration](using/sms/sms-configuration-surface.md)
   + Direktutskick {#direct-mail}
      + [Kom igång med direktreklam](using/direct-mail/get-started-direct-mail.md)
      + [Create a direct mail](using/direct-mail/create-direct-mail.md)
      + [Check and send a direct mail message](using/direct-mail/test-send-direct-mail.md)
      + [Konfigurera direktreklam](using/direct-mail/direct-mail-configuration.md)
   + Webbkanal {#web}
      + [Get started with web channel](using/web/get-started-web.md)
      + {#configure-web-channel}
         + [Web channel prerequisites](using/web/web-prerequisites.md)
         + [Konfigurera webbunderdomäner](using/web/web-delegated-subdomains.md)
         + [Skapa webbkanalskonfiguration](using/web/web-configuration.md)
      + [Skapa webbupplevelser](using/web/create-web.md)
      + Skapa webbsidor {#author-web-pages}
         + [Arbeta med webbdesignern](using/web/web-visual-editor.md)
         + [Använda den icke-visuella redigeraren](using/web/web-non-visual-editor.md)
         + [Hantera ändringar](using/web/manage-web-modifications.md)
         + [Övervaka era webbupplevelser](using/web/monitor-web-experiences.md)
         + [Skapa single-page-appar](using/web/web-spa.md)
   + Kodbaserad upplevelse {#code-based-experience}
      + [Get started with code-based channel](using/code-based/get-started-code-based.md)
      + [Garantier och krav](using/code-based/code-based-prerequisites.md)
      + [Skapa kodbaserad upplevelsekonfiguration](using/code-based/code-based-configuration.md)
      + [Exempel på implementeringsmetoder](using/code-based/code-based-implementation-samples.md)
      + [Skapa kodbaserade upplevelser](using/code-based/create-code-based.md)
   + {#content-card}
      + [Get started with content cards](using/content-card/get-started-content-card.md)
      + {#configure}
         + [Content cards prerequisites](using/content-card/content-card-configuration-prereq.md)
         + [Configure content cards channel in Journey Optimizer](using/content-card/content-card-configuration.md)
         + [Konfigurera stöd för innehållskort i Web SDK](using/content-card/content-card-configuration-sdk.md)
      + [Skapa innehållskort](using/content-card/create-content-card.md)
      + [Design content cards](using/content-card/design-content-card.md)
+ Landningssidor {#landing-pages}
   + [Get started with landing pages](using/landing-pages/get-started-lp.md)
   + [Skapa en landningssida](using/landing-pages/create-lp.md)
   + Designinnehåll {#landing-pages-design}
      + [Om landningssidans design](using/landing-pages/design-lp.md)
      + [Skapa innehållet på landningssidan](using/landing-pages/lp-content.md)
      + [Skapa mallar](using/landing-pages/lp-templates.md)
      + [Lägg till anpassad JavaScript](using/landing-pages/lp-custom-js.md)
   + [Skapa en prenumerationslista](using/landing-pages/subscription-list.md)
   + [Lär dig mer om användningsexempel](using/landing-pages/lp-use-cases.md)
   + Konfigurera landningssidor {#lp-configuration}
      + [Konfigurera underdomäner för landningssidor](using/landing-pages/lp-subdomains.md)
      + [Definiera förinställningar för landningssidor](using/landing-pages/lp-presets.md)
+ Innehållshantering {#content-management}
   + Arbeta med AI-assistenten{#ai-assistant}
      + [Get started with the AI Assistant Content Accelerator](using/content-management/gs-generative.md)
      + [Email generation with AI](using/content-management/generative-email.md)
      + [Push generation with AI](using/content-management/generative-push.md)
      + [SMS generation with AI](using/content-management/generative-sms.md)
      + [Webbgenerering med AI](using/content-management/generative-web.md)
      + [Innehållsexperiment med AI](using/content-management/generative-experimentation.md)
      + [Användningsexempel för AI-assistenten](using/content-management/generative-uc.md)
   + Arbeta med flerspråkigt innehåll{#content-multilingual}
      + [Kom igång med flerspråkigt innehåll](using/content-management/multilingual-gs.md)
      + [Skapa flerspråkigt innehåll med manuell översättning](using/content-management/multilingual-manual.md)
      + [Skapa flerspråkigt innehåll med automatiserad översättning](using/content-management/multilingual-automated.md)
   + Arbeta med innehållsexperiment {#content-experiment}
      + [Kom igång med innehållsexperiment](using/content-management/get-started-experiment.md)
      + [Skapa ett innehållsexperiment](using/content-management/content-experiment.md)
      + Tekniska anmärkningar {#technotes}
         + [Förstå statistiska beräkningar](using/content-management/experiment-calculations.md)
         + [Förstå statistiska beräkningar i experimentrapporten](using/content-management/experiment-report-calculations.md)
   + Assets/Bilder {#assets-images}
      + [Work with Experience Manager Assets](using/content-management/assets.md)
      + [Work with Adobe Stock](using/content-management/stock.md)
   + Personalisering {#personalization}
      + [Get started with personalization](using/personalization/personalize.md)
      + [Personalization-kontexter](using/personalization/personalization-contexts.md)
      + [Personalization syntax](using/personalization/personalization-syntax.md)
      + [Använd Adobe Experience Platform-data för personalisering](using/personalization/lookup-aep-data.md)
      + Arbeta med personaliseringsredigeraren {#expression-editor}
         + [Om personaliseringsredigeraren](using/personalization/personalization-build-expressions.md)
         + [Lägg till attribut i favoriter](using/personalization/personalization-favorites.md)
         + [Använd uttrycksfragment](using/personalization/use-expression-fragments.md)
         + [Personalization-validering](using/personalization/personalization-validation.md)
      + Hjälpfunktioner {#functions}
         + [Kom igång med hjälpfunktioner](using/personalization/functions/functions.md)
         + [Aggregation functions](using/personalization/functions/aggregation.md)
         + [Arithmetic functions](using/personalization/functions/arithmetic-functions.md)
         + [Arrayer och listfunktioner](using/personalization/functions/arrays-list.md)
         + [Datumfunktioner](using/personalization/functions/dates.md)
         + [Boolean- och jämförelsefunktioner](using/personalization/functions/operators.md)
         + [Helpers](using/personalization/functions/helpers.md)
         + [Map functions](using/personalization/functions/maps.md)
         + [Math functions](using/personalization/functions/math.md)
         + [Object functions](using/personalization/functions/objects.md)
         + [](using/personalization/functions/string.md)
      + {#personalization-use-cases}
         + [Meddelande om orderstatus](using/personalization/personalization-use-case.md)
         + [E-post om att kunden överger en kundvagn](using/personalization/personalization-use-case-helper-functions.md)
         + [Health plan prescriptions email](using/personalization/perso-uc-plan-prescriptions.md)
   + {#content-templates}
      + [Get started with content templates](using/content-management/content-templates.md)
      + [Få åtkomst till och hantera mallar](using/content-management/access-content-templates.md)
      + [Skapa innehållsmallar](using/content-management/create-content-templates.md)
      + [Lås innehåll i e-postmallar](using/content-management/content-locking.md)
      + [Testa innehållsmallar](using/content-management/test-content-templates.md)
      + [Använda innehållsmallar](using/content-management/use-content-templates.md)
   + Återanvändbara innehållsfragment {#fragments}
      + [Kom igång med fragment](using/content-management/fragments.md)
      + [Skapa ett fragment](using/content-management/create-fragments.md)
      + [Spara befintligt innehåll som fragment](using/content-management/save-fragments.md)
      + [Anpassningsbara fragment](using/content-management/customizable-fragments.md)
      + [Hantera fragment](using/content-management/manage-fragments.md)
   + Dynamiskt innehåll {#dynamic}
      + [Kom igång med dynamiskt innehåll](using/personalization/get-started-dynamic-content.md)
      + [Skapa villkorsregler](using/personalization/create-conditions.md)
      + [Skapa dynamiskt innehåll](using/personalization/dynamic-content.md)
+ Målgrupper, profiler och identitet{#audiences-profiles-identities}
   + Målgrupper {#audiences}
      + [Kom igång med målgrupper](using/audience/about-audiences.md)
      + [Skapa segmentdefinitioner](using/audience/creating-a-segment-definition.md)
      + Disponera målgrupper {#audience-orchestration}
         + [Kom igång med målgruppsmaterial](using/audience/get-started-audience-orchestration.md)
         + [Skapa kompositionsarbetsflöden](using/audience/create-compositions.md)
         + [Arbeta med arbetsytan](using/audience/composition-canvas.md)
         + [Få åtkomst till och hantera målgrupper](using/audience/access-audiences.md)
      + [Sammansatt målgruppskomposition (begränsad tillgänglighet)](https://experienceleague.adobe.com/sv/docs/federated-audience-composition/using/home)
   + Profiler{#profiles}
      + [Kom igång med profiler](using/audience/get-started-profiles.md)
      + [Skapa testprofiler](using/audience/creating-test-profiles.md)
      + [Arbeta med beräknade attribut](using/audience/computed-attributes.md)
   + [Identiteter](using/audience/get-started-identity.md)
   + [Licensanvändning](using/audience/license-usage.md)
+ {#reporting}
   + {#live-report}
      + [Get started with Live Report](using/reports/live-report.md)
      + [Lista över komponenter](using/reports/live-report-components.md)
      + [Journey Live-rapport](using/reports/journey-live-report.md)
      + [Campaign Live-rapport](using/reports/campaign-live-report.md)
      + [Live-rapport för landningssida](using/reports/lp-report-live.md)
      + [Live-rapport om prenumerationslista](using/reports/subscription-report-live.md)
   + Rapporteringsupplevelsen {#channel-report} har uppdaterats
      + [Kom igång med den uppdaterade rapportupplevelsen](using/reports/report-gs-cja.md)
      + [Konfigurera Customer Journey Analytics manuellt](using/reports/cja-ajo.md)
      + [Hantera dina rapporter](using/reports/report-cja-manage.md)
      + [Krav för rapportering och experimenterande](using/reports/reporting-configuration.md)
      + {#reporting}
         + [Campaign report](using/reports/campaign-global-report-cja.md)
         + [Kodbaserad kampanjrapport](using/reports/campaign-global-report-cja-code.md)
         + [Kampanjrapport för innehållskort](using/reports/campaign-global-report-cja-content.md)
         + [Rapport om direktreklamkampanj](using/reports/campaign-global-report-cja-direct.md)
         + [Rapport om e-postkampanj](using/reports/campaign-global-report-cja-email.md)
         + [Experimentation campaign report](using/reports/campaign-global-report-cja-experimentation.md)
         + [In-app campaign report](using/reports/campaign-global-report-cja-inapp.md)
         + [Push notification campaign report](using/reports/campaign-global-report-cja-push.md)
         + [SMS campaign report](using/reports/campaign-global-report-cja-sms.md)
         + [Web campaign report](using/reports/campaign-global-report-cja-web.md)
      + Reserapporter{#reporting}
         + [Reserapport](using/reports/journey-global-report-cja.md)
         + [Code-based journey report](using/reports/journey-global-report-cja-code.md)
         + [Content card journey report](using/reports/journey-global-report-cja-content.md)
         + [Direct mail journey report](using/reports/journey-global-report-cja-direct.md)
         + [Email journey report](using/reports/journey-global-report-cja-email.md)
         + [In-app journey report](using/reports/journey-global-report-cja-inapp.md)
         + [Push journey report](using/reports/journey-global-report-cja-push.md)
         + [SMS-reserapport](using/reports/journey-global-report-cja-sms.md)
         + [Web journey report](using/reports/journey-global-report-cja-web.md)
      + [Overview report](using/reports/channel-report-cja.md)
      + [Landing page report](using/reports/lp-report-global-cja.md)
      + [Subscription list report](using/reports/subscription-report-global-cja.md)
   + {#reports}
      + Global rapport {#global-report}
         + [Kom igång med global rapport](using/reports/global-report.md)
         + [Lista över komponenter](using/reports/global-report-components.md)
         + [Rapport om global resa](using/reports/journey-global-report.md)
         + [Global kampanjrapport](using/reports/campaign-global-report.md)
         + [Målrapport](using/reports/objective-report.md)
         + [Global rapport för landningssida](using/reports/lp-report-global.md)
         + [Global rapport om prenumerationslista](using/reports/subscription-report-global.md)
      + Kanalrapporter {#channel-report}
         + [Kom igång med kanalrapporter](using/reports/channel-report-gs.md)
         + [Kanalrapporter](using/reports/channel-report.md)
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
   + {#deliverability}
      + [Get started with deliverability](using/reports/deliverability.md)
      + [Understand the suppression list](using/reports/suppression-list.md)
      + [Nytt krav från DMARC](using/configuration/dmarc-record-update.md)
   + [Aviseringar](using/reports/alerts.md)
   + [Uteslutningsorsaker](using/reports/exclusion-list.md)
+ Beslutsfunktioner {#decisioning}
   + Beslutshantering {#offer-decisioning}
      + Kom igång med beslutshantering {#get-started-decision}
         + [Om beslutshantering](using/offers/get-started/starting-offer-decisioning.md)
         + [Användargränssnitt](using/offers/get-started/user-interface.md)
         + [Viktiga steg för att skapa och hantera erbjudanden](using/offers/offer-library/key-steps.md)
         + [Utnyttja anpassade uppladdningsmålgrupper för beslut](using/offers/custom-upload-decisioning.md)
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
         + {#configure-offers}
            + [Skapa personaliserade erbjudanden](using/offers/offer-library/creating-personalized-offers.md)
            + [Add representations](using/offers/offer-library/add-representations.md)
            + [Add constraints](using/offers/offer-library/add-constraints.md)
         + [Skapa reserverbjudanden](using/offers/offer-library/creating-fallback-offers.md)
         + [Skapa samlingar](using/offers/offer-library/creating-collections.md)
      + Skapa och hantera beslut {#create-manage-activities}
         + [Skapa beslut](using/offers/offer-activities/create-offer-activities.md)
         + [Konfigurera urval av erbjudanden i beslut](using/offers/offer-activities/configure-offer-selection.md)
         + [Create simulations](using/offers/offer-activities/simulation.md)
      + [Använd batchbeslut](using/offers/batch-delivery.md)
      + Samla in händelsedata {#collect-event-data}
         + [Komma igång med datainsamling](using/offers/data-collection/data-collection.md)
         + [Skapa en datauppsättning för att samla in händelser](using/offers/data-collection/create-dataset.md)
         + [Konfigurera händelsehämtning](using/offers/data-collection/schema-requirement.md)
      + Skapa beslutshanteringsrapporter {#create-reports}
         + [Arbeta med beslutsledningshändelser](using/offers/reports/get-started-events.md)
         + [Åtkomst till XDM-fält för händelser](using/offers/reports/xdm-fields.md)
      + Exportera din erbjudandekatalog {#export-catalog}
         + [Kom igång med export av din erbjudandekatalog](using/offers/export-catalog/get-started-export.md)
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
            + {#decisions-api}
               + [Lista beslut](using/offers/api-reference/activities-api/activities/activities-list.md)
               + [Söka efter ett beslut](using/offers/api-reference/activities-api/activities/lookup.md)
               + [Skapa ett beslut](using/offers/api-reference/activities-api/activities/create.md)
               + [Uppdatera ett beslut](using/offers/api-reference/activities-api/activities/update.md)
               + [Ta bort ett beslut](using/offers/api-reference/activities-api/activities/delete.md)
            + Äldre API:er {#legacy-api}
               + [Om äldre API:er](using/offers/api-reference/offers-api/legacy-apis/about-legacy-apis.md)
               + Placeringar {#placements}
                  + [Lista placeringar](using/offers/api-reference/offers-api/legacy-apis/placements/placements-list.md)
                  + [Söka efter en placering](using/offers/api-reference/offers-api/legacy-apis/placements/lookup.md)
                  + [Skapa en placering](using/offers/api-reference/offers-api/legacy-apis/placements/create.md)
                  + [Uppdatera en placering](using/offers/api-reference/offers-api/legacy-apis/placements/update.md)
                  + [Ta bort en placering](using/offers/api-reference/offers-api/legacy-apis/placements/delete.md)
               + Beslutsregler {#decision-rules}
                  + [Lista beslutsregler](using/offers/api-reference/offers-api/legacy-apis/decision-rules/rules-list.md)
                  + [Söka efter en beslutsregel](using/offers/api-reference/offers-api/legacy-apis/decision-rules/lookup.md)
                  + [Skapa en beslutsregel](using/offers/api-reference/offers-api/legacy-apis/decision-rules/create.md)
                  + [Uppdatera en beslutsregel](using/offers/api-reference/offers-api/legacy-apis/decision-rules/update.md)
                  + [Ta bort en beslutsregel](using/offers/api-reference/offers-api/legacy-apis/decision-rules/delete.md)
               + {#tags}
                  + [List collection qualifiers](using/offers/api-reference/offers-api/legacy-apis/tags/tags-list.md)
                  + [Lookup a collection qualifier](using/offers/api-reference/offers-api/legacy-apis/tags/lookup.md)
                  + [Create a collection qualifier](using/offers/api-reference/offers-api/legacy-apis/tags/create.md)
                  + [Update a collection qualifier](using/offers/api-reference/offers-api/legacy-apis/tags/update.md)
                  + [Delete a collection qualifier](using/offers/api-reference/offers-api/legacy-apis/tags/delete.md)
               + Personaliserade erbjudanden {#personalized-offers}
                  + [Lista personaliserade erbjudanden](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/offers-list.md)
                  + [Söka efter ett personaliserat erbjudande](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/lookup.md)
                  + [Skapa ett personaliserat erbjudande](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/create.md)
                  + [Uppdatera ett personaliserat erbjudande](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/update.md)
                  + [Ta bort ett personaliserat erbjudande](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/delete.md)
               + Reserverbjudanden {#fallback-offers}
                  + [Lista reserverbjudanden](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/fallback-list.md)
                  + [Söka efter ett reserverbjudande](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/lookup.md)
                  + [Skapa ett reserverbjudande](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/create.md)
                  + [Uppdatera ett reserverbjudande](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/update.md)
                  + [Ta bort ett reserverbjudande](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/delete.md)
               + Samlingar {#collections}
                  + [Lista samlingar](using/offers/api-reference/offers-api/legacy-apis/collections/collections-list.md)
                  + [Söka efter en samling](using/offers/api-reference/offers-api/legacy-apis/collections/lookup.md)
                  + [Skapa en samling](using/offers/api-reference/offers-api/legacy-apis/collections/create.md)
                  + [Uppdatera en samling](using/offers/api-reference/offers-api/legacy-apis/collections/update.md)
                  + [Ta bort en samling](using/offers/api-reference/offers-api/legacy-apis/collections/delete.md)
               + {#decisions-api}
                  + [Lista beslut](using/offers/api-reference/offers-api/legacy-apis/activities-api/activities-list.md)
                  + [Söka efter ett beslut](using/offers/api-reference/offers-api/legacy-apis/activities-api/lookup.md)
                  + [Skapa ett beslut](using/offers/api-reference/offers-api/legacy-apis/activities-api/create.md)
                  + [Uppdatera ett beslut](using/offers/api-reference/offers-api/legacy-apis/activities-api/update.md)
                  + [Ta bort ett beslut](using/offers/api-reference/offers-api/legacy-apis/activities-api/delete.md)
         + {#offer-delivery-api}
            + [Get started with offer delivery APIs](using/offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
            + [Decisioning API](using/offers/api-reference/offer-delivery-api/decisioning-api.md)
            + [Edge Decisioning API](using/offers/api-reference/offer-delivery-api/edge-decisioning-api.md)
            + [Batch Decisioning API](using/offers/api-reference/offer-delivery-api/batch-decisioning-api.md)
   + {#experience-decisioning}
      + [Get started with Decisioning](using/experience-decisioning/gs-experience-decisioning.md)
      + {#api-reference}
         + {#decision-items}
            + [Create decision items](using/experience-decisioning/api-reference/decisions-items/create.md)
            + [Decision items list](using/experience-decisioning/api-reference/decisions-items/decision-items-list.md)
            + [Delete decision items](using/experience-decisioning/api-reference/decisions-items/delete.md)
            + [Lookup decision items](using/experience-decisioning/api-reference/decisions-items/lookup.md)
            + [Update decision items](using/experience-decisioning/api-reference/decisions-items/update.md)
         + {#items-collections}
            + [Skapa objektsamlingar](using/experience-decisioning/api-reference/items-collections/create.md)
            + [Ta bort objektsamlingar](using/experience-decisioning/api-reference/items-collections/delete.md)
            + [Lista över objektsamlingar](using/experience-decisioning/api-reference/items-collections/items-collections-list.md)
            + [Söka efter objektsamlingar](using/experience-decisioning/api-reference/items-collections/lookup.md)
            + [Update items collections](using/experience-decisioning/api-reference/items-collections/update.md)
         + Markeringsstrategier{#selection-strategies}
            + [Skapa urvalsstrategier](using/experience-decisioning/api-reference/selection-strategies/create.md)
            + [Ta bort urvalsstrategier](using/experience-decisioning/api-reference/selection-strategies/delete.md)
            + [Sökstrategier för markering](using/experience-decisioning/api-reference/selection-strategies/lookup.md)
            + [Urvalsstrategilista](using/experience-decisioning/api-reference/selection-strategies/selection-strategies-list.md)
            + [Uppdatera urvalsstrategier](using/experience-decisioning/api-reference/selection-strategies/update.md)
      + Hantera beslutsobjekt {#decision-items}
         + [Konfigurera artikelkatalogen](using/experience-decisioning/catalogs.md)
         + [Skapa beslutsobjekt](using/experience-decisioning/items.md)
         + [Hantera artikelsamlingar](using/experience-decisioning/collections.md)
      + Konfigurera objektmarkering {#selection}
         + [Skapa beslutsregler](using/experience-decisioning/rules.md)
         + [Create ranking methods](using/experience-decisioning/ranking.md)
         + [Utnyttja kontextdata](using/experience-decisioning/context-data.md)
      + [Skapa urvalsstrategier](using/experience-decisioning/selection-strategies.md)
      + [Skapa beslutsprofiler](using/experience-decisioning/create-decision.md)
      + [Rapportering i Customer Journey Analytics](using/experience-decisioning/cja-reporting.md)
+ Datahantering {#data-management}
   + [Get started with data management](using/data/gs-data.md)
   + [Work with schemas](using/data/get-started-schemas.md)
   + {#datasets}
      + [Get started with datasets](using/data/get-started-datasets.md)
      + [segmenteringsuppdateringar i realtid och direktuppspelning](using/data/datasets-ttl.md)
      + [Exportera Journey Optimizer-datauppsättningar](using/data/export-datasets.md)
      + [Frågeexempel](using/data/datasets-query-examples.md)
      + [Inbyggda scheman >](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)
   + [Frågor](using/data/get-started-queries.md)
+ Konfiguration {#configuration}
   + [Kom igång med Journey Optimizer-konfiguration](using/configuration/get-started-configuration.md)
   + [Konfigurera kanalkonfigurationer](using/configuration/channel-surfaces.md)
   + Inställningar för guidad kanal {#guided-setup}
      + [Kom igång med konfiguration av guidade kanaler](using/configuration/set-mobile-config.md)
      + [Skapa en kanalkonfiguration](using/configuration/create-channel-set-up.md)
   + {#delegate-subdomains}
      + [Get started with subdomain delegation](using/configuration/about-subdomain-delegation.md)
      + [Delegate a subdomain](using/configuration/delegate-subdomain.md)
      + [Set up DMARC record](using/configuration/dmarc-record.md)
      + [Add a Google TXT record](using/configuration/google-txt.md)
      + [Access and edit PTR records](using/configuration/ptr-records.md)
      + [Create IP pools](using/configuration/ip-pools.md)
   + {#implement-ip-warmup-plan}
      + [Get started with IP warmup plans](using/configuration/ip-warmup-gs.md)
      + [Create IP warmup campaigns](using/configuration/ip-warmup-campaign.md)
      + [Create an an IP warmup plan](using/configuration/ip-warmup-plan.md)
      + [Run the IP warmup plan](using/configuration/ip-warmup-execution.md)
      + [IP warmup plan files](using/configuration/ip-warmup-plan-files.md)
   + {#monitor-reputation}
      + [Suppression list](using/configuration/manage-suppression-list.md)
      + [Retries](using/configuration/retries.md)
      + [Allowed list](using/configuration/allow-list.md)
   + [Use seed lists](using/configuration/seed-lists.md)
   + [Support for archiving](using/configuration/archiving-support.md)
   + [Change execution addresses](using/configuration/primary-email-addresses.md)
   + [Configure business rules](using/configuration/frequency-rules.md)
   + [Work with rule sets](using/configuration/rule-sets.md)
   + Konfigurera resor {#configure-journeys}
      + [Om datakällor, händelser och åtgärder](using/configuration/about-data-sources-events-actions.md)
      + Integrera med externa system {#external-systems}
         + [Integrering av resor med externa system](using/configuration/external-systems.md)
         + [API för reglering](using/configuration/capping.md)
         + [API för begränsning](using/configuration/throttling.md)
      + Händelsekonfiguration {#events-journeys}
         + [Work with journey events](using/event/about-events.md)
         + {#unitary-events}
            + [Get started with unitary events](using/event/about-creating.md)
            + [Om scheman i ExperienceEvent](using/event/experience-event-schema.md)
            + [Arbeta med Adobe Analytics](using/event/about-analytics.md)
         + [Konfigurera en affärshändelse](using/event/about-creating-business.md)
         + [Ytterligare steg för att skicka händelser](using/event/additional-steps-to-send-events-to-journey.md)
      + Datakällans konfiguration{#data-source-journeys}
         + [Om datakällor](using/datasource/about-data-sources.md)
         + [Konfigurera en datakälla](using/datasource/configure-data-sources.md)
         + [Datakällan i Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
         + [Externa datakällor](using/datasource/external-data-sources.md)
      + {#action-journeys}
         + [Om åtgärder](using/action/action.md)
         + [Konfigurera en åtgärd](using/action/about-custom-action-configuration.md)
         + [Integrate with Adobe Campaign Standard](using/action/acs-action.md)
         + [Integrate with Adobe Campaign v7/v8](using/action/acc-action.md)
         + [Use API call responses in custom actions](using/action/action-response.md)
         + [Integrate with Marketo Engage](using/action/marketo-engage.md)
   + [Källor](using/start/get-started-sources.md)
   + [Export objects to another sandbox](using/configuration/copy-objects-to-sandbox.md)
+ Åtkomstkontroll {#access-control}
   + Översikt över åtkomstkontroll {#privacy}
      + [Kom igång med användarhantering](using/administration/permissions-overview.md)
      + [Inbyggda roller](using/administration/ootb-product-profiles.md)
      + [Inbyggda behörigheter](using/administration/ootb-permissions.md)
      + [Behörighetsnivåer](using/administration/high-low-permissions.md)
   + [Hantera användare och roller](using/administration/permissions.md)
   + [Attributbaserad åtkomstkontroll](using/administration/attribute-based-access.md)
   + [Åtkomstkontroll på objektnivå](using/administration/object-based-access.md)
   + [Hantering av sandlådor](using/administration/sandboxes.md)
+ Sekretess {#privacy}
   + [Get started with privacy](using/privacy/get-started-privacy.md)
   + [Förfrågningar om användarens information](using/privacy/requests.md)
   + [Audit actions on resources](using/privacy/audit-logs.md)
   + [Perform data hygiene operations](using/privacy/data-hygiene.md)
   + Hantera medgivande {#consent}
      + [Manage opt-out](using/privacy/opt-out.md)
      + [Work with consent policies](using/action/consent.md)
   + [Dataförvaltning](using/action/action-privacy.md)
   + [Set up and manage Customer Managed Keys](using/privacy/cmk.md)

