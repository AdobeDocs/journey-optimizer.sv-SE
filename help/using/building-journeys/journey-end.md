---
title: Avsluta en resa
description: Avsluta en resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: d0d914156eaa7fe54a513ee7b4e870edbc76c846
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---

# Resans livscykel{#journey-lifecyle}

## Profiler under resor{#profile-journey}

På en enhetlig resa:

* Om återinträde är aktiverat kan en profil gå in på en resa flera gånger, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt.

* Om återinträde är inaktiverat kan en profil inte ange flera gånger samma resa

Mer information om återinträde av profiler finns i [section](../building-journeys/journey-gs.md#change-properties).

I en läsande segmentresa:

* För icke återkommande resor: profilen anger en gång och endast en gång under resan.
* för återkommande resor: profilen kommer in på resan vid varje upprepning, om han/hon befinner sig i segmentet/förväntad status. Om han fortfarande var på resan från en tidigare upprepning, kommer han att återuppta den från början.

Vid affärshändelseresor som börjar med ett lässegment:

Eftersom den här resan baseras på mottagningen av en affärshändelse, och om profilen är kvalificerad i det förväntade segmentet, kommer han att gå in på resan för varje mottagen affärshändelse, vilket innebär att profilen kan vara flera gånger under samma resa samtidigt, men i samband med olika affärshändelser.

## Reseslut{#journey-ending}

En resa kan ta slut för en individ i två specifika sammanhang:

* Personen kommer till den sista aktiviteten i en bana.
* Personen kommer till **Villkor** aktivitet (eller **Vänta** aktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Läs [den här sidan](../building-journeys/journey-gs.md#change-properties)

Om du vill avsluta en direktresa rekommenderar vi att du stänger den. Nya kunders ankomst till resan kommer då att blockeras. Kunder som redan är med på resan kan uppleva det hela tiden. Se [det här avsnittet](../building-journeys/journey-end.md#close-journey)

Du kan bara stoppa en resa om en kris inträffar och all behandling måste avslutas omedelbart under en resa. Personer som redan har gått in i en resa stoppas under hela resan. Se [det här avsnittet](../building-journeys/journey-end.md#stop-journey)

>[!NOTE]
>
>Observera att du inte kan återuppta en stängd eller stoppad resa.

<!--

### Journey end tag{#end-tag}

While authoring a journey, an "end node" is displayed at the end of each path. This node cannot be added by a user, cannot be removed and only its label can be changed. It marks the end of each path of the journey. If the journey has several paths, we recommend that you add a label to each end to make reports easier to read. See [this page](../reports/live-report.md).

![](assets/journey-end.png)

-->

### Avsluta aktivitet{#journey-end-activity}

The **[!UICONTROL End]** kan du markera slutet på varje väg på resan. Det är inte obligatoriskt men rekommenderas för att synskärpan ska bli tydlig. Läs [den här sidan](../building-journeys/end-activity.md)

![](assets/journey54.png)

### Stänga en resa{#close-journey}

En resa kan avslutas på grund av följande orsaker:

* Resan stängs manuellt via **[!UICONTROL Close to new entrances]** -knappen.
* En segmentbaserad resa som utförts i ett enda steg.
* Efter den sista förekomsten av en återkommande segmentbaserad resa.

Genom att stänga en resa manuellt försäkrar du dig om att kunder som redan har gått in på resan kan slutföra sin resa, men att nya användare inte kan ta sig in på resan. När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt. Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

Om du vill stänga en resa från listan över resor klickar du på **[!UICONTROL Ellipsis]** knapp som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Journeys]** klickar du på den resa du vill stänga.
1. Klicka på nedpilen längst upp till höger.

   ![](assets/finish_drop_down_list.png)

1. Klicka **[!UICONTROL Close to new entrances]** och bekräfta i dialogrutan.

### Stoppa en resa{#stop-journey}

Om ni behöver stoppa alla personers framsteg på resan kan ni stoppa den. Om du stoppar resan kommer alla personer på resan att tidsgränsen för timeout. Att stoppa en resa innebär dock att alla som redan har tagit sig in på en resa stoppas under resan. Resan är i stort sett avstängd. Om du vill avsluta en resa rekommenderar vi att du stänger den.

Det går inte att starta om en stoppad reseversion.

När det stoppas anges resans status till **[!UICONTROL Stopped]**.

Du kan till exempel stoppa en resa om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt. Om du vill stoppa en resa från listan över resor klickar du på **[!UICONTROL Ellipsis]** knapp som finns till höger om resenamnet och väljer **[!UICONTROL Stop]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Journeys]** klickar du på den resa du vill stoppa.
1. Klicka på nedpilen i det övre högra hörnet.

![](assets/finish_drop_down_list.png)

1. Klicka **[!UICONTROL Stop]** och bekräfta i dialogrutan.
