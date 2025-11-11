---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Datainsamling
description: Läs mer om insamling av feedback från beslutsfattare
badge: label="Äldre" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Experienced
exl-id: 278cb255-439c-4ce8-ab59-07df79774b98
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---

# Insamling av data för beslutshantering {#data-collection}

## Om datainsamling

Du kan samla in feedback om offertbeslut i Adobe Experience Platform, inklusive vilka erbjudanden som visas och hur användarna interagerar med dem. Dessa data kan användas för:

* Disponerar [beslutsrapporter](../reports/get-started-events.md);
* Använder [regler för frekvensbegränsning](../offer-library/add-constraints.md#capping);
* Skapar [AI-modeller](../ranking/create-ranking-strategies.md) som kan användas som en rangordningsmetod.

## Olika typer av händelser

Hur data samlas in varierar beroende på vilken händelsetyp du vill hämta.

### Beslutshändelser

Varje gång en beslutshantering fattar ett beslut skickas information som rör den beslutshändelsen **automatiskt** till Adobe Experience Platform för alla kanaler. [Läs mer](../reports/get-started-events.md)

### Impression- och klickningshändelser

Avvisningar och klickningar för beslutshantering definieras enligt följande:

* En **intryckshändelse** inträffar när ett erbjudande visas för en användare.

* En **click**-händelse är när en användare klickar på eller interagerar med ett erbjudande.

Feedback om visningar och klickningar hämtas beroende på vilken [!DNL Journey Optimizer]-kanal som används.

**E-postmeddelanden** som skapats av [!DNL Journey Optimizer] **automatiskt** spårar visningar och klickningar.

De **flesta kanaler** kräver dock att visningar och klickdata skickas till Adobe Experience Platform som en **upplevelsehändelse**. Detta inkluderar:

* Webbsidor som använder [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"} för att återge erbjudanden

* Mobilappar som använder [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html){target="_blank"} för att återge erbjudanden - [Läs mer](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
* Kiosker
* Meddelanden som skickas via program från tredje part
  <!--Mobile push notifications authored by [!DNL Journey Optimizer] - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer/api-reference/#handlenotificationresponse){target="_blank"}-->

>[!NOTE]
>
>Kanaler som använder en API-begäran för beslut för att ta emot erbjudanden måste skicka in feedback som en upplevelsehändelse. Det innebär att om erbjudandet kräver anvisningar om hur det ska återges kan du anta att du ska skicka in feedback som upplevelsehändelser.

### Anpassade händelser

Synpunkter på anpassade evenemang som är kopplade till ett erbjudande kan skickas till Adobe Experience Platform enligt dina egna önskemål. Om ett erbjudande t.ex. innehåller flera knappar som *Intresserad*, *Inte intresserad* osv., kanske du vill skicka in dessa händelser separat, men de kan också skickas som upplevelsehändelser.

## Skicka feedback

Om du vill skicka in feedback-data måste du skapa en datauppsättning för att samla in händelser och, för varje händelsetyp, definiera en upplevelsehändelse som ska skickas till Adobe Experience Platform.

* Lär dig hur du skapar en datauppsättning där upplevelsehändelser samlas in i [det här avsnittet](create-dataset.md).

* Lär dig hur du definierar upplevelsehändelser som ska skickas in feedback-data i [det här avsnittet](schema-requirement.md).
