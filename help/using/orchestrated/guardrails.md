---
solution: Journey Optimizer
product: journey optimizer
title: Samordnade kampanjer skyddar mot detaljer och begränsningar
description: Läs mer om säkra kampanjer och begränsningar
exl-id: 82744db7-7358-4cc6-a9dd-03001759fef7
version: Campaign Orchestration
source-git-commit: a9b790bc833b5819862bf2f3284968d81f595f28
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---


# Skyddsritningar och begränsningar {#guardrails}

Nedan visas säkerhetsbeskrivningar och begränsningar när du använder orkestrerade kampanjer.

## Begränsningar för dataflöde

### Datadesign och lagring

* Relationsdatalagret stöder **maximalt 200 tabeller** (scheman).

* För samordnade kampanjer får den totala storleken för det enskilda schemat **inte överstiga 100 GB**.

* Dagliga uppdateringar av ett schema bör vara **begränsat till mindre än 20 %** av det totala antalet poster för att bibehålla prestanda och stabilitet.

* Relationsdata är den primära modellen som stöds för användning vid förtäring, datamodellering och segmentering.

* Scheman som används för mål måste innehålla minst **ett identitetsfält av typen`String`**, mappat till ett definierat identitetsnamnområde.

* Det genomsnittliga antalet attribut per schema **får inte överstiga 50 kolumner** för att upprätthålla hanterbarhet och prestanda.

* Modellbaserade scheman kan inte aktiveras för Adobe Experience Platform **Profiler**. Endast XDM-standardscheman stöds för Adobe Experience Platform **Profiles**. Modellbaserade scheman kan aktiveras för samordnade kampanjer eller åtgärdskampanjer. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#enable-profile)

### Datainhämtning

* Profil + relationsdataöverföring krävs.

* All förtäring måste ske via **källor för datainhämtning**:

   * För **filbaserat**: `_change_request_type`-fält krävs. Värden som stöds är `U` (upsert) eller `D` (delete).

   * För **molnbaserade**: Tabellloggning måste vara aktiverat.

* **Delvisa postuppdateringar tillåts inte**. Varje rad måste anges som en fullständig post.

* Gruppintaget för kampanjsamordning är begränsat till **en gång var femtonde minut**.

* Fördröjning för intag i relationsbutiken varierar vanligtvis **från 15 minuter till 2 timmar**, beroende på:

   * Datavolym

   * Systemsamtidighet

   * Typ av åtgärd, t.ex. infogningar är snabbare än uppdateringar

* **Dataflödet till datauppsättningsrelationen är 1-1**. Detta innebär att bara en källa kan mata en datauppsättning åt gången. Om du vill byta källa måste det befintliga dataflödet tas bort och ett nytt dataflöde skapas med den nya källan.

### Datamodellering

* Alla scheman, inklusive faktatabeller, måste innehålla **en versionsbeskrivning** för att versionskontrollen och spårbarheten ska bli korrekt.

* Varje tabell måste ha en definierad **primärnyckel** för dataintegritet och underordnade åtgärder.

* `table_name` som tilldelas när en datauppsättning skapas är permanent och används genom segmenterings- och personaliseringsfunktioner.

* **Fältgrupper stöds inte** i det aktuella ramverket för datamodellering.

* Stöd för sammansatta primärnycklar med filöverföringsflöden är för närvarande inte tillgängligt.

## Verksamhetsbegränsningar

* Endast **skalära attribut stöds** i målgruppsdefinitioner. **Kartor och matriser tillåts inte**.

* **Segmenteringsaktiviteter är främst beroende av relationsdata**. Profildata kan inkluderas, men om du använder stora profildatauppsättningar kan det påverka prestandan.

* **Gränser har angetts för antalet profilattribut** som kan användas i både grupp- och direktuppspelande målgrupper för att upprätthålla systemets effektivitet.

* **Uppräkningar** stöds helt.

* **Läsa målgrupper cachelagras inte**, varje kampanjkörning utlöser en fullständig målgruppsutvärdering utifrån underliggande data.

* **Optimering rekommenderas** när du arbetar med stora eller komplexa målgruppsdefinitioner för att säkerställa prestanda.

* **Sparade målgruppsaktiviteter är statiska**, de speglar de data som finns tillgängliga när kampanjen körs.

* **Tillägg till en sparad målgruppsaktivitet stöds inte**. Alla ändringar kräver att publiken skrivs över fullständigt.

## Kanalbegränsningar

Endast SMS-, push- och e-postkanaler stöds i samordnade kampanjer.
