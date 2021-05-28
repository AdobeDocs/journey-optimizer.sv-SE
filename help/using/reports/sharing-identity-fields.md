---
title: journeyStep, händelser, identitetsfält
description: journeyStep, händelser, identitetsfält
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 20%

---

# journeyStep, händelser, identitetsfält {#sharing-identity-fields}

![](../assets/do-not-localize/badge.png)

Den här mixinen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profidentiteten, om någon.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

## profileID

Profilidentifierare

Typ: string

## profileNamespace

Namnutrymme för profilidentifierare

Typ: string
