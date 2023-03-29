---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en innehållsexperiment
description: Lär dig skapa ett innehållsexperiment i era kampanjer
feature: A/B Testing
topic: Content Management
role: User
level: Beginner
keywords: innehåll, experiment, multipelt, målgrupp, behandling
hide: true
hidefromtoc: true
exl-id: bd35ae19-8713-4571-80bc-5f40e642d121
badge: label="Beta" type="Informative"
source-git-commit: 4f3d22c9ce3a5b77969a2a04dafbc28b53f95507
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 1%

---

# Skapa ett innehållsexperiment {#content-experiment}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment"
>title="Innehållsexperiment"
>abstract="Du kan välja att variera leveransinnehåll, ämne eller avsändare för att definiera flera leveransbehandlingar och fastställa den bästa kombinationen för era målgrupper."

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* [Kom igång med innehållsexperiment](get-started-experiment.md)
* **[Skapa ett innehållsexperiment](content-experiment.md)**
* [Förstå statistiska beräkningar](experiment-calculations.md)
* [Konfigurera experimentrapporter](reporting-configuration.md)
* [Statistiska beräkningar i experimentrapporten](experiment-report-calculations.md)

>[!ENDSHADEBOX]

Med Journey Optimizer Content Experiment kan ni definiera flera olika leveranssätt för att mäta vilken som fungerar bäst för er målgrupp. Du kan välja att variera leveransinnehåll, ämne eller avsändare. Intressemålgruppen fördelas slumpmässigt till varje behandling för att avgöra vilken som fungerar bäst med det angivna mätvärdet.

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

<!--
1. In the **[!UICONTROL Properties]** section, choose your **[!UICONTROL Campaign type]**:

    * **[!UICONTROL Scheduled]**: designed to send marketing messages and can be executed immediately or at a specified date.

    * **[!UICONTROL API-Triggered]**: designed to send transactional messages, such as password reset notifications or cart abandonment reminders. 
    
        To execute an API-triggered campaign, you will need to make an API call. [Learn more](api-triggered-campaigns.md)
-->
1. Välj kanal och sedan **[!UICONTROL Surface]** du vill använda för den här leveransen och klicka på **[!UICONTROL Create]**. Mer information finns i [Kanalytor](../configuration/channel-surfaces.md) sida.

   ![](assets/content_experiment_2.png)

1. Konfigurera **[!UICONTROL Properties]** av leveransen:
   * **[!UICONTROL Name]**
   * **[!UICONTROL Description]**

1. Definiera målgruppen. Om du vill göra det klickar du på **[!UICONTROL Select audience]** om du vill visa en lista över tillgängliga Adobe Experience Platform-segment. [Läs mer om segment](../segment/about-segments.md)

   I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer](get-started-experiment.md#content-experiment-work)

   ![](assets/content_experiment_16.png)

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

   Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts.

1. Konfigurera **[!UICONTROL Schedule]** -avsnitt. [Läs mer](create-campaign.md)

1. Klicka **[!UICONTROL Edit content]** för att personalisera leveransen. [Läs mer](../email/content-from-scratch.md)

   ![](assets/content_experiment_17.png)

1. Från **[!UICONTROL Edit content]** börjar du personalisera behandling A.

   För den här behandlingen ska vi specificera specialerbjudandet direkt i ämnesraden och lägga till personalisering.

   ![](assets/content_experiment_5.png)

## Konfigurera ditt innehållsexperiment {#configure-experiment}

1. När leveransen har anpassats går du till sammanfattningssidan för Campaign och klickar på **[!UICONTROL Create experiment]** för att börja konfigurera ert innehållsexperiment.

   ![](assets/content_experiment_3.png)

1. Välj **[!UICONTROL Success metric]** som du vill använda för ditt experiment.

   För vårt experiment väljer vi **[!UICONTROL Email open]** för att testa om mottagarna öppnar sina e-postmeddelanden om kampanjkoden finns på ärenderaden.

   ![](assets/content_experiment_11.png)

1. Klicka **[!UICONTROL Add treatment]** för att skapa så många nya behandlingar som behövs.

   ![](assets/content_experiment_8.png)

1. Ändra **[!UICONTROL Title]** för att särskilja dem bättre.

1. Välj om du vill lägga till en **[!UICONTROL Holdout]** gruppera efter leverans. Den här gruppen kommer inte att få något innehåll från den här kampanjen.

   Om du aktiverar alternativfältet tar det automatiskt 10 % av din befolkning. Du kan justera procentandelen om det behövs.

   ![](assets/content_experiment_12.png)

1. Du kan sedan välja att tilldela varje **[!UICONTROL Treatment]** eller bara aktivera **[!UICONTROL Distribute evenly]** växlingsfält.

   ![](assets/content_experiment_13.png)

1. Klicka **[!UICONTROL Create]** när konfigurationen är inställd.

## Utforma dina behandlingar {#treatment-experiment}

1. Från **[!UICONTROL Edit content]** väljer du behandling B för att ändra innehållet.

   Här väljer vi att inte ange erbjudandet i **[!UICONTROL Subject line]**.

   ![](assets/content_experiment_18.png)

1. Klicka **[!UICONTROL Edit email body]** för att ytterligare personalisera behandlingen B.

   ![](assets/content_experiment_9.png)

1. När du har utformat dina behandlingar klickar du på **[!UICONTROL More actions]** för att få tillgång till behandlingar: **[!UICONTROL Rename]**, **[!UICONTROL Duplicate]** och **[!UICONTROL Delete]**.

   ![](assets/content_experiment_7.png)

1. Om det behövs kan du komma åt **[!UICONTROL Experiment settings]** för att ändra din behandlingskonfiguration.

   ![](assets/content_experiment_19.png)

1. När meddelandeinnehållet har definierats klickar du på **[!UICONTROL Simulate content]** för att styra återgivningen av leveransen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../email/preview.md)

1. När ditt innehållsexperiment är klart kan du klicka på **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen. Varningar visas om någon parameter är felaktig eller saknas.

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

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="Resultatmått"
>abstract="Det totala värdet för resultatmåttet, som tidigare valts när du skapade dina experiment, delat med antalet profiler."

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
