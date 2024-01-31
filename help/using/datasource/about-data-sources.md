---
solution: Journey Optimizer
product: journey optimizer
title: Om datakällor
description: Läs om hur du konfigurerar en datakälla
feature: Journeys, Data Sources
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate, Experienced
keywords: data, källa, resa, plattform
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 60%

---

# Om datakällor {#about-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="Om datakällor"
>abstract="Datakällans konfiguration utförs alltid av en teknisk användare. Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna. Dessa kan till exempel vara: villkorsdefinitioner, parameter- och personaliseringsdata i åtgärder, anpassade väntedefinitioner och definitionen av tidszoner."

Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna, till exempel:

* [villkorsdefinition](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [åtgärder](../action/action.md)
* [egen väntedefinition](../building-journeys/wait-activity.md#custom)
* [tidszonsdefinition](../building-journeys/timezone-management.md)

➡️ [Upptäck den här funktionen i video](#video)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelses nyttolast. Om din resa till exempel består av en händelse som följs av en kanalåtgärdsaktivitet som bara använder data från händelsen, behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den förkonfigurerade datakällan i Adobe Experience Platform som definierar anslutningen till kundprofilen i realtid. Detta är en inbyggd datakälla. Läs [den här sidan](../datasource/adobe-experience-platform-data-source.md).
* De externa datakällor som du använder för att definiera en anslutning till externa system. Dessa är de du kan skapa. Läs [den här sidan](../datasource/external-data-sources.md).

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall.

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Läs [den här sidan](../datasource/configure-data-sources.md#define-field-groups).

>[!NOTE]
>
>Schemarelationer stöds inte för datakällor.

Mer information om hur du konfigurerar en Adobe Experience Platform-datakälla och en extern datakälla samt hur du söker efter och använder data under en resa finns i [videokurs](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html){target="_blank"}.

## Instruktionsvideo {#video}

Lär dig mer om vad en datakälla är och hur du konfigurerar Experience Platform och externa datakällor.

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

