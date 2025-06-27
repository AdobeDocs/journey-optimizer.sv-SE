---
solution: Journey Optimizer
product: journey optimizer
title: Upplevelsehändelser som söks igenom resor
description: Lär dig använda Experience Events-sökning i resor
exl-id: 35e2e347-0669-44a3-92ba-aee52e54c219
source-git-commit: cee47accd4f5427f7e10015eba8b952d4e86daab
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 1%

---

# Upplevelsehändelsesökning i resor {#ee-journeys}

>[!CAUTION]
>
>Från och med den 8 juli 2025 stöds inte längre skapande av uttryck med upplevelsehändelser i den uttrycksredigerare som används i resevillkoren i nya kundorganisationer. Därför kan upplevelsehändelser i [Experience Platform-datakällan](../datasource/adobe-experience-platform-data-source.md) inte användas för att skapa uttryck. Nedan finns referenser till alternativa metoder och bästa metoder för att skapa uttryck/logik med upplevelsehändelser.
>
>Behöver du mer information? [Läs Frågor och svar](#faq-ee).

På den här sidan beskrivs vanliga mönster och skalbara strategier som hjälper dig att få ut det mesta av Experience Events i Adobe Journey Optimizer. De här användningsexemplen är utformade för att hjälpa dig att lösa vanliga problem som att hantera avanmälan, styra meddelandefrekvensen, anpassa innehåll baserat på användarbeteende och reagera på realtidssignaler.

Genom att utnyttja dessa strategier kan ni omvandla beteendedata till meningsfulla åtgärder - att undertrycka, kvalificera eller exkludera profiler baserat på de händelser de utlöser eller de attribut de har. Oavsett om du bygger upp logik för inköpströsklar, övergivna triggers eller studshantering ger de här exemplen praktisk vägledning som du kan anpassa efter dina behov.

När du utvärderar vilken metod som passar bäst bör du överväga latenskraven för din användning för att försäkra dig om att dina resor förblir responsiva och effektiva.

## Avanmäl inaktivering

Använd inbyggd samtyckeshantering för att utelämna profiler som har valt bort marknadsföringskommunikation. Inställningar för avanmälan registreras automatiskt i profilens medgivandefält. De kan refereras direkt under resan och används automatiskt av Journey Optimizer under meddelandeleveransen.

Läs mer:

* [Hantera medgivande](../privacy/opt-out.md)
* [Hantering av avanmälan via e-post](../email/email-opt-out.md)
* [Hantering av avanmälan för textmeddelanden](../sms/sms-opt-out.md)


## Studsbaserad undertryckning

Om du vill exkludera profiler som har fått e-poststudsar använder du Adobe Journey Optimizer automatiska lista för inaktivering för studsade adresser. Denna inbyggda mekanism säkerställer att ogiltiga eller onåbara e-postmeddelanden utesluts från framtida utskick utan att någon anpassad logik krävs.

Läs mer:

* [Hantera listan över inaktiveringar](../configuration/manage-suppression-list.md)


## Allmän undertryckning

Om du vill inaktivera profiler som har visat vissa beteenden använder du gruppmålgrupper med händelsebaserad logik för att hämta profiler som uppfyller undertryckningskriterierna. Se den här målgruppen under reseförhållanden.

Läs mer:

* Adobe Experience Platform [Segment builder - händelser](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [Segment builder - tidsbegränsningar](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [Använda målgrupper under förhållanden](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [funktionen inAudience()](../building-journeys/functions/functioninaudience.md)


## Undantag för mottagen kommunikation

Så här förhindrar du att meddelanden skickas till profiler som har tagit emot meddelanden inom ett tidsfönster:

* Använd gruppmålgrupper med tidsbaserade kriterier och hänvisa till dem under resan.
* Använd affärsregler för frekvensbegränsning för att tillämpa dagliga eller veckovisa meddelandegränser.


Läs mer om hur du använder målgrupper:

* Adobe Experience Platform [Segment builder - händelser](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [Segment builder - tidsbegränsningar](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [Använda målgrupper under förhållanden](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [funktionen inAudience()](../building-journeys/functions/functioninaudience.md)


Se även:

* [Frekvensbegränsning per kanal och kommunikationstyp](../conflict-prioritization/channel-capping.md)



## Meddelandespecifik inkludering/exkludering

Om du vill inkludera eller exkludera profiler baserat på om de har fått ett visst meddelande, skapar du gruppmålgrupper som kapslar in den här logiken och refererar till dem under resan.


Läs mer:

* Adobe Experience Platform [Segment builder - händelser](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#events){target="_blank"}

* Adobe Experience Platform [Segment builder - tidsbegränsningar](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder#time-constraints){target="_blank"}

* [Använda målgrupper under förhållanden](../building-journeys/condition-activity.md#using-audiences-in-conditions)

* [funktionen inAudience()](../building-journeys/functions/functioninaudience.md)

## Kundvagn eller bläddra bland övergivna personaliseringar

Skräddarsy kommunikationen utifrån den senaste kundvagnen eller se händelser i olika kundvagnstyper eller produktvyer:

* Om du har tillgång till [Adobe Experience Platform Data Distiller](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview){target="_blank"} konfigurerar du automatiska frågor för att extrahera nödvändiga data från händelsen, ändra dem så att de passar användningsfallet och skriva tillbaka dem till en profilaktiverad datauppsättning för aktivering.
* Om övergivna data kan modelleras utifrån profilen med skalära attribut kan du använda beräknade attribut för att hämta in den senaste informationen och sedan referera till dessa attribut under resan för att skapa kommunikationen. [Läs mer i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}


## Beteendebaserad reseutgång

Om du vill ta bort profiler från resan när de uppvisar ett visst beteende använder du avslutningskriterier för att lämna profilen från resan när en viss händelse tas emot eller profilen kvalificerar sig för en viss målgrupp.

Läs mer:

* [Ange resans egenskaper - avslutningskriterier](journey-properties.md#exit-criteria)

## Inköpsbaserad kvalificering med tröskelvärden

Om du vill utlösa resor baserat på inköp och undertrycka om värdet ligger över/under ett tröskelvärde, definierar du beräknade attribut som summerar inköp under en viss tidsperiod. Skapa en målgrupp som innehåller profiler vars utgiftsbelopp uppfyller vissa kriterier.

Läs mer:

* Adobe Experience Platform [Översikt över beräknade attribut](https://experienceleague.adobe.com/en/docs/experience-platform/profile/computed-attributes/overview){target="_blank"}



## Vanliga frågor {#faq-ee}

Användning av upplevelsehändelser i reseuttryck/villkor stöds inte längre. Effekter listas i Frågor och svar nedan:

+++Vilka specifika funktioner påverkas?

Endast sökningen efter upplevelsehändelser i uttrycksredigeraren påverkas. Följande funktioner påverkas **inte** och förblir desamma:

* Observera upplevelsehändelser som är associerade med en viss profil i profilens användargränssnitt

* Använda upplevelsehändelser i beräknade attributregler och komma åt beräknade attribut under en resa

* Startar en resa med ett enhets- eller affärsevenemang

* Använda data om resekontext från händelser som utlöser resan i redigeringsprogram för uttryck och personalisering

* Lyssna på en händelse under en resa

* Konfigurera händelser som ska utlösa en resa

* Identifiera användarreaktion på marknadskommunikation (t.ex. öppna e-postmeddelanden)

+++

+++Kommer min befintliga Adobe-organisation att påverkas av den här uppdateringen?

Din Adobe-organisation påverkas bara om du inte redan använder funktionen för händelsesökning. Om du redan använder upplevelsehändelser i [Experience Platform-datakällan](../datasource/adobe-experience-platform-data-source.md) har din Adobe-organisation fortfarande stöd för sökning efter upplevelsehändelser.

+++

+++Jag har en ny Adobe-organisation. Hur kan jag lösa mitt användningsfall som kräver data från upplevelsehändelser?

Det finns alternativa metoder och bästa praxis som omfattar upplevelsehändelser ovan för att uppnå önskade användningsfall.

+++

+++ Vad händer om alternativa metoder inte fungerar för min användning?

Om ditt fall inte kan lösas på något av de sätt som anges ovan, kontakta din Adobe-representant.

+++
