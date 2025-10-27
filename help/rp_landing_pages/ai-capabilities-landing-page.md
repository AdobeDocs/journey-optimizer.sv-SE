---
solution: Journey Optimizer
product: Journey Optimizer
title: AI Capabilities in Adobe Journey Optimizer
description: AI Capabilities in Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: 9d0460d303a3701ad7ff5b7f2487ac6ccdd6facd
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 1%

---

# AI Capabilities in Adobe Journey Optimizer{#section-overview}

Adobe Journey Optimizer utnyttjar kraften i artificiell intelligens och maskininlärning för att förändra hur ni skapar, optimerar och levererar kundupplevelser. Med AI-funktionerna kan ni effektivisera arbetsflödet och maximera effekten, från att generera personaliserat innehåll i alla kanaler till att förutsäga den optimala tiden för kundinteraktion. I det här avsnittet beskrivs hur AI-baserade funktioner fungerar tillsammans för att hjälpa er att fatta smartare beslut, automatisera komplexa uppgifter och skapa upplevelser som verkligen får genklang hos er målgrupp. Oavsett om ni utnyttjar generativ AI för att skapa innehåll, använder prediktiva modeller för beslutsfattande eller optimerar sändningstiderna för bättre engagemang, kommer ni att upptäcka praktiska verktyg och strategier för att utnyttja den fulla potentialen hos AI i er kundresa.

## AI-funktioner

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/sparkles.svg)

AI-assistenten för innehållsgenerering

Utnyttja generativ AI för att skapa och personalisera innehåll i e-postmeddelanden, SMS, push-meddelanden, webbsidor och landningssidor.

[Utforska AI Assistant](ai-assistant-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg?lang=sv-SE)

Sändningsoptimering

Använd AI för att förutsäga den optimala tiden för att skicka meddelanden och maximera kundengagemanget baserat på historiskt beteende.

[Läs mer om optimering vid sändning](../using/building-journeys/send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/data.svg)

AI-modeller för beslut

Skapa automatiska optimeringsmodeller och personaliserade optimeringsmodeller för att rangordna och leverera de bästa erbjudandena till era kunder.

[Upptäck AI-modeller](ai-models-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/help.svg)

AI Assistant Product Knowledge

Få svar och driftsinsikter om Adobe Journey Optimizer med hjälp av konversationsbaserad API.

[Arbeta med AI Assistant](../using/start/ai-assistant.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/experiment.svg)

Experimentera med AI

Generera olika varianter och experimentera för att identifiera det material som ger er bäst resultat.

[Lär dig mer om AI-experiment](../using/content-management/generative-experimentation.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/user-group.svg?lang=sv-SE)

AI-integrering för kunder

Integrera med Adobe Intelligent Services för att förutsäga kundbeteende och utnyttja bortfalls- och konverteringspoäng under kundresan.

[Utforska intelligenta tjänster](../using/building-journeys/ai-services-overview.md)
:::

::::


## Ytterligare resurser

- **[Värdering av varumärkesjustering](../using/content-management/brands-score.md)** - Utvärdera hur väl ditt AI-genererade innehåll överensstämmer med varumärkesriktlinjerna med hjälp av AI-baserad poängsättning.
- **[Experimentera med accelerator](../using/content-management/experiment-accelerator-gs.md)** - Snabba upp innehållsexperimenterandet med AI-drivna insikter och rekommendationer.
- **[API:er med AI-funktioner](../using/configuration/ajo-apis.md)** - få tillgång till Journey Optimizer AI och maskininlärningsfunktioner via programmering via API:er.

## Vanliga frågor

+++**Vilka behörigheter krävs för att använda AI-funktioner?**

Om du vill använda AI Assistant för innehållsgenerering måste användarna ha behörighet **Skapa innehåll**. Den här behörigheten tilldelas via AI Assistant-resursen i produkten Behörigheter. För att kunna använda AI Assistant för produktkunskaper och driftsinsikter måste användarna godkänna Adobe Experience Cloud Generative AI User Guidelines.

[Läs mer om behörigheter](../using/administration/ootb-permissions.md)

+++

+++**Vilka kanaler stöder generering av AI Assistant-innehåll?**

AI-assistenten för innehållsgenerering är tillgänglig för kanalerna **E-post**, **Push**, **SMS** och **Webb**. Den är för närvarande inte tillgänglig för kanalerna Direct Mail, Content Cards, LINE och WhatsApp.

+++

+++**Vilka är de bästa sätten att använda AI Assistant?**

- **Använd väldefinierade uppmaningar** - Kvaliteten på det genererade innehållet påverkas starkt av ert marknadsföringsmål och er uppmaning. Var tydlig och tydlig.
- **Överför varumärkesresurser** - Tillhandahåll varumärkesresurser i PDF-, JPEG-, PNG- eller ZIP-format (högst 50 MB) för korrekt varumärkesinnehåll.
- **Använd egna mallar** - Använd varumärkesspecifika e-postmallar med upp till 8-10 bilder för optimala resultat.
- **Ge feedback** - Rapportera problematiska utdata med hjälp av ikoner för tummen uppåt, tummen nedåt eller flagga för att förbättra modellerna.
- **Utnyttja endast en varumärkesresurs per generation** - Du kan överföra flera resurser, men du kan bara använda en för varje specifik generation.

[Läs mer om AI Assistant-skyddsräcken](../using/content-management/gs-generative.md#generative-guardrails)

+++

+++**Vilka är de bästa sätten att optimera sändningstid?**

- **Vänta 30 dagar** - Använd e-post och push-åtgärder i minst 30 dagar innan du aktiverar optimering för sändningstid för att säkerställa tillräcklig datainsamling.
- **Välj optimala väntetider** - Ange maximal väntetid mellan 6-24 timmar för bästa resultat. Kortare tidsperioder begränsar optimeringspotentialen, medan längre kan resultera i inaktuella meddelanden.
- **Optimera för rätt mätvärden** - För e-post, optimera för klickningar vid körning eller öppnar för informationsmaterial. Push-meddelanden är alltid optimerade för Öppna.
- **Undvik tidskänsliga meddelanden** - Använd inte optimering av Skicka-tid för brådskande operativa meddelanden som orderbekräftelser, lösenordsåterställningar eller flygmeddelanden. Passar bäst för marknadsföringsmaterial som kampanjer och nyhetsbrev.
- **Planerad morgon skickar för push** - För att undvika nattmeddelanden skickar schemaläggningen batchpush in på morgonen med kortare varaktighet (t.ex. 9 AM-sändning med 8 timmars väntetid).

[Läs mer om optimering av sändningstid](../using/building-journeys/send-time-optimization.md)

+++

+++**Vilka begränsningar gäller för optimering av sändningstid?**

- **Kanaler** - Endast tillgängligt för e-post- och push-meddelandekanaler i Resor. Inte tillgängligt i kampanjer eller via anpassade åtgärder.
- **Tillgänglighet** - måste aktiveras av Adobe kundtjänst eller din Adobe-representant.
- **Utbildningsperiod** - Kräver minst 30 dagars historik för e-post eller push-data före användning.
- **Modellutbildning** - Modeller utbildas initialt varje vecka med de senaste 16 veckorna av data och omutbildas sedan månadsvis.
- **Utforskande kontra optimering** - 5 % av meddelandena får slumpmässiga utforskande sändningstider och 95 % får optimerade sändningstider.

+++

+++**Vilka begränsningar gäller för AI-modeller i beslutet?**

- **Maximalt antal AI-modeller** - Upp till 5 AI-rankningsmodeller per organisation.
- **Datauppsättningskrav** - Minst två erbjudanden måste ha över 100 visningshändelser och över 5 klickningshändelser under de senaste 14 dagarna för automatisk optimering.
- **Feedback-händelser** - Måste skickas som upplevelsehändelser och inte samlas in automatiskt i Journey Optimizer-kanaler.
- **API-begränsningar** - Automatiska optimeringsmodeller fungerar inte med API:t för gruppbeslut (endast beslutshantering).

[Läs mer om AI-modeller](../using/experience-decisioning/ranking/ai-models.md)

+++

+++**Vilka säkerhetsutkast gäller för AI-aktiverat beslut?**

| Komponent | Gräns |
|-----------|-------|
| AI-rangordningsmodeller | 5 per organisation |
| Beslutsbegäranden (kodbaserade med Edge-segmentering) | 1 500 per sekund |
| Beslutsansökningar (kodbaserade utan Edge-segmentering) | 5 000 per sekund |
| Objektsamlingar | 10 000 totalt |
| Erbjud artiklar per samling | 500 |
| Urvalsstrategier per beslutspolicy | 10 |
| Erbjudandeartiklar som returneras per beslutspolicy | 30 |
| Behörighetsregler + rankningsformler | 10 000 kombinerade |
| Profilattribut per regel | 25 |
| Kontextdataattribut per regel | 30 |

[Läs mer om hur du bestämmer skyddsutkast](../using/experience-decisioning/decisioning-guardrails.md)

+++

+++**Måste jag godkänna några villkor för att använda AI-funktioner?**

Ja, du måste godkänna [Adobe Experience Cloud Generative AI User Guidelines](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html) innan du kan använda AI Assistant i Journey Optimizer. Kontakta Adobe om du vill ha mer information. Dessutom tillämpar Adobe Content Credentials på Firefly-genererade mediefiler som en del av företagets strävan efter transparens vid generativ AI-användning.

+++

+++**Är AI-genererat innehåll alltid korrekt?**

Nej. Generativt AI-innehåll kanske inte alltid är korrekt. Granska alltid AI-genererade utdata för att se om de är korrekta och lämpliga för ditt användningssätt. Utbyt feedback med de betygsverktyg som tillhandahålls för att hjälpa ingenjörer att förfina modellerna.

+++

