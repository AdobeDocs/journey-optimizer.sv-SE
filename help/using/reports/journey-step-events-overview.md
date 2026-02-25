---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med steg för resa
description: Lär dig hur du arbetar med steg för kundresor i Adobe Journey Optimizer - förstå vad de är, varför de betyder något och hur du använder dem för analys och optimering
feature: Journeys, Reporting
role: Developer, Admin, User
level: Intermediate, Experienced
keywords: resa, stegvisa händelser, analys, rapportering, övervakning, XDM
exl-id: 2e7c5ea5-d8c5-416d-ab88-d2bc02043558
source-git-commit: 97fa287d94efb7fb95817fc15268e736517cb629
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 1%

---

# Arbeta med steg för resa {#work-with-journey-step-events}

Resestegshändelser genereras automatiskt händelser som samlar in detaljerad information om varje steg som en [profil](../audience/get-started-profiles.md) tar när de går igenom en [resa](../building-journeys/journey.md) i Adobe Journey Optimizer. Dessa händelser ger en omfattande insyn i [reseprestanda](../building-journeys/report-journey.md) och möjliggör kraftfulla analysfunktioner.

## Vad är steg-händelser för resan? {#what-are-step-events}

Resestegshändelser är systemgenererade [XDM-händelser (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"} som Adobe Journey Optimizer automatiskt skapar och skickar till [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=sv-SE){target="_blank"} när en profil flyttas från en nod till en annan under en resa. Varje händelse motsvarar en specifik [reseaktivitet](../building-journeys/about-journey-activities.md) eller övergång i kundens reseupplevelse.

Det finns två huvudtyper av steg för resan:

- **travelStepEvent**: Händelser som rör förloppet för en enskild profil genom hela kundresan
- **travelStepProfileEvent**: Händelser som innehåller ytterligare profilkontextinformation

### Vilka utlöser steg för resan? {#event-triggers}

Resestegshändelser genereras automatiskt för olika reseaktiviteter:

- **Anmälningshändelser**: När en profil [går in i en resa](../building-journeys/entry-management.md)
- **Åtgärdskörning**: När [meddelanden skickas](../building-journeys/journey-action.md) eller [anpassade åtgärder](../building-journeys/using-custom-actions.md) utförs
- **Villkorsutvärdering**: När profiler passerar genom [villkor](../building-journeys/condition-activity.md) och beslutspunkter
- **Vänta på aktiviteter**: När profiler anges och avslutas [väntar du på noder](../building-journeys/wait-activity.md)
- **Avsluta händelser**: När profiler är klara eller [Avsluta en resa](../building-journeys/end-journey.md)
- **Felhantering**: När fel inträffar under körning

>[!NOTE]
>
>Resestegshändelser aktiveras som standard för alla instanser. Du kan inte ändra eller uppdatera [scheman och datamängder](sharing-overview.md) som har skapats under etablering för steghändelser. Dessa scheman och datauppsättningar är skrivskyddade.

Läs mer om [scheman för kundstegshändelser](sharing-field-list.md).

## Varför resestegshändelser är viktiga {#why-step-events-matter}

Resestegshändelser ger viktigt värde för organisationer som använder Adobe Journey Optimizer:

### Realtidsanalys och -övervakning {#real-time-analytics}

- **Prestandaspårning för resan**: Övervaka hur profiler flödar genom dina resor i realtid med [liverapporter](live-report.md)
- **Konverteringsanalys**: Förstå bortfallspunkter och lyckade konverteringssökvägar med [reseanalys](journey-global-report-cja.md)
- **Felidentifiering**: Identifiera och felsök problem när de uppstår med [övervakning och aviseringar](alerts.md)

### Dataintegrering och -insikter {#data-integration}

- **Plattformsoberoende analys**: Kombinera resedata med andra [Adobe Experience Platform-datakällor](../datasource/adobe-experience-platform-data-source.md)
- **Vyn Customer 360**: Skapa omfattande [kundprofiler](../audience/get-started-profiles.md) som innehåller reseinteraktioner
- **Attributionsmodellering**: Koppla kontaktpunkter för resan till affärsresultat längre fram i kedjan med [Customer Journey Analytics](cja-ajo.md)

### Optimeringsmöjligheter {#optimization}

- **A/B-testningsinsikter**: Analysera prestanda för olika kundvägar med [experimenterande](campaign-global-report-cja-experimentation.md)
- **Förbättring av Personalization**: Använd data om resebeteende för att förbättra framtida upplevelser med [dynamiskt innehåll](../personalization/dynamic-content.md)
- **Driftseffektivitet**: Identifiera flaskhalsar och optimera [resedesignen](../building-journeys/using-the-journey-designer.md)

## Så här använder du steg-händelser för resan {#how-to-use-step-events}

### Åtkomst till händelsedata för resesteg {#accessing-data}

Händelsedata för steg på resan lagras automatiskt i Adobe Experience Platform och kan nås via:

1. **Data Lake-frågor**: Använd SQL för att fråga datauppsättningen `journey_step_events` med [frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv){target="_blank"}
2. **Customer Journey Analytics**: Analysera resedata med [avancerade analysverktyg](cja-ajo.md)
3. **Realtidsrapportering**: Få åtkomst till data via Journey Optimizer [inbyggda rapporteringsfunktioner](gs-reports.md)
4. **API:er**: Använd händelsedata för anpassade program programmatiskt

Läs mer om [åtkomst till datauppsättningar](../data/datasets-query-examples.md).

### Tillgängliga nyckeldatapunkter {#key-data-points}

Resestegshändelser samlar in omfattande information, bland annat:

- **Reseidentifiering**: [Resurs-ID, version och namn](sharing-journey-fields.md)
- **Profilinformation**: [Profil-ID och associerade identiteter](sharing-identity-fields.md)
- **Steginformation**: [Nodnamn, stegtyp och körningsstatus](sharing-common-fields.md)
- **Tidsstämplar**: Exakt timing för varje resesteg
- **Åtgärdsresultat**: [Status för lyckad/misslyckad och körningsinformation](sharing-execution-fields.md)
- **Felinformation**: Detaljerade [felkoder och beskrivningar](sharing-field-list.md#discarded-events) när problem uppstår

Utforska alla [tillgängliga fältdefinitioner](sharing-field-list.md).

### Vanliga användningsfall {#common-use-cases}

**Prestandaövervakning**

```sql
-- Example: Count profiles entering a journey in the last 24 hours
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events 
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-id>'
AND _experience.journeyOrchestration.stepEvents.nodeType='start'
AND DATE(timestamp) > (now() - interval '24' hour);
```

**Felanalys**

```sql
-- Example: Identify errors by journey node
SELECT _experience.journeyOrchestration.stepEvents.nodeName,
       count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName;
```

**Reseanalys för funnel**

- Spåra konverteringsgraden vid varje resesteg
- Identifiera var profiler oftast lämnar resan
- Mät hur lång tid som tillbringats i olika resefaser

Läs mer om [frågetekniker för funnel-analys](query-examples.md#common-queries).

## Exempel och resurser {#samples-resources}

### Frågeexempel och mallar {#query-examples}

Utforska omfattande frågeexempel för en gemensam analys av resesegmenthändelser:

- **[Exempel på guidade steg i händelsefråga](query-examples.md)**: Körklara SQL-frågor för vanliga analysscenarier
- **[Datauppsättningsfrågeexempel](../data/datasets-query-examples.md#journey-step-event)**: Exempel på frågor om händelsedatamängder för kundsteg
- **[Profilbaserade frågor](query-examples.md#profile-based-queries)**: Spåra enskilda profilresor och interaktioner

### Fältdokumentation {#field-documentation}

Förstå den fullständiga datastrukturen för steg-händelser i kundresan:

- **[Listan med händelser i steg på resan](sharing-field-list.md)**: Omfattande referens till alla tillgängliga fält
- **[Vanliga fält](sharing-common-fields.md)**: Delade fält över travelStepEvent och travelStepProfileEvent
- **[Fält för åtgärdskörning](sharing-execution-fields.md)**: Fält som är specifika för spårning av åtgärdskörning
- **[Resefält](sharing-journey-fields.md)**: Resespecifika metadata och identifierare

### Bästa praxis och felsökning {#best-practices}

**Prestandaoptimering**

- Använd `journeyVersionID` i stället för `journeyVersionName` för bättre frågeprestanda ([läs mer om reseegenskaper](../building-journeys/expression/journey-properties.md))
- Filtrera efter datumintervall för att förbättra frågehastigheten på stora datamängder
- Utnyttja profilidentiteter som matchar konfigurationen för [resenamnrymden](../building-journeys/entry-management.md)

**Datakvalitet**

- Övervaka regelbundet för [ignorerade händelser](sharing-field-list.md#discarded-events) för att identifiera dataproblem
- Validera att händelsetcheman matchar dina analyskrav
- Implementera korrekt felhantering i anpassade frågor

**Analysstrategier**

- Kombinera steg-händelser för resan med [feedbackdata](../data/datasets-query-examples.md#message-feedback-event-dataset) för fullständig attribuering
- Använd tidsbaserad analys för att förstå hur snabbt resan går och hur många flaskhalsar den har

### Avancerade analysfunktioner {#advanced-analytics}

**Integrering med Customer Journey Analytics**
Resestegshändelser kan analyseras med [Customer Journey Analytics](cja-ajo.md) för:

- Avancerad attribueringsmodellering
- Visualisering av flerkanalsresor
- Prediktiv analys av reseresultat

Lär dig hur du [konfigurerar Customer Journey Analytics](report-gs-cja.md) för Journey Optimizer-data.

## Ytterligare resurser {#additional-resources}

### Dokumentationslänkar {#documentation-links}

- **[Översikt över delning av resesteg](sharing-overview.md)**: Förstå hur resedata flödar till Adobe Experience Platform
- **[Inbyggda schemaordlistor](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=sv-SE){target="_blank"}**: Fullständig XDM-schemareferens
- **[Journey Optimizer-rapportering](report-gs-cja.md)**: Översikt över rapportfunktioner i Journey Optimizer

### Integreringsguider {#integration-guides}

- **[Adobe Customer Journey Analytics](cja-ajo.md)**: Analyserar Journey Optimizer-data i CJA
- **[Datahantering](../data/export-datasets.md)**: Exportera och hantera resedata
- **[Sekretess och styrning](../privacy/audit-logs.md)**: Datastyrningsaspekter för resehändelser


**Nästa steg:**

- Börja med att [skapa dina första reserapporter](sharing-overview.md)
- Utforska [frågeexempel](query-examples.md) för specifika användningsområden
- Läs mer om [bästa praxis för resehantering](../building-journeys/journey.md)
