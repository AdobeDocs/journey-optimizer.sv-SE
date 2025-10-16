---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Get Started for Data Engineer
description: Som datatekniker får du lära dig mer om hur du arbetar med Journey Optimizer
feature: Get Started
role: Data Engineer
level: Intermediate
exl-id: 8beaafc2-e68d-46a1-be5c-e70892575bfb
source-git-commit: 6c73a1ee024ca61b30d71e77268e51b93576ae62
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 2%

---

# Kom igång med datatekniker {#data-engineer}

Som **Adobe Journey Optimizer datatekniker** kan du förbereda och underhålla kundprofildata för att driva upplevelser som är samordnade av [!DNL Journey Optimizer], modellera kund- och affärsdata i scheman och konfigurera källanslutningar för datainhämtning. Du kan börja arbeta med [!DNL Adobe Journey Optimizer] när [systemadministratören](administrator.md) har gett dig åtkomst och förberett miljön.


Lär dig hur du **identifierar data och skapar schema och datauppsättning** för att hämta data till Adobe Experience Platform på den här sidan.

>[!NOTE]
>
>Läs mer om **dataöverföring** i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html){target="_blank"}.

Steg för att skapa ett identitetsnamnutrymme och en datauppsättning som är aktiverad för profiler samt testprofiler beskrivs i avsnitten nedan:

1. **Skapa ett identitetsnamnområde**. I Adobe [!DNL Journey Optimizer] länkar **Identiteter** konsumenter över olika enheter och kanaler, vilket resulterar i ett identitetsdiagram. Det länkade identitetsdiagrammet används för att personalisera upplevelser baserat på interaktioner över alla era affärskontaktytor.  Läs mer om identiteter och identitetsnamnutrymmen [på den här sidan](../../audience/get-started-identity.md).

1. **Skapa ett schema** och aktivera det för profiler. Ett schema är en uppsättning regler som representerar och validerar datastrukturen och dataformatet. På en hög nivå ger scheman en abstrakt definition av ett objekt i verkligheten (till exempel en person) och ger en översikt över vilka data som ska inkluderas i varje instans av objektet (till exempel förnamn, efternamn, födelsedag o.s.v.).  Läs mer om scheman [på den här sidan](../../data/get-started-schemas.md).

1. **Skapa datauppsättningar** och aktivera dem för profiler. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). Datauppsättningar innehåller också metadata som beskriver olika aspekter av de data som lagras. När en datauppsättning har skapats kan du mappa den till ett befintligt schema och lägga till data i det. Läs mer om datauppsättningar [på den här sidan](../../data/get-started-datasets.md).

1. **Konfigurera källanslutningar**. Med Adobe Journey Optimizer kan data hämtas från externa källor samtidigt som du kan strukturera, märka och förbättra inkommande data med hjälp av plattformstjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lager, databaser och många andra. Läs mer om Source-anslutningar [på den här sidan](../get-started-sources.md).

1. **Skapa testprofiler**. Testprofiler krävs när [testläget](../../building-journeys/testing-the-journey.md) används i en resa och när du [förhandsgranskar och testar meddelanden](../../content-management/preview-test.md) innan du skickar iväg dem. Steg för att skapa testprofiler finns detaljerade [på den här sidan](../../audience/creating-test-profiles.md).


För att kunna skicka meddelanden under resor måste du konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. Läs mer [i det här avsnittet](../../configuration/about-data-sources-events-actions.md).

![](../assets/admin-menu.png)

* Med konfigurationen **Data Source** kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. Läs mer om datakällor [i det här avsnittet](../../datasource/about-data-sources.md).

* **Med händelser** kan du utlösa dina resor åt gången för att skicka meddelanden i realtid till den person som flyger in på resan. I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobes upplevelsedatamodell (XDM). Händelser kommer från API:er för direktuppspelning av inmatning för autentiserade och oautentiserade händelser (t.ex. Adobe Mobile SDK-händelser). Läs mer om händelserna [i det här avsnittet](../../event/about-events.md).

* [!DNL Journey Optimizer] har inbyggda meddelandefunktioner: du kan skapa dina meddelanden under en resa och utforma ditt innehåll. Om du använder ett tredjepartssystem för att skicka meddelanden, till exempel Adobe Campaign, skapar du en **anpassad åtgärd**. Läs mer om åtgärder i denna/detta [i detta avsnitt](../../action/action.md).
