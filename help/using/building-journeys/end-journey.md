---
solution: Journey Optimizer
product: journey optimizer
title: Reseslut
description: Se hur en resa slutar i Journey Optimizer
feature: Journeys
role: User
level: Intermediate
keywords: återinträde, resa, slut, live, stopp
exl-id: ea1ecbb0-12b5-44e8-8e11-6d3b8bff06aa
source-git-commit: a536336ec7b37ffa0cd860c2c7479c75365eff00
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Avsluta en resa {#journey-ending}

En resa kan ta slut för en individ i två specifika sammanhang:

* Personen kommer till den sista aktiviteten i en bana och går sedan till [sluttaggen](#end-tag).
* Personen uppnår en aktivitet av typen **Condition** (eller en **Wait**-aktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Se [den här sidan](../building-journeys/journey-properties.md#entrance)

Om du vill avsluta en direktresa rekommenderar vi att du stänger den. Nya kunders ankomst till resan kommer då att blockeras. Profiler som redan har deltagit i resan kan uppleva det hela tiden. Se [det här avsnittet](#close-journey)

Du kan bara stoppa en resa om en kris inträffar och all behandling måste avslutas omedelbart under en resa. Personer som redan har gått in i en resa stoppas under hela resan. Se [det här avsnittet](../building-journeys/journey.md#stop-journey)

>[!IMPORTANT]
>
>Du kan inte starta om en [stängd](#close-journey)- eller [stoppad](#stop-journey)-resa.


## Sluttagg för resa {#end-tag}

När du skapar en resa visas sluttaggen i slutet av varje bana. Den här noden kan inte läggas till av en användare, kan inte tas bort och bara dess etikett kan ändras. Det markerar slutet på varje väg på resan. Om resan har flera sökvägar rekommenderar vi att du lägger till en etikett i varje ände för att göra rapporter enklare att läsa. Läs mer om [reserapporter](../reports/live-report.md).

![](assets/journey-end.png)

## Stänga en resa {#close-journey}

En resa kan avslutas på grund av följande orsaker:

* Resan stängs manuellt med knappen [**[!UICONTROL Close to new entrances]**](#close-to-new-entrances).
* En enstegsbaserad resa som har slutförts och nått den globala tidsgränsen på 91 dagar.
* Efter den sista förekomsten av en återkommande målgruppsbaserad resa.

Genom att stänga en resa manuellt försäkrar du dig om att kunder som redan har gått in på resan kan slutföra sin resa, men att nya användare inte kan ta sig in på resan. När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan slutar med att nya individer kan komma in på resan. Profiler som redan finns på resan kan slutföra resan normalt. Efter den globala standardtidsgränsen på 91 dagar växlar resan till statusen **Slutförd**.

Efter den globala tidsgränsen **för** 91-dagarsresan växlar en läsmålgruppsresa till statusen **Slutförd**. Beteendet är inställt för 91 dagar eftersom all information om profiler som har gått in i resan tas bort 91 dagar efter att de har gått in. Personer som fortfarande befinner sig på resan påverkas automatiskt. De avslutar resan efter 91-dagarstimeout.  Läs mer om [den globala tidsgränsen för resan](../building-journeys/journey-properties.md#global_timeout).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

### Nära nya ingångar {#close-to-new-entrances}

Om du vill stänga en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stänga i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![](assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Close to new entrances]** och bekräfta i dialogrutan.

>[!TIP]
>
>En segmentbaserad engångsresa behåller statusen **Live** även efter att en gång har körts. Profiler kommer inte att anges igen när de är klara, men resan är fortfarande i **Live**-status tills den globala standardtidsgränsen går ut. Du kan stänga den manuellt tidigare med alternativet **Stäng till nya ingångar**.


## Stoppa en resa {#stop-journey}

Om ni behöver stoppa alla enskilda personers framsteg på resan kan ni stoppa den. Tidsgränsen för att stoppa resan för alla personer på resan har uppnåtts. Att stoppa en resa innebär dock att alla som redan har tagit sig in på en resa stoppas under resans gång. Resan är i stort sett avstängd. Om du vill avsluta en resa bör du [stänga den](#close-journey).

När den stoppas anges resestatusen till **[!UICONTROL Stopped]**.

Du kan till exempel stoppa en resa om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt. Om du vill stoppa en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Stop]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stoppa i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![](assets/finish_drop_down_list2.png)

1. Klicka på **[!UICONTROL Stop]** och bekräfta i dialogrutan.
