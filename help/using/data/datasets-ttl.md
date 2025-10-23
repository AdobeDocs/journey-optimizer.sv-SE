---
solution: Journey Optimizer
product: journey optimizer
title: Om skyddsutkast för tidsbegränsad livstid (TTL)
description: Datauppsättningar Tid-till-live-skyddsutkast i  [!DNL Adobe Journey Optimizer]
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
exl-id: 08633a79-5601-4e36-b8cf-080234956d99
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 2%

---

# Datauppsättningar TTL-skyddsutkast (Time-to-live) {#ttl-guardrail}

Från och med februari 2025 introduceras ett TTL-skyddsräcke (time-to-live) för Journey Optimizer systemgenererade datauppsättningar i **nya sandlådor och nya organisationer** enligt följande:

* 90 dagar för data i profilarkivet,
* 13 månader för data i sjön.

Den här ändringen introduceras till **befintliga kundsandlådor** i en efterföljande fas.

## Påverkade datauppsättningar {#datasets}

Tabellen nedan listar alla påverkade datauppsättningar och deras respektive Time-To-Live i datasjön och profilarkivet.

| Datauppsättning | Data Lake TTL | Profilarkiv-TTL |
|------|-----|-----|
| AJO Message Feedback Event Dataset | 13 månader | 90 dagar |
| AJO Experience Event-datauppsättning för e-postspårning | 13 månader | 90 dagar |
| AJO Push Tracking Experience, händelsedatauppsättning | 13 månader | 90 dagar |
| AJO Entity Dataset | 13 månader | 90 dagar |
| AJO Surfaces Dataset | 13 månader | n/a |
| Inkommande aktivitetshändelsedatauppsättning för AJO | 13 månader | 90 dagar |
| AJO Klassificeringsdatauppsättning | 13 månader | n/a |
| AJO BCC Feedback Event DataSet | 13 månader | n/a |
| acpEntity - händelsedatamängd | 13 månader | n/a |
| Resor | 13 månader | n/a |
| Resestegshändelser | 13 månader | n/a |
| Repository - Personalized offers | 13 månader | n/a |
| Beslutsobjektarkiv - reserverbjudanden | 13 månader | n/a |
| Beslutsobjektsdatabas - placeringar | 13 månader | n/a |
| Repositionen för beslutsobjekt - aktiviteter | 13 månader | n/a |
| Objektarkiv för Experience Decision - personaliserade erbjudanden | 13 månader | n/a |
| ODE-beslutHändelser - preliminär beslut | 13 månader | n/a |

## Vanliga frågor {#faq}

Nedan följer en lista med svar på vanliga frågor om datauppsättningens TLL.

+++Gäller den här ändringen endast för produktionssandlådor eller gäller den även för dev-sandlådor?

Den här ändringen gäller för alla sandlådetyper.

+++

+++Påverkas själva profilerna för den 90-dagars TTL-värdet i profilbutiken?

Systemgenererade data i profilen tas bort efter 90 dagar, inte själva profilerna.

+++

+++Om ett systemgenererat datauppsättningsdata skickas till [!DNL Customer Journey Analytics] (CJA), kommer data i CJA också att påverkas av TTL-värdet?

Data i [!DNL Customer Journey Analytics] är synkroniserade med Experience Platform. En borttagning av data på grund av en TTL på systemgenererade datauppsättningsdata kommer därför också att påverka data i [!DNL Customer Journey Analytics].

+++

+++ Kan kunder öka TTL-värdet för [!DNL Journey Optimizer]-systemdatauppsättningsdata i profilarkivet? 

TTL-tillägg stöds för närvarande inte. Det finns dock planer på att optimera TTL-processen för att tillåta dessa tilläggsbegäranden någon gång från och med det senare halvåret 2025.

>[!NOTE]
>
>Data som lagras i profilen omfattas av berättigandet Total Data Volume. Alla datalagringsökningar i profilen som ett resultat av ett TTL-tillägg räknas därför av mot det totala datavolymtillståndet. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/landing/license/total-data-volume.html){target=_blank}

+++

+++Kan kunder öka TTL-värdet för [!DNL Journey Optimizer]-systemdatauppsättningsdata i datasjön? 

TTL-tillägg stöds för närvarande inte. Kunderna kan exportera data via Destinationer för att behålla data längre. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html){target=_blank}. Dessutom kan kunder med ett **[!DNL Data Distiller]**-berättigande skapa härledda datauppsättningar för att lagra data i datasjön utan en TTL. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/derived-datasets/overview){target=_blank}

+++

+++Kommer följande funktioner att påverkas av TTL:er? 

* **Sök efter butik**: Nej
* **Resekurser**: Nej
* **Erbjudandebegränsning**: Nej
* **Tidsoptimering för sändning (STO)**: Nej
* **Gränsvärde för meddelandefrekvens** (dvs. affärsregler): Nej
* **Rapportering**: Nej

  >[!NOTE]
  >
  >En TTL har redan implementerats på [!DNL Customer Journey Analytics] (CJA)-anslutningen, vilket minskar den effektiva maximala kontrollperioden för data som påverkas till 13 månader.

* **Experience Platform-datakälla**: Ej tillämpligt - Experience-händelsehämtning stöds inte via datakällor.
* **Beräknade attribut**: Ja - Den initiala efterfyllningsberäkningen begränsas till de senaste 90 dagarnas data. Det beräknade attributet uppdateras baserat på inkrementella händelser för efterföljande uppdateringar. Så snart de följande uppdateringarna når summeringsperioden (max 6 månader) påverkar TTL-värdet inte längre det beräknade attributet. Läs mer.
* **Segmentering och återmarknadsföring**: Ja - Segmenteringen är beroende av data i profilarkivet. Därför är summeringen begränsad till 90 dagar för data som påverkas.
* **Spärra/knip**: Ja - Minskar den effektiva perioden för maximal summering av data som påverkas till 90 dagar. Data från datauppsättningar som påverkas finns i 13 månader inom datasjön.

+++

+++Vilken tidsstämpel används för att kontrollera TTL (t.ex. för bakåtfyllnad)? 

Händelsens tidsstämpel används (dvs. inte datumet för inmatningen).

+++
