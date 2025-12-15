---
solution: Journey Optimizer
product: journey optimizer
title: Inträdes- och utträdeskriterier för resor
description: Lär dig hur ni effektivt hanterar när profiler går in och ut på resor med verkliga exempel och bästa praxis
feature: Journeys, Profiles
role: User
level: Intermediate
keywords: inträde, utförsel, kriterier, resa, profil, återinträde, bästa praxis
version: Journey Orchestration
source-git-commit: b495462aed9a67ff25c2563288bb2ca57e9b7db7
workflow-type: tm+mt
source-wordcount: '1536'
ht-degree: 0%

---


# Arbeta med kriterier för inträde och utträde på resan {#entry-exit-criteria-guide}

Vid kundupplevelsesamordning kräver rätt budskap vid rätt tidpunkt exakt kontroll över när kunderna kommer in på och lämnar era resor. Att förstå och konfigurera kriterier för inträde och utträde kan göra skillnaden mellan en framgångsrik, engagerande kampanj och missade möjligheter eller utmattning av meddelanden.

Den här guiden ger praktisk vägledning, exempel från verkligheten och bästa metoder för att hantera kriterier för att ta sig in på och lämna resan i Adobe Journey Optimizer.

## Vad är kriterier för inträde och utträde? {#what-are-criteria}

**Anmälningskriterier** avgör under vilka villkor en [kundprofil](../audience/get-started-profiles.md) kvalificerar sig för att ange en viss resa. Profiler kan anges baserat på:

* **[Kundbeteende](../event/about-events.md)** - Åtgärder som vidtas av kunder utlöser reseinträde i realtid, som att göra ett köp, överge en kundvagn eller öppna mobilappen.

* **[Profilattribut](../audience/get-started-profiles.md)** - Kundens egenskaper avgör behörighet baserat på data som lagras i deras profil, som lojalitetsnivå, plats, ålder eller kommunikationsinställningar.

* **[Externa händelser](../event/about-creating-business.md)** - Affärs- eller miljöutlösare som påverkar flera kunder samtidigt, till exempel låga lagervarningar, väderförhållanden eller prisförändringar.

* **[Målgruppsmedlemskap](../audience/about-audiences.md)** - Tillhör ett specifikt målgruppssegment och möjliggör riktade resor för grupper som värdefulla kunder, inaktiva användare eller nya prenumeranter.

**Avslutsvillkor** definierar när och hur en profil lämnar eller tas bort från en resa:

* **Reseslutförande** - Profilerna avslutas automatiskt när de når [slutet av alla resvägar](end-journey.md), vilket slutför den designade upplevelsen.

* **Resultat av lyckad mätning** - Profilerna avslutas när de slutför [resemålet](success-metrics.md), till exempel att göra ett köp eller hämta en app, vilket eliminerar onödig uppföljningskommunikation.

* **Villkorsbaserad** - Profilerna avslutas när [specifika villkor](condition-activity.md) uppfylls, som inaktivitet under en angiven period eller ändringar i profilattribut.

* **Händelsebaserad** - Profilerna avslutas när [specifika händelser inträffar](../event/about-events.md), till exempel att prenumerationen avbryts eller att produkten returneras.

* **Diskvalificering av målgrupp** - Profilerna avslutas när de inte längre uppfyller [målgruppskriterierna](../audience/about-audiences.md), vilket säkerställer att meddelandena förblir relevanta.

## Varför kriterier för inträde och utträde gäller {#why-they-matter}

En korrekt definiering av kriterier för inträde och utträde ger ett betydande affärsvärde:

* **Relevans**: Det är bara rätt kunder som deltar i resan, vilket ökar engagemanget och konverteringsgraden genom att rikta sig till den lämpligaste målgruppen vid den optimala tidpunkten.

* **Effektivitet**: Hindrar kunderna från att stanna på irrelevanta resor, vilket minskar onödiga kommunikationer, driftskostnader och kundernas irritation.

* **Personalization**: Möjliggör dynamisk anpassning av upplevelser baserat på realtidsdata och beteenden, vilket skapar mer meningsfulla kundinteraktioner.

* **Efterlevnad**: Hjälper till att hantera frekvensbegränsning och undvika överkommunikation, samtidigt som kundens preferenser och lagstadgade krav respekteras samtidigt som varumärkets anseende bevaras.

## Exempel på inträde och utträde i verkligheten {#real-world-examples}

Här följer vanliga scenarier som visar hur start- och slutkriterier fungerar i praktiken:

**Välkomstkampanj för nya prenumeranter**

Skapa ett personligt första intryck genom att automatiskt vägleda nya prenumeranter genom en introduktion till ert varumärke, era produkter och era tjänster.

* **Post**: Profiler går in på resan när de prenumererar på ett nyhetsbrev
* **Avsluta**: Profilerna avslutas när de har slutfört en välkomstserie med e-postmeddelanden eller efter en angiven tid om de inte engagerar
* **Fördelar**: Ser till att nya prenumeranter får snabb introduktion samtidigt som repetitiva meddelanden undviks

**Övergiven kundvagnsåterställning**

Återvinn förlorade intäkter genom att påminna kunderna om artiklar de lämnat och ge incitament att slutföra köpet.

* **Post**: Kunder anger resan om de lägger till artiklar i en kundvagn men inte slutför utcheckningen inom 24 timmar
* **Avsluta**: Profilerna avslutas när köpet har slutförts eller efter 7 dagar om inget köp har gjorts
* **Fördel**: Skapar konverteringar genom att skapa påminnelser i rätt tid utan att spamma ointresserade kunder

**Förmånsprogramsengagemang**

Belöna era mest värdefulla kunder med exklusiva fördelar och personlig kommunikation som stärker varumärkeslojaliteten och ökar livstidsvärdet.

* **Post**: Kunder ansluter sig till resan efter att ha uppnått ett visst tröskelvärde för förmånspoäng
* **Avsluta**: Profilerna avslutas efter att du har gjort om belöningar eller om de varit inaktiva i 60 dagar
* **Fördelar**: håller värdefulla kunder engagerade med personaliserade erbjudanden och undviker kommunikationströtthet

**Samling med produktfeedback**

Samla in insikter om kundnöjdhet och produktresultat genom att begära feedback vid det rätta tillfället efter leveransen.

* **Post**: Kunder anger resan efter att ha tagit emot en bekräftelsehändelse för produktleverans
* **Avsluta**: Profilerna avslutas när feedback skickas eller efter 10 dagar om inget svar ges
* **Fördel**: Hämtar värdefull feedback snabbt utan att irritera kunder med beständiga begäranden

## Så här konfigurerar du kriterier för reseanmälan {#configure-entry}

>[!BEGINSHADEBOX]

**Lär dig allt du behöver veta om anmälningsvillkor här:**

* **[Händelsebaserade utlösare](../event/about-events.md)**: Använd händelser som&quot;profilskapande&quot;,&quot;transaktionen slutförd&quot; eller anpassade händelser för att starta en resa. [Konfigurera händelser](../event/about-creating.md) i **[!UICONTROL Administration]** > **[!UICONTROL Events]**, definiera [händelseschema och fält](../event/experience-event-schema.md) och lägg sedan till händelsen från paletten **[!UICONTROL Events]** i [resedesignern](using-the-journey-designer.md).

* **[Målgruppsbaserad post](read-audience.md)**: Målsöker profiler som tillhör en viss målgrupp, antingen som en engångsbatch eller som ett återkommande schema. [Skapa målgrupper](../audience/creating-a-segment-definition.md) på menyn **[!UICONTROL Audiences]**, lägg till en **[!UICONTROL Read Audience]**-aktivitet och [konfigurera schemat](journey-properties.md#schedule).

* **[Publikkvalificeringspost](audience-qualification-events.md)**: Utlös resor när profiler kvalificerar sig för eller lämnar vissa målgrupper i realtid. Definiera [direktuppspelade målgrupper](../audience/about-audiences.md), lägg till en **[!UICONTROL Audience Qualification]**-händelse från paletten **[!UICONTROL Events]** och välj utlösartyp.

* **[Attributfilter](condition-activity.md)**: Förfina startvillkoren genom att kombinera händelser eller målgrupper med profilattribut och kontext med hjälp av AND/OR-logik. Använd [villkor](conditions.md) för att referera till [profilattribut](../audience/get-started-profiles.md), händelser eller [externa data](../datasource/about-data-sources.md).

* **[Tidsfönster och schemaläggning](journey-properties.md#schedule)**: Ange tidsbegränsningar för att hålla resorna aktuella och relevanta. Konfigurera [scheman för Läs målgruppsaktiviteter](read-audience.md), använd [Vänteaktiviteter](wait-activity.md) och lägg till [tidsbaserade villkor](conditions.md) för att styra timing.

>[!ENDSHADEBOX]

## Så här ställer du in kriterier för avfärd {#configure-exit}

>[!BEGINSHADEBOX]

**Lär dig allt du behöver veta om avslutningskriterier här:**

* **[Färdigställande av resan](end-journey.md)**: Profilerna avslutas automatiskt när de har nått det sista steget i resan. Utforma resvägar som avslutas vid **[!UICONTROL End]** aktiviteter.

* **[Resultatmått](journey-properties.md#exit-criteria)**: Definiera framgångsmått (som köp eller prenumeration) och avslutsprofiler när de är klara. Klicka på ikonen **[!UICONTROL Show exit criteria]**, markera **[!UICONTROL Add exit criteria]** och välj en [Event](../event/about-events.md) eller [Audience](../audience/about-audiences.md) som slututlösare.

* **[Tidsgränser för inaktivitet](wait-activity.md)**: Avsluta profiler om inget engagemang inträffar inom en angiven tidsram. Använd [avslutningskriterier](journey-properties.md#exit-criteria) med målgrupper som kontrollerar det senaste interaktionsdatumet, ställ in [Vänta-aktiviteter](wait-activity.md) med definierade varaktigheter och använd [villkor](condition-activity.md) för att kontrollera aktivitet.

* **[Regler för återinträde](entry-management.md)**: Bestäm om profiler kan återkomma till resan flera gånger eller bara en gång, beroende på kampanjstrategin. Konfigurera inställningarna för **[!UICONTROL Re-entrance]** på resan **[!UICONTROL Properties]** om du vill ange vänteperioder, aktivera tvingad återinträde eller använda [extra identifierare](supplemental-identifier.md) för sammanhangsspecifik återinträde.

>[!ENDSHADEBOX]

## Detaljerade exempel på resan {#journey-examples}

Använd följande dokumenterade användningsexempel för stegvis implementeringsvägledning med fullständig teknisk information:

* **[Kundintroduktionsresa](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding)** - Skapa personliga välkomstupplevelser med målgruppskvalificering, tidsgräns för evenemang och målbaserade avslutningar

* **[Återvinning av övergiven kundvagn](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart)** - Återställa förlorad försäljning med händelseutlösta resor, spelböcker och kanalroutning

* **[Återengagemangskampanjer](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma)** - Återvänd till inaktiva kunder med beteendeanpassning och aktivering av betalda medier

* **[Skicka meddelanden till prenumeranter](message-to-subscribers-uc.md)** - Målprenumerationslistor med Läs publik och personaliserat innehåll

* **[Skicka flerkanalsmeddelanden](journeys-uc.md)** - Kombinera e-post och push-meddelanden med reaktionshändelser och logik för flera sökvägar

* **[Skicka endast e-post på veckodagar](weekday-email-uc.md)** - Schemalägg kommunikation med tidsbaserade villkor och vänteformler

>[!TIP]
>
>Bläddra bland alla tillgängliga användningsfall i [biblioteket för reseanvändningsfall](jo-use-cases.md) om du vill ha fler mönster och implementeringar, inklusive [mappa upp leveranser](ramp-up-deliveries-uc.md), [upplevelsehändelsemönster](exp-event-lookup.md) och [ta bort profiler från direktresor](journey-pause.md#apply-an-exit-criteria-in-a-paused-journey).

## Bästa tillvägagångssätt för hantering av inträde och utträde {#best-practices}

**Radera definition**

Upprätta tydlig dokumentation och namnkonventioner för att säkerställa att teamet förstår hur profiler rör sig genom era resor:

* Dokumentera era era in- och utresegleringslogik innan ni bygger upp resor för att anpassa marknadsförings- och analysteam
* Skapa flödesscheman med ingångspunkter, resvägar och avslutningsvillkor
* Definiera tydligt affärsregler:&quot;Profilerna avslutas när X inträffar ELLER efter Y-dagar&quot;
* Använd beskrivande etiketter: &quot;Avsluta - Inköpet har slutförts&quot; är inte &quot;Avsluta 1&quot;
* [Tagga resor](../start/search-filter-categorize.md#tags) konsekvent för rapportering och filtrering

**Undvik överlappande resor**

Förhindra förvirring och meddelandekonflikter mellan kunder genom att samordna er strategi för olika kampanjer:

* [Granska aktiva resor](journey-ui.md) innan liknande startas för att förhindra konflikter
* Utnyttja [konflikthantering](../conflict-prioritization/conflicts.md) och [prioritetspoäng](../conflict-prioritization/priority-scores.md) för att lösa överlappningar och prioritera resor
* Utforma resor som kompletterar varandra i stället för att konkurrera med varandra

>[!NOTE]
>
>För avancerade scenarier som att automatiskt ta bort profiler när de kvalificerar för högprioriterade resor använder du [resefackning och medling](../conflict-prioritization/journey-capping.md) i stället för avslutningskriterier.

**Övervaka och optimera**

Kontinuerlig utvärdering av reseprestanda och förfina era kriterier för inträde och utträde baserat på kundbeteende:

* Spåra ingångs-, avslutnings- och slutförandefrekvens för varje resa med [reserapporter](../reports/journey-global-report-cja.md)
* Övervaka [framgångsmått](success-metrics.md): procentandelen som avslutas via måttet för lyckad åtgärd kontra tidsgränsen
* [Testa start- och avslutsvillkor](testing-the-journey.md) med olika profilscenarier innan du startar
* Justera baserat på data: Om det finns ett högt antal tidiga utgångar, se vad som är relevant för tävlingsbidragen. Om mätningen för ett lågt antal lyckade försök är bäst analyserar du innehållet och tidsangivelsen
* Granska alla aktiva resor kvartalsvis

**Respektera frekvensändar**

Bevara kundernas förtroende och engagemang genom att styra meddelanderefrekvensen i all kommunikation under resan:

* Ange lämpliga [vänteperioder för återinträde](entry-management.md) eller inaktivera återinträde för engångsresor
* Använd [regler för frekvensbegränsning](../conflict-prioritization/rule-sets.md) för att förhindra överkommunikation
* Övervaka frekvensvärden i rapporter för att säkerställa regelefterlevnad

>[!NOTE]
>
>Om du vill hantera frekvensgränser och gränser för reseinmatning över flera resor använder du [kundens capping och medling](../conflict-prioritization/journey-capping.md) och [frekvenscapping per kanal](../conflict-prioritization/channel-capping.md).

## Slutsats {#conclusion}

Kriterierna för att resa in och ut är grundläggande när det gäller att leverera personaliserade, vältajmade och effektiva kundupplevelser med Adobe Journey Optimizer. Genom att skapa dessa villkor noggrant kan marknadsförarna öka engagemanget, minska friktionen och bygga starkare kundrelationer.

Börja med att tydligt kartlägga kundens triggers och exitpunkter, testa noggrant och övervaka resultaten för att kontinuerligt förfina kundresan.

## Relaterade resurser {#related-resources}

**Teknisk dokumentation**

[Profilingångshantering](entry-management.md) | [&#x200B; Reseegenskaper och avslutningskriterier &#x200B;](journey-properties.md) | [Hur resorna avslutas](end-journey.md) | [Ytterligare identifierare](supplemental-identifier.md) | [Resedesigner](using-the-journey-designer.md)

**Självstudiekurser och exempel**

[Användningsexempel på resan](jo-use-cases.md) | [Video om kundintroduktion](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding) | [Övergiven kundvagnsvideo &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart) | [Community-blogg: Inmatnings- och avslutningskriterier](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-journey-entry-and-exit-criteria-in-adobe-journey/ba-p/760958)

**Relaterade funktioner**

[Publikkvalificeringshändelser](audience-qualification-events.md) | [Resultatstatistik och mål &#x200B;](success-metrics.md) | [Konflikthantering](../conflict-prioritization/conflicts.md) | [Frekvensbegränsning](../conflict-prioritization/rule-sets.md) | [Testa resor](testing-the-journey.md) | [Villkorsaktivitet](condition-activity.md) | [Reaktionshändelser](reaction-events.md) | [Vänteaktivitet](wait-activity.md)
