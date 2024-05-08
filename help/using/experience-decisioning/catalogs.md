---
title: Artikelkatalog
description: Lär dig hur du arbetar med artikelkatalogen
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet"
exl-id: 2d118f5a-32ee-407c-9513-fe0ebe3ce8f0
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Artikelkatalog {#catalog}

I Experience Decision fungerar kataloger som centrala behållare för att organisera beslutsobjekt. Varje katalog är länkad till ett Adobe Experience Platform-schema som innehåller alla attribut som kan tilldelas ett beslutsobjekt.

För närvarande konsolideras alla beslutsobjekt som skapats i en enda katalog, tillgänglig via **[!UICONTROL  Catalogs]** -menyn.

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
   >För närvarande stöder Experience Decisioning endast följande datatyper: String, Integer, Boolean, Date, DateTime och Decisioning Asset. Fält som ligger utanför dessa datatyper är inte tillgängliga för redigering av beslutsobjekt eller kataloger.

   Värdet som anges för ett attribut med ett decimalresursattribut är en publik url. För det mesta pekar detta på en bild.

   Detaljerad information om hur du arbetar med Adobe Experience Platform scheman finns i [XDM-systemdokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html).

1. Spara schemat när du har lagt till de anpassade attributen. Det nya fältet är nu tillgängligt på skärmen för att skapa artikelbeslut i **[!UICONTROL Custom attributes]** -avsnitt.
