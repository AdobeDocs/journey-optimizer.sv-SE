---
solution: Journey Optimizer
product: journey optimizer
title: Kanalnivårapporter
description: Lär dig använda data från översiktsrapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
badge: label="Beta" type="Informative"
source-git-commit: 2a5c04477b38e2fccdde86af56714261c6638160
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---

# Översiktsrapport {#channel-report-cja}

Översiktsrapporten ger användarna en detaljerad sammanfattning av trafik- och engagemangsmätningar för alla kampanjer och resor inom er miljö. Dessa mätvärden kombineras för att presentera enhetliga värden för åtgärder som kommer från olika kanaler, vilket omfattar olika kampanjer och resor.

Du kommer åt översiktsrapporten genom att gå till **Rapporter** menyn i **Resehantering** -avsnitt.

Rapportsidan visas med följande flikar:

* [Resor](#journey)
* [Kampanjer](#campaign)
* [Kanaler](#channel)

Mer information om arbetsytan i Customer Journey Analytics och hur du filtrerar och analyserar data finns i [den här sidan](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home).

## Högdagrar {#highlights}

![](assets/cja-highlights.png)

The **[!UICONTROL Highlights]** KPI:er fungerar som en omfattande kontrollpanel med en detaljerad beskrivning av nyckeltal för alla kampanjer och resor i er miljö, så att ni snabbt kan utvärdera resultatet och identifiera områden som ska förbättras.

+++ Läs mer om Highlights metrics

* **[!UICONTROL Journey engagement]**: Totalt antal personer som interagerat med de meddelanden som skickats från resan.

* **[!UICONTROL Journey Enters]**: Totalt antal personer som har nått ingångshändelsen för resan.

* **[!UICONTROL Journey Failures]**: Totalt antal enskilda resor som inte slutfördes.

* **[!UICONTROL Click through rate]**: Procentandel klick i meddelanden.

* **[!UICONTROL Click-through open rate (CTOR)]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som användaren klickat på ett innehåll i dina meddelanden.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

* **[!UICONTROL Unsubscribes]**: Antal klick på länken för att avbryta prenumerationen.

+++

## Resa {#journey}

![](assets/cja-channel-journeys.png)

The **[!UICONTROL Journey]** tabellen fungerar som en omfattande kontrollpanel som ger en analys av viktiga mått som rör din resa. Det innehåller detaljer som antalet profiler som angetts och antalet misslyckade enskilda resor, vilket ger en grundlig förståelse för hur effektiv resan är och hur hög den är.

Genom att klicka på namnet på en resa som listas i tabellen kan du enkelt utforska varje resa individuellt och få omedelbar tillgång till den fullständiga rapporten på en ny flik.

+++ Läs mer om resestatistik

* **[!UICONTROL Journey Enters]**: Totalt antal personer som har nått ingångshändelsen för resan.

* **[!UICONTROL Journey Exits]**: Totalt antal personer som avbrutit resan.

* **[!UICONTROL Journey Failures]**: Totalt antal enskilda resor som inte slutfördes.

+++

## Kampanjer {#campaign}

![](assets/cja-channel-campaigns.png)

The **[!UICONTROL Campaign]** tabellfunktioner som en heltäckande kontrollpanel, med en detaljerad översikt över viktiga mätvärden för er kampanj. Det innehåller viktiga data som antal profiler och utskick, vilket ger er en heltäckande insikt i kampanjens resultat och engagemangsnivåer.

Genom att klicka på namnet på en kampanj i den här tabellen kan du enkelt utforska varje enskild kampanj och få omedelbar tillgång till den fullständiga rapporten på en ny flik.

+++ Läs mer om Campaign-statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för varje kampanj.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som användaren klickat på ett innehåll i dina meddelanden.

+++

## Kanaler {#channel}

### Kanaler

![](assets/cja-channels.png)

The **[!UICONTROL Channels]** tabellen ger en detaljerad beskrivning av hur era profiler interagerar med era meddelanden på kanalnivå. På så sätt kan ni få djupare insikter i hur olika kanaler fungerar.

+++ Läs mer om kanalstatistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Click through rate]**: Procentandel klick i meddelanden.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för varje kampanj.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som användaren klickat på ett innehåll i dina meddelanden.

+++

### Utgående fel

![](assets/cja-channels-outbound-errors.png)

The **[!UICONTROL Outbound errors]** tabellen ger dig möjlighet att identifiera de exakta fel som har uppstått under sändningsprocessen, vilket ger en tydlig förståelse för eventuella problem som har uppstått.

### Utgående undantag

![](assets/cja-channels-outbound-excluded.png)

The **[!UICONTROL Outbound exclusions]** tabellen ger en heltäckande bild av de olika faktorer som har lett till att användarprofiler har utelämnats från målgruppen, vilket leder till att meddelandet inte tas emot.
