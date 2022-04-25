---
title: Leverera erbjudanden med Edge Decisioning API
description: Med Adobe Experience Platform Web SDK kan du hämta och återge anpassade erbjudanden som du har skapat med hjälp av API:er eller erbjudandebiblioteket.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: b02981f2c0cf74c8dba657570157709bc422d94c
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 1%

---


# Leverera erbjudanden med Edge Decisioning API {#edge-decisioning-api}

## Komma igång och krav {#aep-web-sdk-overview-and-prerequisites}

The [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html#video-overview) är ett JavaScript-bibliotek på klientsidan som gör att Adobe Experience Cloud-kunder kan interagera med de olika tjänsterna i Experience Cloud via Experience Platform Edge Network.

Experience Platform Web SDK stöder frågor om personaliseringslösningarna på Adobe, inklusive beslutsstöd, så att du kan hämta och återge personaliserade erbjudanden som du har skapat med hjälp av API:er eller erbjudandebiblioteket. Mer detaljerad information finns i dokumentationen om [skapa ett erbjudande](../../get-started/starting-offer-decisioning.md).

Det finns två sätt att implementera Offer decisioning med [Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html#video-overview). Ett sätt är inriktat på utvecklare och kräver kunskaper om webbplatser och programmering. Det andra sättet är att använda Adobe Experience Platform användargränssnitt för att ställa in erbjudanden som bara kräver att ett litet skript refereras till i sidhuvudet på HTML-sidan.

Läs dokumentationen om [offer decisioning](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/offer-decisioning/offer-decisioning-overview.html?lang=en#enabling-offer-decisioning) om du vill ha mer information om hur du kan leverera personaliserade erbjudanden med Platform Web SDK.

>[!NOTE]
>
>Beslutshantering i Adobe Experience Platform Web SDK är för närvarande tillgängligt i ett tidigt skede för vissa användare. Den här funktionen är inte tillgänglig för alla IMS-organisationer.

## Webb-SDK för Adobe Experience Platform  {#aep-web-sdk-overview-and-prerequisites}

Platform Web SDK ersätter följande SDK:

* Visitor.js
* AppMeasurement.js
* AT.js
* DIL.js

SDK kombinerade inte dessa bibliotek och är en ny implementering från grunden. Om du vill använda den måste du först göra följande:

1. Se till att din organisation har rätt behörighet att använda SDK och att du har konfigurerat behörigheterna korrekt.

   <!-- For more detailed instructions, refer to the documentation on using the [Adobe Experience Platform Web SDK](). -->

1. [Konfigurera ditt datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html?lang=en) på fliken Datainsamling i ditt konto i Adobe Experience Cloud.

1. Installera SDK. Det finns flera metoder för detta, som beskrivs i [Installera SDK-sidan](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en). Den här sidan fortsätter med varje implementeringsmetod.

För att kunna använda SDK måste du ha en [schema](../../../start/get-started-schemas.md) och [datastream](../../../start/get-started-datasets.md) definierad.

<!-- ****TODO - Configure schema**** -->

För att personalisera erbjudanden måste ni konfigurera er personalisering/profiler separat.

<!-- Refer to the [doc](www.link.com) for detailed instructions.  -->

Om du vill konfigurera SDK för Offer decisioning följer du något av följande två steg:

## Alternativ 1 - Installera taggtillägget och implementeringen med Launch

Det här alternativet är mer användarvänligt för personer som kan ha en mindre kodningsupplevelse.

1. [Skapa en taggegenskap](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en)

1. [Lägg till inbäddningskoden](https://experienceleague.adobe.com/docs/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch-add-embed.html?lang=en)

1. Installera och konfigurera Platform Web SDK-tillägget med den dataström du skapade genom att välja konfigurationen i listrutan Datastream. Läs dokumentationen om [tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=en).

   ![Webb-SDK för Adobe Experience Platform](../../assets/installed-catalog-web-sdk.png)

   ![Konfigurera tillägg](../../assets/configure-sdk-extension.png)

1. Skapa de nödvändiga [Dataelement](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en). Minimikravet är att du måste skapa en plattformsbaserad SDK-identitetskarta och ett XDM-objektdataelement för plattformswebben.

   ![Identitetskarta](../../assets/sdk-identity-map.png)

   ![XDM-objekt](../../assets/xdm-object.png)

1. Skapa [Regler](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=en):

   Lägg till en SDK-sändningshändelse för en plattform och lägg till relevanta beslutsomfattningar i åtgärdens konfiguration

   ![Renderingserbjudande](../../assets/rule-render-offer.png)

   ![Erbjudande](../../assets/rule-request-offer.png)

1. [Skapa och publicera](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en) ett bibliotek som innehåller alla relevanta regler, dataelement och tillägg som du har konfigurerat.

## Alternativ 2 - Implementera manuellt med den fristående versionen

Här beskrivs de steg som krävs för att använda Offer decisioning med den färdiga fristående installationen av web SDK. I den här handboken antas att det är första gången du implementerar SDK, så alla steg kanske inte gäller för dig. Den här guiden förutsätter också viss utvecklingsupplevelse.

Inkludera följande JavaScript-utdrag från alternativ 2: Den fördefinierade fristående versionen på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en) i `<head>` på HTML-sidan.


## Begränsningar

Vissa begränsningar för erbjudanden stöds för närvarande inte i mobila Experience Edge-arbetsflöden, till exempel Capping. Fältvärdet för begränsning anger hur många gånger ett erbjudande kan visas för alla användare. Mer information finns i [Lägg till begränsningar i ett erbjudande](../../offer-library/add-constraints.md#capping).
