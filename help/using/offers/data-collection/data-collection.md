---
title: Datainsamling
description: Läs mer om insamling av feedback från beslutsfattare
feature: Offers
topic: Integrations
role: User
level: Intermediate
source-git-commit: c9e970bc231fc3d19f0243b71256ea0f5a981af7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Insamling av data för beslutshantering {#data-collection}

## Om datainsamling

Du kan samla in feedback från offera decisioningar i Adobe Experience Platform, inklusive vilka erbjudanden som visas och hur användare interagerar med dem. Dessa data kan användas för:
* Disponering [Beslutsfattarrapporter](../reports/get-started-events.md);
* Använda [frekvensbegränsning](../offer-library/add-constraints.md#capping) regler,
* Byggnad [AI-modeller](../ranking/create-ranking-strategies.md) som kan användas som en rangordningsmetod.

## Olika typer av händelser

Hur data samlas in varierar beroende på vilken händelsetyp du vill hämta.

### Beslutshändelser

Varje gång en beslutshantering fattar ett beslut är informationen om den beslutshändelsen **automatiskt** skickas till Adobe Experience Platform för alla kanaler. [Läs mer](../reports/get-started-events.md)

### Impression- och klickningshändelser

Avvisningar och klickningar för beslutshantering definieras enligt följande:

* An **intrycket** -händelsen är när ett erbjudande visas för en användare.

* A **klicka** händelsen är när en användare klickar på eller interagerar med ett erbjudande.

Hur man får in feedback om intryck och klick beror på [!DNL Journey Optimizer] kanal som används.

**E-post** skapad av [!DNL Journey Optimizer] **automatiskt** spåra visningar och klickningar.

Men **de flesta kanaler** kräver att man skickar in trycksaker och klickdata till Adobe Experience Platform som **upplevelsehändelse**. Det inkluderar:

* Webbsidor med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"} för att återge erbjudanden

* Mobilappar med [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html){target="_blank"} to render offers - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
* Kiosker
* Meddelanden som skickas via program från tredje part
   <!--Mobile push notifications authored by [!DNL Journey Optimizer] - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer/api-reference/#handlenotificationresponse){target="_blank"}-->

>[!NOTE]
>
>Kanaler som använder en API-begäran för beslut för att ta emot erbjudanden måste skicka in feedback som en upplevelsehändelse. Det innebär att om erbjudandet kräver anvisningar om hur det ska återges kan du anta att du ska skicka in feedback som upplevelsehändelser.

### Anpassade händelser

Synpunkter på anpassade evenemang som är kopplade till ett erbjudande kan skickas till Adobe Experience Platform enligt dina egna önskemål. Om ett erbjudande t.ex. innehåller flera knappar, som *Intresserad*, *Inte intresserad* och så vidare, du kanske vill skicka in dessa händelser separat, men de kan också skickas in som upplevelsehändelser. <!--Not sure to get that part. How feedback is collected in the first case, i.e. when events are sent in separately? Does it mean the customer just handles it the wau he wants?-->

## Skicka feedback

Om du vill skicka in feedback-data måste du skapa en datauppsättning för att samla in händelser och, för varje händelsetyp, definiera en upplevelsehändelse som ska skickas till Adobe Experience Platform.

* Lär dig hur du skapar en datauppsättning där upplevelsehändelser samlas in i [det här avsnittet](create-dataset.md).

* Lär dig hur du definierar upplevelsehändelser som ska skickas in feedback-data i [det här avsnittet](schema-requirement.md).

