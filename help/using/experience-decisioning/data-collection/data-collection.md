---
title: Datainsamling
description: Läs mer om insamling av feedback från beslutsfattare
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 32e3a5b9-0633-48df-95b5-c03536be23a1
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# Insamling av data för beslutshantering {#data-collection}

## Om datainsamling

Du kan samla in feedback om offertbeslut i Adobe Experience Platform, inklusive vilka erbjudanden som visas och hur användarna interagerar med dem. Dessa data kan användas för:

* Disponerar [beslutsrapporter](../cja-reporting.md);
* Använder [begränsning](../items.md#capping)-regler;
* Skapar [AI-modeller](../ranking/ai-models.md) som kan användas som en rangordningsmetod.

## Olika typer av händelser

Hur data samlas in varierar beroende på vilken händelsetyp du vill hämta.

### Beslutshändelser

Varje gång ett beslut fattas, skickas information om den beslutshändelsen **automatiskt** till Adobe Experience Platform. <!--TBC + link-->

### Impression- och klickningshändelser

Avvisningar och klickningar för beslutshantering definieras enligt följande:

* En **intryckshändelse** inträffar när ett erbjudande visas för en användare.

* En **click**-händelse är när en användare klickar på eller interagerar med ett erbjudande.

Feedback om visningar och klickningar hämtas beroende på vilken [!DNL Journey Optimizer]-kanal som används.

**E-postmeddelanden** som skapats av [!DNL Journey Optimizer] **automatiskt** spårar visningar och klickningar.

De **flesta kanaler** kräver dock att visningar och klickdata skickas till Adobe Experience Platform som en **upplevelsehändelse**. Detta inkluderar:

* Webbsidor som använder [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE){target="_blank"} för att återge erbjudanden

* Mobilappar som använder [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=sv-SE){target="_blank"} för att återge erbjudanden - [Läs mer](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
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
