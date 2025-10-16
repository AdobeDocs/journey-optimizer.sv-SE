---
solution: Journey Optimizer
product: journey optimizer
title: Resor, frågor och svar
description: Frågor och svar om Journey Optimizer Journeys
feature: Journeys, Get Started
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: resa, frågor, svar, felsökning, hjälp, guide
version: Journey Orchestration
hide: true
hidefromtoc: true
source-git-commit: a7da542320a38dbc739ec42ee4926fce1dea1df0
workflow-type: tm+mt
source-wordcount: '2363'
ht-degree: 0%

---


# Vanliga frågor {#faq-journeys}

Nedan finns Frågor och svar om Adobe Journey Optimizer Journeys.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

## Allmänna begrepp

+++ Vad är en resa i Adobe Journey Optimizer?

En resa är en flerstegssamordning som gör att ni kan designa och köra kundupplevelser i realtid i flera kanaler. Journeys kombinerar händelser, samordnade aktiviteter, åtgärder och meddelanden för att skapa personaliserade, sammanhangsbaserade upplevelser baserade på kundbeteende och affärshändelser.

Läs mer om [resor](journey.md).

+++

+++ Vilka typer av resor finns det?

Adobe Journey Optimizer stöder tre typer av resor:

* **Unitära resor**: Utlöses individuellt av en händelse (t.ex. ett köp, appinloggning). Profilerna kommer in på resan en i taget när händelsen inträffar.
* **Läs målgruppsresor**: Börja med en målgrupp från Adobe Experience Platform och skicka meddelanden gruppvis till alla profiler i den målgruppen.
* **Affärshändelseresor**: Utlöses av affärshändelser (t.ex. börsuppdateringar, vädervarningar) som påverkar flera profiler samtidigt.

Läs mer om [resetyper](entry-management.md#types-of-journeys).

+++

+++ Vad är skillnaden mellan en resa och en kampanj?

**Resor** är flerstegsorkestrationer som reagerar på händelser eller målgrupper, vilket möjliggör komplex logik, villkor, väntetider och flera kontaktpunkter under kundens livscykel.

**Kampanjer** är engångskommunikation eller återkommande kommunikation som skickas till en viss målgrupp, vilket är idealiskt för fristående meddelanden som kampanjmeddelanden eller nyhetsbrev.

**Bästa praxis**: Använd resor för pågående flerstegsengagemang och kampanjer för riktad, fristående kommunikation.

+++

+++ Vilka är huvudkomponenterna i en resa?

En resa består av

* **Händelser**: Startpunkter som utlöser resan (t.ex. profilkvalificering, affärshändelser)
* **Orchestration-aktiviteter**: Logikkomponenter som villkor, väntan, läsning, målgrupp och slut
* **Åtgärder**: Aktiviteter som utför uppgifter, till exempel att skicka meddelanden, uppdatera profiler eller anropa externa API:er
* **Inbyggda kanalåtgärder**: Inbyggda meddelandefunktioner för e-post, SMS, push och andra kanaler
* **Anpassade åtgärder**: Integrering med tredjepartssystem

Läs mer om [reseaktiviteter](about-journey-activities.md).

+++

## Byggnadsresor

+++ Hur börjar jag bygga min första resa?

Följ de här stegen:

1. **Konfigurera nödvändiga komponenter**: Konfigurera händelser, datakällor och åtgärder efter behov
2. **Skapa resan**: Navigera till menyn Resor och klicka på Skapa resa.
3. **Definiera reseegenskaper**: Ange resenamn, beskrivning, namnutrymme och andra inställningar
4. **Utforma resan**: Dra och släpp aktiviteter från paletten på arbetsytan
5. **Testa resan**: Använd testläge för att validera din reselogik
6. **Publicera resan**: Aktivera resan för att göra den offentlig

Följ [steg för steg-guiden](journey-gs.md).

+++

+++ Vilka förutsättningar krävs innan en resa byggs?

Förutsättningar beror på din resetyp:

* **Händelseutlösta resor**: Konfigurera händelser för att definiera när profiler ska gå in på resan
* **Målgruppsbaserade resor**: Skapa målgrupper i Adobe Experience Platform
* **Dataanrikning**: Konfigurera datakällor för att hämta ytterligare information
* **Tredjepartsintegreringar**: Konfigurera anpassade åtgärder om externa system används

Läs mer om [resekonfigurationen](../configuration/about-data-sources-events-actions.md).

+++

+++ Kan jag använda data från externa system under min resa?

Ja. Du kan konfigurera **externa datakällor** för att hämta information från API-tjänster från tredje part och använda den i dina resevillkor, din personalisering eller dina åtgärder. På så sätt kan ni berika kundupplevelsen med realtidsdata från era CRM, lojalitetssystem, vädertjänster eller andra externa plattformar.

Läs mer om [externa datakällor](../datasource/external-data-sources.md).

+++

+++ Hur lägger jag till villkor till min resa?

Du kan lägga till villkor med **Villkorsaktiviteten** från orkestreringspaletten. Villkoren gör att du kan:

* Skapa enkla eller avancerade villkor med uttrycksredigeraren
* Dela upp resan på flera olika vägar baserat på profilattribut, målgruppsmedlemskap, event eller sammanhangsberoende data
* Definiera timeout-sökvägar för profiler som inte uppfyller villkoret inom en angiven tid

Läs mer om [villkoren](condition-activity.md).

+++

+++ Kan jag skicka meddelanden till profiler under en resa?

Ja. Journey Optimizer innehåller **inbyggda kanalåtgärder** som gör att du kan skicka meddelanden via e-post, push-meddelanden, SMS/MMS/RCS, meddelanden i appen, webbupplevelser, kodbaserade upplevelser, direktreklam, innehållskort, WhatsApp och LINE. Du kan designa meddelandeinnehåll direkt i Journey Optimizer och lägga till dem som åtgärdsaktiviteter under din resa.

Läs mer om [meddelanden på resor](journeys-message.md).

+++

+++ Hur väntar jag på en viss tid eller händelse under en resa?

Använd aktiviteten **Vänta** om du vill pausa resan under en angiven tid eller tills ett visst datum/tid. Vänteaktiviteter är användbara för:

* Skicka uppföljningsmeddelanden efter en fördröjning (t.ex. 3 dagar efter köpet)
* Väntar på kontorstid innan åtgärd utförs
* Skapa droppkampanjer med tidsbestämda intervall
* Kombinera med villkor för att skapa timeoutscenarier

Läs mer om [vänteaktiviteter](wait-activity.md).

+++

+++ Kan jag uppdatera profilinformation under en resa?

Ja. Använd aktiviteten **Uppdatera profil** för att ändra profilattribut i Adobe Experience Platform baserat på resehändelser eller villkor. Det här är användbart när du vill uppdatera kundlojalitetspunkter, registrera milstolpar för kundresan, ändra inställningar eller spåra kundinteraktionspoäng.

Läs mer om [profiluppdateringar](update-profiles.md).

+++

## Testning och publicering

+++ Hur testar jag min resa innan jag publicerar den?

Journey Optimizer erbjuder två teststrategier:

* **Testläge**: Simulera enskilda profiler som rör sig genom resan steg för steg, så att du kan verifiera logik, villkor och åtgärder innan du publicerar.
* **Torr körning**: Utför din resa med verkliga produktionsdata utan att kontakta faktiska kunder eller uppdatera profilinformationen. Detta ger er förtroende för målgruppsanpassning och resedesign.

**Bästa praxis**: Testa alltid resor före publicering för att kontrollera att de fungerar som förväntat och för att identifiera eventuella problem tidigt.

Läs mer om [testläge](testing-the-journey.md) och [torr körning](journey-dry-run.md).

+++

+++ Vad händer när jag publicerar en resa?

När du publicerar en resa:

* Resan blir **aktiv** och klar att acceptera nya profiler
* Profiler kan anges baserat på tävlingskriterier (händelse eller målgrupp)
* Meddelanden och åtgärder börjar köras för profiler som rör sig genom resan
* Du kan inte redigera en publicerad resa direkt (du måste skapa en ny version)

Läs mer om [publiceringsresor](publishing-the-journey.md).

+++

+++ Kan jag ändra en resa som redan är publicerad?

Du kan inte redigera en direktresa direkt. Så här gör du ändringar:

1. **Skapa en ny version**: Duplicera den publicerade resan och skapa ett utkast till version
2. **Gör dina ändringar**: Redigera utkastet efter behov
3. **Testa den nya versionen**: Använd testläget för att validera ändringar
4. **Publicera den nya versionen**: Den tidigare versionen stängs automatiskt och den nya aktiveras

Profiler som redan är under färd kommer att slutföra den ursprungliga versionen, medan nya profiler kommer att gå in i den nya versionen.

Läs mer om [reseversioner](journey-ui.md#journey-versions).

+++

+++ Hur stoppar jag en resa?

Du kan hantera körning av resan på flera sätt:

* **Nära nya ingångar**: Stoppa nya profiler från att komma in samtidigt som befintliga profiler tillåts slutföra sin resa
* **Stoppa omedelbart**: Avsluta resan och avsluta alla profiler i den
* **Paus**: Stoppa resan tillfälligt och återuppta den senare (tillgängligt för särskilda resetyper)

Läs mer om [slutresor](end-journey.md).

+++

## Körning och övervakning av resor

+++ Hur kan jag spåra profilstatus under en resa?

Du kan övervaka körningen av resan med:

* **ReseLive-rapport**: Visa realtidsstatistik och nyckeltal för din resa
* **Resa, heltidsrapport**: Analysera reseprestanda med Customer Journey Analytics
* **Resestegshändelser**: Få åtkomst till detaljerade körningsdata för anpassad rapportering
* **Kör kontrollpanel för körning av körningsfärd**: Granska testkörningsresultat innan du aktiverar

Läs mer om [reserapportering](report-journey.md).

+++

+++ Varför gick ingen profil in på min resa?

Vanliga orsaker till varför profiler inte får resa:

* **Händelsen togs inte emot**: Utlösarhändelsen skickades inte eller konfigurerades inte korrekt
* **Målgruppskriterierna uppfylls inte**: Profilen uppfyller inte kraven för målgruppen
* **Regler för återinträde**: Profilen har nyligen slutfört resan och återinträde blockeras
* **Resan har inte publicerats**: Resan har statusen Utkast
* **Ogiltigt namnområde**: Resursens namnområde matchar inte profilens identitet
* **Resan stängd**: Resan tar inte längre emot nya ingångar

Läs mer om [hantering av inträde](entry-management.md).

+++

+++ Vad är resestegshändelser och hur kan jag använda dem?

Resestegshändelser genereras automatiskt datauppsättningar som samlar in detaljerad information om varje steg en profil tar på en resa. De omfattar in- och utträdeshändelser, åtgärdskörning (skickade meddelanden, anpassade åtgärder anropade), reseövergångar (mellan aktiviteter) samt fel och tidsgränser.

**Användningsexempel**:

* Skapa anpassade rapporter i Customer Journey Analytics- eller BI-verktyg
* Felsöka problem med körning av resan
* Spåra detaljerat profilbeteende
* Skapa avancerade analyser och attribueringsmodeller

Läs mer om [steg för kundresan](../reports/sharing-overview.md).

+++

+++ Hur kan jag felsöka en resa som inte fungerar som väntat?

Journey Optimizer tillhandahåller flera felsökningsresurser:

* **Felindikatorer**: Visuella aviseringar på arbetsytan visar konfigurationsproblem
* **Testläge**: Gå igenom resan för att identifiera var det finns problem
* **Resursrapporter**: Granska körningsmått för att hitta flaskhalsar eller fel
* **Resestegshändelser**: Analysera detaljerade körningsdata för att förstå profilbeteende

**Vanliga problem**:

* Felaktigt konfigurerade händelser eller målgrupper
* Datakällanslutningar saknas
* Ogiltiga uttryck i villkor eller personalisering
* Timeoutinställningar som är för korta

Läs mer om [felsökning av resor](troubleshooting.md).

+++

+++ Vad händer om en åtgärd misslyckas under en resa?

När en åtgärd misslyckas (t.ex. timeout för API-anrop, meddelandeleveransfel) fortsätter resan som standard om inte något annat konfigureras. Du kan definiera villkorsaktiviteter för att hantera felscenarier, och fel loggas i reserapporter och steghändelser för övervakning.

**Bästa praxis**: Ange lämpliga timeoutvärden för externa åtgärder och definiera alternativa sökvägar för kritiska felscenarier.

Läs mer om [åtgärdssvar](../action/action-response.md).

+++

## Avancerade begrepp

+++ Vad är ett resenamnområde och varför spelar det någon roll?

Ett **namnområde** är en identitetstyp (t.ex. e-post, ECID, telefonnummer) som avgör hur profiler identifieras under resan. Namnutrymmet definierar vilken identifierare som används för att matcha profiler, måste vara konsekvent för händelser, målgrupper och profildata och påverka hur resan registreras och återupptas.

**Bästa praxis**: Välj ett namnutrymme som identifierar dina kunder på ett tillförlitligt sätt över alla beröringspunkter.

Läs mer om [identitetsnamnutrymmen](../audience/get-started-identity.md).

+++

+++ Kan profiler ta sig in på samma resa flera gånger?

Ja, beroende på inställningarna för **återinträde**:

* **Tillåt återinträde**: Profiler kan gå in på resan flera gånger efter att de har slutförts
* **Vänteperiod för återinträde**: Definiera en minimitid mellan reseposter (t.ex. 7 dagar)
* **Tvinga återinträde för händelse**: Utlös en ny reseinstans även om profilen redan finns under resan

**Bästa praxis**: Använd regler för återinträde för att förhindra att meddelandet tröttnar och för att säkerställa rätt paketering.

Läs mer om [hantering av inträde](entry-management.md).

+++

+++ Vad är optimering vid sändning?

**Sändningsoptimering (STO)** använder AI för att förutsäga den bästa tidpunkten för att skicka ett meddelande till varje enskild profil, vilket maximerar öppningsfrekvenser och engagemang. STO analyserar historiska engagemangsmönster för att avgöra när varje mottagare troligast interagerar med ert budskap.

**Fördelar**:

* Förbättrade öppnings- och klickfrekvenser
* Bättre kundupplevelse med optimalt tidsinställda meddelanden
* Minskade avbeställningsavgifter

Läs mer om [optimering vid sändning](send-time-optimization.md).

+++

+++ Vad är regler för resefackning?

Med **resefackning** kan du begränsa hur många gånger en profil kan ta sig in på resor inom en angiven tidsperiod, vilket förhindrar att meddelandet tröttnar och ger en optimal kundupplevelse. Du kan ange högsta antal poster per profil för olika resor eller specifika resor, definiera tidsfönster (varje dag, varje vecka, varje månad) och prioritera resor när flera resor konkurrerar om samma profil.

Läs mer om [resefackning](../conflict-prioritization/journey-capping.md).

+++

+++ Kan jag integrera min resa med externa system?

Ja. Använd **anpassade åtgärder** för att anropa API:er från tredje part (CRM, automatiserad marknadsföring, lojalitetssystem), skicka data till externa system, hämta realtidsinformation för beslut och aktivera arbetsflöden på externa plattformar.

Anpassade åtgärder stöder autentisering (API-nyckel, OAuth 2.0), anpassning av nyttolast för begäran/svar, felhantering och timeout samt dynamiska parametrar från kundresans kontext.

Läs mer om [anpassade åtgärder](using-custom-actions.md).

+++

+++ Hur kan jag använda Adobe Campaign på resor?

Journey Optimizer kan integreras med Adobe Campaign för att utnyttja sina avancerade funktioner:

* **Adobe Campaign Standard**: Använd Campaign Standard-åtgärder för att skicka transaktionsmeddelanden
* **Adobe Campaign v7/v8**: Utlös kampanjarbetsflöden och använd Campaigns leveransinfrastruktur

**Bästa praxis**: Använd den här integreringen om du har befintliga Campaign-mallar, datamodeller eller om du behöver Campaign-specifika funktioner.

Läs mer om [Campaign-integrering](ajo-ac.md).

+++

+++ Vad är hoppaktiviteten?

Med **hoppaktiviteten** kan du övergå profiler från en resa till en annan, vilket möjliggör återanvändbara resemönster, resesamordning över flera resor, förenklat reseunderhåll och strategier för progressivt engagemang.

När en profil når en hoppaktivitet avslutar de den aktuella resan och går in på målresan vid startpunkten.

Läs mer om [hoppaktiviteten](jump.md).

+++

## God praxis och begränsningar

+++ Vilka är de viktigaste begränsningarna jag bör vara medveten om?

Viktiga skyddsräcken är:

* **Resans komplexitet**: Maximalt antal aktiviteter, sökvägar och kapslingsnivåer
* **Genomströmning**: Meddelandeöverföringshastigheter och API-anropsbegränsningar
* **Tid för live**: Maximal restid (t.ex. 91 dagar för heltidsresor)
* **Målgruppsstorlek**: Begränsningar för läsmålgruppsstorlekar
* **Uttryckskomplexitet**: Teckenbegränsningar i villkor och personalisering

Visa fullständiga [skyddsutkast och begränsningar](../start/guardrails.md).

+++

+++ Vilka är de bästa sätten att designa resor?

**Struktur och organisation**:

* Håll resorna fokuserade på särskilda användningsfall
* Använd beskrivande namn för aktiviteter
* Lägg till anteckningar och etiketter för komplex logik
* Gruppera relaterade resor med taggar

**Prestanda**:

* Optimera väntetiderna för att balansera engagemang och volym
* Begränsa externa API-anrop till viktiga användningsfall
* Använd regler för att förhindra att meddelanden tröttnar
* Övervaka resemätningar regelbundet

**Testar**:

* Testa alltid resor före publicering
* Testa alla villkorsstyrda sökvägar och scenarier
* Använd realistiska testprofiler
* Validera personalisering och dynamiskt innehåll

**Underhåll**:

* Regelbundet granska reseresultaten
* Arkivera eller stäng oanvända resor
* Dokumentreselogik och affärsregler
* Planera för reseversionshantering

Läs mer om [de bästa sätten att utforma resor](using-the-journey-designer.md).

+++

+++ Hur många aktiviteter kan jag lägga till på en resa?

Även om det inte finns någon strikt begränsning av antalet aktiviteter kan mycket komplexa resor (fler än 50 aktiviteter) bli svåra att underhålla och felsöka. Stora resor med många filialer och förhållanden kan påverka bearbetningstiden och läsbarheten.

**Bästa praxis**: Om din resa blir alltför komplex kan du dela in den i flera resor med hjälp av hoppaktiviteten, skapa återanvändbara delresor eller förenkla logiken med mer effektiva villkor.

Läs mer om [resedesign](using-the-journey-designer.md).

+++

+++ Hur kan jag säkerställa att min resa fungerar bra i stor skala?

**Designöverväganden**:

* Använd målgruppsbaserad post för gruppkommunikation i stället för enskilda händelser
* Implementera lämpliga väntetider för att sprida meddelandevolymen
* Utnyttja regler för capping för att förhindra systemöverbelastning
* Optimera villkorslogiken för att minska komplexiteten i behandlingen

**Övervakning**:

* Spåra resemätningar regelbundet
* Övervaka API-prestanda för anpassade åtgärder
* Granska felfrekvenser och timeout-förekomster
* Ställ in aviseringar för allvarliga fel i resan

**Optimering**:

* Använd testläge och torr körning för att validera prestanda före publicering
* Begränsa externa datakällanrop till viktiga scenarier
* Cachelagra data som ofta används när det är möjligt
* Granska och optimera meddelandeleveransen

Läs mer om [optimering av resan](../start/guardrails.md).

+++

## Ytterligare resurser

Utforska följande resurser om du vill ha mer information och uppdateringar:

* [Kom igång med resor](journey.md)
* [Skapa den första resan](journey-gs.md)
* [Felsökningsguider](troubleshooting.md)
* [Användningsexempel på resa](jo-use-cases.md)
* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}
