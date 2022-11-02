---
solution: Journey Optimizer
product: journey optimizer
title: Profilhantering
description: Lär dig hantera profilpost
feature: Journeys
role: User
level: Intermediate
source-git-commit: 412f7efe2da9f9b1a8fa49f1243ca63c4e0d01c0
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---


# Profilhantering {#entry-management}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

![](assets/journey-re-entrance.png)

När en resa avslutas är dess status **[!UICONTROL Closed]**. Nya individer kan inte längre ta sig in på resan. Personer som redan är på resan slutför resan normalt.

Efter den globala standardtidsgränsen på 30 dagar ändras resan till **Slutförd** status.  [Läs mer](journey-gs.md#global_timeout).


## Enhetsresor{#entry-unitary}

Enhetsresor (med början vid en händelse eller en segmentkvalificering) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.

Dessutom:

* Om återinträde är aktiverat kan en profil gå in på en resa flera gånger, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt.

* Om återinträde är inaktiverat kan en profil inte ange flera gånger samma resa

## Läs segmentresor{#entry-read-segment}

I en läsande segmentresa:

* För icke återkommande resor: profilen anger en gång och endast en gång under resan.

* För återkommande resor: profilen kommer in på resan vid varje upprepning, om han/hon befinner sig i segmentet/förväntad status. Om han fortfarande var på resan från en tidigare upprepning, kommer han att återuppta den från början.

Vid affärsevenemangsresor som börjar med en **Lässegment** aktivitet: i vetskap om att resan bygger på mottagningen av en affärshändelse, och om profilen är kvalificerad i det förväntade segmentet, kommer han att delta i resan för varje mottagen affärshändelse, vilket innebär att denna profil kan vara flera gånger under samma resa samtidigt, men i samband med olika affärshändelser.
