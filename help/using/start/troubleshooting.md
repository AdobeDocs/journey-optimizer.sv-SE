---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer felsökning
description: Journey Optimizer frågor om felsökning
feature: Get Started
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 3ab8957d0aec6f30853de5537e03f0e7bec2017c
workflow-type: tm+mt
source-wordcount: '1663'
ht-degree: 0%

---

# Felsökning {#ajo-troubleshooting}


Nedan följer en lista över felsökningsartiklar för Adobe Journey Optimizer. Varje felsökningsavsnitt ger svar på vanliga frågor och lösningar på problem.

Se även [Vanliga frågor om Adobe Experience Platform och felsökningsdokumentation](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/troubleshooting#service-troubleshooting-directory){target="_blank"}.

## E-postkanal {#ajo-troubleshooting-email}

### E-postdesign {#ajo-troubleshooting-design}

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

+++ Varför försvinner e-postmallar och innehåll från opublicerade resor?

När du redigerar e-postmallar på en opublicerad resa kan innehållet och mallarna i vissa e-postmeddelanden oväntat försvinna. Detta kan orsaka omarbetningar och förseningar. Undvik samtidiga redigeringar, begränsa antalet öppna flikar och spara ändringarna ofta för att minska risken för det här problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om mallarna [på den här sidan](../email/use-email-templates.md).

+++

+++ Kan en profil ha flera push-token i Adobe Journey Optimizer?

När du implementerar push-meddelanden i Journey Optimizer kan en enskild profil ha flera push-tokens kopplade till olika enheter. Under en kampanj för push-meddelanden är Journey Optimizer utformat för att hantera dessa tokens och säkerställa att målprofilen kan nås på alla associerade enheter.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26738){target="_blank"} om du vill veta mer om hantering av push-token.

Läs mer om push-konfigurationen [ på den här sidan](../push/push-configuration.md).

+++

### Spårning och rapportering av e-post {#ajo-troubleshooting-tracking}

+++ Hur undviker man saknade länkar för e-postspårning i rapporter?

Spårning av saknade länkar i Adobe Journey Optimizer inträffar när e-post-URL:er använder dynamiska variabler och inte börjar med http, eller när logiska satser placeras i URL-fältet. För att lösa detta måste alla URL:er börja med http, undvika logik i URL-fältet och flytta komplex personaliseringslogik till HTML-innehåll eller förbearbetade attribut.


Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26932){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om e-postspårning [på den här sidan](../email/message-tracking.md).

+++

### E-postutskick {#ajo-troubleshooting-sending}

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

Läs mer om push-konfigurationen [ på den här sidan](../push/push-configuration.md).

+++

+++ Varför omdirigeras inte jag till den konfigurerade webb-URL:en när du klickar på ett push-meddelande?  

Om push-meddelanden inte omdirigeras till den avsedda webb-URL:en kan det bero på felaktig klickningskonfiguration eller inaktiverade inställningar för push-meddelanden. Kontrollera att **klickåtgärden** för push-meddelandet är korrekt inställd och att **automatisk visning och spårning** av push-meddelanden är aktiverat för att lösa problemet.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26226){target="_blank"} om du vill veta mer om det här problemet.

Läs mer om push-konfigurationen [ på den här sidan](../push/push-configuration.md).

+++


## SMS-kanal {#ajo-troubleshooting-sms}

+++ Varför levereras inte mitt transaktionsmeddelande trots att samtycke har angetts till `marketing.sms.value=y`?

Om en mottagare svarar **STOP** på ett SMS blockeras alla framtida meddelanden från det korta numret, inklusive transaktionsmeddelanden. Om du vill garantera oavbruten leverans av transaktionsmeddelanden konfigurerar och skickar du dem via ett **separat kort nummer** som mottagarna inte tidigare har avanmält.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26258){target="_blank"} om du vill veta mer om det här problemet.

Läs mer om SMS-avanmälningskonfiguration [på den här sidan](../sms/sms-opt-out.md).

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

Läs mer om aktiviteten **Uppdatera profil** på resorna [ på den här sidan](../building-journeys/update-profiles.md).

Se även [Adobe Experience Platform-dokumentationen om datainhämtning](https://experienceleague.adobe.com/sv/docs/experience-platform/ingestion/tutorials/ingest-batch-data?lang=en#dataset-activity){target="_blank"}.

+++

+++ Varför stämmer det inte överens när det gäller antalet profiler som går in på en resa jämfört med den associerade publiken?

Skillnaden kan uppstå när resan använder en profilögonblicksbild från en föregående dag om den aktuella dagens ögonblicksbild inte är tillgänglig vid tidpunkten för resan.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26253){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer i [det här Journey Optimizer Community-inlägget](https://experienceleaguecommunities.adobe.com/t5/real-time-customer-data-platform/profile-snapshot-and-segment-qualification-troubleshooting/ba-p/698998){target="_blank"}.

Se även [API-dokumentationen för Adobe Experience Platform-scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/segmentation/api/schedules?lang=en){target="_blank"} för att kontrollera när ditt dagliga jobb är schemalagt.

+++


+++ Hur löser man problem med målgruppspopulationen?

Problem med målgruppspopulationen kan uppstå när komponenter eller resurser saknas, ofta på grund av fel i tillstånd, etablering eller behörigheter. Om du vill åtgärda de här problemen börjar du med att verifiera berättiganden, säkerställa korrekt etablering och granska behörigheter. Om problemet kvarstår eskalerar du ärendet och koordinerar det med supportteamen för att få en fullständig lösning.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26333){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om aktiviteten **Uppdatera profil** på resorna [ på den här sidan](../building-journeys/update-profiles.md).

Se även [dokumentationen för Adobe Real-Time CDP-profilen](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/ui/user-guide?lang=en#profile-detail){target="_blank"}.

+++

+++ Hur löser jag problem som utlöser resan efter att målgruppen har förändrats i Adobe Journey Optimizer? 

Om en resa slutar triggas efter ändringar av den associerade målgruppen - till exempel ändringar av sammanfogningspolicyn - kan ni få avbrutna kampanjflöden. Lös detta genom att **duplicera och publicera om resan** med de uppdaterade målgruppsinställningarna så att utlösarna fungerar korrekt.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26224){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Lär dig hur du duplicerar en resa [på den här sidan](../building-journeys/journey-ui.md#duplicate-a-journey).

+++


## Resor

### Händelser

+++ Varför utlöser min händelse inte den planerade resan?  

Händelser kan misslyckas med att utlösa en resa även om alla villkor uppfylls när de **skapas via frågetjänster** i stället för att direktuppspelas till **datainsamlingens bastjänst (DCCS)**. Du löser detta genom att granska händelsekonfigurationen, kontrollera att händelserna **direktuppspelas till DCCS** och verifiera funktionaliteten med **testläge**.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26031){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om händelserna [på den här sidan](../event/about-events.md).

Se även [ReseEvent-skyddsräcken](../start/guardrails.md#events).

+++

## Beslut {#ajo-troubleshooting-decisioning}

+++ Hur löser jag problem när jag skapar offertsamlingar?

Det är ofta problem att skapa erbjudandesamlingar när **kataloger inte har etablerats** för din organisation. För att lösa detta kontrollerar du att alla nödvändiga kataloger har etablerats korrekt innan du försöker skapa erbjudandesamlingar.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26265){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om erbjudandesamlingar [på den här sidan](../offers/offer-library/creating-collections.md).

+++


## Flerspråkig {#ajo-troubleshooting-multilingual}

+++ Hur löser jag det här problemet `Message validation error (CJMMAS - 1069-500)`?

I Adobe Journey Optimizer förhindrar ett meddelandevalideringsfel (CJMMAS - 1069-500) som är kopplat till den flerspråkiga funktionen att resor ställs in på testläge eller publiceras.

Läs [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26168){target="_blank"} om du vill veta mer om hur du löser det här problemet.

Läs mer om flerspråkigt innehåll [på den här sidan](../content-management/multilingual-gs.md).

++


## Konfiguration {#ajo-troubleshooting-config}

### Säkerhet {#ajo-troubleshooting-security}

+++ Hur aktiverar jag TLS v1.3 för anpassade åtgärder?  

Om du vill behålla **dataintegritet och -säkerhet** vid anslutning till tredjepartssystem kontrollerar du att Transport Layer Security (**TLS**) v1.3 är aktiverat för dina anpassade åtgärder. Detta bidrar till att skydda kommunikationen och förhindrar potentiella säkerhetsrisker.


Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26223){target="_blank"}.

Läs mer om flerspråkigt innehåll [på den här sidan](../action/about-custom-action-configuration.md).

+++

### Kontrollpaneler {#ajo-troubleshooting-dashboards}

+++ Varför kan jag inte skapa en kontrollpanel direkt från en fråga i Adobe Journey Optimizer? 

I Adobe Journey Optimizer går det inte att skapa kontrollpaneler direkt från frågor. Om du vill skapa kontrollpaneler använder du de tillgängliga **funktionerna för att skapa kontrollpaneler** i Adobe Experience Platform, som gör att du kan visualisera och analysera frågedata effektivt.

Mer information finns i [den här felsökningsartikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-26201){target="_blank"}.

++