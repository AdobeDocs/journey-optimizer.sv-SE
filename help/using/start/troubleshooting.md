---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer felsökningsartiklar
description: Journey Optimizer felsökningsartiklar
feature: Get Started, Monitoring
role: User
level: Intermediate
exl-id: f8acb987-5c6e-4545-93b9-fdfc0d74db57
source-git-commit: 4a15ee3ac4805880ce80f788e4619b501afb3d8b
workflow-type: tm+mt
source-wordcount: '2943'
ht-degree: 0%

---

# Vanliga frågor om felsökning {#ajo-troubleshooting}

Nedan följer en lista över felsökningsartiklar för Adobe Journey Optimizer. Varje felsökningsavsnitt ger svar på vanliga frågor och lösningar på problem.

Se även [Vanliga frågor om Adobe Experience Platform och felsökningsdokumentation](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/troubleshooting){target="_blank"}.

## E-postkanal {#ajo-troubleshooting-email}

+++ Hur undviker man e-postformateringsproblem i Adobe Journey Optimizer med teman?

Om du ändrar standard-CSS-blocken i e-posthuvudet i Adobe Journey Optimizer (AJO) kan det leda till oväntade formateringsproblem, särskilt efter att innehållsfragment har tagits bort. Dessa problem är tydligare på mobila enheter och kan leda till layoutändringar eller inkonsekvenser i formateringen. Du kan förhindra detta genom att använda funktionen Teman för att använda anpassad CSS utan att ändra systemgenererade CSS-format.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-27252){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om e-postformatering [på den här sidan](../email/get-started-email-design.md).

+++


+++ Varför fungerar inte fragment med redigerbara fält?

I Adobe Journey Optimizer kan fragment med redigerbara fält inte läsas in korrekt eller dupliceras på ett oväntat sätt när de läggs till i mallar. Felet påverkar vanligtvis specifika fragment i olika miljöer.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26908){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om anpassningsbara fragment [på den här sidan](../content-management/customizable-fragments.md).

+++

+++ Varför visas inte HTML-fragment korrekt i e-postmeddelanden?

HTML-fragment kan misslyckas med att återges korrekt i e-postmeddelanden, som ofta visas som **fragment-ID** i stället för faktiskt innehåll. Till skillnad från visuella fragment kräver HTML fragment noggrann konfiguration. Lös detta genom att följa bästa praxis för användning av både **visuella fragment och HTML-uttrycksfragment** i e-postkampanjer.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-25441){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om HTML fragment [på den här sidan](../content-management/fragments.md).

+++

+++ Varför försvinner e-postmallar och innehåll från opublicerade resor?

När du redigerar e-postmallar på en opublicerad resa kan innehållet och mallarna i vissa e-postmeddelanden oväntat försvinna. Detta kan orsaka omarbetningar och förseningar. Undvik samtidiga redigeringar, begränsa antalet öppna flikar och spara ändringarna ofta för att minska risken för det här problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om mallarna [på den här sidan](../email/use-email-templates.md).

+++

+++ Varför visas inte fältet E-postförrubrik i kodläge? 

I **&#39;Koda ditt eget&#39;**-läge under funktionen **Redigera e-postbrödtext** visas inte indatafältet för sidhuvud. Om du vill ta med prerubriktext måste användarna **manuellt koda prerubriken** i sitt anpassade HTML-innehåll.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26174){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om konfigurationen [för e-postpreheader på den här sidan](../email/header-parameters.md).

+++

+++ Varför finns det skillnader i länkbeteendet när en HTML-komponent används i e-postmallar?  

När du lägger till en **HTML-komponent** i en e-postmall kan länkar bete sig på olika sätt beroende på **e-postklienten**, **visningsläget** eller **enheten/webbläsaren**. Ankarlänkar kan till exempel fungera annorlunda i **Outlook sida vid sida** jämfört med helskärmsläge. Tänk på dessa variationer när du utformar e-postmallar och testar för flera klienter och enheter.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26221){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Se även Bästa praxis för e-postdesign [på den här sidan](../email/get-started-email-design.md).

+++


+++ Hur undviker man saknade länkar för e-postspårning i rapporter?

Spårning av saknade länkar i Adobe Journey Optimizer inträffar när e-post-URL:er använder dynamiska variabler och inte börjar med http, eller när logiska satser placeras i URL-fältet. För att lösa detta måste alla URL:er börja med http, undvika logik i URL-fältet och flytta komplex personaliseringslogik till HTML-innehåll eller förbearbetade attribut.


Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26932){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om e-postspårning [på den här sidan](../email/message-tracking.md).

+++

+++ Hur löser jag ett fel i Mail Exchanger när jag ställer in API-utlösta transaktionella e-postkampanjer? 

Om du får ett MX-fel (Mail Exchanger) när du skapar en kanalkonfiguration för en API-utlöst transaktionell e-postkampanj i Adobe Journey Optimizer kan det bero på **DNS-felkonfigurationer** eller **begränsningar i DMARC-principen**. Kontrollera att din DNS är korrekt konfigurerad och verifiera att din domän uppfyller kraven för **Domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC)**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26200){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om e-postprinciper för DMARC [på den här sidan](../configuration/dmarc-record-update.md).

Se även [API-utlöst kampanjdokumentation](../campaigns/api-triggered-campaigns.md).
+++

## Push-kanal {#ajo-troubleshooting-push}

+++ Kan en profil ha flera push-token i Adobe Journey Optimizer?

När du implementerar push-meddelanden i Journey Optimizer kan en enskild profil ha flera push-tokens kopplade till olika enheter. Under en kampanj för push-meddelanden är Journey Optimizer utformat för att hantera dessa tokens och säkerställa att målprofilen kan nås på alla associerade enheter.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} om du vill veta mer om hantering av push-token.

Läs mer om push-konfigurationen [&#x200B; på den här sidan](../push/push-configuration.md).

+++

+++ Varför omdirigeras inte jag till den konfigurerade webb-URL:en när du klickar på ett push-meddelande?  

Om push-meddelanden inte omdirigeras till den avsedda webb-URL:en kan det bero på felaktig klickningskonfiguration eller inaktiverade inställningar för push-meddelanden. Kontrollera att **klickåtgärden** för push-meddelandet är korrekt inställd och att **automatisk visning och spårning** av push-meddelanden är aktiverat för att lösa problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26226){target="_blank"} om du vill veta mer om det här problemet.

Läs mer om push-konfigurationen [&#x200B; på den här sidan](../push/push-configuration.md).

+++


## SMS-kanal {#ajo-troubleshooting-sms}

+++ Varför levereras inte mitt transaktionsmeddelande trots att samtycke har angetts till `marketing.sms.value=y`?

Om en mottagare svarar **STOP** på ett SMS blockeras alla framtida meddelanden från det korta numret, inklusive transaktionsmeddelanden. Om du vill garantera oavbruten leverans av transaktionsmeddelanden konfigurerar och skickar du dem via ett **separat kort nummer** som mottagarna inte tidigare har avanmält.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26258){target="_blank"} om du vill veta mer om det här problemet.

Läs mer om SMS-avanmälningskonfiguration [på den här sidan](../sms/sms-opt-out.md).

+++

## Kanal i appen

+++ Varför kan jag inte rapportera om In-app-kanalen i Customer Journey Analytics?

Svårigheter som rapporteras för **In-app-kanalen** i Adobe Customer Journey Analytics beror ofta på felkonfigurerade **datavyer**, **datamängder** eller **schemauppdateringar**. Kontrollera att dessa konfigurationer används på rätt sätt för att lösa problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26206){target="_blank"} om du vill veta mer om det här problemet.

Läs mer om hur du integrerar Journey Optimizer analysdata i Customer Journey Analytics [på den här sidan](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/integrations/ajo#automatically-configure-journey-optimizer-integration){target="_blank"}.

Se även [Journey Optimizer All-time Reports documentation](../reports/report-gs-cja.md)

+++


## Datahantering {#ajo-troubleshooting-data-management}

+++ Hur tillämpas TTL-inställningar (Time-to-Live) på data för profiler och datasjöer när du skapar en ny sandlåda?

Organisationer som etablerar nya sandlådor i Adobe Journey Optimizer har ställt frågor om hur TTL-inställningar (Time-to-Live) gäller för datauppsättningarna Profile och Data Lake. I den här artikeln klargörs att TTL-inställningar inte påverkar befintliga sandlådor och tillämpas automatiskt bara på nyligen tilldelade sandlådor.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"} om du vill veta mer om hur du hanterar TTL.

Läs mer om datauppsättningen Tid till live [på den här sidan](../data/datasets-ttl.md).

+++


## Profiler och målgruppshantering {#ajo-troubleshooting-audiences}

+++ Hur löser man avvikelser i antal målgrupper?

Antalet bearbetade poster i funktionen **Läs målgrupp** i Adobe Journey Optimizer kan vara lägre än det förväntade antalet målgrupper. Detta problem uppstår ofta på grund av felaktiga namnområdeskonfigurationer, vilket leder till att profiler utesluts från resor. Upplösningen innebär att kontrollera och korrigera namnutrymmeskonfigurationer, granska relevant dokumentation och justera prioriteter för att säkerställa smidigare åtgärder i Adobe Journey Optimizer.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26135){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Se även [den här artikeln om antalet inaktuella målgrupper](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26166){target="_blank"}.

Läs mer om aktiviteten **Läs målgrupp** på resorna [på den här sidan](../building-journeys/read-audience.md).

+++

+++ Varför misslyckas profiluppdateringarna?

I Adobe Journey Optimizer uppdateras vissa fältvärden eventuellt inte korrekt efter att en **Uppdatera profil**-aktivitet har körts under en resa. I vissa fall kan uppdaterade fält försvinna eller återställas till sitt tidigare läge. Du kan åtgärda detta genom att kontrollera om det finns regler eller villkor som står i konflikt, granska behörighetsinställningar, använda en unik datauppsättning för aktiviteten **Uppdatera profil** och se till att ingen annan inmatningsprocess skriver till samma profil samtidigt.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26352){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om aktiviteten **Uppdatera profil** på resorna [&#x200B; på den här sidan](../building-journeys/update-profiles.md).

Se även [Adobe Experience Platform-dokumentationen om datainhämtning](https://experienceleague.adobe.com/sv/docs/experience-platform/ingestion/tutorials/ingest-batch-data#dataset-activity){target="_blank"}.

+++

+++ Varför stämmer det inte överens när det gäller antalet profiler som går in på en resa jämfört med den associerade publiken?

Skillnaden kan uppstå när resan använder en profilögonblicksbild från en föregående dag om den aktuella dagens ögonblicksbild inte är tillgänglig vid tidpunkten för resan.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26253){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer i [det här Journey Optimizer Community-inlägget](https://experienceleaguecommunities.adobe.com/t5/real-time-customer-data-platform/profile-snapshot-and-segment-qualification-troubleshooting/ba-p/698998?profile.language=sv){target="_blank"}.

Se även [API-dokumentationen för Adobe Experience Platform-scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/segmentation/api/schedules){target="_blank"} för att kontrollera när ditt dagliga jobb är schemalagt.

+++

+++ Varför visar målgruppsväljaren olika antal profiler i Campaigns jämfört med Journeys?

Ni kan lägga märke till att samma målgrupp visar olika antal profiler när de visas i kampanjer jämfört med resor. Det beror på att varje funktion använder olika API:er för att hämta målgruppsdata, som kan returnera olika värden.

Detta är ett förväntat beteende som inte påverkar er kampanjkörning - de rätta profilerna kommer fortfarande att användas. Om du vill kontrollera den faktiska målgruppsstorleken går du till **[!UICONTROL Customer]** > **[!UICONTROL Audiences]** och väljer målgrupp.

+++


+++ Hur löser man problem med målgruppspopulationen?

Problem med målgruppspopulationen kan uppstå när komponenter eller resurser saknas, ofta på grund av fel i tillstånd, etablering eller behörigheter. Om du vill åtgärda de här problemen börjar du med att verifiera berättiganden, säkerställa korrekt etablering och granska behörigheter. Om problemet kvarstår eskalerar du ärendet och koordinerar det med supportteamen för att få en fullständig lösning.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26333){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om aktiviteten **Uppdatera profil** på resorna [&#x200B; på den här sidan](../building-journeys/update-profiles.md).

Se även [dokumentationen för Adobe Real-Time CDP-profilen](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/ui/user-guide#profile-detail){target="_blank"}.

+++

+++ Varför har antalet aktiverbara profiler ökat avsevärt under en kort period? 

Måttet **Aktiverbara profiler** visar antalet unika profiler som använts av resor eller kampanjer under de senaste 12 månaderna. En plötslig ökning kan bero på resor eller kampanjer riktade till stora målgrupper som inte har engagerats nyligen, eller på förändringar i datamängder som har aktiverats för profiltjänsten.

För att undersöka och lösa detta problem måste ni förstå logiken för att räkna profiler, undersöka resor och kampanjer som riktar sig till stora målgrupper, filtrera målgrupper på rätt sätt, övervaka förändringar av datauppsättningar och eventuellt minska er adresserbara målgruppsstorlek.

Lär dig hur du felsöker och löser problem som kan aktiveras ökar och övervakar din organisations licensanvändning i [dokumentationen för kontrollpanelen för licensanvändning](../audience/license-usage.md#troubleshooting-engageable-profiles).

+++

+++ Varför skickas e-postmeddelanden till individer utanför den avsedda målgruppen baserat på datumfunktioner?

E-postmeddelanden kan skickas till mottagare som **inte uppfyller de angivna målgruppskriterierna**. Till exempel kan medlemmar med inlösendatum **före 4 juli 2025** få e-postmeddelanden som bara är avsedda för dem efter det datumet. Det här beteendet kan bero på **felkonfigurerad målgruppssegmentering** eller **oväntade förändringar i profilkvalificeringslogiken**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26173){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om datumfunktionerna [på den här sidan](../building-journeys/functions/date-functions.md).

+++

+++ Varför överskrider Levererade + Uteslutningar min målgruppsstorlek i kampanjrapporter?

I kampanjrapporter kan du se att summan av **Levererade** och **Undantag** överskrider den ursprungliga målgruppsstorleken. Detta inträffar eftersom måttet **Undantag** räknar alla undantagshändelser, inklusive dubblettundantagshändelser för samma profil. Om en profil utesluts flera gånger under en kampanj räknas varje händelse separat.

**Exempel**: En kampanj med 94 000 profiler som mål visar 69 000 levererade och 37 000 undantag, totalt 106 000 - vilket överskrider de ursprungliga 94 000 målprofiler. Detta är förväntat beteende.

Mer information om skillnaden mellan totala undantagshändelser och unika profilundantag finns i [Beräkningsförklaring för uteslutning](../reports/exclusion-list.md#exclusion-list).

Läs mer om [Kampanjrapporter](../reports/campaign-global-report-cja.md) och [Rapportstatistik](../reports/global-report-components-cja.md).

+++

+++ Hur löser jag problem med målgruppsval och Chrome-fel när jag sparar resor?

Om du lägger till målgrupper i resevillkor kan det ibland orsaka **programkrascher** eller visa ett **Aw Snap-fel** i Chrome, inklusive fel när resor sparas. Dessa problem är ofta relaterade till **Kromiumtjänster**. Lös dem genom att tillämpa en **webbläsaruppdatering** eller använda en lämplig **tillfällig lösning**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26145){target="_blank"} om du vill veta mer om hur du löser det här problemet.

+++

## Resor {#ajo-troubleshooting-journeys}

För Resor, se följande felsökningsavsnitt:

* [Felsöka fel innan du testar din resa](../building-journeys/troubleshooting.md)
* [Felsöka inkommande åtgärder under resor](../building-journeys/troubleshooting-inbound.md)
* [Felsök körningen av din direktresa](../building-journeys/troubleshooting-execution.md)
* [Felsöka anpassade åtgärder](../action/troubleshoot-custom-action.md)


+++ Varför försvinner uttryck när du skapar en ny version?  

När du skapar en ny version av en resa kan **uttryck i specifika steg** gå förlorade, vilket kan orsaka fel och kräva manuell inmatning. Lös detta genom att **duplicera resan**, testa om den är reproducerbar, **undvika webbläsaromladdningar** och använda den **uppdaterade arbetsytan** för äldre resor.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26152){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Lär dig hur du duplicerar en resa [på den här sidan](../building-journeys/journey-ui.md#duplicate-a-journey).

+++

+++ Varför avslutas profiler för tidigt? 

Profiler kan avsluta en resa oväntat utan att passera genom en angiven nod när **status för villkorskontroll** av skickade meddelanden är felkonfigurerad. Lös detta genom att granska **villkorslogiken**, implementera **alternativ logik** eller rådfråga ditt **implementeringsteam**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26127){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Se även [Riktlinjer för resedesign](../building-journeys/using-the-journey-designer.md).

+++


+++ Varför avslutar profiler oväntat resorna?

Profiler kan avsluta en resa oväntat när **händelsebegränsning** inträffar, vilket gör att vissa profiler ignoreras om antalet bearbetade händelser överstiger systemkapaciteten. Om du vill minska antalet profilutgångar förstår du **systemgränserna**, övervakar **händelsetoppar** och optimerar **dataflödet** för att förhindra att tröskelvärdena överskrids.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26018){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Se även [Resegarantier](../start/guardrails.md#decisioning-guardrails).

+++


+++ Varför utlöser min händelse inte den planerade resan?  

Händelser kan misslyckas med att utlösa en resa även om alla villkor uppfylls när de **skapas via frågetjänster** i stället för att direktuppspelas till **datainsamlingens bastjänst (DCCS)**. Du löser detta genom att granska händelsekonfigurationen, kontrollera att händelserna **direktuppspelas till DCCS** och verifiera funktionaliteten med **testläge**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26031){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om händelserna [på den här sidan](../event/about-events.md).

Se även [ReseEvent-skyddsräcken](../start/guardrails.md#events-g).

+++


+++ Hur löser jag problem som utlöser resan efter att målgruppen har förändrats i Adobe Journey Optimizer? 

Om en resa slutar utlösas efter ändringar av den associerade målgruppen - till exempel ändringar av kopplingsprofilen - kan du få avbrutna flöden. Lös detta genom att **duplicera och publicera om resan** med de uppdaterade målgruppsinställningarna så att utlösarna fungerar korrekt.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26224){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Lär dig hur du duplicerar en resa [på den här sidan](../building-journeys/journey-ui.md#duplicate-a-journey).

+++

+++ Varför tar en anpassad åtgärd som anropar en extern slutpunkt från tredje part slut?

Timeoutfel kan uppstå när en **anpassad åtgärd** anropar en extern tredje parts slutpunkt. Du kan lösa problemet genom att kontrollera att **slutpunkten är tillgänglig**, kontrollera **serverloggar**, kontrollera att det inte finns **någon blockering från Adobe**, uppdatera slutpunktskonfigurationer efter behov och **testa efter uppdateringar**. Tänk också på **API-anrop med timeout-specifikationer**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26156){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om Journey Throttling API [på den här sidan](../configuration/throttling.md).

Se även [Integrering med dokumentation för externa system](../configuration/external-systems.md).

+++

+++ Vilka åtgärder ska du vidta om du råkar ut för ett 403-fel med meddelandet **invalid_access** eller **Ingen åtkomst till dataId=XX beviljad** vid publicering av en målgrupp från en pil?

Du kan åtgärda det här felet genom att be administratören verifiera att din användarprofil har åtkomst till de datavyer som krävs för målgruppspublicering och sedan försöka publicera målgruppen igen.

Mer information om hur du löser det här problemet finns i [behörighetsdokumentationen](../administration/permissions.md){target="_blank"}.

+++

## Regler {#ajo-troubleshooting-rules}

+++ Varför fungerar inte applådereglerna?

Problem med listrutan **Takregler** uppstår ofta när regeluppsättningar är **felkonfigurerade** eller **inte tillgängliga**. Kontrollera att alla regeluppsättningar är korrekt konfigurerade och tillgängliga för att lösa problemet.

Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26204){target="_blank"}.

Lär dig hur du tillämpar capping-regler [i det här avsnittet](../conflict-prioritization/rule-sets.md).

+++

## Beslut {#ajo-troubleshooting-decisioning}

+++ Hur löser jag problem när jag skapar offertsamlingar?

Det är ofta problem att skapa erbjudandesamlingar när **kataloger inte har etablerats** för din organisation. För att lösa detta kontrollerar du att alla nödvändiga kataloger har etablerats korrekt innan du försöker skapa erbjudandesamlingar.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26265){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om erbjudandesamlingar [på den här sidan](../offers/offer-library/creating-collections.md).

+++

+++ Varför kan jag inte komma åt Offer Decisioning?  

När du integrerar Adobe Target i ett program med Adobe Journey Optimizer kan det hända att alternativet **Offer Decisioning** inte är tillgängligt i DataStream-konfigurationen. Detta inträffar vanligtvis på grund av **behörighetsinställningar** eller **etableringsbegränsningar**. Kontrollera användarbehörigheterna och se till att nödvändig etablering finns på plats för att lösa problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26175){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om nödvändiga behörigheter för Offer Decisioning [på den här sidan](../offers/get-started/starting-offer-decisioning.md#granting-acess-to-decision-management).

+++



## Flerspråkig {#ajo-troubleshooting-multilingual}

+++ Hur löser jag det här problemet `Message validation error (CJMMAS - 1069-500)`?

I Adobe Journey Optimizer förhindrar ett meddelandevalideringsfel (CJMMAS - 1069-500) som är kopplat till den flerspråkiga funktionen att resor ställs in på testläge eller publiceras.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26168){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om flerspråkigt innehåll [på den här sidan](../content-management/multilingual-gs.md).

+++


## Konfiguration {#ajo-troubleshooting-config}

+++ Hur aktiverar jag TLS v1.3 för anpassade åtgärder?  

Om du vill behålla **dataintegritet och -säkerhet** vid anslutning till tredjepartssystem kontrollerar du att Transport Layer Security (**TLS**) v1.3 är aktiverat för dina anpassade åtgärder. Detta bidrar till att skydda kommunikationen och förhindrar potentiella säkerhetsrisker.


Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26223){target="_blank"}.

Läs mer om flerspråkigt innehåll [på den här sidan](../action/about-custom-action-configuration.md).

+++

+++ Varför kan jag inte skapa en kontrollpanel direkt från en fråga i Adobe Journey Optimizer? 

I Adobe Journey Optimizer går det inte att skapa kontrollpaneler direkt från frågor. Om du vill skapa kontrollpaneler använder du de tillgängliga **funktionerna för att skapa kontrollpaneler** i Adobe Experience Platform, som gör att du kan visualisera och analysera frågedata effektivt.

Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26201){target="_blank"}.

+++

## API:er {#ajo-troubleshooting-apis}

+++ Hur löser jag åtkomstproblem med API:t för frågetjänsten?  

Åtkomstfel när **API:t för frågetjänsten** används via Postman eller liknande verktyg orsakas vanligtvis av **otillräcklig behörighet**. Lös problemet genom att verifiera användarbehörigheter, kontrollera API-autentiseringsuppgifter och ge detaljerad information till support om det behövs.

Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26196){target="_blank"}.

Se även dokumentationen för [Hantera API-autentiseringsuppgifter](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/abac/permissions-ui/permissions#manage-api-credentials-for-role){target="_blank"}.

+++
