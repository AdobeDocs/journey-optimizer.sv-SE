---
solution: Journey Orchestration
title: Allmänna händelser
description: Lär dig hur du använder allmänna händelser
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 285942ec51859a4cea888d9974f79f52acf3aabf
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---

# Allmänna händelser {#section_ofg_jss_dgb}

För den här händelsetypen kan du bara lägga till en etikett och en beskrivning. Resten av konfigurationen kan inte redigeras. Den utfördes av den tekniska användaren. Läs [den här sidan](../event/about-events.md).

![](../assets/general-events.png)

När du släpper en affärshändelse lägger den automatiskt till en **Läs segment**-aktivitet. Mer information om affärshändelser finns i [det här avsnittet](../event/about-events.md)

## Lyssna på händelser under en viss tid {#events-specific-time}

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du konfigurera en timeout för händelsen.

Resan lyssnar sedan på händelsen under den tid som anges i tidsgränsen. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden antingen att flöda in i en tidsgräns eller avsluta sin resa.

Så här konfigurerar du en timeout för en händelse:

1. Aktivera alternativet **[!UICONTROL Define the event timeout]** från händelseegenskaperna.

1. Ange hur lång tid resan ska vänta på händelsen.

1. Om du vill skicka personerna till en timeout-sökväg när ingen händelse tas emot inom den angivna tidsgränsen aktiverar du alternativet **[!UICONTROL Set a timeout path]**. Om det här alternativet inte är aktiverat avslutas kundresan för personen när tidsgränsen nås.

   ![](../assets/event-timeout.png)

I det här exemplet skickar resan en första välkomstknuff till en kund. Sedan skickas en reklamfilm för måltidsrabatt endast om kunden kommer in på restaurangen nästa dag. Därför har vi konfigurerat restaurangevenemanget med en 1-dagars timeout:

* Om restauranghändelsen tas emot mindre än 1 dag efter välkomstsändningen skickas push-aktiviteten för måltidsrabatt.
* Om ingen restauranghändelse tas emot under nästa dag flödar personen genom timeoutvägen.

Observera, att om du vill konfigurera en timeout för flera händelser som placerats efter en **[!UICONTROL Wait]**-aktivitet, måste du bara konfigurera timeout för en av dessa händelser.

Tidsgränsen gäller för alla händelser som placerats efter aktiviteten **[!UICONTROL Wait]**. Om ingen händelse tas emot före den angivna tidsgränsen kommer individerna att flyta in i en enda tidsgräns eller avsluta sin resa.

![](../assets/event-timeout-group.png)
