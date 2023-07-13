---
solution: Journey Optimizer
product: journey optimizer
title: Profilhantering
description: Lär dig hantera profilpost
feature: Journeys
role: User
level: Intermediate
keywords: återinträde, resa, profil, återkommande
exl-id: 8874377c-6594-4a5a-9197-ba5b28258c02
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# Profilhantering {#entry-management}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

![](assets/journey-re-entrance.png)

När en resa avslutas är dess status **[!UICONTROL Closed]**. Nya individer kan inte längre komma in på resan. Personer som redan är på resan slutför resan normalt.

Efter den globala standardtidsgränsen på 30 dagar ändras resan till **Slutförd** status.  [Läs mer](journey-gs.md#global_timeout).


## Enhetsresor{#entry-unitary}

Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.

Dessutom:

* Om återinträde är aktiverat kan en profil gå in på en resa flera gånger, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt.

* Om återinträde är inaktiverat kan en profil inte ange flera gånger samma resa

## Läs målgruppsresor{#entry-read-segment}

I en läsande målgruppsresa:

* För icke återkommande resor: profilen anger en gång och endast en gång under resan.

* För återkommande resor: Profilen kommer in på resan varje gång den återkommer, om han är i målgruppens/förväntad status. Om han fortfarande var på resan från en tidigare upprepning, kommer han att återuppta den från början.

Vid affärsevenemangsresor som börjar med en **Läsa målgrupper** aktivitet: i vetskap om att resan bygger på mottagningen av ett affärsevenemang, och om profilen är kvalificerad för den förväntade målgruppen, kommer han att delta i resan för varje mottaget affärsevenemang, vilket innebär att profilen kan vara flera gånger under samma resa samtidigt, men i samband med olika affärsevenemang.
