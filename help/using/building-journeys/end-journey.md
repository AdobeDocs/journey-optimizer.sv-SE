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
version: Journey Orchestration
source-git-commit: 63f7b09d8b8de578c32ba0f5d6fdd6b2f5786722
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 1%

---

# Avsluta en resa {#journey-ending}

>[!TIP]
>
>Letar du efter praktisk vägledning om när och hur profiler bör avsluta resor? Se vår [omfattande guide till resans in- och utträdeskriterier](entry-exit-criteria-guide.md), som innehåller verkliga utträdesscenarier, bästa praxis och konfigurationsvägledning.

## Så här slutar en live-resa

Resorna stängs när tidsgränsen för den globala resan nås, eller efter den sista förekomsten av en återkommande målgruppsbaserad resa. [Lär dig hur resorna stängs](#close-journey).

Om du behöver avsluta en direktresa rekommenderar vi att [du stänger den](#close-to-new-entrances) manuellt. Nya kunders ankomst till resan blockeras sedan. Profiler som redan har deltagit i resan kan uppleva det hela tiden.

Du kan också [stoppa en resa](#stop-journey) endast i händelse av en nödsituation och om all resebearbetning måste avslutas omedelbart. Personer som redan har gått in i en resa stoppas under hela resan.

>[!IMPORTANT]
>
>* Du kan inte starta om eller ta bort en [stängd](#close-journey)- eller [stoppad](#stop-journey)-resa. Du kan [skapa en ny version](publish-journey.md#journey-versions) av den eller [duplicera den](journey-ui.md#duplicate-a-journey).
>
>* Endast slutförda resor kan tas bort.

## Hur profiler avslutar en resa

En resa slutar för en individ i två specifika sammanhang:

* Personen kommer till den sista aktiviteten i en bana och går sedan till [sluttaggen](#end-tag).
* Personen uppnår en aktivitet av typen **Condition** (eller en **Wait**-aktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. [Läs mer om hantering av inträde/återinträde](../building-journeys/journey-properties.md#entrance)

## Sluttagg för resa {#end-tag}

När du skapar en resa visas sluttaggen i slutet av varje bana. Den här noden kan inte läggas till av en användare, kan inte tas bort och bara dess etikett kan ändras. Det markerar slutet på varje väg på resan.

Om resan har flera sökvägar rekommenderar vi att du lägger till en etikett i varje ände för att göra rapporter enklare att läsa. Läs mer om [reserapporter](../reports/live-report.md).

![Knappen Slutåtgärd för resan i verktygsfältet för resan](assets/journey-end.png)

## Stänga en resa {#close-journey}

En resa kan avslutas på grund av följande orsaker:

* En enstegsbaserad resa som har slutförts och nått den globala tidsgränsen på 91 dagar.
* Efter den sista förekomsten av en återkommande målgruppsbaserad resa.
* Resan stängs manuellt med knappen [**[!UICONTROL Close to new entrances]**](#close-to-new-entrances).

Efter den globala tidsgränsen **för** 91-dagarsresan växlar en läsmålgruppsresa till statusen **Slutförd**. Beteendet är inställt för 91 dagar eftersom all information om profiler som har gått in i resan tas bort 91 dagar efter att de har gått in. Personer som fortfarande befinner sig på resan påverkas automatiskt. De avslutar resan efter 91-dagarstimeout.  Läs mer om [den globala tidsgränsen för resan](../building-journeys/journey-properties.md#global_timeout).

>[!TIP]
>
>En segmentbaserad engångsresa behåller statusen **Live** även efter att en gång har körts. Profiler kan inte anges igen när de är klara, men resan är fortfarande i **Live**-status tills standardtidsgränsen för global är slut. Du kan stänga den manuellt tidigare med alternativet **Stäng till nya ingångar**.

### När betraktas en resa som&quot;avslutad&quot;? {#journey-finished-definition}

Definitionen av&quot;färdig&quot; varierar beroende på resetyp:

| Resetyp | Återkommande? | Har slutdatum? | Definition av&quot;färdigt&quot; |
|--------------|------------|---------------|--------------------------|
| Läs målgrupp | Nej | n/a | 91 dagar efter att körningen har startat |
| Läs målgrupp | Ja | Nej | 91 dagar efter att körningen har startat |
| Läs målgrupp | Ja | Ja | När slutdatumet nås |
| Händelseutlöst resa | n/a | Ja | När slutdatumet nås |
| Händelseutlöst resa | n/a | Nej | När den stängs i användargränssnittet eller via API |

### Nära nya ingångar {#close-to-new-entrances}

Genom att stänga en resa manuellt försäkrar du dig om att kunder som redan har gått in på resan kan slutföra sin resa, men att nya användare inte kan ta sig in på resan. När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan slutar med att nya individer kan komma in på resan. Profiler som redan finns på resan kan slutföra resan normalt. Efter den globala standardtidsgränsen på 91 dagar växlar resan till statusen **Slutförd**.

Om du vill stänga en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![Slutför åtgärdslistrutan i snabbåtgärdsmenyn för att avsluta resan](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stänga i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![Menyn Slutalternativ som visar slutresan och alternativa åtgärder](assets/finish_drop_down_list.png){width="50%" align="left" zoomable="yes"}

1. Klicka på **[!UICONTROL Close to new entrances]** och bekräfta i dialogrutan.




## Stoppa en resa {#stop-journey}

Om ni behöver stoppa alla enskilda personers framsteg på resan kan ni stoppa den. Tidsgränsen för att stoppa resan för alla personer på resan har uppnåtts. Att stoppa en resa innebär dock att alla som redan har tagit sig in på en resa stoppas under resans gång. Resan är i stort sett avstängd. Om du vill avsluta en resa bör du [stänga den](#close-journey).

Du kan till exempel stoppa en resa om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt. Om du vill stoppa en resa från listan med resor klickar du på knappen **[!UICONTROL Ellipsis]** som finns till höger om resenamnet och väljer **[!UICONTROL Stop]**.

![Slutför åtgärdslistrutan i snabbåtgärdsmenyn för att avsluta resan](assets/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stoppa i listan **[!UICONTROL Journeys]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![Ytterligare avslutningsalternativ, inklusive närresa och rensning](assets/finish_drop_down_list2.png){width="50%" align="left" zoomable="yes"}

1. Klicka på **[!UICONTROL Stop]** och bekräfta i dialogrutan.

När den stoppas anges resestatusen till **[!UICONTROL Stopped]**.

>[!CAUTION]
>
>**[!DNL Manage journeys]**-behörighet krävs för att stoppa en resa. Om resan omfattar textbundna kampanjer eller meddelandenoder behöver användarna även behörighet **Kampanjer > Publicera kampanjer**. Om resurserna används i resan (till exempel i e-postmeddelanden) måste användarna ha tillgång till dessa resursmappar. Läs mer om hur du hanterar [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).

## Relaterade ämnen

* [Guide för in- och utträdeskriterier för resor](entry-exit-criteria-guide.md) - Fullständig guide med verkliga exempel och bästa praxis
* [Profilingångshantering](entry-management.md) - Konfigurera hur profiler anger resor
* [Konfigurera avslutsvillkor](journey-properties.md#exit-criteria) - Konfigurera automatisk profilborttagning från resor
* [Pausa en resa](journey-pause.md) - Stoppa körning tillfälligt