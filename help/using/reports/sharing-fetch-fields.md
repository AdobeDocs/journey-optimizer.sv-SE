---
solution: Journey Optimizer
product: journey optimizer
title: datafält för hämtning för händelsen journeyStep
description: datafält för hämtning för händelsen journeyStep
feature: Journeys, Reporting
topic: Content Management
role: Engineer, Admin
level: Experienced
exl-id: 948fe843-47cf-4b20-976a-48069eb9cf5c
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 3%

---

# datafält för hämtning för händelsen journeyStep {#sharing-fetch-fields}

Den här fältgruppen delas av travelStepEvent och travelStepProfileEvent.

Under en stegvis bearbetning kan vi hämta N-data i fältgrupper.

## fetchTotalTime {#fetchtotaltime-field}

Total tid i millisekunder som datahämtningen pågick under stegbearbetningen.

Typ: lång

## fetchTypeInError {#fetchtypeinerror-field}

Definierar om den felaktiga hämtningen finns i Adobe Experience Platform eller i en anpassad datakälla.

Typ: sträng

Värden:

* aep
* anpassad

## fetchError {#fetcherror-field}

Typ av fel som inträffar när datahämtningen bearbetas.

Typ: sträng

Värden:

* http
* capping
* tidsgränsen
* fel

## fetchErrorCode {#fetcherrorcode-field}

Kod för hämtningsfel. Visa om felet har en kod, t.ex. en HTTP-kod. Om actionExecError till exempel är http representerar koden 404 HTTP 404-felet.

Typ: sträng

## fetchOriginError {#fetchoriginerror-field}

En timeout kan uppstå i två fall:

* vid första försöket utförs åtgärden. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: i det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Data hämtas till exempel från Unified Profile Service och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på de två försöken överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Typ: sträng

## fetchOriginErrorCode {#fetchoriginerrorcode-field}

Felkoden som tillhandahålls av systemet [!DNL Journey Optimizer] efterfrågas. Det kan till exempel vara en 404, 500 osv.

Typ: sträng

## fetchCount {#fetchcount-field}

Hur många gånger data hämtas, oavsett källtyp.

Typ: lång

## fetchPlatformTotalTime {#fetchplatformtotaltime-field}

Den totala tiden det tar att hämta data från Adobe Experience Platform i millis. Anmärkning: Den här tiden beräknas från den tidpunkt då motorn skickar anrikningshändelsen till anrikningstjänsten och tar emot svaret.

Typ: lång

## fetchPlatformCount {#fetchplatformcount-field}

Hur många gånger data hämtas från Adobe Experience Platform.

Typ: lång

## fetchCustomTotalTime {#fetchcustomtotaltime-field}

Hur lång tid det tar att hämta anpassade data i millis. Anmärkning: Den här tiden beräknas från den tidpunkt då motorn skickar anrikningshändelsen till anrikningstjänsten och får svaret

Typ: lång

## fetchCustomCount {#fetchcustomcount-field}

Hur många gånger som anpassade data hämtas från externa system.

Typ: lång
