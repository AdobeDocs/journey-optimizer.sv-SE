---
title: Konflikthantering och -prioritering
description: Lär dig utnyttja Journey Optimizer verktyg för konfliktlösning och prioritering.
role: User
level: Beginner
badge: label="Begränsad tillgänglighet"
exl-id: 9dc0cd89-d29a-42d2-a73f-d95f9c39c86e
source-git-commit: dbe312f332031391c49a973f323994f860e354e3
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# Konflikthantering och -prioritering {#conflict-prioritization}

>[!AVAILABILITY]
>
>Konflikter och prioriteringsfunktioner är för närvarande tillgängliga i begränsad tillgänglighet för en viss kundgrupp. Observera att dessa funktioner gradvis kommer att lanseras för fler användare i framtiden. Kontakta ditt kontoteam om du vill bli tillagd i väntelistan för dessa funktioner.

I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Journey Optimizer har flera verktyg för konflikthantering och -prioritering.

## Konflikthantering och prioriteringsverktyg {#tools}

Med **konfliktidentifieringsverktyget** kan du identifiera potentiella överlappningar i resor och kampanjer. Detta är avgörande eftersom alltför många samtidiga kommunikationer kan leda till att kunderna blir trötta. Med Journey Optimizer kan du övervaka element som tidslinjer, målgruppsöverlappning och kanalkonfigurationer. Genom att identifiera konflikter tidigt kan ni förfina era kampanjer för att undvika att bombardera kunder med flera meddelanden samtidigt. [Lär dig hur du upptäcker potentiella konflikter i resor och kampanjer](conflicts.md)

Dessutom hjälper **prioritetspoäng** dig att styra vilka kampanjer eller resor som har företräde när en kund kvalificerar sig för flera kommunikationer. Detta är särskilt användbart för inkommande kanaler som webben och mobiler, där endast en kampanj kan visas åt gången. Genom att tilldela varje resa eller kampanj en prioritetspoäng kan ni se till att det viktigaste meddelandet levereras först. [Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer](priority-scores.md)

Med **resekap och skiljevägg** kan du begränsa hur ofta och hur många resor en kund kan ta sig in inom en viss tidsperiod. Du kan ställa in regler för att begränsa antalet reseposter för en profil eller begränsa antalet resor som en kund kan registrera samtidigt. Dessutom kan ni använda skiljedomsinställningar för att bestämma vilken resa en kund ska ange om de är kvalificerade för flera resor, och använda prioriteringspoäng för att avgöra vilken resa som passar bäst. [Lär dig hur du arbetar med capping och medling på resan](journey-capping.md)

Slutligen kan du även använda regeluppsättningar för att ange **frekvensbegränsning per kommunikationstyp** (t.ex. Försäljning, Marknadsföring) för att förhindra att kunder med liknande meddelanden överbelastas. Ni kan styra frekvensen över flera kanaler och automatiskt utesluta överbegärda profiler för att få en bättre kundupplevelse. [Lär dig arbeta med regeluppsättningar](../configuration/rule-sets.md)</li></ul>

Genom att utnyttja dessa funktioner kan ni säkerställa smidigare och mer riktad marknadsföring och leverera rätt budskap vid rätt tidpunkt samtidigt som ni undviker konflikter och överbelastningar.

## Skyddsritningar och begränsningar

**Frekvensbegränsning och gruppmålgrupper**

För frekvensbegränsning, både kanal och resa, och om målgruppen som används är en grupppublik, kommer det profilräkningsvärde som refereras vid tidpunkten för inträde i resan, eller meddelandemiljön för en kanalkommunikation att hämtas från den dagliga ögonblicksbilden som tas.

Detta kan vara problematiskt eftersom kunderna kan överskrida gränsvärdet för antal besökare om de har besökt en annan resa eller tagit emot en annan kommunikation mellan tidpunkten för den dagliga ögonblicksbilden och tidpunkten för den resa som anges (eller det meddelande som levereras).

**Frekvensbegränsning och strömmande målgrupper**

För direktuppspelande målgrupper kan det ta upp till två timmar för systemet att känna igen ett uppdaterat motvärde, och därför rekommenderar vi att man avskiljer kommunikationen och resorna minst två timmar om det är möjligt för att minska denna risk.

**Resornas starttid**

För att konflikthanteringen och prioriteringsfunktionerna ska fungera på rätt sätt rekommenderar vi att du ställer in kundens starttid minst 10 minuter framåt så att systemet kan uppdatera räknaren i enlighet med detta.

Om kunderna redan nått sin övre gräns när de går in på en resa tillåts de fortfarande inte komma in, men om de inte har nått sin övre gräns ökas inte antalet.

**Reseskiljeförfarande**

För närvarande stöds endast läsmålgruppsresor för skiljeväggar av resor. Skiljedomsinställningar kan inte utnyttjas för enställnings- eller målgruppsresor.
