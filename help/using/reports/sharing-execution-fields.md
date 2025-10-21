---
solution: Journey Optimizer
product: journey optimizer
title: fält för händelseexekvering för händelsen journeyStep
description: fält för händelseexekvering för händelsen journeyStep
feature: Journeys, Reporting
topic: Content Management
role: Engineer, Admin
level: Experienced
exl-id: 273cda84-0261-4c5b-b5f4-0202e8874d05
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---

# fält för händelseexekvering för händelsen journeyStep {#sharing-execution-fields}

Den här fältgruppen delas av travelStepEvent och travelStepProfileEvent.

Om steget har en åtgärd som ska bearbetas läggs dessa fält till i händelsens nyttolast.

## actionID {#actionid-field}

ID för åtgärden som körs.

Typ: sträng

## actionName {#actionname-field}

Åtgärdens namn. Om inget namn har angetts används stepName.

Typ: sträng

## actionType {#actionType-field}

Typ av åtgärd.

Typ: sträng

## actionParametriszed {#actionparameterized-field}

Anger om åtgärden är parametriserad eller inte.

Typ: boolesk

## actionExecutionTime {#actionexecutiontime-field}

Den tid (i millisekunder) som krävs för att köra en aktuell åtgärd.

Typ: lång

Fältet `actionExecutionTime` representerar den totala tiden (i millisekunder) som har ägnats åt att utföra åtgärden, inklusive både den tid som begäran väntar i kön (om begränsning har konfigurerats och hastighetsgränsen har uppnåtts) och den faktiska körningstiden (inklusive nätverksfördröjning till den externa slutpunkten).

Fältet `Timestamp` anger åtgärdens sluttid. Ta bort `actionExecutionTime` från `Timestamp` för att avgöra när profilen angavs i den anpassade åtgärdsnoden.

Om `Timestamp` till exempel är &quot;2025-02-04 09:39:03 UTC&quot; och `actionExecutionTime` är 1 813 227 ms (~31 minuter), angavs profilen i noden med ungefär &quot;2025-02-04 09:08:32 UTC&quot;.




## actionExecutionError {#actionexecutionerror-field}

Typ av fel som inträffar när åtgärden anropas.

Typ: sträng

Värden:

* http
* capping
* timeout
* fel

## actionExecutionErrorCode {#actionexecutionerrorcode-field}

Kod för körningsfel för åtgärd. Visa om felet har en kod, t.ex. en HTTP-kod.

Typ: sträng

## actionExecutionOriginError {#actionexecutionoriginerror-field}

En timeout kan uppstå i två fall:

* vid första försöket utförs en åtgärd. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: i det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Ett e-postmeddelande skickas till exempel och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på de två försöken överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Typ: sträng

## actionExecutionOriginCode {#actionexecutionorigincode-field}

Felkod för actionExecOrigError.

Typ: sträng

## actionBusinessType {#actionbusinesstype-field}

Anger typen av åtgärd.

Värden:

* inbyggd
   * ACS-e-post
   * ACS SMS
   * ACS-push
* kund
   * Epsilon
   * ...

Typ: sträng

## deliveryJobID {#deliveryjobid-field}

Detta beskriver leveransjobb-ID för batchresan.

Typ: sträng

## batchDeliveryID {#batchdeliveryid-field}

Detta beskriver leverans-ID för batchresan.

Typ: sträng

## fromSegmentTrigger {#fromsegmenttrigger-field}

Detta beskriver om batchresan aktiveras från målgruppssegmentet.

Typ: boolesk

## actionSchedulerCount {#actionschedulercount-field}

Antal begäranden om schemaläggningsmeddelanden som skickats till schemaläggningstjänsten under stegbearbetningen.

Typ: lång
