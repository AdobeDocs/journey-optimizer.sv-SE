---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datakällor
description: Lär dig hur du kommer igång med datakällor
feature: Journeys, Data Sources
topic: Administration
role: Engineer, Admin
level: Intermediate, Experienced
keywords: data, källa, resa, plattform
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 56%

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

Titta på den här [självstudievideon](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html){target="_blank"} för att få mer information om hur du konfigurerar en datakälla i Adobe Experience Platform och en extern datakälla samt hur du hittar och använder data i en resa.

## Instruktionsvideo {#video}

Lär dig mer om vad en datakälla är och hur du konfigurerar Experience Platform och externa datakällor.

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

