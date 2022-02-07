---
title: fält för händelseexekvering för händelsen journeyStep
description: fält för händelseexekvering för händelsen journeyStep
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 273cda84-0261-4c5b-b5f4-0202e8874d05
source-git-commit: 6d744c0289e81ab2229f02c44ead43943b945b89
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 4%

---

# fält för händelseexekvering för händelsen journeyStep {#sharing-execution-fields}

Den här fältgruppen delas av travelStepEvent och travelStepProfileEvent.

Om steget har en åtgärd som ska bearbetas läggs dessa fält till i händelsens nyttolast.

## actionID {#actionid-field}

ID för åtgärden som körs.

Typ: string

## actionName {#actionname-field}

Åtgärdens namn. Om inget namn har angetts används stepName.

Typ: string

## actionType {#actionType-field}

Typ av åtgärd.

Typ: string

## actionParametriszed {#actionparameterized-field}

Anger om åtgärden är parametriserad eller inte.

Typ: boolesk

## actionExecutionTime {#actionexecutiontime-field}

Den tid (i millisekunder) som krävs för att köra en aktuell åtgärd.

Typ: long

## actionExecutionError {#actionexecutionerror-field}

Typ av fel som inträffar när åtgärden anropas.

Typ: string

Värden:
* http
* capping
* timeout
* error

## actionExecutionErrorCode {#actionexecutionerrorcode-field}

Kod för körningsfel för åtgärd. Visa om felet har en kod, t.ex. en HTTP-kod.

Typ: string

## actionExecutionOriginError {#actionexecutionoriginerror-field}

En timeout kan uppstå i två fall:

* vid första försöket utförs en åtgärd. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: I det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Ett e-postmeddelande skickas till exempel och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på två försök överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

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

Typ: string

## actionExecutionOriginCode {#actionexecutionorigincode-field}

Felkod för actionExecOrigError.

Typ: string

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

Typ: string

## deliveryJobID {#deliveryjobid-field}

Detta beskriver leveransjobb-ID för batchresan.

Typ: string

## batchDeliveryID {#batchdeliveryid-field}

Detta beskriver leverans-ID för batchresan.

Typ: string

## fromSegmentTrigger {#fromsegmenttrigger-field}

Detta beskriver om batchresan aktiveras från målgruppssegmentet.

Typ: boolesk

## actionSchedulerCount {#actionschedulercount-field}

Antal begäranden om schemaläggningsmeddelanden som skickats till schemaläggningstjänsten under stegbearbetningen.

Typ: long
