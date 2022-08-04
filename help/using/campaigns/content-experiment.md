---
title: Skapa ett innehållsexperiment
description: Lär dig skapa ett innehållsexperiment i era kampanjer
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 0036c905b9344a6f99e8525acbe9caab5932f361
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Skapa ett innehållsexperiment {#content-experiment}

>[!AVAILABILITY]
>
>Funktionen för innehållsexperiment är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

Med funktionen för innehållsexperiment kan du definiera flera olika leveranssätt. Intressemålgruppen fördelas slumpmässigt till varje behandling för att avgöra vilken som fungerar bäst med avseende på intressemätningen. Du kan välja att ändra e-postmeddelandets innehåll, ämne eller avsändare.

I exemplet nedan har leveransmålet delats upp i två grupper, som var och en representerar 45 % av målpopulationen, och en slutgruppsgrupp på 10 % som inte får leveransen.

Varje person i målgruppen får en version av e-postmeddelandet med en ämnesrad som är en av följande två:

* en som direkt marknadsför ett 10-procentigt erbjudande på den nya samlingen och en bild.
* den andra bara ger ut ett specialerbjudande utan att ange 10 % rabatt utan någon bild.

Målet här är att se om mottagarna kommer att interagera med e-postmeddelandet beroende på det mottagna experimentet. Vi väljer därför **[!UICONTROL Email Opens]** som det primära målmåttet i detta innehållsexperiment.

![](assets/content_experiment.png)

## Skapa en kampanj {#campaign-experiment}

1. Från **[!UICONTROL Campaigns]** sida, klicka **[!UICONTROL Create Campaign]**.

   ![](assets/content_experiment_1.png)

1. Välj **[!UICONTROL Email]** sedan **[!UICONTROL Surface]** du vill använda för den här leveransen. Mer information finns i [Kanalytor](../configuration/channel-surfaces.md) sida.

   ![](assets/content_experiment_2.png)

1. Klicka på **[!UICONTROL Create]**.

1. Konfigurera **[!UICONTROL Properties]** av leveransen:
   * **[!UICONTROL Title]**
   * **[!UICONTROL Description]**
   * **[!UICONTROL Category]**: **[!UICONTROL Marketing]** / **[!UICONTROL Transactional]**

1. Om du vill starta ditt innehållsexperiment växlar du **[!UICONTROL Content experiment]** alternativ. The **[!UICONTROL Content experiment]** visas.

   ![](assets/content_experiment_3.png)

1. Konfigurera **[!UICONTROL Audience]** och **[!UICONTROL Schedule]** parametrar för leveranser. [Läs mer](create-campaign.md)

1. Klicka **[!UICONTROL Edit content]** för att personalisera din egen **[!UICONTROL Treatments]**.

   ![](assets/content_experiment_4.png)

## Skapa egna behandlingar {#treatment-experiment}

1. Från **[!UICONTROL Edit content]** fönster, lägga till **[!UICONTROL Subject line]** för din behandling Ett e-postmeddelande och klicka **[!UICONTROL Save]**.

   För denna behandling anger vi erbjudandet direkt i ämnesraden.

   ![](assets/content_experiment_5.png)

1. Klicka **[!UICONTROL Email designer]** för att personalisera era leveranser.

   ![](assets/content_experiment_6.png)

1. När du har utformat e-postmeddelandet klickar du på **[!UICONTROL Save]** och gå tillbaka till **[!UICONTROL Edit content]** för att skapa Behandling B.

1. Från **[!UICONTROL More actions]** knapp, klicka **[!UICONTROL Duplicate]**.

   Du kan också välja att starta en ny behandling från början genom att klicka på **[!UICONTROL Content experiment]** för att komma åt de avancerade alternativen och sedan **[!UICONTROL Add treatment]**.

   ![](assets/content_experiment_7.png)

1. Ändra **[!UICONTROL Title]** för att särskilja dem bättre.

   ![](assets/content_experiment_8.png)

1. Välj den e-postleverans som är länkad till din nya e-postleverans **[!UICONTROL Treatment]**.

1. Lägg till **[!UICONTROL Subject line]** för leverans.

   För den här behandlingen väljer vi att inte ange erbjudandet i **[!UICONTROL Subject line]**.

   ![](assets/content_experiment_9.png)

1. Klicka **[!UICONTROL Email designer]** för att ytterligare personalisera leveransen av behandling B vid behov.

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

## Experimentationsrapport {#experimentation-report}

![](assets/experimentation_report_3.png)

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Experimentation]** innehåller huvudinformationen om hur varje variant fungerar och om det fanns en bästa utförare under testet.

Mer information om den här rapporten finns i [Global kampanjrapport](../campaigns/content-experiment.md#experimentation-report) sida.

