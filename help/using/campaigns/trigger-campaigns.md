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
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# Kör en API-utlöst kampanj {#execute}

När kampanjen har aktiverats måste du hämta den genererade cURL-exempelbegäran och använda den i API:t för att skapa din nyttolast och utlösa kampanjen.

1. Öppna kampanjen och kopiera och klistra sedan in nyttolastbegäran från avsnittet **[!UICONTROL cURL request]**. Den här nyttolasten innehåller alla personaliseringsvariabler (profil och kontext) som används i meddelandet. Den blir tillgänglig när kampanjen är live.

   ![](assets/api-triggered-curl.png)

1. Använd denna cURL-begäran i API:erna för att bygga upp din nyttolast och utlösa kampanjen. Mer information finns i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution).


   Exempel på API-anrop finns också på [den här sidan](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/).

   >[!NOTE]
   >
   >Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.
