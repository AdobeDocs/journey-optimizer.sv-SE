---
solution: Journey Optimizer
product: journey optimizer
title: Bläddra och filtrera dina resor
description: Bläddra och filtrera dina resor i Adobe Journey Optimizer
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: resa, första, start, snabbstart, målgrupp, händelse, åtgärd
source-git-commit: 4847415fa33ebf1c21622ebf4faecafd4decc8d3
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 2%

---

# Bläddra och filtrera dina resor {#browse-journeys}

## Åtkomstresor {#journey-access}

### Kontrollpanel för resan {#dashboard-jo}

Klicka på **[!UICONTROL Journeys]** på menyn RESURSHANTERING. Det finns två flikar: **[!UICONTROL Overview]** och **[!UICONTROL Browse]**.

* På fliken **[!UICONTROL Overview]** visas en instrumentpanel med nyckelvärden för dina resor:

   * **Bearbetade profiler**: totalt antal profiler som har bearbetats under de senaste 24 timmarna
   * **Live-resor**: Totalt antal live-resor med trafik under de senaste 24 timmarna. Live-resor omfattar **Unitary-resor** (händelsebaserade) och **Batch-resor** (läs målgrupp).
   * **Felfrekvens**: förhållandet mellan alla felaktiga profiler och det totala antalet profiler som har angetts under de senaste 24 timmarna.
   * **Ignorera frekvens**: förhållandet mellan alla ignorerade profiler och det totala antalet profiler som har angetts under de senaste 24 timmarna. En ignorerad profil representerar en person som inte är berättigad att delta i resan, till exempel på grund av ett felaktigt namnutrymme eller på grund av återinträdesregler.

  >[!NOTE]
  >
  >På denna kontrollpanel beaktas trafiken under de senaste 24 timmarna. Endast de resor du har åtkomst till visas. Mätvärdena uppdateras var 30:e minut och endast när nya data är tillgängliga.

  ![](assets/journeys-dashboard.png)

* Fliken **[!UICONTROL Browse]** visar en lista över befintliga resor. Du kan söka efter resor, använda filter och utföra grundläggande åtgärder för varje element. Du kan till exempel skapa dubbletter eller radera en post.

  ![](assets/journeys-browse.png)

### Filtrera dina resor {#filter}

I listan över resor kan du använda olika filter för att förfina listan över resor för bättre läsbarhet.

![](assets/filter-journeys.png)

Här är de olika filtreringsåtgärderna som du kan utföra:

Filtrera resor efter status, typ, version och tilldelade taggar från **[!UICONTROL Status and version filters]**.

Typen kan vara: **[!UICONTROL Unitary event]**, **[!UICONTROL Audience qualification]**, **[!UICONTROL Read audience]** eller **[!UICONTROL Business event]**.

Status kan vara:

* **Stängd**: resan har stängts med knappen **Stäng till nya ingångar**. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt.
* **Utkast**: resan är i det första steget. Den har inte publicerats än.
* **Utkast (test)**: Testläget har aktiverats med knappen **Testläge** .
* **Slutförd**: resan växlar automatiskt till den här statusen efter den globala tidsgränsen på 91 dagar [](journey-properties.md#global_timeout). Profiler som redan finns på resan slutför normalt. Nya profiler kan inte längre komma in på resan.
* **Live**: resan har publicerats med knappen **Publicera** .
* **Stoppad**: resan har inaktiverats med knappen **Stoppa**. Alla individer lämnar resan direkt.

>[!NOTE]
>
>Reseutvecklingscykeln innehåller också en uppsättning mellanliggande statusvärden som inte är tillgängliga för filtrering: &quot;Publicera&quot; (mellan &quot;Utkast&quot; och &quot;Live&quot;), &quot;Aktivera testläge&quot; eller &quot;Inaktivera testläge&quot; (mellan &quot;Utkast&quot; och &quot;Utkast (test)&quot;) och &quot;Stoppar&quot; (mellan &quot;Live&quot; och &quot;Stoppad&quot;). När en resa befinner sig i ett mellanliggande tillstånd är den skrivskyddad.

Använd **[!UICONTROL Creation filters]** om du vill filtrera resorna efter när de skapades eller efter den användare som skapade dem.

Visa resor som använder en specifik händelse, fältgrupp eller åtgärd från **[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**.

Använd **[!UICONTROL Publication filters]** för att välja ett publiceringsdatum eller en användare. Du kan till exempel välja att visa de senaste versionerna av direktresor som publicerades igår.

Om du vill filtrera resor baserat på ett visst datumintervall väljer du **[!UICONTROL Custom]** i listrutan **[!UICONTROL Published]**.

I konfigurationsrutorna Händelse, Datakälla och Åtgärd visar fältet **[!UICONTROL Used in]** dessutom antalet resor som använder just den händelsen, fältgruppen eller åtgärden. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

![](assets/journey3bis.png)


## Reseversioner {#journey-versions}

I reselistan visas alla reseversioner med versionsnumret. När du söker efter en resa visas de senaste versionerna högst upp i listan första gången programmet öppnas. Sedan kan du definiera den sortering som du vill ha så att programmet behåller den som en användarinställning. Färdens version visas också överst i reseupplagans gränssnitt, ovanför arbetsytan.

![](assets/journeyversions1.png)

>[!NOTE]
>
>Vanligtvis kan en profil inte finnas flera gånger på samma resa samtidigt. Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](end-journey.md).

Om du behöver ändra till en direktresa skapar du en ny version av din resa.

1. Öppna den senaste versionen av din liveresa, klicka på **[!UICONTROL Create a new version]** och bekräfta.

   ![](assets/journeyversions2.png)

   >[!NOTE]
   >
   >Du kan bara skapa en ny version av den senaste versionen av en resa.

1. Gör ändringarna, klicka på **[!UICONTROL Publish]** och bekräfta.

Från det att resan har publicerats kommer individerna att börja flöda in i den senaste versionen av resan. Personer som redan har gått in i en tidigare version stannar kvar tills de är klara med resan. Om de senare kommer in på samma resa igen kommer de att gå in i den senaste versionen.

Reseversioner kan stoppas individuellt. Alla versioner av resor har samma namn.

När du publicerar en ny version av en resa avslutas den tidigare versionen automatiskt och ändras till statusen **Stängd** . Ingen inträde på resan kan ske. Även om du stoppar den senaste versionen förblir den tidigare versionen stängd.



## Duplicera en resa {#duplicate-a-journey}

Du kan duplicera en befintlig resa från fliken **Bläddra**. Alla objekt och inställningar dupliceras till kopian av resan.

Gör så här:

1. Navigera till den resa du vill kopiera och klicka på ikonen **Fler åtgärder** (de tre punkterna bredvid resans namn).
1. Välj **Duplicera**.

   ![Duplicera en resa](assets/duplicate-jo.png)

1. Ange namnet på resan och bekräfta. Du kan också ändra namnet på skärmen för reseegenskaper. Som standard anges namnet på följande sätt: `[JOURNEY-NAME]_copy`

   ![](assets/duplicate-jo2.png)

1. Den nya resan skapas och är tillgänglig i reselistan.

