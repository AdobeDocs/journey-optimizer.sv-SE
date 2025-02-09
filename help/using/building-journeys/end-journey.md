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
source-git-commit: 20d99c082ef8d1f2442900dc6a6e6db6b0aaa46f
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 1%

---

# Avsluta en resa{#journey-ending}

En resa kan ta slut för en individ i två specifika sammanhang:

* Personen kommer till den sista aktiviteten i en bana.
* Personen kommer till en **villkorsaktivitet** (eller en **Wait**-aktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återkomma till resan om återinträde tillåts. Se [den här sidan](../building-journeys/journey-properties.md#entrance)

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

* Resan stängs manuellt med knappen **[!UICONTROL Close to new entrances]**.
* En enstegsbaserad resa som har slutförts och nått den globala tidsgränsen på 91 dagar.
* Efter den sista förekomsten av en återkommande målgruppsbaserad resa.

Genom att stänga en resa manuellt försäkrar du dig om att kunder som redan har gått in på resan kan slutföra sin resa, men att nya användare inte kan ta sig in på resan. När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt. Efter den globala standardtidsgränsen på 91 dagar växlar resan till statusen Slutförd. Se [det här avsnittet](journey-properties.md#timeout).

Efter den [globala tidsgränsen ](journey-properties.md#timeout) på 91 dagar ändras målgruppsresan till statusen **Slutförd**. Det här beteendet är inställt för endast 91 dagar (dvs. [globalt tidsgränsvärde för resa](journey-properties.md#global_timeout)) eftersom all information om profiler som har gått in i resan tas bort 91 dagar efter att de har gått in. Personer som fortfarande befinner sig på resan påverkas automatiskt. De avslutar resan efter 91-dagarstimeout.

Se [avsnittet](../building-journeys/journey-properties.md#global_timeout).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

Om du vill stänga en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stänga i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![](assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Close to new entrances]** och bekräfta i dialogrutan.

## Stoppa en resa{#stop-journey}

Om ni behöver stoppa alla enskilda personers framsteg på resan kan ni stoppa den. Om du stoppar resan kommer alla personer på resan att tidsgränsen för timeout. Att stoppa en resa innebär dock att alla som redan har tagit sig in på en resa stoppas under resans gång. Resan är i stort sett avstängd. Om du vill avsluta en resa rekommenderar vi att du stänger den.

Det går inte att starta om en stoppad reseversion.

När den stoppas anges resestatusen till **[!UICONTROL Stopped]**.

Du kan till exempel stoppa en resa om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt. Om du vill stoppa en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Stop]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stoppa i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![](assets/finish_drop_down_list2.png)

1. Klicka på **[!UICONTROL Stop]** och bekräfta i dialogrutan.
