---
solution: Journey Optimizer
product: journey optimizer
title: identitetsfält för händelsen journeyStep
description: identitetsfält för händelsen journeyStep
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: c447fcf0-51ec-4d88-8b2d-f15db076bfbc
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 20%

---

# identitetsfält för händelsen journeyStep {#sharing-identity-fields}

Den här fältgruppen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profilens identitet, om sådan finns.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

## profileID

Profilidentifierare

Typ: sträng

## profileNamespace

Namnutrymme för profilidentifierare

Typ: sträng
