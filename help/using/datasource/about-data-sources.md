---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datakällor
description: Lär dig hur du kommer igång med datakällor
feature: Journeys, Data Sources
topic: Administration
role: Developer, Admin
level: Intermediate, Experienced
keywords: data, källa, resa, plattform
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 302db58525a7b2648bb9c44bc9b42da787ca9c43
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 31%

---

# Kom igång med datakällor {#about-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="Om datakällor"
>abstract="Datakällans konfiguration utförs alltid av en teknisk användare. Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna. Dessa kan till exempel vara: villkorsdefinitioner, parameter- och personaliseringsdata i åtgärder, anpassade väntedefinitioner och definitionen av tidszoner."

Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna, till exempel:

* [villkorsdefinition](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [åtgärder](../action/action.md)
* [egen väntedefinition](../building-journeys/wait-activity.md#custom)
* [tidszonsdefinition](../building-journeys/timezone-management.md)

➡️ [Upptäck den här funktionen i en video](#video)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelses nyttolast. Om din resa till exempel består av en händelse som följs av en kanalåtgärdsaktivitet som bara använder data från händelsen, behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den **förkonfigurerade** Adobe Experience Platform-datakälla som definierar anslutningen till kundprofiltjänsten i realtid. Detta är en inbyggd datakälla. Läs [den här sidan](../datasource/adobe-experience-platform-data-source.md).
* De **externa**-datakällor som du kan använda för att definiera en anslutning till externa system. Dessa är de du kan skapa. Läs [den här sidan](../datasource/external-data-sources.md).

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall. Mer information om svar finns i [avsnittet](../action/action-response.md)

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Läs [den här sidan](../datasource/configure-data-sources.md#define-field-groups).

>[!NOTE]
>
>Schemarelationer stöds inte för datakällor.

## Välj en strategi för dataåtkomst {#data-access-strategy}

Innan du konfigurerar en datakälla bör du tänka på vilken metod som passar bäst för ditt användningssätt. Det finns tre alternativ, var och en med olika kompromisser vad gäller beständighet, profilberikning och återanvändbarhet. Mer information om de här alternativen finns i [Bästa tillvägagångssätt för avancerade resor i Journey Optimizer](https://experienceleague.adobe.com/en/perspectives/best-practices-for-advanced-journeys-in-journey-optimizer){target="_blank"}.

**Alternativ 1 - få åtkomst till externa data via anpassade åtgärder (ingen datasjön)**

Anslut direkt till ett externt API vid körning utan beständiga data i Experience Platform Data Lake. Passar bäst när:

* Data är bara användbara i resans sammanhang och behövs inte någon annanstans.
* Det externa systemet är tillgängligt via en API-slutpunkt som returnerar de attribut som behövs.

Läs mer om [anpassade åtgärder](../action/action.md) och [anpassade åtgärdssvar](../action/action-response.md).

**Alternativ 2 - Datauppsättning i datasjön, inte aktiverad för profil**

Infoga data i en datauppsättning för att utlösa och personalisera resor baserat på kontextuella händelsedata, utan att bidra till kundprofilen i realtid. Passar bäst när:

* Posterna innehåller ett identitetsfält som kan användas för att komma åt profiler som redan lagrats i Experience Platform.
* Data behövs inte för att skapa målgrupper eller för att sätta ihop identiteter utanför Journey Optimizer.

**Alternativ 3 - Profilaktiverad datauppsättning i datasjön**

Infoga data i en profilaktiverad datauppsättning för att skapa målgrupper, förbättra identitetsdiagram och utnyttja data över flera resor och RT-CDP-destinationer. Passar bäst när:

* Data är användbara för målgruppsdefinitioner som används i kanaler utanför Journey Optimizer.
* Data innehåller flera identiteter som bidrar till mer detaljerade, sammanfogade profilfragment.

| | Data bevaras i datasjön | Datauppsättning aktiverad för profil |
| --- | --- | --- |
| **Alternativ 1** - Externa data via anpassade åtgärder | Nej | Nej |
| **Alternativ 2** - Datauppsättningen har inte aktiverats för profilen | Ja | Nej |
| **Alternativ 3** - Profilaktiverad datauppsättning | Ja | Ja |

Titta på den här [självstudievideon](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html){target="_blank"} för att få mer information om hur du konfigurerar en datakälla i Adobe Experience Platform och en extern datakälla samt hur du hittar och använder data i en resa.

## Instruktionsvideo {#video}

Lär dig mer om vad en datakälla är och hur du konfigurerar Experience Platform och externa datakällor.

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

