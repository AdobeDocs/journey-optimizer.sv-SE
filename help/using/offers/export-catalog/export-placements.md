---
title: Datauppsättning med placeringar
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för placeringar
badge: label="Äldre" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: 3e45f3cf-e17e-43a6-8424-98afef07aaa3
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Datauppsättning med placeringar {#placements-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för ersättningar.

![](../assets/dataset-placements.png)

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

>[!NOTE]
>
>Lär dig hur du får åtkomst till exporterade datauppsättningar för varje objekt i ditt Erbjudandebibliotek i [det här avsnittet](../export-catalog/access-dataset.md).

Här är en lista över alla fält som kan användas i datamängden **[!UICONTROL Decision Object Repository - Placements]**.

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

+++ Identifierare

**Fält:**&#x200B;_id
**Titel:** Identifierare
**Beskrivning:** En unik identifierare för posten.
**Typ:** sträng

+++

+++ upplevelse

**Fält:**&#x200B;_upplevelse
**Typ:** objekt

+++

+++ _experience > decisioning

**Fält:** beslut
**Typ:** objekt

+++

+++ _experience > decisioning > Placements Channel Identifier

**Fält:** channelID
**Titel:** Placeringens kanal-ID
**Beskrivning:** Den kanal som förslaget gjordes i. Värdet är en giltig kanal-URI. Se https://ns.adobe.com/xdm/channels/channel.
**Typ:** sträng

+++

+++ _experience > decisioning > Content Component Type

**Fält:** componentType
**Titel:** Innehållskomponenttyp
**Beskrivning:** En uppräknad uppsättning URI:er där varje värde mappas till en typ som anges för innehållskomponenten. En del användare av innehållsrepresentationerna förväntar sig att värdet @type ska vara en referens till schema som beskriver ytterligare egenskaper för innehållskomponenten.
**Typ:** sträng

+++

+++ _experience > Decision > contentTypes

**Fält:** contentTypes
**Typ:** array

+++

+++_experience > decisioning > contentTypes > MIME Media Type

**Titel:** MIME-mediatyp
**Beskrivning:** En begränsning för medietypen för komponenterna som förväntas i placeringen. Det kan finnas mer än en medietyp för en komponent, t.ex. ett annat bildformat.
**Typ:** sträng

+++

+++ _experience > decisioning > Placement Description

**Fält:** beskrivning
**Titel:** Beskrivning av placering
**Beskrivning:** Det används för att förmedla mänskliga läsbara avsikter om hur dynamiskt innehåll används i den övergripande meddelandeleveransen. Att ett visst utrymme är en \&quot;Banner\&quot; på en webbsida förmedlas ofta via beskrivningen och inte med en formell metod.
**Typ:** sträng

+++

+++ _experience > decisioning > Placement name

**Fält:** namn
**Titel:** Placeringsnamn
**Beskrivning:** Ett tilldelat namn för placeringen som refererar till den i mänsklig interaktion.
**Typ:** sträng

+++

+++ repo

**Fält:**&#x200B;_repo
**Typ:** objekt

+++

+++ _repo > Placement ETag

**Fält:**-tagg
**Titel:** Placement ETag
**Beskrivning:** Den revision som beslutsalternativsobjektet var när ögonblicksbilden togs.
**Typ:** sträng

+++
