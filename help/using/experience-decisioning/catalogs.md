---
title: Objektkatalog
description: Lär dig hur du arbetar med objektkatalogen
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 2d118f5a-32ee-407c-9513-fe0ebe3ce8f0
source-git-commit: c13cd73229b2fab80722663afae9fe24b660c0f9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Objektkatalog {#catalog}

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsposter: **[Konfigurera objektkatalogen](catalogs.md)** - [Skapa beslutsobjekt](items.md) - [Hantera artikelsamlingar](collections.md)
* Konfigurera objektmarkering: [Skapa beslutsregler](rules.md) - [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

I Experience Decision fungerar kataloger som centrala behållare för att organisera beslutsobjekt. Varje katalog är länkad till ett Adobe Experience Platform-schema som innehåller alla attribut som kan tilldelas ett beslutsobjekt.

För närvarande konsolideras alla beslutsobjekt som skapats i en enda katalog, tillgänglig via **[!UICONTROL Items]** -menyn.

![](assets/catalogs-list.png)

Följ de här stegen för att komma åt katalogschemat där beslutsobjektens attribut lagras:

1. Klicka på **[!UICONTROL Edit schema]** knappen finns bredvid **[!UICONTROL Create item]** -knappen.

1. Katalogens schema öppnas på en ny flik, enligt strukturen nedan:

   * The **`_experience`** noden innehåller standardobjektattribut som namn, start- och slutdatum samt beskrivning.
   * The **`_<imsOrg>`** noden innehåller anpassade beslutsobjektattribut. Som standard har inga anpassade attribut konfigurerats, men du kan lägga till så många som behövs för att passa dina behov. När du är klar visas anpassade attribut tillsammans med standardattributen på skärmen för att skapa beslutsobjekt.

   ![](assets/catalogs-schema.png)

1. Om du vill lägga till ett anpassat attribut i schemat expanderar du **`_<imsOrg>`** och klicka på plusknappen (+) på önskad plats i strukturen.

   ![](assets/catalogs-add.png)

1. Fyll i de fält som behövs för attributet som lagts till och klicka på **[!UICONTROL Apply]**.

   >[!CAUTION]
   >
   >För närvarande har Experience Decision exklusivt stöd för de datatyper som anges nedan. Fält som ligger utanför dessa datatyper är inte tillgängliga för användning när ett beslutsobjekt skapas.
   >* Sträng
   >* Boolean
   >* Nummer

   Detaljerad information om hur du arbetar med Adobe Experience Platform scheman finns i [XDM-systemdokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html).

1. Spara schemat när du har lagt till de anpassade attributen. Det nya fältet är nu tillgängligt på skärmen för att skapa artikelbeslut i **[!UICONTROL Custom attributes]** -avsnitt.
