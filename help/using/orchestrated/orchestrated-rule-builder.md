---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med regelbyggaren
description: Lär dig skapa regler för era samordnade kampanjer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
source-git-commit: 450f83eb53068df10a63d39d1a43483ad3c7e803
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---


# Arbeta med regelbyggaren {#orchestrated-rule-builder}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)<br/><br/>[Inställningar för orkestrerade kampanjer](orchestrated-campaign-settings.md)<br/><br/>[Samordna aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | <b>[Arbeta med regelbyggaren](orchestrated-rule-builder.md)</b><br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena{1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Samordnade kampanjer har en regelbyggare som förenklar processen att filtrera databasen baserat på olika kriterier. Regelbyggaren hanterar mycket komplexa och långa frågor effektivt och erbjuder större flexibilitet och precision.

Programmet har också stöd för fördefinierade filter under förhållanden, vilket gör det enkelt för användarna att förfina frågor samtidigt som avancerade uttryck och operatorer används för omfattande målgruppsanpassning och segmenteringsstrategier.

## Åtkomst till regelbyggaren

Regelbyggaren är tillgänglig när en fråga skapas i en **[!UICONTROL Build audience]**-aktivitet för att rikta sig till en målgrupp. Det gör att ni kan specificera vilken målgrupp ni vill rikta och enkelt skapa nya målgrupper som är skräddarsydda efter era behov.

![bild som visar en målgruppsaktivitet för bygge](assets/rule-builder-query.png)

## Gränssnitt för regelbyggaren {#interface}

Regelbyggaren innehåller en central arbetsyta där du skapar frågan och en egenskapsruta som innehåller information om regeln.

![Bild som visar gränssnittet för regelbyggaren](assets/rule-builder-interface.png)

* På den **centrala arbetsytan** kan du lägga till och kombinera de olika komponenterna för att skapa regeln. [Lär dig skapa en regel](../orchestrated/build-query.md)

* Panelen **[!UICONTROL Rule properties]** innehåller information om din regel. Det gör att du kan utföra olika åtgärder för att kontrollera regeln och se till att den passar dina behov.

  Den här rutan visas när du skapar en fråga för att skapa en målgrupp. [Lär dig hur du kontrollerar och validerar din fråga](build-query.md#check-and-validate-your-query)
