---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med andra lösningar
description: Läs mer om hur man integrerar Journey Optimizer med andra lösningar
topic: Content Management
role: User
level: Intermediate
exl-id: 700dc66e-ae2d-418f-b75e-ece15af57ab3
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Integrera med andra lösningar {#integration}

Med Adobe Journey Optimizer kan ni enkelt hantera, behålla och exportera dessa data till plattformar eller system som ingår i er teknologi. Dessa integreringar hjälper er att hantera era specifika användningsfall och utöka Adobe Journey Optimizer funktionalitet.

>[!NOTE]
>
> Adobe Journey Optimizer är uppkopplat till Adobe Experience Platform [Adobe kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}. Den här inbyggda datakällan är förkonfigurerad och utformad för att hämta och använda data från kundprofilen i realtid (kontrollera till exempel om den person som angav en resa är en klient eller inte). Ni kan använda profildata och Experience Events-data. [Läs mer](../datasource/adobe-experience-platform-data-source.md).
>

## Adobe Customer Journey Analytics{#integration-cja}

Du kan använda Customer Journey Analytics för att utföra avancerad analys av data som genererats av Journey Optimizer.

Journey Optimizer lagrar data i Adobe Experience Platform och med Customer Journey Analytics ger ni en helhetsbild av alla era resor, kampanjer och erbjudanden med automatiserad rapportdistribution och anpassade visualiseringar av data.

När ni har skapat er resa i Journey Optimizer kan Customer Journey Analytics hämta in data från plattformen för att ta fram rapporter och förstå hur varje kundinteraktion påverkar era resor.

Läs mer om [Journey Optimizer + Customer Journey Analytics](../reports/cja-ajo.md).

## Adobe Analytics{#integration-aa}

Ni kan utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till Adobe Experience Platform för att utlösa realtidsresor och automatisera kundernas upplevelser. Dessa data kan också användas för att skapa målgrupper som kan engageras med Journey Optimizer.

Läs mer om [Journey Optimizer + Analytics](../event/about-analytics.md).


## Adobe Experience Manager Assets Essentials{#integration-assets}

Samla marknadsförings- och kreativa arbetsflöden med [!DNL Adobe Experience Manager Assets Essentials]. Inbyggt i [!DNL Adobe Journey Optimizer], åtkomst [!DNL Assets Essentials] att lagra, hantera, identifiera och distribuera digitala resurser. Det utgör en central databas med resurser som du kan använda för att fylla i dina meddelanden.

[!DNL Adobe Experience Manager Assets Essentials] kan nås direkt från [!DNL Adobe Journey Optimizer] via den vänstra menyn **[!UICONTROL Assets]** -avsnitt.

Läs mer om [Journey Optimizer + Assets Essentials](../email/assets-essentials.md).


## Adobe Stock{#integration-stock}

The [!DNL Adobe Stock] och [!DNL Adobe Journey Optimizer] Integrationspluginen för e-postdesignern ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning i meddelanderedigering.

Med [!DNL Adobe Journey Optimizer]kan du överföra bilder till e-postmeddelanden direkt från [!DNL Adobe Stock] och lägga in **[!UICONTROL Assets]** mapp med **[!UICONTROL Find Adobe Stock photos]** alternativ. Dessutom är **[!UICONTROL Find Similar Stock photos]** kan du söka efter bilder som matchar innehållet, färgen och kompositionen för resursen som används i leveransen.

Läs mer om [Journey Optimizer + Stock](../email/stock.md).


## Adobe Intelligent Services{#integration-intelligent-service}

Adobe Intelligent Services som är inbyggt i kunddataplattformen i realtid gör att ni kan utnyttja kraften i artificiell intelligens och maskininlärning i kundupplevelsefall. På så sätt kan marknadsföringsanalytiker skapa prediktioner som är specifika för ett företags behov med hjälp av konfigurationer på företagsnivå utan behov av datavetenskaplig expertis.

Med kundens AI kan varumärken skapa maskininlärningsbaserade poäng som är tillgängliga som profilattribut i Adobe Experience Platform och som kan användas för att personalisera en resa.

[Läs mer](../building-journeys/ai-services-overview.md).


## Adobe Campaign{#integration-ac}

Det finns en integrering om du har Adobe Campaign v7 eller v8. Använd den här integreringen för att skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Läs mer om [Journey Optimizer + Campaign](../building-journeys/ajo-ac.md).

Du kan också konfigurera en integrering med Adobe Campaign Standard för att skicka meddelanden på dina resor.

Läs mer om [Journey Optimizer + Campaign Standard](../building-journeys/ajo-ac.md).

## Egna kanaler{#integration-custom}

Om du använder ett system från en annan leverantör för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett system från en annan leverantör, ska du använda anpassade åtgärder för att ansluta till din resa. Du kan till exempel ansluta till följande system med anpassade åtgärder: Epsilon, Slack, [Adobe Developer](https://developer.adobe.com){target="_blank"}, Firebase osv.

Anpassade åtgärder är ytterligare åtgärder som definieras av tekniska användare och görs tillgängliga för marknadsförare. När de är konfigurerade visas de i den vänstra paletten på din resa i **[!UICONTROL Action]** kategori. Läs mer i [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

Läs mer om [anpassade åtgärder](../action/about-custom-action-configuration.md).

## Externa datakällor{#integration-external-systems}

Med Journey Optimizer kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan ni till exempel berika era resor med data från ett externt bokningssystem.

Lär dig hur du använder externa datakällor för att definiera en anslutning till ett tredjepartssystem i [det här avsnittet](../datasource/external-data-sources.md).
