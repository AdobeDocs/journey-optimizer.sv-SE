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
source-git-commit: b0cda95aee58a3dd3a0e22d09b5938ff11abcf32
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# Profilhantering {#entry-management}

Det finns två huvudtyper av resor:

* Händelsebaserade resor: från och med en händelse är dessa resor enhetliga, de är kopplade till en person. När evenemanget tas emot går personen in på resan. [Läs mer](#entry-unitary)
* läs målgruppsresor: från och med en läsare är detta batchresor. Enskilda personer som tillhör målgruppen deltar alla i samma resa. Resorna kan vara återkommande eller engångsvisa. [Läs mer](#entry-read-segment)

I båda resetyperna kan en profil inte finnas flera gånger på samma resa samtidigt.

## Enhetsresor{#entry-unitary}

På enastående resor kan du aktivera eller inaktivera återinträde:

* Om återinträde är aktiverat kan en profil gå in på en resa flera gånger, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt.

* Om återinträde är inaktiverat kan en profil inte ange flera gånger samma resa.

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångspresentation när en person besöker en butik. I så fall får kunden inte kunna återuppta resan och få erbjudandet igen. När en resa avslutas är dess status **[!UICONTROL Closed]**. Nya individer kan inte längre komma in på resan. Personer som redan är på resan slutför resan normalt. [Läs mer](journey-gs.md#entrance)

![](assets/journey-re-entrance.png)

Efter standardinställningen [global timeout](journey-gs.md#global_timeout) om 30 dagar ändras resan till **Slutförd** status. Profiler som redan finns på resan slutför normalt. Nya profiler kan inte längre komma in på resan. Detta beteende är inställt för endast 30 dagar (d.v.s. standardvärdet för timeout för resa) eftersom all information om profiler som har gått in i resan tas bort 30 dagar efter att de har gått in. Efter den perioden kan profiler återinträda i resan. För att undvika detta och helt inaktivera återinträde för dessa profiler kan du lägga till ett villkor som testar om profilen redan har angetts eller inte.

<!--
Due to the 30-day journey timeout, when journey re-entrance is not allowed, we cannot make sure the re-entrance blocking will work more than 30 days. Indeed, as we remove all information about persons who entered the journey 30 days after they enter, we cannot know the person entered previously, more than 30 days ago. -->

Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.

Nyckeln används också för att kontrollera att en person befinner sig på en resa. En person kan faktiskt inte befinna sig på två olika platser på samma resa. Därför tillåter systemet inte att samma nyckel, till exempel nyckeln CRMID=3224, finns på olika platser under samma resa.

## Läs målgruppsresor{#entry-read-segment}

I en läsande målgruppsresa:

* För icke återkommande resor: profilen anger en gång och endast en gång under resan.

* För återkommande resor: som standard kommer alla profiler som tillhör målgruppen in på resan vid varje upprepning. De måste slutföra resan innan de kan komma in igen vid ett annat tillfälle.

>[!NOTE]
>
>Det finns två alternativ för återkommande läsningar. The **Tvinga återinträde vid upprepning** gör att alla profiler som fortfarande finns kvar i resan automatiskt avslutar den vid nästa körning. The **Inkrementell läsning** Alternativet riktar sig endast till de personer som gått in i målgruppen sedan den senaste resan utfördes. Se detta [section](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

Vid affärsevenemangsresor som börjar med **Läsa målgrupper** aktivitet: i vetskapen om att resan baseras på mottagningen av ett affärsevenemang, och om profilen är kvalificerad för den förväntade målgruppen, kommer de att gå in på resan för varje mottaget affärsevenemang, vilket innebär att profilen kan vara flera gånger under samma resa samtidigt, men i samband med olika affärsevenemang.