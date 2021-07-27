---
title: Om datakällor
description: Läs om hur du konfigurerar en datakälla
feature: Datakällor
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: d69779418d50fdc4b75cc777b27a62392d1634a0
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 72%

---

# Om datakällor {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Om datakällor"
>abstract="Datakällans konfiguration utförs alltid av en teknisk användare. Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna. Dessa kan till exempel vara: villkorsdefinitioner, parameter- och personaliseringsdata i åtgärder, anpassade väntedefinitioner och definitionen av tidszoner."

Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna, till exempel:

* [villkorsdefinitioner](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [åtgärder](../action/action.md)
* [anpassade väntedefinitioner](../building-journeys/wait-activity.md#custom)
* [definition av tidszoner](../building-journeys/timezone-management.md)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelses nyttolast. Om din resa till exempel består av en händelse som följs av en meddelandeaktivitet som bara använder data från händelsen behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den förkonfigurerade datakällan i Adobe Experience Platform som definierar anslutningen till kundprofilen i realtid. Detta är en inbyggd datakälla. Läs [den här sidan](../datasource/adobe-experience-platform-data-source.md).
* De externa datakällor som du använder för att definiera en anslutning till externa system. Dessa är de du kan skapa. Läs [den här sidan](../datasource/external-data-sources.md).

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Läs [den här sidan](../datasource/configure-data-sources.md#define-field-groups).

>[!NOTE]
>
>Schemarelationer stöds nu för datakällor.

Mer information om hur du konfigurerar en Adobe Experience Platform-datakälla och en extern datakälla samt hur du söker efter och använder data under en resa finns i denna [självstudievideo](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/configure-data-sources.html){target=&quot;_blank&quot;}.
