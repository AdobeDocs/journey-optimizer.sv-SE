---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en innehållsexperiment
description: Lär dig skapa ett innehållsexperiment i era kampanjer
feature: A/B Testing
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: bd35ae19-8713-4571-80bc-5f40e642d121
source-git-commit: ef838945e0c3595de8ad920203b278bb51671d16
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 0%

---

# Skapa ett innehållsexperiment {#content-experiment}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment"
>title="Innehållsexperiment"
>abstract="Du kan välja att variera leveransinnehåll, ämne eller avsändare för att definiera flera leveransbehandlingar och fastställa den bästa kombinationen för era målgrupper."

>[!AVAILABILITY]
>
>The **Content Experiment** är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

Använd Journey Optimizer Content Experiment för att definiera olika leveranssätt. Intressemålgruppen fördelas slumpmässigt till varje behandling för att avgöra vilken som fungerar bäst med avseende på intressemätningen. Du kan välja att variera leveransinnehåll, ämne eller avsändare.

>[!NOTE]
>
>Innan du börjar med Content Experiment bör du kontrollera att rapportkonfigurationen är inställd för dina anpassade datauppsättningar. Läs mer i [det här avsnittet](reporting-configuration.md).

I exemplet nedan har leveransmålet delats upp i två grupper, som var och en representerar 45 % av målpopulationen, och en slutgruppsgrupp på 10 % som inte får leveransen.

Varje person i målgruppen får en version av ett e-postmeddelande med en ämnesrad som är en av följande två:

* en som direkt marknadsför ett 10-procentigt erbjudande på den nya samlingen och en bild.
* den andra bara ger ut ett specialerbjudande utan att ange 10 % rabatt utan någon bild.

Målet här är att se om mottagarna kommer att interagera med e-postmeddelandet beroende på det mottagna experimentet. Vi väljer därför **[!UICONTROL Email Opens]** som det primära målmåttet i detta innehållsexperiment.

![](assets/content_experiment.png)

## Skapa en kampanj {#campaign-experiment}

1. Från **[!UICONTROL Campaigns]** sida, klicka **[!UICONTROL Create campaign]**.

   ![](assets/content_experiment_1.png)

1. Välj kanal och sedan **[!UICONTROL Surface]** du vill använda för den här leveransen. Mer information finns i [Kanalytor](../configuration/channel-surfaces.md) sida.

   ![](assets/content_experiment_2.png)

1. Klicka **[!UICONTROL Create]**.

1. Konfigurera **[!UICONTROL Properties]** av leveransen:
   * **[!UICONTROL Title]**
   * **[!UICONTROL Description]**
   * **[!UICONTROL Category]**: **[!UICONTROL Marketing]** / **[!UICONTROL Transactional]**

1. Om du vill starta ditt innehållsexperiment växlar du **[!UICONTROL Content experiment]** alternativ. The **[!UICONTROL Content experiment]** visas.

   ![](assets/content_experiment_3.png)

1. Definiera målgruppen. Om du vill göra det klickar du på **[!UICONTROL Select audience]** om du vill visa en lista över tillgängliga Adobe Experience Platform-segment. [Läs mer om segment](../segment/about-segments.md)

   I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer](get-started-experiment.md#content-experiment-work)

1. Konfigurera avsnittet Schema om du vill köra kampanjen på ett visst datum eller med en återkommande frekvens. [Läs mer](create-campaign.md)

1. Klicka **[!UICONTROL Edit content]** för att personalisera din egen **[!UICONTROL Treatments]**.

   ![](assets/content_experiment_4.png)

## Skapa egna behandlingar {#treatment-experiment}

1. Från **[!UICONTROL Edit content]** börja personalisera din behandling A.

   Vi kommer att specificera specialerbjudandet direkt i ämnesraden.

   ![](assets/content_experiment_5.png)

1. När du har designat din första behandling kan du **[!UICONTROL More actions]** knapp, klicka **[!UICONTROL Duplicate]**.

   Du kan också välja att starta en ny behandling från början genom att klicka på **[!UICONTROL Content experiment]** knapp ![](assets/content_experiment_16.png) för att komma åt de avancerade alternativen och sedan **[!UICONTROL Add treatment]**.

   ![](assets/content_experiment_7.png)

1. Ändra **[!UICONTROL Title]** för att särskilja dem bättre.

   ![](assets/content_experiment_8.png)

1. Anpassa din andra behandling efter behov.

   Här väljer vi att inte ange erbjudandet i **[!UICONTROL Subject line]**.

   ![](assets/content_experiment_9.png)

När du har anpassat dina behandlingar kan du börja konfigurera ditt innehållsexperiment.

## Konfigurera ditt innehållsexperiment {#configure-experiment}

1. När båda leveranserna är personaliserade kan du **[!UICONTROL Edit content]** fönster, markera **[!UICONTROL Configure content experiment]**.

   ![](assets/content_experiment_10.png)

1. Välj de mål som du vill ställa in för ditt experiment.

   För vårt experiment väljer vi **[!UICONTROL Email open]** för att testa om mottagarna öppnar sina e-postmeddelanden om kampanjkoden finns på ärenderaden.

   ![](assets/content_experiment_11.png)

1. Välj om du vill lägga till en **[!UICONTROL Holdout]** gruppera efter leverans. Den här gruppen kommer inte att få något innehåll från den här kampanjen.

   Om du aktiverar alternativfältet tar det automatiskt 10 % av din befolkning. Du kan justera procentandelen om det behövs.

   ![](assets/content_experiment_12.png)

1. Du kan sedan välja att tilldela varje **[!UICONTROL Treatment]** eller bara aktivera **[!UICONTROL Distribute evenly]** växlingsfält.

   ![](assets/content_experiment_13.png)

1. Klicka **[!UICONTROL Save]** när konfigurationen är inställd.

1. När ditt innehållsexperiment är klart kan du klicka **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen. Varningar visas om någon parameter är felaktig eller saknas.

   ![](assets/content_experiment_15.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]** för att starta den.

   ![](assets/content_experiment_14.png)

När du har konfigurerat dina experiment och kampanjer kan du följa resultatet av leveransen med Campaign-rapporten.

## Målrapport {#objectives-global}

>[!AVAILABILITY]
>
>Funktionen för innehållsexperiment är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

![](assets/performance_report.gif)

The **[!UICONTROL Objectives]** kan ni finjustera era leveransrapporter bättre genom att rikta in er på ett specifikt mätvärde.

The **[!UICONTROL Objectives]** listade är länkade till **[!UICONTROL Datasets]** som definierar en anslutning till ett system för att hämta ytterligare information. En lista med inbyggda **[!UICONTROL Objectives]** är tillgängligt, men du kan lägga till egna genom att lägga till nya **[!UICONTROL Dataset]**. För det detaljerade förfarandet, se [section](reporting-configuration.md).

När du har valt de mål som du vill ha som mål för **[!UICONTROL Performance overview]** och **[!UICONTROL Campaign objective]** -widgetar ger en detaljerad sammanfattning av leveransresultatet.

Med **[!UICONTROL Campaign objective]** kan du också välja att jämföra huvudmålet med ett annat mätvärde.

Observera att varje widget kan storleksändras och tas bort om det behövs. Mer information finns i [section](../reports/global-report.md#modify-dashboard).

## Experimentationsrapport {#experimentation-global}

>[!AVAILABILITY]
>
>Funktionen för innehållsexperiment är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

![](assets/experimentation_report_3.png)

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Experimentation]** innehåller huvudinformationen om hur varje variant fungerar och om det finns en bästa utförare.

Observera att det kan ta en stund att definiera den bästa utföraren, men den representeras av den här ikonen ![](assets/experimentation_report_1.png).

The **[!UICONTROL Experiment result]** widgeten anger prestanda för varje variant. Du kan ändra din baslinje genom att välja en av behandlingarna i **[!UICONTROL Baseline]** listrutan. Den bästa behandlingen visas med en stjärnikon.

Tabellen visar följande mått:

* **[!UICONTROL Profiles]**: Antal profiler som är avsedda för denna behandling.

* **[!UICONTROL Unique outbound clicks]**: Totalt antal klick i utgående kanaler.

* **[!UICONTROL Count per profile]**: Det totala värdet för det experimentella målmåttet delat med antalet profiler.

* **[!UICONTROL Confidence interval]**: Procentskillnad i prestanda mellan baslinjen och den bästa behandlingen. [Läs mer](../campaigns/experiment-calculations.md#confidence-intervals).

* **[!UICONTROL Average lift]**: Procentuell förbättring av konverteringsgraden för en given behandling jämfört med baslinjen. [Läs mer](../campaigns/experiment-calculations.md#understand-lift)

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../campaigns/experiment-calculations.md#understand-confidence)

En djupdykning i dessa resultat och hur du tolkar dem finns i [den här sidan](../campaigns/get-started-experiment.md#interpret-results).
