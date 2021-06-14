---
title: Återförsök
description: Lär dig hur nya försök utförs innan du skickar en adress till listan över inaktiveringar
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 2%

---


# Återförsök {#retries}

När ett meddelande misslyckas på grund av ett tillfälligt **Mjukt studs** eller **Ignorerat**-fel, utförs flera försök. Varje fel ökar en felräknare. När den här räknaren når gränsvärdet läggs adressen till i listan över spärrade adresser.

I standardkonfigurationen<!--so can you edit this setting or not?? contradictory information was given--> anges tröskelvärdet till tre fel:

* Vid det tredje felet som påträffades vid samma leverans ignoreras adressen.

* Om det finns olika leveranser och två fel inträffar med minst 24 timmars mellanrum, ökas felräknaren vid varje fel och adressen visas inte vid det tredje försöket.

Om en leverans lyckas efter ett nytt försök initieras adressräknaren på nytt.

Du kan ändra gränsvärdet med knappen **[!UICONTROL Edit]** på menyn **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL General]**.<!--currently you can edit this in staging // now I see in UI: Suppression rule > Bounce days??? > 4-->

![](../assets/retries-edition.png)

## Varaktighet för nytt meddelandeförsök {#retry-duration}

Nya försök utförs i **3,5 dagar** från den tidpunkt då meddelandet lades till i e-postkön.

Den minsta fördröjningen mellan återförsök och det maximala antalet återförsök som ska utföras är <!--managed by the Enhanced MTA,--> baserat på hur bra en IP fungerar, både historiskt och för närvarande på en viss domän.

Efter 3,5 dagar tas alla meddelanden i kön för nya försök bort från kön och skickas tillbaka som ett studs.<!--???-->