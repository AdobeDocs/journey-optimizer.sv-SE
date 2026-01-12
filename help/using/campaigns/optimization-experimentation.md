---
solution: Journey Optimizer
product: journey optimizer
title: Experimentera med meddelandeoptimering
description: Lär dig hur du använder innehållsexperiment för att testa flera versioner av innehåll och avgöra vilka som fungerar bäst.
role: User
level: Intermediate
keywords: experiment, optimering, A/B-testning, innehållsexperiment, behandlingar
source-git-commit: fec72c63d41a41adce5107082c50a68a7b8c0af2
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Använd experimenterande {#experimentation}

>[!NOTE]
>
>På den här sidan finns en översikt över hur du använder experimenterande inom innehållsoptimering. Mer information om innehållsexperiment, bland annat konfigurationsalternativ, mätvärden och analyser finns i [Dokumentationen om innehållsexperiment](../content-management/get-started-experiment.md).

Experimentation gör att du kan testa flera versioner av innehåll för att avgöra vilken som fungerar bäst baserat på fördefinierade framgångsmått.

Följ stegen nedan när du vill konfigurera experimenterande.

Säg att du vill testa följande kampanjmeddelanden i en kampanj:

* **Behandling A**:&quot;20 % rabatt på ditt nästa köp&quot;
* **Behandling B**:&quot;Fri frakt för beställningar över 50 USD&quot;
* **Behandling C**: &quot;Hämta ditt presentkort på 10 USD&quot;

Följ stegen nedan om du vill konfigurera experimenterande och avgöra vilket meddelande som ger flest inköp.

1. Skapa en [resa](../building-journeys/journey-gs.md#jo-build) eller en [kampanj](../campaigns/create-campaign.md).

   >[!NOTE]
   >
   >Om du befinner dig på en resa lägger du till en **[!UICONTROL Action]**-aktivitet, väljer en kanalaktivitet och sedan **[!UICONTROL Configure action]**. [Läs mer](../building-journeys/journey-action.md#add-action)

1. På fliken **[!UICONTROL Actions]** väljer du två inkommande åtgärder, till exempel [kodbaserad upplevelse](../code-based/get-started-code-based.md) och [I appen](../../rp_landing_pages/in-app-landing-page.md).

1. Välj **[!UICONTROL Optimization]** i avsnittet **[!UICONTROL Create experiment]**.

   ![](assets/msg-optimization-select-experiment.png){width=85%}

1. Designa och konfigurera ditt innehållsexperiment som du vill. [Lär dig hur](../content-management/content-experiment.md)

   ![](assets/msg-optimization-create-experiment.png){width=85%}

   När experimentet har definierats gäller det alla åtgärder som har infogats i kampanjen eller genom **[!UICONTROL Action]**-aktiviteten, vilket innebär att samma kunder ser samma erbjudanden på alla ytor.

   >[!NOTE]
   >
   >Du kan välja andra åtgärder: experimentet gäller för alla åtgärder som läggs till i kampanjen eller för resan [Åtgärdsaktivitet](../building-journeys/journey-action.md).

1. [Aktivera](review-activate-campaign.md) din resa eller kampanj.

När resan/kampanjen är live tilldelas användarna slumpvis olika innehållsvariationer. [!DNL Journey Optimizer] spårar vilka varianter som driver fler inköp och ger åtgärdbara insikter.

Följ kampanjens framgångar med rapporterna om [kundresan](../reports/journey-global-report-cja.md) och [kampanjen](../reports/campaign-global-report-cja-experimentation.md). <!--Link to Experimentation journey reportis missing-->

