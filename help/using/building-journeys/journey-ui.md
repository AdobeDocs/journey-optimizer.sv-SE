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
exl-id: 770bdbf2-560d-4127-bdb9-1f82495a566f
version: Journey Orchestration
source-git-commit: 118bf89f56d26213fde71fa795fc6576ce764ef2
workflow-type: tm+mt
source-wordcount: '1412'
ht-degree: 2%

---

# Bläddra och filtrera dina resor {#browse-journeys}

>[!CONTEXTUALHELP]
>id="ajo_journey_view"
>title="Reselista och kalendervyer"
>abstract="Utöver reselistan innehåller [!DNL Journey Optimizer] en kalendervy över dina resor, som ger en tydlig visuell representation av deras scheman. Du kan när som helst växla mellan list- och kalendervyer med dessa knappar."

## Kontrollpanel för resan {#dashboard-jo}

Klicka på **[!UICONTROL Journeys]** på menyn RESURSHANTERING. Det finns två flikar: **[!UICONTROL Overview]** och **[!UICONTROL Browse]**.

### Reseöversikt

Fliken **[!UICONTROL Overview]** visar en instrumentpanel med nyckelvärden för dina resor.

![Reseinstrumentpanelen markerar fliken Översikt](assets/journeys-dashboard.png)

* **Bearbetade profiler**: totalt antal profiler som har bearbetats under de senaste 24 timmarna
* **Live-resor**: Totalt antal live-resor med trafik under de senaste 24 timmarna. Live-resor omfattar **Unitary-resor** (händelsebaserade) och **Batch-resor** (läs målgrupp).
* **Felfrekvens**: förhållandet mellan alla felaktiga profiler och det totala antalet profiler som har angetts under de senaste 24 timmarna.
* **Ignorera frekvens**: förhållandet mellan alla ignorerade profiler och det totala antalet profiler som har angetts under de senaste 24 timmarna. En ignorerad profil representerar en person som inte är berättigad att delta i resan, till exempel på grund av felaktiga namnområdes- eller återinträdesregler.

>[!NOTE]
>
>På denna kontrollpanel beaktas trafiken under de senaste 24 timmarna. Endast de resor du har åtkomst till visas. Mätvärdena uppdateras var 30:e minut och endast när nya data är tillgängliga.

### Reselista

Fliken **[!UICONTROL Browse]** visar en lista över befintliga resor. Du kan söka efter resor, använda filter och utföra grundläggande åtgärder för varje element. Du kan till exempel skapa dubbletter eller radera en post.

![kontrollpanelen för resan markerar fliken Bläddra](assets/journeys-browse.png)

I reselistan visas alla reseversioner med versionsnumret. När du söker efter en resa visas de senaste versionerna högst upp i listan första gången programmet öppnas. Sedan kan du definiera den sortering som du vill ha så att programmet behåller den som en användarinställning. Färdens version visas också överst i reseupplagans gränssnitt, ovanför arbetsytan. Läs mer om [reseversionshantering](publishing-the-journey.md#journey-versions-journey-versions).

### Resekalender {#calendar}

Utöver reselistan innehåller [!DNL Journey Optimizer] en kalendervy över dina resor, som ger en tydlig visuell representation av deras scheman.

Hur resorna presenteras:

* Som standard visas alla aktiva och schemalagda resor för den valda veckan i kalenderrutnätet. Ytterligare filteralternativ kan visa slutförda, stoppade och avslutade aktiveringar eller aktiveringar.
* Utkastresor och resor i testläge visas inte.
* Resor som sträcker sig över flera dagar visas högst upp i kalenderrutnätet.
* Om ingen starttid anges används den närmaste manuella aktiveringstiden för att placera den i kalendern.
* Resor visas som 1-timmars tidsintervall, men detta återspeglar inte den faktiska tiden för sändning eller slutförande.

Så här navigerar du i din resekalender:

1. Om du vill komma åt kalendervyn öppnar du reselistan och klickar på ikonen ![kalenderikon](assets/do-not-localize/timeline-icon.svg) .

1. Använd pilknapparna eller datumväljaren ovanför kalendern för att flytta mellan veckor.

   I kalendern visas alla schemalagda resor för den aktuella veckan.

   ![kalendervy som visar direktresor](assets/timeline-journeys.png)

1. Klicka på ![kugghjulsikonen](assets/do-not-localize/Smock_Gears_18_N.png) för att växla visningen av objekt som sträcker sig över flera dagar eller veckor.

   ![kalendervy som visar aktiva kampanjer](assets/journey-calendar-1.png)

1. Klicka på ikonen ![Lägg till kalender](assets/do-not-localize/Smock_CalendarAdd_18_N.svg) för att hantera och lägga till upp till tre externa kalendrar.

   ![kalendervy som visar externa kalendrar](assets/journey-calendar-2.png)

1. Dra och släpp dina CSV-filer med händelsenamn, startdatum och slutdatum.

   Överförda händelser visas för alla användare i din organisation och visas i både Resekalendrar och Campaign-kalendrar.

   +++CSV-formatet ska vara följande:

   | Kolumn1 | Kolumn2 | Column3 |
   |-|-|-|
   | Händelsenamn | Startdatum i formatet mm/dd/åå | Slutdatum i formatet mm/dd/åå |

   +++

1. Om det behövs kan du dölja, visa eller ta bort tillagda externa kalendrar.

   ![kalendervy som visar externa kalendrar](assets/journey-calendar-3.png)

1. Om du vill ha mer information om en resa klickar du på det visuella blocket för att öppna och utforska dess detaljer.

   ![kampanjlista med informationsrutan öppnad](assets/journey-calendar-4.png)


## Filtrera dina resor {#journey-filter}

Använd olika filter i listan över resor för att förfina listan över resor.

![Skärm som visar ett urval av reseverktfiltrering med två typer av valda resor](assets/filter-journeys.png)

Du kan filtrera resor utifrån deras [status](#journey-statuses), [typ](#journey-types), [version](publishing-the-journey.md#journey-versions-journey-versions) och tilldelade [taggar](../start/search-filter-categorize.md#tags) från **[!UICONTROL Status and version filters]**.

Använd **[!UICONTROL Creation filters]** om du vill filtrera resorna efter när de skapades eller efter den användare som skapade dem.

Visa resor som använder en specifik händelse, fältgrupp eller åtgärd från **[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**.

Använd **[!UICONTROL Publication filters]** för att välja ett publiceringsdatum eller en användare. Du kan till exempel välja att visa de senaste versionerna av direktresor som publicerades igår.

Om du vill filtrera resor baserat på ett visst datumintervall väljer du **[!UICONTROL Custom]** i listrutan **[!UICONTROL Published]**.

I konfigurationsrutorna Händelse, Datakälla och Åtgärd visar fältet **[!UICONTROL Used in]** dessutom antalet resor som använder just den händelsen, fältgruppen eller åtgärden. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

![](assets/journey3bis.png)

## Resetyper {#journey-types}

Vilken typ av resa det är beror på vilka aktiviteter som används under resan. Den kan vara:

* **[!UICONTROL Unitary event]** - Rutiner för enhetshändelser är kopplade till en viss profil. Händelser relaterar till en persons beteende eller något som händer i samband med en person (en person har till exempel nått 10 000 poäng för lojalitet). [Läs mer](../event/about-events.md).
* **[!UICONTROL Business event]**. Affärsevenemangets resa börjar med en händelse som inte är profilrelaterad. Händelsekonfigurationen utförs av en teknisk användare och kan inte redigeras. [Läs mer](../event/about-events.md).
* **[!UICONTROL Audience Qualification]** - Publikkvalificeringsresor lyssnar på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa. [Läs mer](audience-qualification-events.md).
* **[!UICONTROL Read audience]** - Vid målgruppsresor för läsning kommer alla personer i målgruppen in på resan och får de meddelanden som ingår i din resa.  [Läs mer](read-audience.md).


Läs mer om resetyper och hantering av associerade poster på [den här sidan](entry-management.md).

## Resestatyer {#journey-statuses}

Resans status beror på dess livscykel. Den kan vara:

* **Utkast**: resan är i det första steget. Den har inte publicerats än.
* **Utkast (test)**: Testläget har aktiverats med knappen **Testläge** . [Läs mer](../building-journeys/testing-the-journey.md)
* **Slutförd**: resan växlar automatiskt till den här statusen efter den globala tidsgränsen på 91 dagar [&#128279;](journey-properties.md#global_timeout). Profiler som redan finns på resan slutför normalt. Nya profiler kan inte längre komma in på resan.
* **Live**: resan har publicerats med knappen **Publicera** . [Läs mer](../building-journeys/publishing-the-journey.md)
* **Pausad**: den aktiva resan har pausats med knappen **Paus** . [Läs mer](../building-journeys/journey-pause.md)
* **Stoppad**: resan har inaktiverats med knappen **Stoppa**. Alla individer lämnar resan direkt. [Läs mer](../building-journeys/end-journey.md#stop-a-journey)
* **Stängd**: resan har stängts med knappen **Stäng till nya ingångar**. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt. [Läs mer](../building-journeys/end-journey.md)

>[!NOTE]
>
>* Resursredigeringscykeln innehåller också en uppsättning mellanliggande statusvärden som inte är tillgängliga för filtrering: **Publicering** (mellan &quot;Utkast&quot; och &quot;Live&quot;), **Aktiverar testläge** eller **Inaktiverar testläge** (mellan **Utkast** och **Utkast (test)**), **Stoppar** **(mellan Live** och **Stoppad**), **Återupptar** (mellan **Pausad** och **Live**), **Pausar** (mellan **Live** och **&rbrace;Pausad**) När en resa befinner sig i ett mellanliggande tillstånd är den skrivskyddad.
>
>* Om du behöver ändra till en **Live**-resa [skapar du en ny version](#journey-versions) av din resa. Du kan även pausa dina resor, utföra alla ändringar som behövs och återuppta dem igen när som helst. [Läs mer om att pausa resor](../building-journeys/journey-pause.md)


## Duplicera en resa {#duplicate-a-journey}

Du kan duplicera en befintlig resa från fliken **Bläddra**. Alla objekt och inställningar dupliceras till kopian av resan.

Gör så här:

1. Navigera till den resa du vill kopiera och klicka på ikonen **Fler åtgärder** (de tre punkterna bredvid resans namn).
1. Välj **Duplicera**.

   ![Duplicera en resa](assets/duplicate-jo.png)

1. Ange namnet på resan och bekräfta. Du kan också ändra namnet på skärmen för reseegenskaper. Som standard anges namnet på följande sätt: `[JOURNEY-NAME]_copy`

   ![](assets/duplicate-jo2.png)

1. Den nya resan skapas och är tillgänglig i reselistan.


## Massåtgärder {#bulk-operations}

I listan över dina resor kan du pausa flera **Live**-resor. Om du vill pausa en grupp resor (_masspaus_) markerar du dem i listan och klickar på knappen **Paus** i det blå fältet längst ned på skärmen. Knappen **Paus** är bara tillgänglig när **Live**-resor har valts.

![Pausa två direktresor i grupp från det nedre fältet](assets/bulk-pause-journeys.png)

Du kan även återuppta en eller flera **pausade** resor. Om du vill återuppta en grupp av resor (_massåteruppta_) markerar du dem och klickar på knappen **Återuppta** i det blå fältet längst ned på skärmen. Observera att knappen **Återuppta** endast är tillgänglig när **Pausade** resor har valts.

[Läs mer om att pausa/återuppta resor](journey-pause.md).

>[!NOTE]
>
>Du kan pausa/återuppta till 10 resor per operation.

