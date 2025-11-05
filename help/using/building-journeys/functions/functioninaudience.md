---
product: journey optimizer
title: funktionen inAudience
description: Läs om funktionen Adobe Experience Platform inAudience
feature: Journeys
role: Developer
level: Experienced
keywords: målgrupp, funktion, uttryck, resa, målgrupp, segmentering
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
version: Journey Orchestration
source-git-commit: a866442aa073c648d4455754e9945f0dddfb079d
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# funktionen inAudience {#inAudience}

Funktionen `inAudience` är en Adobe Experience Platform-funktion som gör att du kan kontrollera om en person i din resa tillhör en viss målgrupp. Denna kraftfulla funktion gör att ni kan skapa personaliserade kundresor baserat på målgruppsmedlemskap, vilket möjliggör avancerad segmentering och målgruppsanpassning i era kundupplevelser.

Använd funktionen `inAudience` när du behöver:

* [Sökvägar för grenresor baserat på målgruppsmedlemskap](../condition-activity.md#using-a-segment)
* Använd villkorsstyrd logik som beror på om en profil tillhör ett visst segment
* Rikta in er till specifika kundgrupper med personaliserade upplevelser
* Utvärdera målgruppernas deltagande i realtid under resan
* Kombinera olika målgruppskontroller för att skapa komplexa målgruppsregler

Funktionen utvärderar målgruppsmedlemskap i realtid och returnerar ett booleskt värde, vilket gör det idealiskt för beslutsnoder och villkorsuttryck. Målgrupper definieras och hanteras i [Adobe Experience Platform](https://platform.adobe.com/audience/overview){target="_blank"} (läs mer om [att arbeta med målgrupper](../../audience/about-audiences.md) i Journey Optimizer) och uttrycksredigeraren ger förslag på automatisk komplettering som hjälper dig att referera till dem korrekt.

**Målgruppsstatus:**

Målgrupper kan ha två deltagarstatusar:

* **Realiserad**: Personen kvalificerar sig för målgruppsdefinitionen och är en aktiv medlem
* **Avslutade**: Personen har lämnat målgruppen och kvalificerar sig inte längre

Endast personer med statusen **Realized** betraktas som aktiva målgruppsmedlemmar. När funktionen returnerar `true` bekräftar det att personen har uppnått status. När den returnerar `false` anger den att den har avslutat status. Mer information om målgruppsutvärdering finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results){target="_blank"}.

+++Syntax

`inAudience(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| Målgrupp | Målgruppens namn | `<string>` |

**Viktiga begränsningar:**

* Publiken måste ha ett strängkonstant
* Det kan inte vara en fältreferens eller ett uttryck
* Ni kan hämta upp till 100 målgrupper på en enda resa

+++

+++Signatur och returtyp

`inAudience(<string>)`

Returnerar ett booleskt värde:
* `true`: Personen är medlem i målgruppen (realiserad status)

* `false`: Personen är inte medlem i publiken (avslutad status)

+++

+++Exempel

`inAudience("men over 50")`

Returnerar **true** om den enskilda personen i reseinstansen är en del av Adobe Experience Platform-målgruppen med namnet&quot;men över 50&quot;, annars returneras **false**.

**Exempel på praktisk användning:**

```
// Simple audience check in a condition
inAudience("Premium Customers") == true

// Multiple audience evaluation
inAudience("High Value Customers") == true AND inAudience("Active Last 30 Days") == true

// Negation check
inAudience("Unsubscribed") == false
```

+++

## Skyddsritningar och begränsningar {#guardrails}

När du använder funktionen `inAudience` på dina resor ska du vara medveten om följande skyddsräcken och begränsningar:

**Begränsning för målgruppsåterhämtning:**
* Ni kan få upp till 100 målgrupper inom en enda resa
* Uttrycksredigeraren innehåller en automatiskt ifylld lista över tillgängliga målgrupper som hjälper dig att referera till dem korrekt

**Parameterbegränsningar:**
* Publiken måste ha ett strängkonstant
* Fältreferenser och uttryck stöds inte som parametrar

**Ändringar av målgruppsnamn:**
* Om du ändrar namnet på en befintlig målgrupp i Adobe Experience Platform uppdateras inga referenser till den målgruppen automatiskt i dina reseuttryck
* Om villkorsnoden använder `inAudience('oldAudienceName')` måste du redigera uttrycket manuellt för att använda det nya namnet
* Om målgruppsnamnet inte uppdateras bryts kundens villkor och kan leda till felaktigt resebeteende

**Om principer för sammanslagning:**
* Om du använder flera målgrupper med funktionen `inAudience` kan inkonsekvenser med sammanfogningsprinciper orsaka fel eller varningar
* Mer information om policybeteende för sammanslagning finns i [Reseegenskaper](../journey-properties.md)

## Relaterade ämnen

Läs mer om hur du använder målgrupper i Adobe Journey Optimizer:

* **[Om målgrupper](../../audience/about-audiences.md)** - Förstå hur målgrupper arbetar i Adobe Experience Platform och Journey Optimizer, inklusive hur de skapas och hanteras
* **[Läs målgruppsaktivitet](../read-audience.md)** - Använd målgrupper för att utlösa reseinträde och få alla målgruppsmedlemmar att delta i en resa
* **[Publikkvalificeringshändelser](../audience-qualification-events.md)** - Lyssna på profilingångar och utgångar från målgrupper för att aktivera reseåtgärder i realtid
* **[Använda målgrupper i villkor](../condition-activity.md#using-a-segment)** - Skapa villkorliga kundvägar baserat på målgruppsmedlemskap med villkorsaktiviteten
* **[Reseegenskaper - Sammanfoga profiler](../journey-properties.md)** - Förstå hur sammanfogningsprinciper fungerar när flera målgrupper används med funktionen inAudience

