---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med spårning i Journey Optimizer
description: Läs mer om spårnings- och övervakningsfunktionerna i Journey Optimizer
feature: Monitoring
topic: Administration
role: User
level: Beginner
keywords: spåra, övervaka, analysera, rapportera, leverera
source-git-commit: 27de3d2171e6f6575eb66ada20f951f6cb3abc98
workflow-type: tm+mt
source-wordcount: '1916'
ht-degree: 3%

---

# Kom igång med spårning i Journey Optimizer {#get-started-tracking}

Med spårning kan ni mäta kampanjens effektivitet, optimera kundupplevelserna och se till att meddelandena når de avsedda mottagarna. Journey Optimizer har omfattande spårningsfunktioner som fångar upp kundinteraktioner, leveransresultat och systemhälsa - vilket hjälper er att fatta datadrivna beslut samtidigt som ni respekterar sekretess och upprätthåller regelefterlevnaden.

Den mesta spårningen konfigureras automatiskt när du skapar meddelanden och resor. För avancerade scenarier kan du ställa in anpassade mått, konfigurera URL-parametrar och integrera med externa analysplattformar. Få tillgång till dina spårningsdata via inbyggda rapporter eller exportera dem för djupare analys i Customer Journey Analytics.

>[!BEGINSHADEBOX]

Vad du kan spåra i Journey Optimizer:

📧 **E-postinteraktioner** - Öppnar, klickar och länkar

🌐 **Webbbeteende** - sidvyer, klickningar och engagemangsmönster

🛤️ **Reseprestanda** - Anpassade mått, steghändelser och konverteringssökvägar

📊 **Leveranshälsa** - Studsfrekvens, skräppostklagomål och avsändarens anseende

⚙️ **Systemåtgärder** - Varningar, fel och prestanda för anpassade åtgärder

>[!ENDSHADEBOX]

Ta en titt på följande viktiga ämnen för att hjälpa dig att komma igång:

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="../building-journeys/success-metrics.md">
    <img alt="Mätvärden" src="../assets/do-not-localize/success-metrics.jpeg">
    </a>
    <div>
    <a href="../building-journeys/success-metrics.md"><strong>Konfigurera framgångsmått</strong></a>
    </div>
    <p>
    <em>Spåra anpassade nyckeltal som är anpassade efter dina affärsmål</em>
    <p>
  </td>
  <td>
    <a href="../reports/deliverability.md">
    <img alt="Levererbarhetsstrategi" src="../assets/do-not-localize/deliverability.jpeg">
    </a>
    <div>
    <a href="../reports/deliverability.md"><strong>Skärmleverans</strong></a>
    </div>
    <p>
    <em>Se till att dina meddelanden når kundens inkorgar</em>
    <p>
  </td>
  <td>
    <a href="../reports/gs-reports.md">
    <img alt="Rapportering" src="../assets/do-not-localize/reporting.jpeg">
    </a>
    <div>
    <a href="../reports/gs-reports.md"><strong>Utforska rapportering</strong></a>
    </div>
    <p>
    <em>Få tillgång till live- och historiska rapporter för era resor och kampanjer</em>
    <p>
  </td>
</tr>
</table>

## Spåra kundinteraktioner i alla kanaler {#tracking-by-channel}

Journey Optimizer har kanalspecifika spårningsfunktioner. Så här konfigurerar och använder du spårning för varje kanal.

+++E-postspårning

Spårning av e-post aktiveras automatiskt när du skapar ett e-postmeddelande. Journey Optimizer-spår öppnas, klickas och avbryts som standard - ingen ytterligare konfiguration behövs.

**Konfigurera spårningsalternativ:**

* **Aktivera/inaktivera spårning** - Kontrollera spårning på meddelandenivå när du utformar e-postmeddelandet. Du kan välja att spåra öppningar, klick eller båda. [Läs mer](../email/message-tracking.md)

* **Ställ in URL-spårningsparametrar** - Konfigurera spårningsparametrar på ytnivå för att automatiskt lägga till kampanjidentifierare (utm_campaign, utm_source osv.) till alla e-postlänkar. Detta möjliggör attribueringsspårning i hela det digitala ekosystemet. [Läs mer](../email/url-tracking.md)

* **Spåra länkar i sparade fragment** - När du sparar ett fragment från innehåll som har spårning aktiverat spåras länkarna i det fragmentet även när du återanvänder det på andra resor eller i andra kampanjer. [Läs mer](../content-management/save-fragments.md)

* **Lägg till spårning av spegelsida** - Aktivera alternativet för spegelsida om du vill skapa en webbversion av ditt e-postmeddelande med automatisk spårning av vem som tittar på det. [Läs mer](../email/message-tracking.md#mirror-page)

**Övervaka prestanda:** Visa realtidsvärden i kampanjer och reserapporter, inklusive öppningar, klick och länknivåprestanda. [Kampanjrapporter](../reports/campaign-global-report-cja-email.md) | [Reserapporter](../reports/journey-global-report-cja-email.md)

+++

+++Webbspårning

Webbspårning kräver explicit konfiguration för att spåra användarinteraktioner med dina webbändringar.

**Konfigurera klickspårning:**

När du skapar en webbsida kan du markera specifika element (knappar, bilder, länkar) som du vill spåra. Detta aktiverar klickspårning för dessa element utan att ytterligare kod behövs. [Läs mer](../web/monitor-web-experiences.md)

* **Spåra alla klickbara element** - Välj knappar, bilder, länkar eller andra interaktiva element i din webbanpassning.
* **Automatisk datainsamling** - När den har konfigurerats hämtar Journey Optimizer automatiskt klickhändelser och associerar dem med profiler.
* **Övervaka i realtid** - Följ upp användarinteraktioner när de validerar personaliseringseffekten.

**Visa spårningsdata:** Få åtkomst till visningsvärden, klickfrekvens och prestanda på elementnivå i rapporter. [Kampanjrapporter](../reports/campaign-global-report-cja-web.md) | [Reserapporter](../reports/journey-global-report-cja-web.md)

+++

+++Spårning av push-meddelanden

Penselspårning aktiveras automatiskt och visar avtryck (levererat), klickningar (tryck) och öppnas (appen startas). Om du vill maximera spårningsvärdet konfigurerar du klickbara element i ditt push-innehåll.

**Konfigurera spårade element:**

* **Innehållet klickbeteende** - Ange vad som ska hända när användare trycker på meddelandet: öppna app, navigera till en länk eller öppna en webb-URL. Varje åtgärd spåras automatiskt. [Läs mer](../push/design-push.md#on-click-behavior)

* **Lägg till åtgärdsknappar** - Inkludera upp till tre knappar (Android) eller flera knappar (iOS) med oberoende spårning för varje knappåtgärd (öppna program, deplink, webb-URL). [Läs mer](../push/design-push.md#add-buttons-push)

* **Aktivera spårning** - Verifiera att spårning är aktiverat i din push-färgsaktivitet eller i inställningarna för kampanjspårning. [Läs mer](../push/create-push.md#create)

>[!NOTE]
>
>Push tracking kräver mobil SDK-implementering. Kontrollera att din app har Adobe Experience Platform Mobile SDK korrekt konfigurerat. [Läs mer](../push/push-configuration.md#integrate-mobile-app)

**Analysera engagemang:** Visa klickfrekvens, knappprestanda och spårad länkinformation i rapporter. [Kampanjrapporter](../reports/campaign-global-report-cja-push.md) | [Reserapporter](../reports/journey-global-report-cja-push.md)

+++

+++Spåra meddelanden i appen

Meddelanden i appen spårar automatiskt visningar och användarinteraktioner. Konfigurera triggers och innehåll för att maximera spårningseffektiviteten.

**Ställ in spårning:**

* **Definiera visningsregler** - Ange när och var meddelanden i appen ska visas med utlösare (appstart, skärminläsning), frekvensregler och målgruppsvillkor. Korrekt konfiguration säkerställer korrekt spårning av både utlösta och visade meddelanden.

* **Lägg till spårade element** - Inkludera knappar, länkar och interaktiva element i meddelandeinnehållet. Varje interaktion spåras automatiskt med detaljerade etiketter.

* **Optimera visningstidsplanering** - Konfigurera veckodag- och tidsinställningar för att maximera sannolikheten för att utlösta meddelanden visas för användarna.

[Lär dig hur du konfigurerar meddelanden i programmet](../in-app/create-in-app.md)

**Vad som spåras:** Journey Optimizer hämtar automatiskt bildskärmar, knappklickningar, avskedanden, utlösta kontra visade mätvärden och länkprestanda. [Kampanjrapporter](../reports/campaign-global-report-cja-inapp.md) | [Reserapporter](../reports/journey-global-report-cja-inapp.md)

+++

+++SMS- och MMS-spårning

SMS-spårning kräver minimal konfiguration - Journey Optimizer kortar automatiskt ned och spårar länkar som du inkluderar i meddelanden.

**Så här fungerar det:**

* **Automatisk länkspårning** - Lägg till valfri URL till SMS-innehållet med hjälp av URL-hjälpfunktionen. Journey Optimizer förkortar automatiskt länken och spårar klickningar utan ytterligare konfiguration. Om du vill använda URL-förkortning måste du först konfigurera en SMS-underdomän. [Läs mer](../sms/sms-subdomains.md)

* **Spårning av inkommande meddelanden** - Svar från mottagare hämtas automatiskt så att du kan övervaka dubbelriktade konversationer och svarsmönster. [Läs mer](../sms/sms-opt-out.md#sms-native-keywords)

**Visa mått:** Få åtkomst till länkklickdata, inkommande meddelandevolymer och meddelandetypsprestanda i rapporter. [Kampanjrapporter](../reports/campaign-global-report-cja-sms.md) | [Reserapporter](../reports/journey-global-report-cja-sms.md)

+++

+++Kodbaserad uppföljning av upplevelser

Kodbaserade upplevelser kräver implementeringskonfiguration för att skicka spårningsdata till Adobe Experience Platform.

**Förutsättningar:**

Innan spårning fungerar måste du konfigurera implementeringen för att skicka interaktionshändelser (skärmar, klickningar) till Adobe Experience Platform. Detta kräver:

* Konfigurera en dataström för Adobe Experience Platform. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html)
* Implementera händelseinsamling i koden med Web SDK eller Mobile SDK.
* Skicka visnings- och interaktionshändelser när innehåll visas eller klickas.

[Läs mer om implementeringskrav](../code-based/code-based-prerequisites.md#reporting-prerequisites)

**Vad som spåras:** När det är implementerat spåras visningar, klickningar, klickfrekvens och prestanda på elementnivå i alla digitala kontaktytor (webbplatser, mobilappar, IoT-enheter etc.). [Kampanjrapporter](../reports/campaign-global-report-cja-code.md) | [Reserapporter](../reports/journey-global-report-cja-code.md)

+++

+++Spårning av innehållskort

Innehållskort spårar automatiskt användarinteraktioner. Konfigurera innehåll och visningsregler för att styra spårningsbeteendet.

**Så här implementerar du:**

* **Designspårat innehåll** - Lägg till knappar och länkar till ditt innehållskort. Varje interaktivt element spåras automatiskt med etiketter och URL:er.

* **Konfigurera beständighet** - Innehållskort finns kvar mellan appsessioner, så att du kan spåra långsiktiga interaktionsmönster. Ange förfalloregler för att styra hur långa kort som kan spåras.

* **Konfigurera visningsregler** - Definiera när och var kort visas för att säkerställa korrekt spårning av skärmar och interaktioner.

[Lär dig konfigurera innehållskort](../content-card/create-content-card.md)

**Övervaka engagemang:** Spåra visningar, klick, klickfrekvens och engagemangsmönster i flera sessioner. [Kampanjrapporter](../reports/campaign-global-report-cja-content.md) | [Reserapporter](../reports/journey-global-report-cja-content.md)

+++

+++Spårning av landningssida

Landningssidor levereras med inbyggd spårning som inte kräver några ytterligare inställningar. Journey Optimizer samlar automatiskt in besök, konverteringar och studsfrekvenser.

**Vad som spåras automatiskt:**

* **Besök** - Totalt och unikt antal besök för att mäta räckvidd
* **Konverteringar** - Formulärinskickningar, prenumerationsbekräftelser eller andra definierade åtgärder
* **Studsfrekvens** - Andel besökare som lämnar utan att interagera
* **Prestandatrender** - tidsseriedata som visar hur mätvärden utvecklas

[Lär dig konfigurera landningssidor](../landing-pages/create-lp.md)

**Övervaka prestanda:** Spåra besöksmönster, konverteringsgrader och studsfrekvens över tiden för att förstå hur användare interagerar med formulären och identifiera områden som kan förbättras. [Kampanjrapporter](../reports/lp-report-global-cja.md)

+++

## Spåra din resa och kampanjaktivitet {#journey-campaign-tracking}

Förutom spårning på kanalnivå kan du konfigurera spårning för att mäta övergripande prestanda och förstå kundbeteenden i alla era marknadsföringsinitiativ.

* **Definiera anpassade framgångsmått** - Konfigurera specifika nyckeltal som är anpassade till dina affärsmål (inköp, registreringar, förnyelser osv.) utöver standardengagemangsvärden. [Läs mer](../building-journeys/success-metrics.md)

* **Aktivera resesegmenthändelser** - Aktivera detaljerad spårning av alla åtgärder som kunderna utför när de förflyttar sig på resorna. Detta ger detaljerad synlighet för start- och slutpunkter, banmarkering och platser där användaren kan lämna banan. [Läs mer](../reports/journey-step-events-overview.md)

* **Konfigurera schemaläggning** - Konfigurera optimering för sändningstid för att spåra prestanda i olika timingstrategier och identifiera optimala sändningsfönster. [Läs mer](../building-journeys/send-time-optimization.md)

* **Konfigurera övervakning av anpassade åtgärder** - Ställ in spårning för integreringar med externa system för att övervaka API-anrop, svarstider och felmönster. [Läs mer](../action/reporting.md)

* **Skapa anpassade rapporter och exportera data** - Skapa anpassade rapporter och exportera spårningsdata till externa system för djupare analyser. [Läs mer](../reports/sharing-overview.md)

* **Visa enhetliga prestanda:** Få tillgång till omfattande rapporter för både kampanjer och resor för att jämföra prestanda via e-post, push, SMS och andra kanaler och för att förstå vilka kombinationer som ger bäst resultat. [Kampanjrapporter](../reports/campaign-global-report-cja.md) | [Reserapporter](../reports/journey-global-report-cja.md)

## Spåra optimering och beslutsresultat {#optimization-decisioning-tracking}

Journey Optimizer spårar automatiskt optimeringsexperiment, målgruppsstrategier och beslutsresultat. Konfigurera inställningarna för att säkerställa korrekt datainsamling.

### Ställ in optimeringsspårning {#optimization-tracking}

* **Optimering av kampanjer och resor**:

   * När du skapar experiment definierar du vilka mätvärden som ska spåras (konverteringar, klickningar, anpassade händelser). Journey Optimizer samlar automatiskt in prestandadata för varje behandling. [Läs mer](../content-management/optimization-experimentation.md)

   * Skapa målinriktningsregler för att leverera olika innehåll till olika målgruppssegment. Journey Optimizer spårar automatiskt interaktionsstatistik för varje målgrupp så att ni kan jämföra prestanda mellan olika segment. [Läs mer](../content-management/optimization-targeting.md)

* **Sökvägsoptimering**: Lägg till en **Optimera**-aktivitet på resan och konfigurera flera sökvägar. Journey Optimizer spårar automatiskt vilka banprofiler som används och mäter prestandan. [Läs mer](../building-journeys/optimize.md)

Analysera resultaten: visa konverteringsgrader, statistisk signifikans och lyft mellan behandlingar i experimentrapporter, eller jämföra interaktionsvärden för olika målsegment. [Rapport om experimentkampanj](../reports/campaign-global-report-cja-experimentation.md) | [Rapport om experimenterad resa &#x200B;](../reports/journey-global-report-cja-experimentation.md) | [Rapport om målinriktning på resa](../reports/journey-global-report-cja.md#targeting)

### Spåra beslutsprestanda {#decisioning-tracking}

När du använder Decisioning för att personalisera innehåll spårar Journey Optimizer automatiskt beslutshändelser, visningar och klickningar utan någon ytterligare konfiguration.

* **Automatisk händelsehämtning** - Journey Optimizer samlar automatiskt in beslutshändelser när ett beslutsobjekt väljs för en profil.
* **Impressionsspårning** - För e-postmeddelanden spåras visningar automatiskt. För kodbaserade upplevelser måste ni implementera dispositionshändelser i koden. [Läs mer](../code-based/code-based-implementation-samples.md#client-side-how)
* **Klickspårning** - Klickningar på beslutsobjekt spåras automatiskt i e-postmeddelanden. Kodbaserade upplevelser kräver implementeringshändelser.

>[!NOTE]
>
>Om du vill spåra beslut i **kodbaserade upplevelser** kontrollerar du att implementeringen skickar interaktionshändelser (displayer och klickningar) till Adobe Experience Platform med Web SDK eller Mobile SDK. [Läs mer](../experience-decisioning/data-collection/schema-requirement.md)

För att övervaka prestanda: visa KPI:er för beslutsfattande, jämföra beslutsobjekt, analysera urvalsstrategier och övervaka AI-modellens prestanda i rapporter. [Läs mer](../experience-decisioning/cja-reporting.md)

## Kontroll av dataanvändning {#data-governance}

Med datastyrningsprinciper kan ni styra hur spårningsdata kan användas i hela organisationen:

* **Etikettera känsliga spårningsdata** - Använd styrningsetiketter på spårade beteendedata (t.ex. klick på hälsoinnehåll, interaktioner för finansiella produkter) för att markera det som känsligt eller reglerat.

* **Begränsa dataanvändning** - Skapa principer som förhindrar att märkta spårningsdata används i vissa kanaler, exporteras till tredjepartssystem eller används för specifika personaliseringsscenarier.

* **Automatisk tillämpning** - Journey Optimizer kontrollerar automatiskt styrningsprinciper när du skapar resor och kampanjer och blockerar publikationen om spårade data används i strid med definierade principer.

Datastyrning säkerställer efterlevnad av regler som GDPR och CCPA samtidigt som ni kan spåra och analysera kundbeteenden inom godkända gränser. [Läs mer](../action/action-privacy.md)

## Skärmleverans och systemhälsa {#monitoring-capabilities}

Förutom att spåra engagemang kan du konfigurera övervakning för att säkerställa att meddelandena når sina inkorgar och system fungerar optimalt.

Leveransövervakning hjälper till att säkerställa att dina meddelanden når mottagarnas inkorgar och upprätthåller ett gott avsändaranseende genom att spåra viktiga indikatorer:

* **Granska suppressionslistan** regelbundet för att förstå varför adresser blockeras och för att upprätthålla listhygienen. [Läs mer](../reports/suppression-list.md)

* **Analysera leveransfel** för att diagnostisera fel och vidta korrigerande åtgärder. [Läs mer](../configuration/email-error-types.md)

* **Följ bästa praxis** för DMARC, SPF och DKIM för att maximera placeringen av inkorgen. [Läs mer](../reports/deliverability.md)

Konfigurera proaktiv övervakning för att få meddelanden i realtid om kritiska händelser och systemproblem, så att ni kan reagera snabbt innan de påverkar era kundupplevelser:

* **Konfigurera aviseringar** - Konfigurera meddelanden i realtid om resefel, anpassade åtgärdsfel och kritiska problem så att du snabbt kan åtgärda problem. [Läs mer](../reports/alerts.md)

* **Aktivera granskningsloggar** - Aktivera granskningsloggning för att spåra alla åtgärder på resurser för regelefterlevnad och felsökning. [Läs mer](../privacy/audit-logs.md)

* **Övervaka integreringar** - Spåra anpassade åtgärdsprestanda och externa systemanslutningar för att identifiera integreringsproblem tidigt. [Läs mer](../action/reporting.md)

