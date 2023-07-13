---
solution: Journey Optimizer
product: journey optimizer
title: Reseslut
description: Se hur en resa slutar i Journey Optimizer
feature: Journeys
role: User
level: Beginner
keywords: återinträde, resa, slut, live, stopp
exl-id: ea1ecbb0-12b5-44e8-8e11-6d3b8bff06aa
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 3%

---

# Avsluta en resa{#journey-ending}

En resa kan ta slut för en individ i två specifika sammanhang:

* Personen kommer till den sista aktiviteten i en bana.
* Personen kommer till **Villkor** aktivitet (eller **Vänta** aktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Läs [den här sidan](../building-journeys/journey-gs.md#change-properties)

Om du vill avsluta en direktresa rekommenderar vi att du stänger den. Nya kunders ankomst till resan kommer då att blockeras. Kunder som redan är med på resan kan uppleva det hela tiden. Se [det här avsnittet](../building-journeys/journey.md#close-journey)

Du kan bara stoppa en resa om en kris inträffar och all behandling måste avslutas omedelbart under en resa. Personer som redan har gått in i en resa stoppas under hela resan. Se [det här avsnittet](../building-journeys/journey.md#stop-journey)

>[!NOTE]
>
>Observera att du inte kan återuppta en stängd eller stoppad resa.

## Sluttagg för resa{#end-tag}

När du skapar en resa visas sluttaggen i slutet av varje bana. Den här noden kan inte läggas till av en användare, kan inte tas bort och bara dess etikett kan ändras. Det markerar slutet på varje väg på resan. Om resan har flera sökvägar rekommenderar vi att du lägger till en etikett i varje ände för att göra rapporter enklare att läsa. Läs [den här sidan](../reports/live-report.md).

![](assets/journey-end.png)

<!--

### End activity{#journey-end-activity}

The **[!UICONTROL End]** activity allows you to mark the end of each path of the journey. It is not mandatory but recommended for visual clarity. See [this page](../building-journeys/end-activity.md)

![](assets/journey54.png)

-->

## Stänga en resa{#close-journey}

En resa kan avslutas på grund av följande orsaker:

* Resan stängs manuellt via **[!UICONTROL Close to new entrances]** -knappen.
* En segmentbaserad resa som utförts i ett enda steg.
* Efter den sista förekomsten av en återkommande målgruppsbaserad resa.

Genom att stänga en resa manuellt försäkrar du dig om att kunder som redan har gått in på resan kan slutföra sin resa, men att nya användare inte kan ta sig in på resan. När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt. Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

Om du vill stänga en resa från listan över resor klickar du på **[!UICONTROL Ellipsis]** knapp som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Journeys]** klickar du på den resa du vill stänga.
1. Klicka på nedpilen längst upp till höger.

   ![](assets/finish_drop_down_list.png)

1. Klicka **[!UICONTROL Close to new entrances]** och bekräfta i dialogrutan.

## Stoppa en resa{#stop-journey}

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
