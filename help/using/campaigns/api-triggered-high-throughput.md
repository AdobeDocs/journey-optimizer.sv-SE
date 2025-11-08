---
solution: Journey Optimizer
product: journey optimizer
title: Aktivera läget Hög genomströmning för API-utlösta kampanjer
description: Lär dig hur du aktiverar läget Hög genomströmning för API-utlösta kampanjer.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
source-git-commit: 81e54a3e3428d58818805b5dcb397ede4039436a
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---


# Aktivera läget Hög genomströmning för API-utlösta kampanjer {#high-throughput}

Läget för högt dataflöde är utformat för organisationer som behöver **mycket omfattande transaktionsmeddelanden i realtid** (upp till 5 000 transaktioner per sekund). Till skillnad från vanliga API-utlösta kampanjer fungerar kampanjer med hög genomströmning oberoende av Adobe-profiler och kräver en annan konfigurationsmodell.

Den här sidan förklarar hur kampanjer med högt dataflöde skiljer sig från kampanjer som triggas av standard-API, konfigurationskrav och när de ska väljas för varje läge.

## Skyddsritningar och begränsningar

* **Åtkomst** - Endast tillgängligt i USA-regionen för organisationer som är licensierade med tillägget Transactional Messaging med hög genomströmning.

* **Kanaler**: Är för närvarande endast tillgängliga för e-post.

* **Personalization**:

   * All personalisering måste inkluderas i API-nyttolasten som **kontextuella data**. [Lär dig hur du anpassar innehåll med sammanhangsberoende data](../campaigns/api-triggered-campaign-content.md#contextual)
   * Profilbaserad personalisering stöds inte. Om profilvariabler används inträffar valideringsfel.

* **Personaliserade kanalkonfigurationer** - Kanalkonfigurationer som använder [profilbaserad personalisering](../email/surface-personalization.md) kan inte användas med kampanjer med högt dataflöde. Endast ytor utan profilanpassning kan användas.

* **API-slutpunkt** - Högflödeskampanjer använder en annan slutpunkt än standardkampanjer som utlöses av API. Mer information finns i [Kör en API-utlöst kampanj](../campaigns/trigger-campaigns.md#trigger).

* **Exklusivitet för kampanj** - Högeffektiva kampanjer använder inte Adobe-profiler. Meddelanden levereras oavsett om det finns en profil eller inte.

  Dessutom kan en kampanj inte användas för både profilaktiverade och icke-profilerade användningsfall. Om ni behöver båda, skapar ni två separata kampanjer och ser till att det anropande systemet avgör vilken som ska utlösas baserat på sammanhanget.

* **Datauppsättningar för feedback och spårning** - Feedback- och spårningsdata för kampanjer med högt dataflöde lagras i dedikerade datauppsättningar som inte är aktiverade för profiler. Detta innebär att dessa händelser inte sammanfogas med profiler, även om det finns en matchande profil.

  De datauppsättningar som används är:

   * **Händelsedatauppsättning för AJO-meddelandefeedback - Ej profil**
   * **AJO Experience Event-datauppsättning för e-postspårning - icke-profil**

* **Genomströmningsallokering** - Genomströmningen som tillhandahålls med tillägget Högdataflöde är exklusivt reserverad för kampanjer med högt dataflöde. Det finns ingen delning av genomströmning mellan standardkampanjer och API-kampanjer med hög genomströmning.

## Välj mellan standardkampanjer och kampanjer med hög genomströmning

Använd den här tabellen för att bestämma vilken API-utlöst kampanjtyp som passar ert användningsfall:

| Funktion/Krav | Standard-API - utlöst kampanj | Höggenomströmningskampanj |
|------------------------|---------------------------------|---------------------------|
| **Tillgänglighet** | Ingår i baserbjudandet | Kräver tillägg för transaktionsmeddelanden med hög genomströmning. |
| **Genomflöde** | Upp till 500 transaktioner per sekund | Upp till 5 000 transaktioner per sekund |
| **Kanaler** | E-post, SMS, push | E-post |
| **Personalization** | Profil + sammanhangsberoende i API-nyttolasten | Sammanhangsberoende i API-nyttolasten |
| **Profil och häftning** | Finns eller skapas med händelser sammanfogade med en profil | Ingen profil |
| **Meddelandevolym** | Standardberättigande och meddelandepaket | Separata volymer med nivåindelade meddelanden |
| **Infrastruktur** | Standard | Förbättrat |
| **Drifttid** | 99,9 % | 99,99 % |
| **API för hälsokontroll** | Ja | Ja |

Med andra ord:

* Välj **Standard API utlöste** kampanjer om:
   * Du har inte kontrakt med högdataström.
   * Ditt genomströmningsbehov är &lt;500 TPS.
   * Ni behöver personalisering baserat på Adobe-profiler.
   * Ni vill att kampanjdata ska sammanfogas med profiler för framtida målinriktning.
   * Du vill använda en annan kanal än E-post.

* Välj **kampanjer med hög genomströmning** om:
   * Du behöver ett genomflöde på >500 TPS.
   * Du behöver inte sy ihop profiler.
   * Du kan skicka all personalisering i API-nyttolasten.
   * Du vill använda e-postkanalen.

## Inställningsriktlinjer

Följ dessa riktlinjer för att konfigurera kampanjer med hög genomströmning korrekt:

1. Skapa en ny IP-pool. [Lär dig skapa IP-pooler](../configuration/ip-pools.md)
1. Skapa en ny kanalkonfiguration. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md)
1. Kontakta Adobe kundtjänst om du vill att den aktiverade ytan ska mappas till kapaciteten för hög genomströmning. Ange information om kanalkonfiguration och IP-pool tillsammans med ditt företags-ID.

>[!IMPORTANT]
>
>IP-poolen och kanalkonfigurationerna som är avsedda för transaktionsmeddelanden med hög genomströmning måste användas uteslutande för det ändamålet, och inte för standardmeddelanden med API-utlösta kampanjer eller resor.
