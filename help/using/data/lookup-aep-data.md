---
solution: Journey Optimizer
product: journey optimizer
title: Använd Adobe Experience Platform-data
description: Lär dig hur du använder Adobe Experience Platform datamängder i [!DNL Journey Optimizer] Funktioner för beslutsfattande och personalisering.
badge: label="Begränsad tillgänglighet" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare
mini-toc-levels: 1
exl-id: 44a8bc87-5ab0-45cb-baef-e9cd75432bde
source-git-commit: 42f231a9b0b34a63d1601dcae653462f6321caed
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Använd Adobe Experience Platform-data {#aep-data}

>[!CONTEXTUALHELP]
>id="lookup-aep-data"
>title="Aktivera för sökning"
>abstract="Aktivera för sökning"

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande tillgänglig för alla kunder i en begränsad version.

Med Journey Optimizer kan ni utnyttja data från Adobe Experience Platform med personalisering och beslutsfunktioner. För att göra detta måste postbaserade datauppsättningar som behövs för sökpersonalisering först aktiveras för söktjänsten enligt beskrivningen nedan.

## Måste läsas

### Guardsutkast och riktlinjer {#guidelines}

Läs följande begränsningar och riktlinjer innan du börjar:

* Datauppsättningar som har aktiverats för sökning får inte innehålla någon PII (Personally Identiitable Information).
* Datauppsättningar som är aktiverade för sökning och används för personalisering är inte skyddade för borttagning. Det är upp till dig att hålla reda på vilka datauppsättningar som används för personalisering för att säkerställa att de inte tas bort eller tas bort.
* Datauppsättningar måste associeras med ett schema som INTE är av profiltyp eller händelsetyp.
* Scheman måste ha en primär identitet. Endast en enda primärnyckel kan användas för sökningar.

### Tillstånd för sökningstjänst

| Funktionskomponent | Begränsning för produktionssandlåda | Anteckningar |
| ------- | ------- | ------- |
| Aktiverade uppslagsdatauppsättningar | Max 10 per organisation | Maximalt antal datauppsättningar som kan konfigureras för sökning vid en given tidpunkt. Den här gränsen gäller det totala antalet uppslagsdatauppsättningar både i produktions- och utvecklingssandlådor i kundinstansen. |
| Antal datauppsättningsposter | Upp till 2 miljoner poster per datauppsättning | Maximalt antal poster som tillåts i en enskild datauppsättning, beräknat som det totala antalet för alla batchar i den datauppsättningen. |
| Poststorlek | Upp till 2 kB per post | Maximal standardpoststorlek stöds. |
| Datauppsättningsstorlek | Upp till 4 GB | Maximal storlek för en enskild datauppsättning, inte den kombinerade storleken för alla datauppsättningar i en sandlåda. Antalet poster och storleksbegränsningarna för datauppsättningar är oberoende garderobar - båda måste vara uppfyllda. |
| Uppdateringar av datauppsättningsfrekvens | Upp till 5 uppdateringar per dag per datauppsättning | Maximal frekvens för uppdateringsåtgärder som tillåts för en enskild datauppsättning per dag. |

>[!NOTE]
>
>Om du behöver ytterligare volymer utöver de säkerhetsalternativ som anges ovan kontaktar du Adobe.

### Ytterligare prestandaöverväganden

Rekommendationerna nedan är riktlinjer för att undvika förseningar i leveransen:

| Övervägande | Rekommenderad gräns | Beskrivning |
| ------- | ------- | ------- |
| Attribut per sökning | Upp till 20 | Antal datafält som har hämtats per post i en enda sökningsaktivitet. |
| Uppslagsaktiviteter | Upp till 5 per resa | Varje resa kan innehålla upp till fem separata sökningsaktiviteter. Varje sökning kan ha en egen datauppsättning som mål. |

## Aktivera en datauppsättning för datasökning {#enable}

För att kunna utnyttja data från datauppsättningen för personalisering måste du aktivera datauppsättningen för sökning.

### Förhandskrav {#prerequisites-enable}

Schemat som är associerat med din datauppsättning som du vill aktivera för sökning måste vara av posttyp. Schemat ska INTE vara av profil- eller händelseklass.

+++Exempel

![](assets/data-lookup-schema.png)

+++

Schemat måste ha en primär identitet definierad.

+++Exempel

![](assets/data-lookup-primary.png)

+++

Om ett anpassat namnutrymme inte har definierats än kontrollerar du att identiteten är en icke-personidentifierare.

+++Exempel

![](assets/aep-data-namespace.png)

+++

### Aktivera datauppsättningen för sökning i datauppsättningens hanteringsgränssnitt

Använd växlingsknappen i användargränssnittet för datauppsättningshantering för att aktivera datauppsättningen för sökning.

![](assets/aep-data-enable.png)

>[!NOTE]
>
>Vi rekommenderar att datauppsättningen INTE är aktiverad för profilen eftersom detta kan leda till ökad profilrikedom och inte behövs för att utföra sökningarna.

### API-metod

Följ anvisningarna i [den här dokumentationen](https://developer.adobe.com/journey-optimizer-apis/references/authentication/) för att konfigurera miljön för att skicka API-kommandon.

#### Förhandskrav

* Utvecklarprojektet måste ha Adobe Journey Optimizer- och Adobe Experience Platform-API:erna tillagda i projektet.

  ![](assets/aep-data-api.png)

* Du måste ha behörighet att hantera datauppsättningar som en del av din roll.

* Schemat som datauppsättningen baseras på måste innehålla en primär identitet som kan fungera som söknyckeln.

#### API-anropsstruktur

```shell
curl -s -XPATCH "https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}" \ -H "Authorization: Bearer ${ACCESS_TOKEN}" \ -H "x-api-key: ${API_KEY}" \ -H "x-gw-ims-org-id: ${IMS_ORG}" \ -H "x-sandbox-name: ${SANDBOX_NAME}" 
```

Var:

* URL är `https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}`
* Datauppsättnings-ID är den datauppsättning som du vill aktivera.
* Åtgärden är aktiverad eller inaktiverad.
* Åtkomsttoken kan hämtas från utvecklarkonsolen.
* API-nyckeln kan hämtas från utvecklarkonsolen.
* IMS Org ID är din Adobe-organisation.
* Sandlådenamn är namnet på sandlådan som datauppsättningen finns i (d.v.s. prod, dev.s.).

>[!NOTE]
>
>Om du får ett felmeddelande nedan när du försöker aktivera datauppsättningar kan du försöka med att ta bort Adobe Journey Optimizer API:er från ditt utvecklarkonsolprojekt och sedan lägga till dem igen:
>
>`"error_code": "403003",`
>`"message": "Api Key is invalid"`

## Datauppsättningsövervakning

När en datauppsättning har aktiverats för sökning kan du granska statusen för inmatning i sökningstjänsten genom att gå till **[!UICONTROL Monitoring]**-menyn och välja fliken **[!UICONTROL Journey Optimizer]**.

Den här processindikatorn hjälper till att förstå när nya grupper med data är tillgängliga i sökningstjänsten.

![](assets/aep-data-monitoring.png)

<!--Ivan Mironchuk
Note - we have a bug here currently. Will need to update screenshot once the lookup service will accurately reflect the progress.-->

## Nästa steg

När en datauppsättning har aktiverats för sökning med ett API-anrop kan du använda data med personalisering och beslutsfunktioner för [!DNL Journey Optimizer]. Mer information finns i följande avsnitt:

* [Använd Adobe Experience Platform-data för personalisering](../personalization/aep-data-perso.md)
* [Använd Adobe Experience Platform-data för beslut](../experience-decisioning/aep-data-exd.md)
