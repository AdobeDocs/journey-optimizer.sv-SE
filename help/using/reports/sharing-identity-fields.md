---
title: journeyStep, händelser, identitetsfält
description: journeyStep, händelser, identitetsfält
feature: Rapportering
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 24%

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
