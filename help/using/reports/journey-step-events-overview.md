---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med steg för resa
description: Lär dig hur du arbetar med steg för kundresor i Adobe Journey Optimizer - förstå vad de är, varför de betyder något och hur du använder dem för analys och optimering
feature: Journeys, Reporting
topic: Content Management
role: Data Engineer, Data Architect, Admin, User
level: Intermediate, Experienced
keywords: resa, stegvisa händelser, analys, rapportering, övervakning, XDM
hide: true
hidefromtoc: true
exl-id: 9f8e7d6c-5b4a-3928-1756-849302a11c2b
source-git-commit: df3abb7da17eb21e5e4120b55bdeb61fec3e202d
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 1%

---

# Arbeta med steg för resa {#work-with-journey-step-events}

Resestegshändelser genereras automatiskt händelser som samlar in detaljerad information om varje steg en profil tar när de går igenom en resa i Adobe Journey Optimizer. Dessa händelser ger en heltäckande bild av reseprestanda och möjliggör kraftfulla analysfunktioner.

## Vad är steg-händelser för resan? {#what-are-step-events}

Resestegshändelser är systemgenererade XDM-händelser (Experience Data Model) som Adobe Journey Optimizer automatiskt skapar och skickar till Adobe Experience Platform när en profil flyttas från en nod till en annan under en resa. Varje händelse motsvarar en viss åtgärd eller övergång i kundens upplevelse.

Det finns två huvudtyper av steg för resan:

- **travelStepEvent**: Händelser som rör förloppet för en enskild profil genom hela kundresan
- **travelStepProfileEvent**: Händelser som innehåller ytterligare profilkontextinformation

### Vilka utlöser steg för resan? {#event-triggers}

Resestegshändelser genereras automatiskt för olika reseaktiviteter:

- **Anmälningshändelser**: När en profil går in på en resa
- **Åtgärdskörning**: När meddelanden skickas eller anpassade åtgärder utförs
- **Villkorsutvärdering**: När profiler passerar genom beslutspunkter
- **Vänta på aktiviteter**: När profiler kommer in och avslutar väntar-noder
- **Avsluta händelser**: När profiler slutför eller avslutar en resa
- **Felhantering**: När fel inträffar under körning

>[!NOTE]
>
>Resestegshändelser aktiveras som standard för alla instanser. Du kan inte ändra eller uppdatera scheman och datauppsättningar som har skapats under etablering för steghändelser. Dessa scheman och datauppsättningar är skrivskyddade.

## Varför resestegshändelser är viktiga {#why-step-events-matter}

Resestegshändelser ger viktigt värde för organisationer som använder Adobe Journey Optimizer:

### Realtidsanalys och -övervakning {#real-time-analytics}

- **Prestandaspårning för resan**: Övervaka hur profiler flödar genom dina resor i realtid
- **Konverteringsanalys**: Förstå bortfallspunkter och lyckade konverteringssökvägar
- **Felidentifiering**: Identifiera och felsök problem när de inträffar

### Dataintegrering och -insikter {#data-integration}

- **Plattformsoberoende analys**: Kombinera resedata med andra Adobe Experience Platform-datakällor
- **Vyn Customer 360**: Skapa omfattande kundprofiler med reseinteraktioner
- **Attributionsmodellering**: Koppla rörelsekontaktytor till affärsresultat längre fram i kedjan

### Optimeringsmöjligheter {#optimization}

- **A/B-testningsinsikter**: Analysera prestanda för olika kundvägar
- **Förbättring av Personalization**: Förbättra framtida upplevelser genom att använda beteendedata för resan
- **Driftseffektivitet**: Identifiera flaskhalsar och optimera resedesignen

## Så här använder du steg-händelser för resan {#how-to-use-step-events}

### Åtkomst till händelsedata för resesteg {#accessing-data}

Händelsedata för steg på resan lagras automatiskt i Adobe Experience Platform och kan nås via:

1. **Data Lake-frågor**: Använd SQL för att fråga datauppsättningen `journey_step_events`
2. **Customer Journey Analytics**: Analysera resedata med avancerade analysverktyg
3. **Realtidsrapportering**: Få åtkomst till data via Journey Optimizer inbyggda rapporteringsfunktioner
4. **API:er**: Använd händelsedata för anpassade program programmatiskt

### Tillgängliga nyckeldatapunkter {#key-data-points}

Resestegshändelser samlar in omfattande information, bland annat:

- **Reseidentifiering**: Resurs-ID, version och namn
- **Profilinformation**: Profil-ID och associerade identiteter
- **Steginformation**: Nodnamn, stegtyp och körningsstatus
- **Tidsstämplar**: Exakt timing för varje resesteg
- **Åtgärdsresultat**: Status för lyckad/misslyckad och körningsinformation
- **Felinformation**: Detaljerade felkoder och beskrivningar när problem uppstår

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

**Resekanalsanalys**

- Spåra konverteringsgraden vid varje resesteg
- Identifiera var profiler oftast lämnar resan
- Mät hur lång tid som tillbringats i olika resefaser

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

- Använd `journeyVersionID` i stället för `journeyVersionName` för bättre frågeprestanda
- Filtrera efter datumintervall för att förbättra frågehastigheten på stora datamängder
- Utnyttja profilidentiteter som matchar konfigurationen för resenamnrymden

**Datakvalitet**

- Övervaka regelbundet för [ignorerade händelser](sharing-field-list.md#discarded-events) för att identifiera dataproblem
- Validera att händelsetcheman matchar dina analyskrav
- Implementera korrekt felhantering i anpassade frågor

**Analysstrategier**

- Kombinera steg-händelser för resan med feedback-data för fullständig attribuering
- Använd tidsbaserad analys för att förstå hur snabbt resan går och hur många flaskhalsar den har
- Skapa kohortanalyser för att jämföra olika varianter av resan

### Avancerade analysfunktioner {#advanced-analytics}

**Integrering med Customer Journey Analytics**
Resestegshändelser kan analyseras med Customer Journey Analytics för:

- Avancerad attribueringsmodellering
- Visualisering av flerkanalsresor
- Prediktiv analys av reseresultat

**Realtidsbeslut**
Använd händelsemönster för kundstegshändelser för att:

- Utlösa personalisering i realtid
- Optimera den dynamiska resan
- Aktivera sammanhangsbaserade rekommendationer för nästa bästa åtgärd

## Ytterligare resurser {#additional-resources}

### Dokumentationslänkar {#documentation-links}

- **[Översikt över delning av resesteg](sharing-overview.md)**: Förstå hur resedata flödar till Adobe Experience Platform
- **[Inbyggda schemaordlistor](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)**: Fullständig XDM-schemareferens
- **[Journey Optimizer-rapportering](report-gs-cja.md)**: Översikt över rapportfunktioner i Journey Optimizer

### Integreringsguider {#integration-guides}

- **[Adobe Customer Journey Analytics](cja-ajo.md)**: Analyserar Journey Optimizer-data i CJA
- **[Datahantering](../data/export-datasets.md)**: Exportera och hantera resedata
- **[Sekretess och styrning](../privacy/audit-logs.md)**: Datastyrningsaspekter för resehändelser

Evenemang för steg på resan utgör grunden för avancerad reseanalys i Adobe Journey Optimizer. Genom att förstå och utnyttja dessa händelser effektivt kan ni få djupgående insikter om kundbeteenden, optimera kundresan och skapa mer personaliserade upplevelser för era kunder.
