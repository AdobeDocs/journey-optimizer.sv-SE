---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Get Started for Data Engineer
description: Som datatekniker får du lära dig mer om hur du arbetar med Journey Optimizer
level: Intermediate
exl-id: 8beaafc2-e68d-46a1-be5c-e70892575bfb
source-git-commit: 6f509a2518866b8e16a16a5550c41f7fb4154642
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Kom igång med datatekniker {#data-engineer}

Som en **Adobe Journey Optimizer datatekniker**, förbereda och underhålla kundprofildata för att driva upplevelser som orkestreras av [!DNL Journey Optimizer], modellera kund- och affärsdata i scheman och konfigurera källkopplingar för datainhämtning. Du kan börja arbeta med [!DNL Adobe Journey Optimizer] en gång [Systemadministratör](administrator.md) har gett dig åtkomst och förberett din miljö.


Lär dig hur **identifiera data och skapa schema och datauppsättning** för att få in data i Adobe Experience Platform på den här sidan.

>[!NOTE]
>
>Läs mer om **dataintag** in [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html){target=&quot;_blank&quot;}.

Steg för att skapa ett identitetsnamnutrymme och en datauppsättning som är aktiverad för profiler samt testprofiler beskrivs i avsnitten nedan:

1. **Skapa ett identitetsnamnutrymme**. I Adobe [!DNL Journey Optimizer], **Identiteter** länka konsumenter mellan olika enheter och kanaler. Resultatet blir ett identitetsdiagram. Det länkade identitetsdiagrammet används för att personalisera upplevelser baserat på interaktioner över alla era affärskontaktytor.  Läs mer om identiteter och identitetsnamnutrymmen [på den här sidan](../../segment/get-started-identity.md).

1. **Skapa ett schema** och aktivera det för profiler. Ett schema är en uppsättning regler som representerar och validerar datastrukturen och dataformatet. På en hög nivå ger scheman en abstrakt definition av ett objekt i verkligheten (till exempel en person) och ger en översikt över vilka data som ska inkluderas i varje instans av objektet (till exempel förnamn, efternamn, födelsedag o.s.v.).  Läs mer om scheman [på den här sidan](../../data/get-started-schemas.md).

1. **Skapa datauppsättningar** och aktivera det för profiler. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). Datauppsättningar innehåller också metadata som beskriver olika aspekter av de data som lagras. När en datauppsättning har skapats kan du mappa den till ett befintligt schema och lägga till data i det. Läs mer om datauppsättningar [på den här sidan](../../data/get-started-datasets.md).

1. **Konfigurera källkopplingar**. Med Adobe Journey Optimzer kan data hämtas från externa källor samtidigt som du kan strukturera, märka och förbättra inkommande data med hjälp av plattformstjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lager, databaser och många andra. Läs mer om källanslutningar [på den här sidan](../get-started-sources.md).

1. **Skapa testprofiler**. Testprofiler krävs när du använder [testläge](../../building-journeys/testing-the-journey.md) på en resa och [förhandsgranska och testa dina meddelanden](../../design/preview.md) före sändning. Steg för att skapa testprofiler är detaljerade [på den här sidan](../../segment/creating-test-profiles.md).


För att kunna skicka meddelanden under resor måste du dessutom konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. Läs mer [i det här avsnittet](../../configuration/about-data-sources-events-actions.md).

![](../assets/admin-menu.png)

* The **Datakälla** kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. Läs mer om datakällor [i det här avsnittet](../../datasource/about-data-sources.md).

* **Händelser** gör det möjligt för er att utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som kommer in på resan. I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK). Läs mer om evenemang [i det här avsnittet](../../event/about-events.md).

* [!DNL Journey Optimizer] följer med [inbyggda meddelandefunktioner](../../messages/get-started-content.md): kan ni skapa meddelanden inom en resa och utforma innehållet. Om du använder ett tredjepartssystem för att skicka meddelanden, till exempel Adobe Campaign, skapar du en **anpassad åtgärd**. Läs mer om åtgärder i det här [i det här avsnittet](../../action/action.md).
