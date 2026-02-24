---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: be05bb72ace2e2084675f4278501a520d592e304
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 0%

---


# Kom igång med målgrupper {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="Målgrupp"
>abstract="Genom att utnyttja kundprofildata i realtid kan Adobe Experience Platform enkelt skapa segmentdefinitioner för att skapa målgrupper som fångar upp kundernas unika beteenden och önskemål."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="Välj kampanjmålgrupp"
>abstract="I den här listan visas alla tillgängliga Adobe Experience Platform-målgrupper. Välj målgrupp för er kampanj. Meddelandet som konfigurerats i kampanjen skickas till alla personer som tillhör den valda målgruppen. [Läs mer om målgrupper](../audience/about-audiences.md)"

Målgrupper är samlingar av personer som har liknande beteenden och/eller egenskaper. De konfigureras och underhålls centralt på Adobe Experience Platform med Adobe Experience Platform Segmentation Service och är tillgängliga inom Journey Optimizer för att aktiveras under resor och kampanjer.

Adobe Journey Optimizer tillhandahåller robusta verktyg för att skapa, hantera och berika målgrupper för att förbättra marknadsföringen. I kombination med Adobe Real-Time Customer Data Platform kan ni med Journey Optimizer skikta in era målgrupper för mer komplex segmentering och dela målgrupper dubbelriktat med andra Adobe Experience Cloud-lösningar.

När dataströmmar i realtid eller batchöverföringar inträffar uppdateras datauppsättningarna och Journey Optimizer flyttar dynamiskt individer in och ut ur målgrupper och resor i realtid.

>[!BEGINSHADEBOX]

Den här dokumentationen innehåller information om hur du arbetar med målgrupper inom [!DNL Adobe Journey Optimizer]. Detaljerad information om Audience-portalen och målgrupper finns i dokumentationen för Adobe Experience Platform Segmentation-tjänsten. Mer information finns i följande avsnitt:

* [Användargränssnittsguide för segmenteringstjänst](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview){target="_blank"}

* [Segmenteringstjänst - Vanliga frågor](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq){target="_blank"}

>[!ENDSHADEBOX]

## Sök bland målgrupper {#browse}

Publiker är tillgängliga på menyn **[!UICONTROL Customer]** > **[!UICONTROL Audiences]**.

En kontrollpanel visar överlappningar mellan viktiga målgrupper och har stöd för att utforska värdefulla målgruppstrender. Till exempel kan publikens storlek ändras under en viss tidsperiod eller plötsliga toppar hos målgrupper markera händelser eller händelser som får en målgrupp att krympa eller växa, som ett lyckat erbjudande.

![](assets/audiences-overview.png)

Från Audience Portal kan ni enkelt hantera, hitta och utforska målgrupper med standardiserade etiketter, styrningsfunktioner, sökbara mappar och taggar.

Mer information om hur du arbetar med målgrupper i publikportalen finns i [dokumentationen för Adobe Experience Platform segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.

## Målgruppstyper {#types}

Målgrupper kan genereras på olika sätt:

* **Segmentdefinitioner**: Skapa en ny målgruppsdefinition med Adobe Experience Platform segmenteringstjänst. Målgrupper genereras från segmentdefinitioner och uppdateras vid olika tidpunkter beroende på utvärderingstyp:

   * Direktuppspelningssegmentering: Målgrupperna uppdateras i realtid när nya data flödar in, vilket ger kontinuerlig relevans baserat på användaraktivitet.
   * Gruppsegmentering: Målgrupperna uppdateras var 24:e timme och en ögonblicksbild av profilerna sparas med ett fast intervall. Vid användning på resor kan nykvalificerade segmentmedlemmar inte visas förrän nästa ögonblicksbild. [Läs mer om timing](../building-journeys/audience-qualification-events.md#timing-segment-membership).
   * Edge Segmentering: Målgrupperna utvärderas direkt i farten, vilket möjliggör personalisering i realtid.

  [Lär dig hur du skapar segmentdefinitioner](creating-a-segment-definition.md)

* **Anpassad överföring**: Importera en målgrupp med en CSV-fil. [Lär dig skapa anpassade överförda målgrupper](custom-upload.md)

* **Målgruppsdisposition**: Skapa ett dispositionsarbetsflöde för att kombinera befintliga målgrupper till en visuell arbetsyta och tillämpa åtgärder som rangordning, delning och förening för att skapa nya målgrupper. [Lär dig hur du arbetar med målgruppsdisposition](get-started-audience-orchestration.md)

* **Federated Audience Composition**: Federate-datauppsättningar direkt från ditt befintliga datalager för att skapa och berika Adobe Experience Platform-målgrupper och attribut i ett och samma system. [Lär dig hur du arbetar med federerad målgruppskomposition](federated-audience-composition.md).

## Rikta målgrupper på resor och kampanjer {#target-audiences}

När era målgrupper är klara kan ni välja dem när ni bygger resor eller skapar kampanjer, så att ni kan nå rätt personer vid rätt tidpunkt med relevanta meddelanden. [Läs mer om målgruppsaktivering i Journey Optimizer](target-audiences.md).

## Instruktionsvideo {#video}

Läs om enhetliga kundprofiler och målgrupper i Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/3432671?quality=12)
