---
solution: Journey Optimizer
product: journey optimizer
title: AEM Content Fragments
description: Lär dig hur du kommer åt och hanterar AEM Content Fragments
topic: Content Management
role: User
level: Beginner
source-git-commit: b06229e7a2fc64fbe28154c798b152cca8203a86
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---

# Kom igång med Adobe Experience Manager Content Fragments {#aem-fragments}

Genom att integrera Adobe Experience Manager as a Cloud Service med Adobe Journey Optimizer kan du nu smidigt införliva dina AEM Content Fragments i ditt Journey Optimizer-innehåll. Denna smidiga anslutning förenklar processen att komma åt och utnyttja AEM-innehåll, vilket gör det möjligt att skapa personaliserade och dynamiska kampanjer och resor.

Mer information om AEM Content Fragments finns i [Arbeta med innehållsfragment](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"} i Experience Manager-dokumentationen.

## Före start {#start}

>[!AVAILABILITY]
>
>För hälso- och sjukvårdskunder aktiveras integreringen endast när man licensierar Journey Optimizer Healthcare Shield och Adobe Experience Manager Enhanced Security-tillägg.

### Begränsningar {#limitations}

Observera följande begränsningar när du arbetar med Adobe Experience Manager Content Fragments i Journey Optimizer:

* **Typer av innehållsfragment**: Enkla innehållsfragment och kapslade innehållsfragment stöds. Varianter av innehållsfragment stöds för närvarande inte.

* **Flerspråkigt innehåll**: Endast det manuella flödet stöds. Varje språkvariant måste vara självständigt skapad i Adobe Experience Manager, taggad, publicerad och manuellt vald i Journey Optimizer. Det finns ingen automatisk språkupplösning eller reservmekanism.

* **Databasåtkomst**: Journey Optimizer integreras exklusivt med Adobe Experience Manager Publish-nivån, där innehållsfragment är tillgängliga via en offentlig, oautentiserad slutpunkt. Författardatabaser kan visas i databasväljaren, men bara innehållsfragment som publiceras till publiceringsnivån kan användas i Journey Optimizer.

* **Status för innehållsfragment**: Journey Optimizer visar innehållsfragment med statusen **Publicerad** och **Ändrad**. I samtliga fall används endast den senaste publicerade versionen. Om ett fragment ändras efter publiceringen återspeglas inte dessa ändringar i Journey Optimizer förrän innehållsfragmentet publiceras på nytt i Adobe Experience Manager. Det finns ingen automatisk versionsavstämning mellan Adobe Experience Manager och Journey Optimizer.

* **Personalization**: Endast profilattribut, kontextattribut, statiska strängar och fördeklarerade variabler stöds. Härledda eller beräknade attribut stöds inte.

* **Uppdateringar och versionshantering**: Uppdateringar av innehållsfragment kräver manuell publicering från Adobe Experience Manager. Det finns ingen automatisk versionsavstämning mellan Adobe Experience Manager och Journey Optimizer. När ett innehållsfragment publiceras i Adobe Experience Manager får Journey Optimizer en händelse och uppdateringar från Journey Optimizer sida. Om uppdateringen lyckas kommer den att vara tillgänglig efter 5 minuter för Unitary Journeys och i nästa batch för Batch use-cases.

* **Cachelagring och korrektur**: Innehållsfragment hämtas i realtid från Adobe Experience Manager publiceringsnivå. Det finns ingen cachelagring före rendering eller ögonblicksbild. Korrektur för kampanjer och resor återspeglar alltid den senast publicerade versionen av innehållsfragmentet, och historiska versioner kan inte låsas för korrektur.

* **Användaråtkomst**: Vi rekommenderar att du begränsar antalet användare som har behörighet att publicera innehållsfragment för att minska risken för oavsiktliga fel.


### Livscykel för innehållsfragment

![](assets/do-not-localize/AEM_CF.png)

Innehållsfragment följer olika livscykelsteg beroende på vilken Adobe Experience Manager-nivå de finns i. [Läs mer i Adobe Experience Manager-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)

Innehåll skapas och hanteras på **författarnivå**, där fragment kan ha status som Nytt, Utkast, Publicerat, Ändrat eller Opublicerat. Dessa statusvärden gäller endast för **författarnivån** och stöder skapande och granskning av innehåll.

När ett innehållsfragment publiceras skapas en kopia på **publiceringsnivån** och visas via en offentlig, oautentiserad slutpunkt. Journey Optimizer integreras exklusivt med denna **publiceringsnivå**.

Därför använder Journey Optimizer bara publicerade eller ändrade innehållsfragment och alltid den senaste publicerade versionen. Ändringar som görs efter publiceringen återspeglas inte i Journey Optimizer förrän innehållsfragmentet publiceras på nytt.


## Felsökning {#troubleshooting}

Om du får problem när du arbetar med Adobe Experience Manager Content Fragments i Journey Optimizer, se följande vanliga problem och lösningar:

| Problem | Orsak | Upplösning |
|-|-|-|
| **Taggen hittades inte** eller **Innehållsfragmentet visas inte i väljaren** | Adobe Experience Manager-taggsyntaxen matchar inte det obligatoriska formatet `ajo-enabled:{OrgId}/{SandboxName}` | Verifiera att tagg-ID:t använder rätt **organisations-ID** och **sandlådenamn**. Kontrollera att det inte finns några blanksteg eller felaktiga avgränsare. Publicera om innehållsfragmentet när du har korrigerat taggen. |
| **Innehållsfragment visas inte i listan** | Innehållsfragment är i utkastläge eller inte godkänt | Endast godkända och publicerade innehållsfragment visas i Journey Optimizer-väljaren. Publicera innehållsfragmentet i Adobe Experience Manager och kontrollera att det har statusen Godkänd. |
| **Variabelfel odefinierat** | Personalization-platshållaren har inte deklarerats i hjälptaggen för fragment | Lägg till alla nödvändiga parametrar i fragmentets hjälptagg. Varje platshållare som används i Content Fragment måste deklareras explicit med dess mappning. |
| **Korrektur visar oväntat innehåll** | Korrektur använder den senaste publicerade versionen från Adobe Experience Manager | Korrektur återspeglar alltid den senaste publikationen av Content Fragment i Adobe Experience Manager. Om du nyligen har gjort ändringar i Adobe Experience Manager publicerar du om fragmentet och uppdaterar korrekturet. |
| **Åtkomst nekad (CPES) fel** | Användarrollen har inte behörighet att komma åt vissa attribut | Kontakta systemadministratören för att verifiera att din roll har rätt behörighet för den profil eller de kontextuella attribut som används vid personalisering. |
| **Fragment visar tomt eller saknat innehåll** | Obligatoriska personaliseringsparametrar eller reservvärden saknas | Se till att alla obligatoriska parametrar anges och överväg att lägga till reservvärden för valfria attribut. |

Om problemet kvarstår kontaktar du Adobe-representanten med information om ditt ID för innehållsfragment, kampanj- eller resa samt eventuella felmeddelanden.
