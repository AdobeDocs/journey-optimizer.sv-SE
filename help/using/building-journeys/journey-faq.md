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
source-git-commit: 74723337f97c8196b506ccc1ace11077710494ea
workflow-type: tm+mt
source-wordcount: '5125'
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

Adobe Journey Optimizer stöder fyra typer av resor:

* **Unitära resor**: Utlöses individuellt av en händelse (t.ex. ett köp, appinloggning). Profilerna kommer in på resan en i taget när händelsen inträffar.
* **Läs målgruppsresor**: Börja med en målgrupp från Adobe Experience Platform och skicka meddelanden gruppvis till alla profiler i den målgruppen.
* **Målgruppskvalificeringsresor**: Utlöses när profiler kvalificerar sig för (eller avslutar) ett visst målgruppssegment. Profilerna går in på resan när de uppfyller målgruppskriterierna.
* **Affärshändelseresor**: Utlöses av affärshändelser (t.ex. börsuppdateringar, vädervarningar) som påverkar flera profiler samtidigt.

Läs mer om [resetyper](entry-management.md#types-of-journeys).

+++

+++ Vad är skillnaden mellan en resa och en kampanj?

**[Resor](journey.md)** är flerstegsorkestrationer som reagerar på händelser eller målgrupper, vilket möjliggör komplex logik, villkor, väntetider och flera kontaktpunkter under kundens livscykel.

**[Kampanjer](../campaigns/get-started-with-campaigns.md)** finns i tre typer:

* **[Åtgärdskampanjer](../campaigns/create-campaign.md)**: Engångs- eller återkommande kommunikation som skickas till en viss målgrupp är idealisk för fristående meddelanden som reklamutskick eller nyhetsbrev.
* **[API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)**: Kampanjer utlöses via API-anrop, vilket gör att integrering med externa system kan skicka meddelanden baserat på realtidshändelser eller affärslogik.
* **[Samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)**: Flerstegs målgruppsbaserade kampanjer som bygger på en arbetsyta och som kan innehålla villkor, väntetider och flera åtgärder för att skapa schemalagda, samordnade upplevelser.

**Bästa praxis**: Använd [resor](journey.md) för komplext, händelseutlöst engagemang med avancerad samordning, [åtgärdskampanjer](../campaigns/create-campaign.md) för schemalagd, målgruppsbaserad kommunikation, [API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md) för programmatisk utlösande från externa system och [samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md) för kommunikation i flera steg med kampanjspecifika krav.

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

+++ Vilka typer av målgrupper stöds vid resor och vilka begränsningar har de?

Adobe Journey Optimizer har stöd för fyra typer av målgrupper med olika egenskaper och skyddsräcken:

**1. Direktuppspelande målgrupper**

* **Beskrivning**: Målgrupper som utvärderas i realtid när profildata ändras
* **Utvärdering**: Kontinuerlig utvärdering när profilattribut eller händelser matchar segmentkriterier
* **Reseanvändning**: Stöds i aktiviteterna Läs målgrupp, Målgruppskvalifikation och Villkor
* **Bäst för**: Interaktion i realtid baserat på beteendeförändringar eller profiluppdateringar
* **Guardrails**:
   * Största antal användare beror på din Journey Optimizer-licens
   * Utvärderingsfördröjning normalt under 5 minuter
   * Komplex segmentlogik kan påverka utvärderingen

**2. Gruppera målgrupper**

* **Beskrivning**: Publiker som utvärderas på schemalagd basis (vanligtvis dagligen)
* **Utvärdering**: Bearbetad i batchjobb med schemalagda intervall
* **Reseanvändning**: Stöds i Läs målgrupps- och villkorsaktiviteter; begränsat stöd i målgruppskompetensresor
* **Bäst för**: Regelbundna kampanjer, nyhetsbrev, schemalagd kommunikation
* **Guardrails**:
   * Utvärderingen sker en gång om dagen (standard) eller enligt konfigurerat schema
   * Profiler kanske inte återspeglar realtidsändringar förrän nästa utvärdering
   * Läsa målgrupper kan bearbeta stora grupper effektivt

**3. Överför målgrupper (anpassad överföring)**

* **Beskrivning**: Målgrupper som skapats genom att CSV-filer har överförts med profilidentifierare
* **Utvärdering**: Statisk lista uppdateras bara när nya filer överförs
* **Reseanvändning**: Stöds i Läs målgrupps- och villkorsaktiviteter; **stöds inte** i målgruppskvalificeringsresor
* **Bäst för**: Engångskampanjer, extern listimport, riktad kommunikation
* **Guardrails**:
   * Storleksbegränsningar för CSV-filer gäller (se produktdokumentationen för aktuella begränsningar)
   * Målgruppsmedlemmarna är statiska tills de uppdateras med ny överföring
   * Identitetsnamnrymden måste matcha resenamnrymden
   * Profilerna måste finnas i Adobe Experience Platform

**4. Vanliga målgrupper (Federated Audience Composition)**

* **Beskrivning**: Målgrupper som skapats med federerade data, så att du kan fråga efter och sätta samman målgrupper från externa datalager utan att kopiera data till Adobe Experience Platform
* **Utvärdering**: Statisk disposition uppdateras när den federerade målgruppskompositionen körs
* **Reseanvändning**: Stöds i Läs målgrupps- och villkorsaktiviteter; **stöds inte** i målgruppskvalificeringsresor (liknar överföring av målgrupper från ett backend-perspektiv)
* **Bäst för**: Integrering av datalager i företag, målgruppskomposition med externa datakällor, scenarier där data måste finnas kvar i externa system
* **Guardrails**:
   * Målgruppsmedlemmarna är statiska tills nästa externa kompositionskörning
   * Identitetsnamnrymden måste matcha resenamnrymden
   * Prestanda beror på externa frågefunktioner för datalager
   * Kräver tillägg för federerad målgruppskomposition

**Customer Journey Analytics (CJA) målgrupper**:

CJA-målgrupper stöds inte direkt på resor, men du kan använda en **tillfällig lösning** genom att&quot;paketera&quot; en CJA-målgrupp i en segmenteringsregel. Detta skapar en batch-UPS-målgrupp (Unified Profile Service) som refererar till CJA-målgruppen och gör den tillgänglig för användning i resor som en batchmålgrupp.

**Resespecifika överväganden**:

* **Läs målgruppsresor**: Alla fyra målgruppstyper stöds; batchexport sker när resan körs
* **Målgruppskvalificeringsresor**: Direktuppspelande målgrupper rekommenderas; batchmålgrupper har fördröjd kvalificeringsidentifiering; uppladdning och FAC-målgrupper stöds inte
* **Villkorsaktiviteter**: Alla målgruppstyper kan användas för att kontrollera medlemskap
* **Namnområdesjustering**: Namnområdet för målets identitet måste matcha kundens namnutrymme för korrekt profilidentifiering

**God praxis**:

* Använd **direktuppspelade målgrupper** för händelsestyrda resor i realtid som kräver omedelbar respons
* Använd **gruppmålgrupper** för schemalagd kommunikation där daglig utvärdering är tillräckligt
* Använd **överför målgrupper** för riktade engångskampanjer med externa listor
* Använd **FAC-målgrupper** när du behöver utnyttja Enterprise-datalagerfunktioner utan datataperering
* Övervaka målgruppens storlek och utvärderingsprestanda i storskaliga installationer
* Fundera på uppdateringsfrekvensen när ni utformar restider och villkor

Läs mer om [målgrupper](../audience/about-audiences.md), [skapa segment](../audience/creating-a-segment-definition.md), [anpassade uppladdningsgrupper](../audience/custom-upload.md) och [Federated målgruppskomposition](../audience/federated-audience-composition.md).

+++

+++ Hur väljer jag mellan en enhetlig resa och en läsande målgruppsresa?

Använd **enhetsresor** när:

* Ni måste reagera på enskilda kundåtgärder i realtid (t.ex. inköpsbekräftelse, övergivna kundvagnar)
* Varje kund bör utvecklas i sin egen takt
* Du vill aktivera baserat på specifika händelser

Använd **läs målgruppsresor** när:

* Du skickar batchkommunikation till en grupp (t.ex. månatliga nyhetsbrev, kampanjkampanjer)
* Alla kunder bör få meddelandet samtidigt
* Ni riktar in er på ett fördefinierat målgruppssegment

+++

## Byggnadsresor

+++ Hur börjar jag bygga min första resa?

Följ de här stegen:

1. **Konfigurera nödvändiga komponenter**: Konfigurera händelser, datakällor och åtgärder efter behov
2. **Skapa resan**: Navigera till menyn Resor och klicka på Skapa resa.
3. **Definiera reseegenskaper**: Ange resenamn, beskrivning och andra inställningar
4. **Utforma resan**: Dra och släpp aktiviteter från paletten på arbetsytan
5. **Testa resan**: Använd testläge för att validera din reselogik
6. **Torr körning av resan**: Använd Torr körning för att testa resan med hjälp av verkliga produktionsdata utan att kontakta riktiga kunder eller uppdatera profilinformationen
7. **Publicera resan**: Aktivera resan för att göra den offentlig

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

Ja, det finns flera sätt att utnyttja externa data:

**God praxis**:

* **Anpassade åtgärder**: Anropa externa API:er via anpassade åtgärder för att hämta eller skicka data till tredjepartssystem. Detta är det rekommenderade tillvägagångssättet för realtidsinteraktion med externa system.
* **Datauppsättningssökning**: Om du kan läsa in data från externa system till Adobe Experience Platform använder du sökfunktionen för datauppsättningar för att hämta information som lagras i Experience Platform datauppsättningar.
* **Externa datakällor**: Konfigurera externa datakällor för att hämta information från API-tjänster från tredje part (mindre rekommenderas än ovanstående metoder).

Med dessa alternativ kan ni berika kundupplevelsen med data från era CRM, lojalitetssystem, vädertjänster eller andra externa plattformar.

Läs mer om [anpassade åtgärder](using-custom-actions.md) och [datasuppslagning](dataset-lookup.md).

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

För kanaler som inte stöds internt kan du använda **anpassade åtgärder** för att integrera med externa meddelandeplattformar och skicka meddelanden via valfri tredjepartskanal.

Läs mer om [meddelanden under resor](journeys-message.md) och [anpassade åtgärder](using-custom-actions.md).

+++

+++ Hur väntar jag på en viss tid eller händelse under en resa?

Använd aktiviteten **Vänta** om du vill pausa resan under en angiven tid eller tills ett visst datum/tid. Vänteaktiviteter är användbara för:

* Skicka uppföljningsmeddelanden efter en fördröjning (t.ex. 3 dagar efter köpet)
* Skapa droppkampanjer med tidsbestämda intervall
* Kombinera med villkor för att skapa timeoutscenarier

Läs mer om [vänteaktiviteter](wait-activity.md).

+++

+++ Kan jag uppdatera profilinformation under en resa?

Ja. Använd aktiviteten **Uppdatera profil** för att ändra profilattribut i Adobe Experience Platform baserat på resehändelser eller villkor. Det här är användbart när du vill uppdatera kundlojalitetspunkter, registrera milstolpar för kundresan, ändra inställningar eller spåra kundinteraktionspoäng.

Läs mer om [profiluppdateringar](update-profiles.md).

+++

+++ Hur skickar jag ett e-postmeddelande direkt efter att någon har gjort ett köp?

Skapa en **unitär händelseutlöst resa**:

1. Konfigurera en Inköpshändelse med orderinformationen
2. Lägg till händelsen som startpunkt för resan
3. Följa direkt med en e-poståtgärd
4. Designa ett e-postmeddelande med orderbekräftelse med personlig orderinformation
5. Publicera resan

Resan utlöses automatiskt när en köphändelse tas emot och bekräftelsemeddelandet skickas i realtid.

Läs mer om [händelsekonfiguration](../event/about-events.md) och [e-poståtgärder](journeys-message.md).

+++

+++ Kan jag skicka om ett meddelande om någon inte öppnar eller klickar på det?

Ja. Använd en **reaktionshändelse** med en **Timeout**:

1. När du har skickat meddelandet lägger du till en Reaction-händelse som lyssnar efter e-postöppningar eller klick
2. Konfigurera en timeout-period (t.ex. 3 dagar) för Reaction-händelsen
3. Skapa två banor:
   * **Om du har öppnat/klickat**: Fortsätt med nästa steg eller avsluta resan
   * **Timeout-sökväg (ej öppnad/klickad)**: Skicka ett påminnelsemeddelande med en annan ämnesrad

**Bästa tillvägagångssätt**: Begränsa antalet omgångar så att inte skräppost visas (vanligtvis 1-2 påminnelser maximalt).

Läs mer om [reaktionshändelser](reaction-events.md).

+++

+++ Hur skapar jag en kundvagnsöverlämningsresa?

Skapa en händelseutlöst resa med en Reaction-händelse med en Timeout:

1. **Konfigurera en händelse om att kundvagnen överges**: Utlöses när objekt läggs till men utcheckningen inte slutförs inom en tidsram
2. **Lägg till en Reaction-händelse**: Konfigurera den för att lyssna efter en Purchase-händelse
3. **Ange en timeout-period**: Definiera en timeout (t.ex. 1-2 timmar) för Reaction-händelsen för att ge kunden tid att slutföra naturligt
4. **Skapa två banor**:
   * **Om en köphändelse inträffar**: Avsluta resan eller fortsätt med flödet efter köpet
   * **Timeout-sökväg (inget köp)**: Skicka en påminnelse om att kunden avbryter prenumerationen via e-post med kundvagnsinnehåll
5. **Valfritt**: Lägg till ytterligare en Reaction-händelse med timeout (24 timmar) och skicka en andra påminnelse med ett incitament (till exempel 10 % rabatt)

Läs mer om [resans användningsfall](jo-use-cases.md) och [reaktionshändelser](reaction-events.md).

+++

+++ Hur delar jag upp kunderna på olika vägar baserat på deras inköpshistorik?

Använd en **villkorsaktivitet** med målgruppsmedlemskap eller profilattribut:

1. Lägg till en villkorsaktivitet på din resa
2. Skapa flera sökvägar baserat på villkor:
   * **Sökväg 1**: Kunder med högt värde (totalt antal köp > $1000)
   * **Sökväg 2**: Vanliga kunder (totalt 100-1 000 USD)
   * **Sökväg 3**: Nya kunder (totalt antal köp &lt; $100)
3. Lägg till olika meddelanden eller erbjudanden för varje sökväg

Läs mer om [villkor](condition-activity.md) och [målgruppskvalifikation](audience-qualification-events.md).

+++

+++ Hur hanterar jag olika tidszoner under min resa?

Journey Optimizer erbjuder flera alternativ för hantering av tidszoner:

* **Profilens tidszon**: Meddelanden skickas baserat på varje persons tidszon som lagras i deras profil
* **Fast tidszon**: Alla meddelanden använder en specifik tidszon som du definierar

Läs mer om [hantering av tidszoner](timezone-management.md).

+++

+++ Hur länge ska jag vänta mellan budskapen under min resa?

**Bästa sättet att vänta**:

* **Transaktionsmeddelanden** (orderbekräftelser): Skicka omedelbart
* **Välkomstserie**: 1-3 dagar mellan e-postmeddelanden
* **Utbildningsinnehåll**: 3-7 dagar mellan meddelanden
* **Kampanjkampanjer**: Minst 7 dagar mellan erbjudandena
* **Återanvändning**: 14-30 dagar för inaktiva användare

**Faktorer att tänka på**:

* Branschstandarder och kundernas förväntningar
* Snabbhet och betydelse
* Den övergripande meddelandefrekvensen i alla kanaler
* Mönster för kundengagemang

**Tips**: Använd regler för begränsning av antalet meddelanden som en kund får på alla resor.

Läs mer om [vänteaktiviteter](wait-activity.md) och [resefackning](../conflict-prioritization/journey-capping.md).

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

* Resan blir **Live** och klar att acceptera nya profiler
* Profiler kan anges baserat på tävlingskriterier (händelse eller målgrupp)
* Meddelanden och åtgärder börjar köras för profiler som rör sig genom resan
* Du kan bara redigera begränsade saker på en publicerad resa (du måste skapa en ny version om du vill redigera fler)

Läs mer om [publiceringsresor](publish-journey.md).

+++

+++ Kan jag ändra en resa som redan är publicerad?

Ja, men med begränsningar. Du kan redigera vissa element i en Live-resa:

**Vad du kan redigera**:

* Reseegenskaper (namn, beskrivning)
* Meddelandeinnehåll i befintliga meddelandeaktiviteter
* Vissa reseinställningar

**Vad du inte kan redigera**:

* Resestruktur (tillägg/borttagning av aktiviteter)
* Anmälningsvillkor
* Journey Canvas-logik

**Så här gör du strukturella ändringar**:

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
* **Paus**: Stoppa resan tillfälligt och återuppta den senare

Läs mer om [slutresor](end-journey.md).

+++

+++ Vad är skillnaden mellan &quot;Närmaste nya ingångar&quot; och &quot;Stopp&quot;?

**Stäng till nya ingångar**:

* Nya profiler kan inte komma in på resan
* Profiler som redan är under resan fortsätter och slutför deras sökväg
* Använd det här när du på ett bra sätt vill minska en resa
* Exempel: Säsongskampanj som har avslutats men som du vill att befintliga kunder ska slutföra sin upplevelse

**Stopp**:

* Slutar omedelbart resan för alla profiler
* Alla profiler som för närvarande är på resan avslutas
* Använd detta för akuta situationer eller kritiska fel
* Exempel: Återkallande av produkter kräver omedelbart stopp av kampanjmeddelanden

Läs mer om [avslut på resor](end-journey.md) och [publiceringsresor](publish-journey.md).

+++

## Körning och övervakning av resor

+++ Hur kan jag spåra profilstatus under en resa?

Du kan övervaka körningen av resan med:

* **ReseLive-rapport**: Visa realtidsstatistik och nyckeltal för din resa. Du kan även granska testkörningens resultat här.
* **Resa, heltidsrapport**: Analysera reseprestanda med Customer Journey Analytics. Du kan även granska testkörningens resultat här.
* **Resestegshändelser**: Få åtkomst till detaljerade körningsdata för anpassad rapportering

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
* **Torr körningsläge**: Testa resan med verkliga produktionsdata utan att kontakta kunderna för att validera riktning och utförande
* **Resursrapporter**: Granska körningsmått för att hitta flaskhalsar eller fel
* **Resestegshändelser**: Analysera detaljerade körningsdata för att förstå profilbeteende

**Vanliga problem**:

* Felaktigt konfigurerade händelser eller målgrupper
* Datakällanslutningar saknas
* Ogiltiga uttryck i villkor eller personalisering
* Timeoutinställningar som är för korta

Läs mer om [felsökning av resor](troubleshooting.md).

+++

<!--
+++ What happens if an action fails in a journey?

When an action fails (e.g., API call timeout, message delivery error), the journey continues by default unless configured otherwise. You can define condition activities to handle failure scenarios, and errors are logged in journey reports and step events for monitoring.

**Best practice**: Set appropriate timeout values for external actions and define alternative paths for critical failure scenarios.

Learn more about [action responses](../action/action-response.md).

+++
-->

+++ Kan jag se vem som är på min resa just nu?

Ja. Använd **resedirektrapporten** för att visa:

* Antal profiler som för närvarande ingår i resan
* Antal profiler för varje aktivitet
* Profiler som har gått in de senaste 24 timmarna
* Mätvärden för körning i realtid

Om du vill visa enskilda profiler använder du **kundstegshändelser** i Customer Journey Analytics eller frågar händelsedatamängderna direkt.

Läs mer om [live-rapportering för resan](report-journey.md).

+++

+++ Varför skickas inte mina meddelanden under min resa?

**Vanliga orsaker och lösningar**:

* **Medgivandeproblem**: Mottagarna har inte anmält sig för att ta emot kommunikation
Lösning: Kontrollera godkännandeprinciper och anmälningsstatus

* **Undertryckandelista**: E-postadresser finns i listan över undertryckningar
Lösning: Granska suppressionslistan för studsar eller klagomål

* **Ogiltig kontaktinformation**: E-postadresser/telefonnummer saknas eller har fel format
Lösning: Validera profilens datakvalitet

* **Resan har inte publicerats**: Resan är fortfarande i utkastläge
Lösning: Publicera resan för att aktivera den

<!-- 
* **Message not approved**: Message content requires approval before sending
  Solution: Submit for approval or check approval status-->

* **Kanalkonfigurationsproblem**: E-post-/SMS-konfigurationen är felaktig
Lösning: Verifiera kanalkonfigurationer och autentisering

Läs mer om [felsökning](troubleshooting.md) och [hantering av samtycke](../action/consent.md).

+++

+++ Hur personaliserar jag meddelanden under min resa?

Du kan anpassa meddelanden med **anpassningsredigeraren**:

**Tillgängliga personaliseringsdata**:

* **Profilattribut**: Förnamn, efternamn, e-post, anpassade fält
* **Händelsedata**: Inköpsinformation, webbläsarbeteende, appaktivitet
* **Sammanhangsbaserade data**: Resevariabler, externa API-data
* **Målgruppsmedlemskap**: Segmentkvalifikationer
* **Beräknade attribut**: Förberäknade värden

**Exempel på personalisering**:

* &quot;Hej `{{profile.firstName}}`, tack för ditt köp av `{{event.productName}}`&quot;
* &quot;Baserat på din lojalitetsnivå (`{{profile.loyaltyTier}}`) finns det ett specialerbjudande&quot;
* Dynamiska innehållsblock som ändras utifrån kundernas önskemål

Läs mer om [personalisering](../personalization/personalize.md).

+++

+++ Kan jag skicka olika meddelanden baserat på vilken kanal jag föredrar?

Ja. Använd en **[villkorsaktivitet](condition-activity.md)** för att dirigera profiler baserat på deras önskade kanal:

1. Lägg till en [villkorsaktivitet](condition-activity.md) i din resa
2. Skapa en sökväg för varje kanal genom att kontrollera det önskade kanalprofilattributet (t.ex. `profile.preferredChannel`)
3. Konfigurera kanalspecifika sökvägar:
   * **E-postsökväg**: Lägg till en [e-poståtgärd](../email/create-email.md) med e-postoptimerat innehåll
   * **SMS-sökväg**: Lägg till en [SMS-åtgärd](../sms/create-sms.md) med kortfattade meddelanden
   * **Push-sökväg**: Lägg till en [push-meddelandeåtgärd](../push/create-push.md) med kort, åtgärdbart innehåll
   * **Sökväg i appen**: Lägg till en [åtgärd i appen](../in-app/create-in-app.md) för engagerade appanvändare
4. Lägg till en standardsökväg för profiler utan en inställning och dirigera dem till din primära kanal

**God praxis**:

* Se till att dina profildata innehåller korrekta kanalinställningar
* Utforma innehåll som passar varje kanals styrkor och begränsningar
* Använd [kanalytor](../configuration/channel-surfaces.md) för att hantera kanalkonfigurationer
* Testa alla sökvägar för att säkerställa korrekt meddelandeleverans

Läs mer om [villkor](condition-activity.md), [meddelandeåtgärder](journeys-message.md) och [kanalval](../channels/gs-channels.md).

+++

+++ Kan jag utesluta vissa kunder från min resa?

Ja, det finns flera sätt att utesluta kunder:

**Vid resepost**:

* Använd [målgruppsdefinitioner](../audience/creating-a-segment-definition.md) med undantagsregler
* Lägg till [anmälningsvillkor](entry-management.md) som filtrerar bort specifika profiler
* Konfigurera [profilattributbaserade avslutningskriterier](journey-properties.md) i resans egenskaper så att profiler automatiskt utesluts baserat på specifika attribut

**Inom resan**:

* Lägg till en [villkorsaktivitet](condition-activity.md) tidigt på resan för att avsluta oönskade profiler
* Kontrollera om det finns exkluderingsattribut (t.ex. VIP-status, testkonton)
* Använd [målgruppskvalifikation](audience-qualification-events.md) för att identifiera profiler som ska uteslutas

**Exempel på undantagsscenarier**:

* Exkludera kunder som nyligen köpt
* Uteslut VIP-kunder från standardkampanjer
* Exkludera medarbetare och testkonton
* Uteslut kunder i vissa regioner

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
* **Kompletterande identifierare**: Använd ett extra ID om du vill tillåta profiler att registrera om resan flera gånger för olika enheter (t.ex. olika order, bokningar eller transaktioner), även när de redan befinner sig på resan

**Bästa praxis**: Använd regler för återinträde för att förhindra att meddelandet tröttnar och för att säkerställa rätt paketering. Överväg att använda tilläggsidentifierare för transaktionsresor där profiler måste ange flera gånger för olika transaktioner.

Läs mer om [hantering av tävlingsbidrag](entry-management.md) och [ytterligare identifierare](supplemental-identifier.md).

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

Med **resefackning** kan du styra hur profiler interagerar med resorna, förhindra att meddelanden tröttnar och säkerställa en optimal kundupplevelse:

* **Ankomstbegränsning**: Begränsa antalet gånger en profil kan registrera resor inom en angiven tidsperiod
* **Samtidighetsbegränsning**: Begränsa antalet resor en profil kan finnas i samtidigt

Du kan ange högsta antal inmatningar eller samtidighet per profil för olika resor eller specifika resor, definiera tidsfönster (varje dag, varje vecka, varje månad) och prioritera resor när flera resor konkurrerar om samma profil.

Läs mer om [resefackning](../conflict-prioritization/journey-capping.md).

+++

+++ Kan jag integrera min resa med externa system?

Ja. Använd **anpassade åtgärder** för att anropa API:er från tredje part (CRM, automatiserad marknadsföring, lojalitetssystem), skicka data till externa system, hämta realtidsinformation för beslut och aktivera arbetsflöden på externa plattformar.

Anpassade åtgärder stöder autentisering (API-nyckel, anpassad autentisering), anpassning av begäran/svar-nyttolast, felhantering och timeout samt dynamiska parametrar från kundresans kontext.

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

+++ Hur skapar jag en välkomstserie?

En vanlig välkomstserie innehåller flera kontaktytor under flera dagar:

**Exempelstruktur**:

1. **Post**: Målgrupp för nya prenumeranter eller event när någon registrerar sig
2. **E-post 1 - omedelbar välkomstplats**: Tack och introduktion
3. **Vänta**: 2 dagar
4. **E-post 2 - Komma igång**: Självstudiekurs eller produktguide
5. **Vänta**: 3 dagar
6. **Villkor**: Har kunden gjort ett köp?
   * **Ja**: Slutför eller flytta till kundresan
   * **Nej**: Fortsätt välkomstserien
7. **E-post 3 - Incentive**: Särskild förstagångsköparrabatt
8. **Vänta**: 5 dagar
9. **E-post 4 - engagemang**: Bästa säljare eller populärt innehåll

**God praxis**:

* Håll den i 3-5 e-postmeddelanden under 2-3 veckor
* Varje e-postmeddelande ska ha ett tydligt syfte och call-to-action
* Övervaka öppningsfrekvenser och justera timing/innehåll därefter
* Avsluta kunderna tidigt om de konverterar eller engagerar sig djupt

Läs mer om [användningsfall för resan](jo-use-cases.md).

+++

+++ Kan jag testa olika vägar under min resa?

Ja. Använd aktiviteten **Optimera** (begränsad tillgänglighet) eller skapa testdelningar manuellt:

**Använda Optimera aktivitet** med metoden Experiment:

* Delar trafik slumpmässigt mellan olika banor för att avgöra vilken som fungerar bäst
* Testar olika meddelanden, erbjudanden, väntetider eller hela resvägar
* Mäter prestanda baserat på fördefinierade framgångsmått och deklarerar en vinnare

**Använda Optimera aktivitet** med villkorsmetoden för datakälla:

* Skapa ett villkor som delar profiler slumpmässigt (t.ex. med en slumpmässig talfunktion)
* Skicka olika upplevelser till varje delning
* Mät resultat med reserapporter

**Vad du kan testa**:

* Olika ämnesrader för e-post
* Alternativt meddelandeinnehåll
* Olika väntetider
* Olika erbjudanden eller incitament
* Helt olika resvägar

Läs mer om [optimera aktivitet](optimize.md) och [innehållsexperiment](../content-management/content-experiment.md).

+++

+++ Hur utlöser jag en resa när lagret är lågt?

Skapa en **affärshändelseresa**:

1. **Konfigurera en affärshändelse**: Konfigurera en händelse som utlöses av ditt lagersystem när lagret faller under ett tröskelvärde
2. **Välj målgrupp**: Välj profiler som ska aviseras (t.ex. kunder som har tittat på produkten, prenumeranter som ska ändra storlek på aviseringar)
3. **Lägg till meddelandeåtgärd**: Skicka e-post eller push-meddelanden
4. **Anpassa innehåll**: Inkludera produktinformation, aktuell lagernivå, snabbmeddelanden

**Exempel på händelser**:

* Varning för lågt lager
* Meddelande om prisfall
* Produkt tillbaka i lager
* Flash-försäljningsmeddelande
* Väderbaserade kampanjer

Läs mer om [affärshändelser](general-events.md).

+++

+++ Vad är sammanslagningspolicyer och hur påverkar de resorna?

**Sammanslagningsprinciper** avgör hur Adobe Experience Platform kombinerar data från flera källor för att skapa en enhetlig profilvy. De definierar regler för dataprioritet och identitetssammanfogning när det finns profilfragment i olika datauppsättningar.

**Påverkan på resor**:

* Resurserna använder den sammanslagningsprincip som är kopplad till målgruppen eller händelsen för att avgöra vilka profildata som är tillgängliga
   * På läs målgrupps- eller målgruppsklassificeringsresor: målgruppspolicyn används
   * Vid Unitary-händelseresor: standardprincipen för sammanslagning används
   * Vid affärsevenemangsresor: sammanfogningspolicyn från målgruppen i följande Läs målgruppsaktivitet används

* Sammanslagningspolicyn påverkar vilka attribut som är tillgängliga i resevillkor, personalisering och åtgärder
* Olika sammanfogningsprinciper kan leda till att olika profildata används under resan

**God praxis**:

* Se till att den sammanslagningsprincip som används av resan överensstämmer med era datastyrningskrav
* Förstå vilka datauppsättningar som ingår i sammanfogningsprincipen för att veta vilka data som är tillgängliga
* Använd konsekventa sammanslagningsprinciper för olika målgrupper och resor för förutsägbara resultat

Läs mer om [sammanfogningsprinciper](../audience/get-started-profiles.md) och [identitetshantering](../audience/get-started-identity.md).

+++

+++ Vad är skillnaden mellan ett villkor och en vänteaktivitet?

| | **Villkorsaktivitet** | **Vänta på aktivitet** |
|---|---|---|
| **Syfte** | Skapar olika banor baserat på logik (if/then) | Pausar resan under en tidsperiod |
| **Funktion** | Utvärderar data och ruttprofiler utifrån detta | Innehåller profiler vid en viss punkt innan du fortsätter |
| **Användningsfall** | Segmentera kunder, kontrollera status, gren baserat på beteende | Tidsinställning mellan meddelanden, väntan på kontorstid, skapa förseningar |
| **Exempel** | Om kunden är VIP skickar du Premium-erbjudande; annars skickar du standarderbjudande | Vänta 3 dagar efter välkomstmeddelandet innan du skickar nästa meddelande |

**De fungerar tillsammans**:

* Vänta en stund och använd sedan ett villkor för att kontrollera om något har hänt under väntetiden
* Exempel: Vänta 7 dagar och kontrollera sedan om kunden har köpt något

Läs mer om [villkor](condition-activity.md) och [vänteaktiviteter](wait-activity.md).

+++

## God praxis och begränsningar

+++ Vilka är de viktigaste begränsningarna jag bör vara medveten om?

Viktiga skyddsräcken är:

* **Resans komplexitet**: Maximalt antal aktiviteter, sökvägar och kapslingsnivåer
* **Genomströmning**: Meddelandeöverföringshastigheter och API-anropsbegränsningar
* **Tid till live**: Maximal restid (t.ex. 91 dagar)
* **Målgruppsstorlek**: Begränsningar för läsmålgruppsstorlekar
* **Uttryckskomplexitet**: Teckenbegränsningar i villkor och personalisering

Visa fullständiga [skyddsutkast och begränsningar](../start/guardrails.md).

+++

+++ Vilka är de bästa sätten att designa resor?

**Struktur och organisation**:

* Håll resorna fokuserade på särskilda användningsfall
* Använd beskrivande namn för aktiviteter
* Lägg till beskrivningar och etiketter för komplex logik
* Gruppera relaterade resor med taggar

**Prestanda**:

* Optimera väntetiderna för att balansera engagemang och volym
* Begränsa externa API-anrop till viktiga användningsfall
* Använd regler för att förhindra att meddelanden tröttnar
* Övervaka resemätningar regelbundet

**Testar**:

* Testa alltid resor före publicering
* Använd testläge för att validera reselogiken och gå igenom resan
* Använd torrt körningsläge för att testa med verkliga produktionsdata utan att kontakta kunderna
* Testa alla villkorsstyrda sökvägar och scenarier
* Använd realistiska testprofiler
* Validera personalisering och dynamiskt innehåll

**Underhåll**:

* Regelbundet granska reseresultaten
* Stoppa eller stänga oanvända resor
* Dokumentreselogik och affärsregler
* Planera för reseversionshantering

Läs mer om [de bästa sätten att utforma resor](using-the-journey-designer.md).

+++

+++ Hur många aktiviteter kan jag lägga till på en resa?

Resorna är begränsade till högst 50 aktiviteter. Vi rekommenderar dock att du förenklar dina resor för bättre underhåll och prestanda.

När resor närmar sig 50 aktiviteter kan de bli mycket komplexa och svåra att underhålla, felsöka och förstå. Stora resor med många kontor och villkor kan också påverka bearbetningstiden, läsbarheten och samarbetet i teamet.

**Bästa praxis**: Håll resorna fokuserade och hanterbara. Om din resa blir komplex, tänk på följande:

* Dela upp det på flera resor med hjälp av hoppaktiviteten
* Skapa återanvändbara mönster för enklare resor
* Förenkla logiken med effektivare villkor
* Granska om alla aktiviteter är nödvändiga

Läs mer om [resedesign](using-the-journey-designer.md) och [skyddsutkast och begränsningar](../start/guardrails.md).

+++

+++ Hur kan jag säkerställa att min resa fungerar bra i stor skala?

**Designöverväganden**:

* Använd [målgruppsbaserad post](read-audience.md) för gruppkommunikation i stället för enskilda händelser
* Implementera lämpliga [väntetider](wait-activity.md) för att sprida meddelandevolymen
* Använd [begränsningsregler](../conflict-prioritization/journey-capping.md) för att förhindra systemöverbelastning
* Optimera [villkorslogik](condition-activity.md) för att minska komplexiteten i bearbetningen

**Övervakning**:

* Spåra [resemått](report-journey.md) regelbundet
* Övervaka API-prestanda för [anpassade åtgärder](using-custom-actions.md)
* Granska felfrekvenser och timeout-händelser med [felsökningsverktyg](troubleshooting.md)
* Prenumerera på [resemeddelanden](../reports/alerts.md) om viktiga resefel

**Optimering**:

* Använd [testläge](testing-the-journey.md) och [torr körning](journey-dry-run.md) för att validera prestanda före publicering
* Minimera externa API-anrop via [anpassade åtgärder](using-custom-actions.md) för att undvika fördröjning och beroende av system från tredje part
* Lagra data som används ofta i Adobe Experience Platform med [datauppslagssökning](dataset-lookup.md) i stället för att göra externa anrop, när det är möjligt
* Granska och optimera prestanda för [meddelandeleverans](journeys-message.md)

Läs mer om [skyddsutkast och begränsningar](../start/guardrails.md).

+++

## Ytterligare resurser

Utforska följande resurser om du vill ha mer information och uppdateringar:

* [Kom igång med resor](journey.md)
* [Skapa den första resan](journey-gs.md)
* [Felsökningsguider](troubleshooting.md)
* [Användningsexempel på resa](jo-use-cases.md)
* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}
