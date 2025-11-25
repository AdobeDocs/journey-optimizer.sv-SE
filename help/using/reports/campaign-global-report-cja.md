---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig använda kampanjdata från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: b74d3137-2dd9-4302-a56e-73503d318d18
source-git-commit: 853e87cdd69a3fc180dcb1aa38b4b67f27977939
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 0%

---

# Kampanjrapport {#campaign-global-report-cja}

>[!BEGINSHADEBOX]

Du kommer åt din Campaign-rapport genom att klicka på knappen **[!UICONTROL Reports]** i kampanjen och sedan välja **[!UICONTROL View all time report]**. [Läs mer](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## KPI:er för kampanj {#campaign-kpis}

![](assets/cja-email-kpis.png)

**[!UICONTROL Campaign]** KPI:er (Key Performance Indicators) fungerar som en heltäckande kontrollpanel, som tillhandahåller en analys av viktig statistik som är kopplad till din kampanj. Detta omfattar detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande inblick i kampanjens effektivitet och nivå av engagemang.

KPI:erna varierar beroende på vilka kanaler som används i kampanjen.

+++ Läs mer om KPI:er för Campaign

* **[!UICONTROL Click through rate]**: Procentandel användare som interagerade med meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i meddelandet.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

+++

>[!AVAILABILITY]
>Samordnade kampanjer har endast stöd för kanalerna SMS, Email och Push. Andra kanaler (i appen, på webben, via direktreklam osv.) är inte tillgängliga i samordnade kampanjer och visas inte i rapporteringen.

### Översikt över Campaign {#delivery-global}

![](assets/cja-campaign-overview.png)

Tabellen **[!UICONTROL Campaign overview]** fungerar som en omfattande kontrollpanel med en detaljerad beskrivning av nyckeltal relaterade till kampanjen. Detta inkluderar viktig information som antalet profiler och de åtgärder som utförts, vilket ger en grundlig förståelse för kampanjens resultat och engagemang.

Observera att mätvärdena varierar beroende på vilka kanaler som används i kampanjen.

+++ Läs mer om mätvärden för Campaign-översikt

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Click through rate]**: Procentandel användare som interagerade med meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i meddelandet.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i meddelandet.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Outbound Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound Exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer. [Läs mer om hur undantag räknas](exclusion-list.md#exclusion-list).

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### Kampanjtrattresultat {#campaign-funnel}

![](assets/cja-campaign-funnel.png)

Diagrammet **[!UICONTROL Campaign funnel results]** innehåller en detaljerad analys av hur era profiler interagerar med dina meddelanden, och ger värdefulla insikter om hur olika profiler interagerade med ditt innehåll.

+++ Läs mer om resultatstatistik för Campaign-tratten

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i meddelandet.
+++

### Etikett för spårad länk {#campaign-track}

![](assets/cja-campaign-tracked-link.png)

Tabellen **[!UICONTROL Tracked link label]** ger viktiga insikter i besökarnas engagemang med de URL:er som ingår i dina meddelanden, och ger värdefull information om vilka länkar som lockar mest interaktion.

+++ Läs mer om spårning av etikettmått för länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i meddelandet.

+++

## Målöversikt {#targeting}

![](assets/cja-journey-targeting-overview.png)

Om du har konfigurerat **[!UICONTROL Targeting rules]** för ditt innehåll ger tabellen **[!UICONTROL Targeting overview]** en detaljerad vy över viktiga engagemangsmått, som visar hur målprofilerna för varje regel interagerade med ditt innehåll.

➡️ [Läs mer om målregler](../campaigns/campaigns-message-optimization.md)

+++ Läs mer om mätvärden för målinriktning

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina händelser.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Unique click rate]**: Procentandel målprofiler som klickade minst en gång.

+++
