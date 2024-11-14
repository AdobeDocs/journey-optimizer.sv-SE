---
solution: Journey Optimizer
product: journey optimizer
title: Anpassad uppladdning (CSV) och sammanställning av externa målgrupper
description: Lär dig viktig information och bästa praxis när du arbetar med målgrupper med anpassad uppladdning (CSV) och Federated Audience Composition.
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
exl-id: d2365e3f-fbef-43c2-bf2a-0a868cb93015
source-git-commit: a98312d9ac5a457bfd6789bf79ad80a24d894a0b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

---

# Anpassad uppladdning (CSV) och sammanställning av externa målgrupper {#csv-fac}

## Om anpassad uppladdning och sammanställning av externa målgrupper {#about}

Förutom segmentdefinitioner och målgruppskomposition kan du med [!DNL Journey Optimizer] generera och rikta in målgrupper genom att importera dem från en CSV-fil eller utnyttja data från datalagret.

* **Anpassad överföring**: Importera en målgrupp med en CSV-fil. Lär dig hur du importerar målgrupper i Adobe Experience Platform [dokumentation för segmenteringstjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}.

* **Federated Audience Composition**: Federate-datauppsättningar direkt från ditt befintliga datalager för att skapa och berika Adobe Experience Platform-målgrupper och attribut i ett och samma system. Läs guiden om [Federated Audience Composition](https://experienceleague.adobe.com/sv/docs/federated-audience-composition/using/home).

Du kan rikta in de här målgrupperna i Journey Optimizer eller aktivera dem till vilket mål som helst som stöds av Adobe Experience Platform

➡️ [Upptäck de här funktionerna i videon](#video)

## Måste läsas {#must-read}

I det här avsnittet finns viktig information som du bör tänka på när du arbetar med målgrupper med anpassad uppladdning (CSV-filer) och Federated Audience Composition.

* **Stöd för förhandsgranskning och korrektur:** För närvarande stöds inte förhandsgranskning och korrektur för målgrupper som skapats med CSV-överföring eller sammanställning av federerade målgrupper. Tänk på detta när ni planerar era kampanjer.

* **Aktiveringsfördröjning:** Publikerna är klara att användas i Journey Optimizer direkt när importen är klar. Detta är vanligtvis inom en timme, men kan variera.

* **Aktiverade poster och identitetssammanfogning:** Alla poster i målgruppen aktiveras, inklusive eventuella dubbletter. Under nästa UPS-profilexport kommer dessa poster att genomgå identitetssammanfogning. Det innebär att antalet aktiverade poster kan skilja sig från antalet profiler efter identitetssammanfogning.

* **Nya profiler:** Om det inte går att hitta någon matchning mellan en post och en UPS-profil skapas en ny tom profil. Den här profilen är kopplad till anrikningsattributen som lagras i datasjön. Eftersom den nya profilen är tom är målfält som vanligtvis används i Journey Optimizer (t.ex. personalEmail.address, mobilePhone.number) tomma och kan därför inte användas som mål.

  För att lösa detta kan du ange &quot;körningsfält&quot; (eller &quot;körningsadress&quot; beroende på kanal) i kanalkonfigurationen som &#39;identityMap&#39;. På så sätt säkerställs att det attribut som väljs som identitet när målgrupper skapas blir det som används för målgruppsanpassning i Journey Optimizer.

## Instruktionsfilmer {#video}

Lär dig hur du överför målgrupper i CSV-format till Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/3421714?quality=12)

Läs mer om sammanställning av federerad publik.

>[!VIDEO](https://video.tv.adobe.com/v/3432261?quality=12)
