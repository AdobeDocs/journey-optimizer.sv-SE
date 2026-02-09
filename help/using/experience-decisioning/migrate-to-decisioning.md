---
title: Fördelar med att migrera till beslut
description: Läs mer om fördelarna med att migrera från beslutshantering till beslut
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: aedd7845-3d8d-457a-a7f3-03897846b241
source-git-commit: 741b39a7588ae4e1161891226d95609508b00031
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 1%

---

# Fördelar med att migrera till beslut {#migrate-to-decisioning}

## Vad är beslut? {#what-is-decisioning}

Journey Optimizer Decisioning är en utökning av beslutsfunktioner som lägger grunden för beslut om andra objekt (som resor) i framtiden. Den nya funktionen förenar viktiga arbetsflödesbegrepp för smidig redigering och hantering, introducerar experimenterande i beslut och flyttar beslutsobjekt till en schemabaserad metod för dynamisk artikelåtergivning.

Med nästa generations beslutsramverk och funktioner i Adobe Journey Optimizer kan varumärken använda tillgängliga data, intelligens och kundens kontext för att avgöra den bästa upplevelsen för varje kund för att optimera affärsvärdet. [Läs mer](gs-experience-decisioning.md)

## Varför gå över till beslut? {#why-migrate}

Beslutsfattandet ger betydande möjligheter och fördelar jämfört med den äldre ramen för beslutsförvaltning:

### AI och maskininlärning

* **Anpassade mått**: Möjlighet att använda anpassade optimeringsmått för AI-modeller. Detta ger interoperabilitet för rapporter med [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview){target="_blank"}, standardiserar rapportering för båda plattformarna och förbättrar datakonsekvensen och tillförlitligheten. Den sömlösa integreringen ger en tydligare bild av prestandamätningarna och lägger till nya funktioner som att skapa enkla mätvärden, publicera målgrupper, ställa ad hoc-frågor med Insight Builder och schemalägga rapporter.

* **Lyft mätning**: Möjlighet att visualisera utforska och utnyttja trafik i AI-modeller. Detta gör det möjligt för marknadsförare och datavetare att kvantifiera hur AI-utforskandet förbättrar den långsiktiga modellens prestanda och upptäcker nya vinnande erbjudanden. Öppenhet när det gäller trafikallokering bygger upp förtroende för AI-beslut och ger team möjlighet att optimera både inlärning och prestanda över tid. [Läs mer](ranking/auto-optimization-model.md#lift)

* **AI-formelbyggare**: Möjlighet att använda AI-modellutdata på befintliga formelfunktioner. Detta ger marknadsförarna möjlighet att sömlöst kombinera AI-utdata med deterministiska regler och vikter för mer avancerade optimeringsstrategier, öka kontrollen och flexibiliteten samtidigt som maskininlärningsinformationen utnyttjas. [Läs mer](ranking/ranking-formulas.md)

### Experimentation

Möjlighet att experimentera med erbjudanden, olika aspekter av ett visst erbjudande och/eller rankningsmetoder. På så sätt kan marknadsförarna köra kontrollerade experiment med kreativa, berättigande och rankningslogik för att identifiera högpresterande varianter, snabba upp inlärningscyklerna och driva en kontinuerlig optimering av beslutssystemet.

### Förbättrad rapportering

Instrumentpanel som dokumenterar prestanda för beslutsobjekt och urvalsstrategier mot nyckelelement i engagemanget funnel. En intuitiv och körklar beslutspanel visar snabbt värdet av kampanjens och kundens resultat för viktiga nyckeltal för leverans av erbjudanden och innehåll, visning och klickning, fallback-användning och lyft från AI- och maskininlärningsmodeller. [Läs mer](cja-reporting.md)

### Driftseffektivitet

* **Sandlådekopia**: Möjlighet att kopiera över objekt mellan sandlådor (t.ex. Dev to Prod). Detta förenklar arbetsflödena för driftsättning och testning genom att möjliggöra smidig migrering av beslutslogik, erbjudanden och konfigurationsobjekt mellan miljöer, vilket minskar installationstiden och minimerar antalet fel hos människor. [Läs mer](../configuration/copy-objects-to-sandbox.md)

* **Schemabaserad hantering av objektkataloger**: Möjlighet att definiera och hantera beslutsobjekt direkt till schemalänkade datauppsättningar, vilket möjliggör dynamiska uppdateringar och förenklad styrning. Detta effektiviserar kataloghanteringen genom att synkronisera beslutsobjekt med underliggande datakällor, säkerställa innehållets exakthet, möjliggöra snabbare uppdateringar och stödja styrning i stor skala. [Läs mer](items.md)

* **Platsbaserat beslut**: Möjlighet att göra beslutslogik återanvändbar över placeringar/platser, frigöra beslutsval från leverans. Detta främjar återanvändbarhet och effektivitet genom att en enda beslutsmodell kan styra flera placeringar eller ytor (t.ex. webb, app, e-post), centralisera logiken och snabba upp arbetet med kanalövergripande personalisering. [Läs mer](placements.md)

* **Återanvändbara innehållsfragment**: Möjlighet att definiera JSON- eller HTML-innehållsblock (t.ex. titlar, sidhuvuden, sidfötter, CTA:er) en gång och referera till dem inom flera objekt för erbjudanden. Detta effektiviserar framtagning och styrning av innehåll genom att låta delade komponenter hanteras centralt och uppdateras automatiskt i alla erbjudanden. [Läs mer](../content-management/fragments.md)

### Kommande funktioner

* **Kanalbeslut**: Möjlighet att använda beslutslogik för att fastställa den bästa kanalen för engagemang (t.ex. e-post kontra push kontra webb), i stället för bara det bästa erbjudandet inom en enda kanal. Detta förbättrar kundupplevelsen genom att optimera var ett meddelande levereras, inte bara vad som levereras.

* **Meddelandeoptimering**: Möjlighet att använda AI eller regelbaserade metoder för att optimera meddelandeinnehåll för varje profil, vilket förbättrar engagemang och konverteringsresultat. Det gör att marknadsförarna kan skräddarsy ton, bilder och layout dynamiskt baserat på målgruppsattribut och prestandadata.

* **Optimering av resan**: Möjlighet att avgöra vilken resa en profil ska följa, baserat på experimentella resultat, realtidskontext, regler och/eller benägenhet att konvertera. På så sätt kan teamen på ett intelligent sätt dirigera profiler genom den optimala kundresan och säkerställa rätt stängsel och innehåll för varje användare.

* **Resebeslut**: Möjlighet att skilja mellan flera resor när en profil kvalificerar för mer än en, så att den mest värdefulla eller relevanta resan väljs. Detta förhindrar meddelandekonflikter och övermeddelanden genom att rangordna och välja den högsta prioriteringsresan för varje profil.

### Ytterligare funktioner

* **Tillämpning av principer**: Företagsanvändarbehörighet att använda funktioner som [Dataanvändningsmärkning och -framtvingning (DULE)](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview){target="_blank"} och [samtycke](../action/consent.md) i beslutet, vilket aktiverar skydd av sekretessen i hela beslutsarbetsflödet. Detta säkerställer att beslut automatiskt följer dataanvändningsprinciper och att kundens samtycke används.

* **Stöd för inbyggda meddelandekanaler**: Integrerade meddelanden och beslut i ett enda ramverk över flera kanaler: [Kodbaserad upplevelse](../code-based/get-started-code-based.md), [E-post](../email/get-started-email.md) (begränsad tillgänglighet), [SMS](../sms/get-started-sms.md) och [push-meddelanden](../push/get-started-push.md). Intuitivt gränssnittsstöd gör att användare kan infoga beslutskomponenter direkt i arbetsflöden för meddelanderedigering.

* **Experience Platform-datauppslagssökning**: Möjlighet att överföra och referera till [Adobe Experience Platform-datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview){target="_blank"} direkt inom urvalsregler, rankning och personaliserat innehåll för erbjudanden. Detta utökar flexibiliteten för personalisering och målinriktning genom att tillåta beslutslogik att använda dynamiska externa datakällor. [Läs mer](../data/lookup-aep-data.md)

* **Skalbarhet och prestanda**: Arkitekturförbättring som flyttar beslutsberäkning från navet till kanten, vilket avsevärt minskar latensen och förbättrar genomströmningen för användning med hög trafik.

## Exempel på användningsområden {#use-cases}

| Användningsfall | Beslutshantering | Beslut |
|----------|---------------------|-------------|
| **Flerplaceringsstrategi** | Beslutslogik som är knuten till en viss placering (t.ex. webb- eller e-postplats) | En och samma strategi driver både hemsidan och mobilappen |
| **Konsekventa attribut för erbjudande** | Varje erbjudande hanterar sina egna attribut manuellt - ingen konsekvens på schemanivå | En marknadsförare definierar&quot;rabattType&quot; och&quot;offerValue&quot; en gång. Alla erbjudanden ärver dessa fält automatiskt |
| **Dynamisk AI-rankning** | Rankningarna bygger endast på modellutdata eller statiska regler | En marknadsförare kan justera viktningen (t.ex. 60 % AI-konverteringspoäng + 40 % vinstmarginal) för att balansera intäkter och engagemang |
| **A/B-testningsstrategier** | Inget inbyggt stöd för experiment | Ett team kan A/B-testa om&quot;AI + företagsregler&quot; matchar&quot;prioritetsbaserad rankning&quot; |
| **Anpassade AI-mått** | Optimerar endast mot klickbenägenhet; ingen synlighet för modellundersökning eller lyft | Återförsäljare utbildar en modell som&quot;sannolikt kommer att köpa&quot; och övervakar lyft över nya jämfört med kända produkter |
| **Återanvändbarhet av innehåll** | Alla erbjudanden lagrar fullständigt innehåll oberoende av varandra | Uppdatera en rubrik eller CTA automatiskt till hundratals erbjudanden |
| **Integrerad redigering** | Beslutsfattandet och budskapet finns i separata ramverk med begränsad integrering | En marknadsförare infogar personaliserade erbjudanden i ett e-postmeddelande utan att lämna meddelanderedigeraren |
| **Sekretessregler** | Kräver manuell samordning med tekniker och datateam för genomförande | En marknadsförare skapar en regel för erbjudanden i vetskap om att medgivandeinställningarna automatiskt utesluter vissa profiler |
| **Realtidslager** | Statiska data; begränsad flexibilitet att använda externa eller kontextuella datauppsättningar | Använd en produktlagerdatamängd för att utelämna erbjudanden för artiklar som inte finns i lager i realtid |
| **Skalningsprestanda** | Beslut som fattas i navet med högre latens | Realtidspersonalisering för miljontals inkommande förfrågningar under 100 ms svarstid |

## Migreringsverktyg {#migration-tooling}

En omfattande uppsättning **API:er för migreringsverktyg** finns tillgängliga för migrering av beslutshanteringsenheter till beslut. Dessa API:er möjliggör sömlös migrering mellan sandlådor med automatisk beroendeupplösning och återställningsfunktioner.

Med API:erna för migreringsverktyget kan du:

* **Analysera beroenden** mellan käll- och målsandlådor
* **Migrera vid olika scope** - sandlåda, erbjudande eller beslutsnivå
* **Återställningsmigreringar** om problem upptäcks

Fullständig API-dokumentation, inklusive autentisering, slutpunkter, exempel på begäran/svar och stegvisa arbetsflöden finns på [den här sidan](decisioning-migration-api.md).

## Relaterade ämnen {#related-topics}

* [Kom igång med beslutsfattande](gs-experience-decisioning.md)
* [Beslut om skyddsräcken och begränsningar](decisioning-guardrails.md)
* [Frågor och svar om beslut](decisioning-faq.md)
