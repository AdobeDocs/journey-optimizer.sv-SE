---
title: Objektkatalog
description: Lär dig hur du arbetar med objektkatalogen
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 613a0a16-2e8f-499d-9db4-5175fefd93cc
source-git-commit: d5b283a9c9b0e3e4104dddb3bcb4b47bbd749113
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 1%

---

# Objektkatalog {#catalog}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * **[Konfigurera objektkatalogen](catalogs.md)**
   * [Skapa beslutsobjekt](items.md)
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
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
   >* Siffra

   Detaljerad information om hur du arbetar med Adobe Experience Platform scheman finns i [XDM-systemdokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html).

1. Spara schemat när du har lagt till de anpassade attributen. Det nya fältet är nu tillgängligt på skärmen för att skapa artikelbeslut i **[!UICONTROL Custom attributes]** -avsnitt.
