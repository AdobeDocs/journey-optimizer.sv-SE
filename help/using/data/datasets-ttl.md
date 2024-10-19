---
solution: Journey Optimizer
product: journey optimizer
title: Om det nya TTL-skyddsräcket (Time-to-live)
description: Ny TTL-garanti (Time-to-live) i Adobe Journey Optimizer
feature: Data Model, Datasets, Data Management
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
source-git-commit: f16ce53f61d64d23f530d007e0124a84e2cc3405
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---


# TTL- och direktuppspelningssegmenteringsuppdateringar {#ttl-guardrail}

## TTL-skydd (Time-to-live) {#ttl}

Från och med 1 november 2024 kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i **nya sandlådor och nya organisationer** enligt följande:

* 90 dagar för data i profilarkivet
* 13 månader för data i sjön

Den här ändringen kommer att introduceras till **befintliga kundsandlådor** i en senare fas.

**Vanliga frågor**

+++ Gäller den här ändringen endast för produktionssandlådor eller gäller den även för dev-sandlådor?

Den här ändringen gäller för alla sandlådetyper.

+++


+++ Påverkas själva profilerna för den 90-dagars TTL-värdet i profilbutiken?

Systemgenererade data i profilen tas bort efter 90 dagar, inte själva profilerna.

+++

+++ Om data från en systemgenererad datauppsättning överförs till Customer Journey Analytics (CJA), kommer data i CJA också att påverkas av TTL-värdet?

Data i CJA hålls synkroniserade med Experience Platform. En borttagning av data på grund av en TTL på systemgenererade datauppsättningsdata kommer därför också att påverka data i CJA.

+++

## Direktuppspelad segmenteringsuppdatering {#segmentation-update}

Dessutom kommer direktuppspelningssegmentering den 1 november inte längre att stödja användning av skicka- och feedback-händelser från spårnings- och feedbackdatauppsättningar. Information om varför den här proceduren har inaktiverats tidigare finns [här](../audience/about-audiences.md#streaming-segmentation-events-guardrails).


**Vanliga frågor**

+++ Kommer dessa ändringar att påverka användningen av klickningar eller andra spårningshändelser?

Den här ändringen påverkar bara användningen av skicka- och öppna händelser. Klickningar och andra spårningshändelser kan fortfarande användas i ett direktuppspelningssegment.

+++

+++ Kommer gruppsegmentering att påverkas av den här ändringen?

Den här förändringen påverkar bara direktuppspelningssegmentering. Sändnings- och öppningshändelser kan fortfarande användas i ett gruppsegment. Om de används i ett direktuppspelningssegment utvärderas de gruppvis.

+++

+++ Kommer detta att påverka insamlingen av spårningsdata?

Den här ändringen påverkar inte insamling av spårningsdata. Evenemang för att skicka och öppna fortsätter att samlas in.

+++


+++ Påverkas reaktionshändelser av denna förändring?

Reaktionshändelser i resor påverkas inte av denna förändring.

+++


+++ Gäller den här ändringen endast för produktionssandlådor eller gäller den även för dev-sandlådor?

Den här ändringen gäller för alla sandlådetyper.

+++