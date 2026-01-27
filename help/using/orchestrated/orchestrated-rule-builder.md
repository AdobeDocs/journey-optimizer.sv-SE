---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med regelbyggaren
description: Lär dig hur du skapar regler för dina samordnade kampanjer
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
version: Campaign Orchestration
source-git-commit: e486aae3a6635d8eec0c398bfe03b6a63a007ef1
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# Arbeta med regelbyggaren {#orchestrated-rule-builder}

Samordnade kampanjer har en regelbyggare som förenklar processen att filtrera databasen baserat på olika kriterier. Regelbyggaren hanterar mycket komplexa och långa frågor effektivt och erbjuder större flexibilitet och precision.

Det har också stöd för fördefinierade filter under förhållanden, vilket gör att du enkelt kan förfina frågor samtidigt som du använder avancerade uttryck och operatorer för omfattande målgruppsanpassning och segmenteringsstrategier.

## Åtkomst till regelbyggaren {#access}

Regelbyggaren är tillgänglig i alla sammanhang där du behöver definiera regler för att filtrera data.

| Användning | Exempel |
|  ---  |  ---  |
| **Bygg målgrupper**: Ange den målgrupp du vill rikta in dig på i dina samordnade kampanjer med en **[!UICONTROL Build audience]** -aktivitet och skapa enkelt nya målgrupper som är anpassade efter dina behov. [Lär dig skapa målgrupper](../orchestrated/activities/build-audience.md) | ![Bild som visar hur du kommer åt gränssnittet för målgruppsskapande](assets/query-access-audience.png){width="200" align="center" zoomable="yes"} |
| **Skapa villkor på kampanjarbetsytan**: Använd regler på kampanjarbetsytan med en **[!UICONTROL Split]**-aktivitet för att anpassa dig efter dina specifika krav. [Lär dig använda en delad aktivitet](../orchestrated/activities/split.md) | ![Bild som visar hur du får åtkomst till alternativ för anpassning av arbetsflöden](assets/query-access-split.png){width="200" align="center" zoomable="yes"} |
| **Skapa avancerade filter**: Skapa regler för att filtrera data som visas i listor som kampanjloggar eller måldimensioner. | ![Bild som visar hur du anpassar listfilter](assets/query-access-advanced-filters.png){width="200" align="center" zoomable="yes"} |

## Gränssnitt för regelbyggaren {#interface}

Regelbyggaren innehåller en central arbetsyta där du skapar frågan och en egenskapsruta som innehåller information om regeln.

![Bild som visar gränssnittet för regelbyggaren](assets/rule-builder-interface.png)

* På den **centrala arbetsytan** kan du lägga till och kombinera de olika komponenterna för att skapa regeln. [Lär dig skapa en regel](../orchestrated/build-query.md)

* Panelen **[!UICONTROL Rule properties]** innehåller information om din regel. Det gör att du kan utföra olika åtgärder för att kontrollera regeln och se till att den passar dina behov.

  Den här rutan visas när du skapar en fråga för att skapa en målgrupp. [Lär dig hur du kontrollerar och validerar din fråga](build-query.md#check-and-validate-your-query)

## Arbeta med fördefinierade filter

Med fördefinierade filter kan du återanvända sparade frågor i regelbyggaren, inklusive versioner med parametrar. En fullständig genomgång av hur du sparar, använder och hanterar fördefinierade filter finns i [Arbeta med fördefinierade filter](predefined-filters.md).
