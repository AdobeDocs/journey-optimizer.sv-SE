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
source-git-commit: 32848633cdfb5683b45286fcdd22711a82d591b5
workflow-type: tm+mt
source-wordcount: '4094'
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

Ja. Använd en **villkorsaktivitet** i kombination med **vänteaktiviteter**:

1. Lägg till en vänteaktivitet (t.ex. vänta 3 dagar)
2. Lägg till en villkorsaktivitetskontroll om e-postmeddelandet öppnades eller klickades
3. Skapa två banor:
   * **Om du har öppnat/klickat**: Avsluta resan eller fortsätt med nästa steg
   * **Om du inte har öppnat/klickat**: Skicka ett påminnelsemeddelande via e-post med en annan ämnesrad

**Bästa tillvägagångssätt**: Begränsa antalet omgångar så att inte skräppost visas (vanligtvis 1-2 påminnelser maximalt).

Läs mer om [reaktionshändelser](reaction-events.md).

+++

+++ Hur skapar jag en kundvagnsöverlämningsresa?

Skapa en händelseutlöst resa med väntetid och logik:

1. **Konfigurera en händelse om att kundvagnen överges**: Utlöses när objekt läggs till men utcheckningen inte slutförs inom en tidsram
2. **Lägg till en vänteaktivitet**: Vänta i 1-2 timmar för att ge kunden tid att slutföra naturligt
3. **Lägg till ett villkor**: Kontrollera om köpet slutfördes under väntan
4. **Om det inte köpts**: Skicka en påminnelse om att kunden har lämnat tjänsten med kundvagnsinnehåll via e-post
5. **Valfritt**: Lägg till ytterligare en väntan (24 timmar) och skicka en andra påminnelse med ett incitament (t.ex. 10 % rabatt)

Läs mer om [användningsfall för resan](jo-use-cases.md).

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
* **Vänta tills specifik tid**: Använd aktiviteten Vänta för att skicka meddelanden vid en viss tidpunkt i mottagarens lokala tidszon (t.ex. 10:00)

**Exempel**: Om du vill skicka ett &quot;Godmorgon&quot;-e-postmeddelande klockan 9.00 i varje kunds tidszon använder du en Wait-aktivitet med &quot;Vänta till ett fast datum/tid&quot; och aktiverar tidszonsalternativet.

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

Läs mer om alternativen för att pausa [resan](journey-pause.md).

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

* **Meddelandet har inte godkänts**: Meddelandeinnehållet måste godkännas innan det skickas
Lösning: Skicka för godkännande eller kontrollera godkännandestatus

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

* &quot;Hej {{profile.firstName}}, tack för ditt köp av {{event.productName}}&quot;
* &quot;Baserat på din lojalitetsnivå ({{profile.loyaltyTier}}) finns det ett specialerbjudande&quot;
* Dynamiska innehållsblock som ändras utifrån kundernas önskemål

Läs mer om [personalisering](../personalization/personalize.md).

+++

+++ Kan jag skicka olika meddelanden baserat på vilken kanal jag föredrar?

Ja. Använd en **villkorsaktivitet** för att kontrollera den önskade kanalen:

1. Lägg till en villkorskontrollprofil.preferredChannel
2. Skapa separata banor för varje kanal:
   * **E-postsökväg**: Skicka e-postmeddelande
   * **SMS-sökväg**: Skicka SMS-meddelande
   * **Push-sökväg**: Skicka push-meddelande
3. Lägga till en standardsökväg för profiler utan en inställning

**Alternativ metod**: Använd **flerkanalsåtgärder** där Journey Optimizer automatiskt väljer den bästa kanalen baserat på profilinställningar och tillgänglighet.

Läs mer om [kanalåtgärder](journeys-message.md).

+++

+++ Kan jag utesluta vissa kunder från min resa?

Ja, det finns flera sätt att utesluta kunder:

**Vid resepost**:

* Använd målgruppsdefinitioner med undantagsregler
* Lägga till anmälningsvillkor som filtrerar bort specifika profiler
* Konfigurera namnutrymmeskrav

**Inom resan**:

* Lägg till en villkorsaktivitet tidigt under resan för att avsluta oönskade profiler
* Kontrollera om det finns exkluderingsattribut (t.ex. VIP-status, testkonton)
* Använd målgruppskvalifikation för att identifiera profiler som ska uteslutas

**Exempel på undantagsscenarier**:

* Exkludera kunder som nyligen köpt
* Uteslut VIP-kunder från standardkampanjer
* Exkludera medarbetare och testkonton
* Uteslut kunder i vissa regioner

Läs mer om [hantering av inträde](entry-management.md) och [villkor](condition-activity.md).

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

Ja. Använd aktiviteten **Optimera** (tillgänglig i specifika Journey Optimizer-paket) eller skapa testdelningar manuellt:

**Använda aktiviteten Optimera**:

* Delar automatiskt upp trafik mellan varianter
* Testar olika meddelanden, erbjudanden eller hela resvägar
* Mäter prestanda och deklarerar en vinnare

**Manuell testning med villkor**:

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

+++ Kan jag pausa en resa för en viss person utan att stoppa hela resan?

Du kan inte pausa en resa för enskilda profiler direkt, men du kan uppnå liknande resultat:

**Alternativ**:

* **Lägg till i exkluderingsmålgrupp**: Skapa en målgrupp med profiler för att exkludera och lägga till en villkorskontroll för den här målgruppen vid strategiska punkter på resan
* **Uppdatera profilattribut**: Ange en pausflagga i profilen och använd villkor för att hoppa över åtgärder för flaggade profiler
* **Anpassad åtgärd**: Använd ett externt system för att spåra pausade profiler och kontrollera status via API-anrop
* **Manuell avslutning**: I brådskande fall kan du ta bort testprofiler manuellt

**Obs!** Reseändringar påverkar bara nya deltagare. Profiler som redan finns på resan följer den ursprungliga vägen om inte resan stoppas helt.

+++

+++ Vad är skillnaden mellan ett villkor och en vänteaktivitet?

**Villkorsaktivitet**:

* **Syfte**: Skapar olika sökvägar baserat på logik (om/då)
* **Funktion**: Utvärderar data och dirigerar profiler därefter
* **Användningsfall**: Segmentera kunder, kontrollera status, gren baserat på beteende
* **Exempel**: Om kunden är VIP skickar du premiumerbjudande; annars skickar du standarderbjudande

**Vänteaktivitet**:

* **Syfte**: Pausar resan under en tidsperiod
* **Funktion**: Innehåller profiler vid en viss punkt innan du fortsätter
* **Användningsfall**: Timing mellan meddelanden, väntan på arbetstider, skapa förseningar
* **Exempel**: Vänta 3 dagar efter välkomstmeddelandet innan du skickar nästa meddelande

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
