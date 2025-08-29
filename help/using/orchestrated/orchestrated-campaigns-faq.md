---
solution: Journey Optimizer
product: journey optimizer
title: Vanliga frågor och svar om samordnade kampanjer
description: Frågor och svar om Journey Optimizer samordnade kampanjer
hide: true
hidefromtoc: true
exl-id: 6a660605-5f75-4c0c-af84-9c19d82d30a0
source-git-commit: 3764d7eebbe304e0773fa329db2755342ce64c85
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 1%

---

# Vanliga frågor {#faq-oc}

Nedan hittar du Vanliga frågor om Adobe Journey Optimizer samordnade kampanjer.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ta upp din fråga.

## Vad är samordnade kampanjer?

Samordnade kampanjer i Adobe Journey Optimizer hjälper varumärken att köra komplexa 1:N-kampanjer i stor skala. De är utformade för varumärkesinitierat engagemang, som kampanjer, säsongskampanjer eller kontobaserad kommunikation.

## Vad kan jag göra med orkestrerade kampanjer?

Viktiga funktioner:

* **On-Demand-målgrupper**: Bygg och förfina målgrupper direkt med hjälp av relationsfrågor.
* **Segmentering för flera enheter**: Skapa exakta målgrupper genom att koppla kunddata till relaterade entiteter (t.ex. konton, inköp, bokningar).
* **Synlighet före sändning**: Se rätt antal målgrupper innan du startar för att optimera målinriktningen.
* **Flerstegsarbetsflöden**: Kör sekventiella kampanjer, till exempel säsongskampanjer, produktlanseringar eller lojalitetserbjudanden.


## Vilka kanaler stöds?

Orchestrated Campaigns har stöd för **e-post-, SMS- och push-meddelanden**.

## Hur skiljer sig Orchestrated Campaigns från Journeys?

* **Samordnade kampanjer**: Bäst för **batch-, en-till-många**-kampanjer. Hela målgrupper rör sig genom kampanjarbetsytan tillsammans.
* **Resor**: Passar bäst för **realtidsengagemang med en-till-en**. Varje kund rör sig genom resan i sin egen takt, triggad av beteende eller händelser.


## Hur fungerar datamodellen?

Kampanjer använder en **relationsdatabas**. På så sätt kan ni söka efter olika datauppsättningar (t.ex. kunder, produkter, prenumerationer) och koppla dem flexibelt för mer avancerad segmentering.


## Kan jag personalisera meddelanden med dessa data?

Ja. Ni kan använda kundprofiler tillsammans med länkade data (som köp eller prenumerationer) för att anpassa innehåll i alla kanaler som stöds.


## Kan programmet integreras med andra Adobe-lösningar?

* **Customer Journey Analytics**: Det finns rapporter om kampanjsamordning.
* **Real-Time CDP**: Publiker som skapats i kampanjer kan läsas i CDP.
* **FFAC (Federated Audience Composition)**: Tillgängligt som tillägg.


## Vad gäller för tillstånd och samtycke?

Tillstånd och samtycke hanteras centralt i Adobe Experience Platform. Samma regler gäller för både resor och samordnade kampanjer för att säkerställa regelefterlevnad och enhetlig kundupplevelse.


## Kan jag göra ad hoc-segmentering?

Ja. Med **Live-segmentering** kan du skapa komplexa frågor på plats och omedelbart aktivera dem i utgående kanaler.

## Stöder detta beslut?

För närvarande används inte relationsdata från Orchestrated Campaigns vid beslut.

