---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med Customer Journey Analytics
description: Kom igång med Customer Journey Analytics
feature: Reporting
topic: Content Management
role: User
level: Beginner
exl-id: 5349b0cf-da4e-458c-89be-c75a38e4721a
source-git-commit: 0e45d6e4995f4f21dc5122203b715ae999e2b760
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Arbeta med [!DNL Customer Journey Analytics] {#cja-ajo}


[!DNL Journey Optimizer] integrering med [!DNL Customer Journey Analytics] ger en helhetsbild av alla era resor med automatiserad rapportdistribution och anpassade visualiseringar av data.

![](assets/cja.png)

När du har skapat din resa i [!DNL Journey Optimizer]kan du importera dina kunddata till [!DNL Customer Journey Analytics] för att ta fram rapporter och förstå effekten av varje interaktion en kund har med era resor.

➡️ [Upptäck Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html){target="_blank"}

>[!NOTE]
>
>Förutom den här integreringen kan du även exportera innehållet i Adobe Journey Optimizer datamängder till molnlagringsplatser och använda informationen i rapporterings- eller analyssyfte. [Lär dig hur du exporterar datauppsättningar till lagringsplatser i molnet](../data/export-datasets.md)
>
>Observera att exportfunktionen för datauppsättningar för närvarande är i betaversion och tillgänglig för alla Adobe Journey Optimizer-användare. Kontakta din Adobe-representant om du vill få åtkomst till mål om du inte redan har åtkomst.

Innan du använder [!DNL Customer Journey Analytics] För dina resor måste du först konfigurera den här integreringen:

1. [Skapa en anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html) in [!DNL Customer Journey Analytics] med **[!UICONTROL Dataset]** som du vill skicka till Adobe Experience Platform.

   Följande [!DNL Journey Optimizer] kan konfigureras:
   * [Resestegshändelse](../data/datasets-query-examples.md#journey-step-event): låter dig se vilka som är med på resorna och hur långt de kommer.
   * [Meddelandefeedback/spårningsdata](../data/datasets-query-examples.md#message-feedback-event-dataset): gör att du kan visa leveransinformation om meddelanden som skickas via [!DNL Journey Optimizer].
   * [Enhetsdata och resedatamängder](../data/datasets-query-examples.md#entity-dataset): låter dig söka efter egna namn och använda dem i din rapportering.

1. [Skapa en datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html) för att konfigurera de dimensioner och mätvärden som du vill använda för rapporten.

   Ni kan skapa Journey Optimizer-specifika mätvärden för att bättre återspegla era resedata. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/integrations/ajo.html#configure-the-data-view-to-accommodate-journey-optimizer-dimensions-and-metrics)

Använda [!DNL Journey Optimizer] med [!DNL Customer Journey Analytics] kan leda till vissa avvikelser i rapporteringsdata som orsakas av:

* **Båda [!DNL Journey Optimizer] och [!DNL Customer Journey Analytics] synkronisera data från Azure Data Lake Storage (ADLS) för rapportering.**

  Bearbetningstiden för inkommande data kan skilja sig något mellan produkterna. På grund av detta kanske data inte matchar när rapporter från ett visst datum visas till den aktuella dagen. Använd datumintervall exklusive den aktuella dagen om du vill minska avvikelsen.

* **I [!DNL Journey Optimizer] -rapporter innehåller Skickat-mått även Försök igen-mått.**

  **[!UICONTROL Retries]** kommer inte att inkluderas i **[!UICONTROL Sent]** mått in [!DNL Customer Journey Analytics]. Detta kommer att orsaka [!DNL Customer Journey Analytics] **[!UICONTROL Sent]** mått för att visa lägre värden än [!DNL Journey Optimizer]. Återförsöksdata konverteras dock till **[!UICONTROL Messages successfully sent]** eller **[!UICONTROL Bounces]** mätvärden.
Använd datumintervall från en vecka sedan eller till och med senare för att minska diskrepansen.

* **Rapporterna hanteras från en annan datakälla.**

  Detta kan leda till dataavvikelser på 1-2 % mellan produkterna.
