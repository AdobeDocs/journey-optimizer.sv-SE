---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera en kampanj
description: Lär dig granska och aktivera kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: kampanj, granskning, validering, aktivering, aktivering, optimering
exl-id: 86f35987-f0b7-406e-9ae6-0e4a2e651610
source-git-commit: d93b7ce225294257f49caee6ac08cfb575611a93
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---


# Kör en API-utlöst kampanj {#execute}

När kampanjen har aktiverats måste du hämta den genererade cURL-exempelbegäran och använda den i API:t för att skapa din nyttolast och utlösa kampanjen.

## Måste läsas {#must-read}

* **Kampanjens start-/slutdatum** - Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.

* **Tidsgräns för anrop** - Anropet till REST API:t för interaktiv meddelandekörning har en tidsgräns på 60 sekunder. Det finns dock interna försök om det skulle uppstå oväntade tidsgränser för att garantera leveransen.

## Utlös kampanjen {#trigger}

1. Öppna kampanjen och kopiera och klistra sedan in nyttolastbegäran från avsnittet **[!UICONTROL cURL request]**. Den här nyttolasten innehåller alla personaliseringsvariabler (profil och kontext) som används i meddelandet. Den blir tillgänglig när kampanjen är live.

   ![](assets/api-triggered-curl.png)

   >[!IMPORTANT]
   >
   >Slutpunkterna i cURL-avsnittet skiljer sig åt mellan standardkampanjer och [kampanjer med hög genomströmning](../campaigns/api-triggered-high-throughput.md).

1. Använd denna cURL-begäran i API:erna för att bygga upp din nyttolast och utlösa kampanjen. Mer information finns i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution), där alla slutpunkter för standard- och högflödeskampanjer listas.

   Exempel på API-anrop finns också på [den här sidan](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/).
