---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med andra lösningar
description: Läs mer om hur man integrerar Journey Optimizer med andra lösningar
feature: Integrations
role: User
level: Intermediate
exl-id: 700dc66e-ae2d-418f-b75e-ece15af57ab3
source-git-commit: 64e225cdc8615e51655ef550866b67ca249a7572
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---

# Integrering med andra lösningar {#integration}

Med Adobe Journey Optimizer kan ni enkelt hantera, behålla och exportera dessa data till plattformar eller system som ingår i er teknologi. Dessa integreringar hjälper er att hantera era specifika användningsfall och utöka Adobe Journey Optimizer funktionalitet.

>[!NOTE]
>
> Adobe Journey Optimizer bygger på Adobe Experience Platform och är internt anslutet till [Adobe kundprofil för realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}. Den här inbyggda datakällan är förkonfigurerad och utformad för att hämta och använda data från kundprofilen i realtid (kontrollera till exempel om den person som angav en resa är en klient eller inte). Ni kan använda profildata och Experience Events-data. [Läs mer](../datasource/adobe-experience-platform-data-source.md).
>

## Adobe Customer Journey Analytics {#integration-cja}

Du kan använda Customer Journey Analytics för att utföra avancerad analys av data som genererats av Journey Optimizer.

Journey Optimizer lagrar data i Adobe Experience Platform och med Customer Journey Analytics ger en helhetsbild av alla era resor, kampanjer och erbjudanden med automatiserad rapportdistribution och anpassade visualiseringar av data.

När ni har skapat er resa i Journey Optimizer kan Customer Journey Analytics hämta in data från plattformen för att ta fram rapporter och förstå hur varje kundinteraktion påverkar era resor.

Läs mer om [Journey Optimizer + Customer Journey Analytics](../reports/cja-ajo.md).

## Adobe Analytics {#integration-aa}

Ni kan utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till Adobe Experience Platform för att utlösa realtidsresor och automatisera kundernas upplevelser. Dessa data kan också användas för att skapa målgrupper som kan engageras med Journey Optimizer.

Läs mer om [Journey Optimizer + Analytics](../event/about-analytics.md).


## Adobe Experience Manager Assets {#integration-assets}

Sammanför arbetsflöden för marknadsföring och kreativitet med [!DNL Adobe Experience Manager Assets]. Inbyggt i [!DNL Adobe Journey Optimizer], åtkomst till [!DNL Adobe Experience Manager Assets] för att lagra, hantera, identifiera och distribuera digitala resurser. Det utgör en central databas med resurser som du kan använda för att fylla i dina meddelanden.

[!DNL Adobe Experience Manager Assets] kan nås direkt från [!DNL Adobe Journey Optimizer] via den vänstra menydelen **[!UICONTROL Assets]**.

Läs mer om [Journey Optimizer + Adobe Experience Manager Assets](../integrations/assets.md).


## Adobe Stock {#integration-stock}

Insticksprogrammet för integrering mellan [!DNL Adobe Stock] och [!DNL Adobe Journey Optimizer] e-post-Designer ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning i meddelanderedigering.

Med [!DNL Adobe Journey Optimizer] kan du överföra bilder till dina e-postmeddelanden direkt från [!DNL Adobe Stock] och lägga till dem i din **[!UICONTROL Assets]**-mapp med alternativet **[!UICONTROL Find Adobe Stock photos]**. Dessutom hjälper alternativet **[!UICONTROL Find Similar Stock photos]** dig att hitta bilder som matchar innehållet, färgen och kompositionen för resursen som används i leveransen.

Läs mer om [Journey Optimizer + Stock](../integrations/stock.md).


## Adobe Intelligent Services {#integration-intelligent-service}

Med Adobe Intelligent Services, som är inbyggd i kunddataplattformen i realtid, kan ni utnyttja kraften i artificiell intelligens och maskininlärning i kundupplevelsefall. På så sätt kan marknadsföringsanalytiker skapa prediktioner som är specifika för ett företags behov med hjälp av konfigurationer på företagsnivå utan behov av datavetenskap.

Med kundens AI kan varumärken skapa maskininlärningsbaserade poäng som är tillgängliga som profilattribut i Adobe Experience Platform och som kan användas för att personalisera en resa.

[Läs mer](../building-journeys/ai-services-overview.md).


## Adobe Campaign {#integration-ac}

Det finns en integrering om du har Adobe Campaign v7 eller v8. Använd den här integreringen för att skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Läs mer om [Journey Optimizer + Campaign](../building-journeys/ajo-ac.md).

Du kan också konfigurera en integrering med Adobe Campaign Standard för att skicka meddelanden på dina resor.

Läs mer om [Journey Optimizer + Campaign Standard](../building-journeys/using-adobe-campaign-standard.md).


## Adobe Workfront {#integration-workfront}

Använd Adobe Journey Optimizer-modulerna i Adobe Workfront för att skapa, läsa, uppdatera eller ta bort poster eller utföra ett anpassat API-anrop till Adobe Journey Optimizer API.

En översikt över det viktiga steget i den här integreringen finns tillgänglig [i blogginlägget](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/accelerating-go-to-market-how-workfront-workfront-fusion-aep-and/ba-p/653685){target="_blank"}.

Läs mer om Journey Optimizer + Adobe Workfront [i Adobe Workfront-dokumentationen](https://experienceleague.adobe.com/docs/workfront/using/adobe-workfront-fusion/fusion-apps-and-modules/adobe-journey-optimizer-modules.html){target="_blank"}.

## Egna kanaler {#integration-custom}

Om du använder ett system från en annan leverantör för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett system från en annan leverantör, ska du använda anpassade åtgärder för att ansluta till din resa. Du kan till exempel ansluta till följande system med anpassade åtgärder: Epsilon, Slack, [Adobe Developer](https://developer.adobe.com){target="_blank"}, Firebase osv.

Anpassade åtgärder är ytterligare åtgärder som definieras av tekniska användare och görs tillgängliga för marknadsförare. När de har konfigurerats visas de i den vänstra paletten på din resa i kategorin **[!UICONTROL Action]**. Läs mer på [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

Läs mer om [anpassade åtgärder](../action/about-custom-action-configuration.md).

## Externa datakällor {#integration-external-systems}

Med Journey Optimizer kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan ni till exempel berika era resor med data från ett externt bokningssystem.

Lär dig hur du använder externa datakällor för att definiera en anslutning till ett tredjepartssystem i [det här avsnittet](../datasource/external-data-sources.md).
