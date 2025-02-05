---
solution: Journey Optimizer
product: journey optimizer
title: Om TTL (Time-to-live) och segmenteringsändringar för direktuppspelning
description: Segmenteringsförändringar i realtid och direktuppspelning i Adobe Journey Optimizer
feature: Data Model, Datasets, Data Management
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
exl-id: 08633a79-5601-4e36-b8cf-080234956d99
source-git-commit: ccb4cc944271fb197e7aee87f57b51c28cb3565f
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# Segmenteringsförändringar i realtid och direktuppspelning {#ttl-guardrail}

## Direktuppspelad segmenteringsuppdatering {#segmentation-update}

Från och med 1 november 2024 har direktuppspelningssegmentering inte längre stöd för användning av skicka och öppna händelser från Journey Optimizer spårnings- och feedbackdatauppsättningar. Den här ändringen gäller för alla kundsandlådor och organisationer. Information om varför den här proceduren har inaktiverats tidigare finns [här](../audience/about-audiences.md#streaming-segmentation-events-guardrails).

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

+++ Påverkas även feedbackhändelser som är ett resultat av sändningshändelsen av ändringen?

Den här ändringen gäller även för uteslutningshändelser och avhopps-/fördröjningshändelser som är ett resultat av sändningen.

+++

## TTL-uppdatering (Phased time-to-live) {#ttl}

Från och med februari 2025 kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i **nya sandlådor och nya organisationer** enligt följande:

* 90 dagar för data i profilarkivet
* 13 månader för data i sjön

Den här ändringen kommer att introduceras i **befintliga kundsandlådor** i en efterföljande fas.

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
