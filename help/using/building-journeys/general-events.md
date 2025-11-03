---
solution: Journey Optimizer
product: journey optimizer
title: Allmänna händelser
description: Lär dig hur du använder allmänna händelser
feature: Journeys, Events
topic: Content Management
role: User
level: Intermediate
keywords: skräddarsydd, allmän, evenemang, resa
exl-id: b1813122-7031-452e-9ac5-a4ea7c6dc57c
version: Journey Orchestration
source-git-commit: 5eddbb1f9ab53f1666ccd8518785677018e10f6f
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Allmänna händelser {#general-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_custom"
>title="Enhetshändelser"
>abstract="Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan. För den här händelsetypen kan du bara lägga till en etikett och en beskrivning. Händelsekonfigurationen utförs av en datatekniker och kan inte redigeras."

>[!CONTEXTUALHELP]
>id="ajo_journey_event_business_canvas"
>title="Affärshändelser"
>abstract="Dessa händelser gör att du kan påbörja en resa med en händelse som inte är profilrelaterad. När den händelsen utlöses kan du skicka meddelanden till en publik med profiler. För den här händelsetypen kan du bara lägga till en etikett och en beskrivning. Händelsekonfigurationen utförs av en teknisk användare och kan inte redigeras."

Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan.

För den här händelsetypen kan du bara lägga till en etikett och en beskrivning. Resten av konfigurationen kan inte redigeras. Den utfördes av den tekniska användaren. Läs [den här sidan](../event/about-events.md).

Läs mer om händelsegenomströmning och resefrekvenser i [det här avsnittet](entry-management.md#journey-processing-rate).

![](assets/general-events.png)

När du släpper en affärshändelse läggs automatiskt en **Läs målgrupp**-aktivitet till. Mer information om affärshändelser finns i [det här avsnittet](../event/about-events.md)

## Lyssna på händelser under en viss tid {#events-specific-time}

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du konfigurera en timeout för händelsen.

Resan lyssnar sedan på händelsen under den tid som anges i tidsgränsen. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden antingen att flöda in i tidsgränsen om den är definierad eller fortsätta den resan.

Om ingen timeout-sökväg har definierats fungerar timeout-inställningen som en vänteaktivitet, vilket gör att profilen väntar en viss tid, vilket kan stoppas om en händelse inträffar före slutet av väntetiden. Om du vill att profiler ska uteslutas från den resan efter timeout måste du ange en timeout-sökväg.

Så här konfigurerar du en timeout för en händelse:

1. Aktivera alternativet **[!UICONTROL Define the event timeout]** från händelseegenskaperna.

1. Ange hur lång tid resan ska vänta på händelsen. Maximala längden är **90 dagar**.

1. När ingen händelse tas emot inom den angivna tidsgränsen är det bästa sättet att skicka personerna till en tidsgräns. Aktivera alternativet **[!UICONTROL Set a timeout path]** för detta. I så fall fortsätter kundresan för personen när tidsgränsen nås. Du bör alltid aktivera alternativet **[!UICONTROL Set a timeout path]**.

   ![](assets/event-timeout.png)

I det här exemplet skickar resan ett första välkomstmeddelande till en kund när han/hon kommer in i lobbyn. Sedan skickas ett mejl med rabatt endast om kunden kommer in på restaurangen nästa dag. Därför har vi konfigurerat restaurangevenemanget med en 1-dagars timeout:

* Om restaurangeventet tas emot mindre än 1 dag efter välkomstmeddelandet skickas ett mejl med rabatt på måltid.
* Om ingen restauranghändelse tas emot under nästa dag flödar personen genom timeoutvägen.

Observera, att om du vill konfigurera en timeout för flera händelser som placerats efter en **[!UICONTROL Wait]**-aktivitet, måste du bara konfigurera timeout för en av dessa händelser.

Den definierade tidsgränsen gäller för alla händelser som placerats efter aktiviteten **[!UICONTROL Wait]**:

* Om en händelse tas emot inom tidsgränsen flödas den enskilda händelsen till den mottagna händelsens sökväg.
* Om ingen händelse tas emot inom tidsgränsen flödar den enskilda händelsen in i den timeout-gren för händelsen där tidsgränsen har definierats.

![](assets/event-timeout-group.png)
