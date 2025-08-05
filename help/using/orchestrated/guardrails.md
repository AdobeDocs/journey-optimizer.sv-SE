---
solution: Journey Optimizer
product: journey optimizer
title: Samordnade kampanjer skyddar mot detaljer och begränsningar
description: Läs mer om säkra kampanjer och begränsningar
exl-id: 82744db7-7358-4cc6-a9dd-03001759fef7
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---


# Skyddsritningar och begränsningar {#guardrails}

Nedan finns ytterligare skyddsförslag och begränsningar när du använder orkestrerade kampanjer.

## Begränsningar för dataflöde

### Datadesign och lagring

* Relationsdatalagret stöder **maximalt 200 tabeller** (scheman).

* För samordnade kampanjer får den totala storleken för det enskilda schemat **inte överstiga 100 GB**.

* Dagliga uppdateringar av ett schema bör vara **begränsat till mindre än 20 %** av det totala antalet poster för att bibehålla prestanda och stabilitet.

* Relationsdata är den primära modellen som stöds för användning vid förtäring, datamodellering och segmentering.

* Scheman som används för mål måste innehålla minst **ett identitetsfält av typen`String`**, mappat till ett definierat identitetsnamnområde.

### Datainmatning

* Profil + relationsdataöverföring krävs.

* All förtäring måste ske via **källor för datainhämtning**:

   * För **filbaserat**: `change_type`-fält krävs.

   * För **molnbaserade**: Tabellloggning måste vara aktiverat.

* **Direktuppdateringar till Snowflake eller datauppsättningar stöds inte**. Systemet är skrivskyddat, alla ändringar måste göras med registrering av ändringsdata.

* **ETL-processer stöds inte**. Data måste omformas fullständigt till det format som krävs före intag.

* **Delvisa uppdateringar tillåts inte**. Varje rad måste anges som en fullständig post.

* Gruppintaget för kampanjsamordning är begränsat till **en gång var femtonde minut**.

* Fördröjning för intag, tid från intag till tillgänglighet i Snowflake, varierar vanligtvis **från 15 minuter till 2 timmar**, beroende på:

   * Datavolym

   * Systemsamtidighet

   * Typ av åtgärd, t.ex. infogningar är snabbare än uppdateringar

### Datamodellering

* Alla scheman, inklusive faktatabeller, måste innehålla **en versionsbeskrivning** för att versionskontrollen och spårbarheten ska bli korrekt.

* Varje tabell måste ha en definierad **primärnyckel** för dataintegritet och underordnade åtgärder.

* `table_name` som tilldelas när en datauppsättning skapas är permanent och används genom segmenterings- och personaliseringsfunktioner.

* **Fältgrupper stöds inte** i det aktuella ramverket för datamodellering.

## Verksamhetsbegränsningar

* Endast **skalära attribut stöds** i målgruppsdefinitioner. **Kartor och matriser tillåts inte**.

* **Segmenteringsaktiviteter är främst beroende av relationsdata**. Profildata kan inkluderas, men om du använder stora profildatauppsättningar kan det påverka prestandan.

* **Gränser har angetts för antalet profilattribut** som kan användas i både grupp- och direktuppspelande målgrupper för att upprätthålla systemets effektivitet.

* **Listan med värden (LOV)** och **uppräkningar** stöds fullt ut.

* **Läsa målgrupper cachelagras inte**, varje kampanjkörning utlöser en fullständig målgruppsutvärdering utifrån underliggande data.

* **Optimering rekommenderas** när du arbetar med stora eller komplexa målgruppsdefinitioner för att säkerställa prestanda.

* **Sparade målgruppsaktiviteter är statiska**, de speglar de data som finns tillgängliga när kampanjen körs.

* **Tillägg till en sparad målgruppsaktivitet stöds inte**. Alla ändringar kräver att publiken skrivs över fullständigt.
