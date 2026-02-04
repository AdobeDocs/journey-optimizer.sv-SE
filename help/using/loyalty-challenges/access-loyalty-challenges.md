---
solution: Journey Optimizer
product: journey optimizer
title: Utmaningar om lojalitet
description: Lär dig hur du får tillgång till, söker efter och filtrerar lojalitetsproblem i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: dbed4ffeb63ec3c58ff61845bbdb91fd2d51e69b
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---


# Utmaningar om lojalitet {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* **Åtkomst till lojalitetsproblem** {2 }︎ ◀Du är här **- Lager och filtrering**
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Få tillgång till lagret med lojalitetsutmaningar {#access-inventory}

<!-- SCREENSHOT: Journey Optimizer main menu showing "Loyalty challenges" under "Customer journeys" section -->

Om du vill få åtkomst till lojalitetsutmaningar går du till Journey Optimizer och väljer **[!UICONTROL Loyalty challenges]** under avsnittet **[!UICONTROL Customer journeys]**.

<!-- SCREENSHOT: Loyalty Challenges landing page showing the two tabs: Challenges and Tasks -->

Sidan Loyalty Challenges visas med två flikar:

* **[!UICONTROL Challenges]**: Visa och hantera alla lojalitetsutmaningar

* **[!UICONTROL Tasks]**: Visa och hantera alla uppgifter som kan återanvändas i flera utmaningar

## Utmaningslager {#challenges-tab}

<!-- SCREENSHOT: Challenges tab showing the inventory table with columns: Challenge name, Status, Type, Start date, End date, Created by, Last modified, Tags -->

På fliken Utmaningar visas alla utmaningar sorterade efter senaste ändringsdatum, där de senast ändrade utmaningarna visas först. Följande information visas:

* **[!UICONTROL Challenge name]**: Namnet som du tilldelade till utmaningen
* **[!UICONTROL Status]**: Aktuellt tillstånd för utmaningen (se statusbeskrivningar nedan)
* **[!UICONTROL Type]**: Utmaningstyp (Standard, Streak eller Sequential)
* **[!UICONTROL Start date]**: När utmaningen blir aktiv
* **[!UICONTROL End date]**: När utmaningen upphör
* **[!UICONTROL Created by]**: Användare som skapade utmaningen
* **[!UICONTROL Last modified]**: Datum och tid för senaste ändring
* **[!UICONTROL Tags]**: Alla taggar som har använts på utmaningen för organisationen

### Utmaningsstatus {#challenge-statuses}

<!-- VISUAL: Status badges showing different challenge statuses with color coding: Draft (gray), Scheduled (blue), Live (green), Completed (gray), Stopped (red), Archived (gray) -->

Utmaningar visas med olika statusvärden som anger deras aktuella status i livscykeln:

* **Utkast**: Utmaningen skapas eller redigeras
* **Schemalagd**: Utmaningen publiceras och blir aktiv på startdatumet
* **Live**: Utmaningen är aktiv och kunderna kan delta
* **Slutförd**: Slutdatum för utmaning har passerats eller mål har uppfyllts
* **Stoppad**: Utmaningen stoppades manuellt innan den slutfördes
* **Arkiverad**: Utmaningen har arkiverats i organisationssyfte

Detaljerad information om statusövergångar och provningens livscykel finns i [Utmaningens livscykel](manage-challenges.md#challenge-lifecycle).

### Söka efter och filtrera problem {#search-challenges}

<!-- SCREENSHOT: Search bar and filter panel showing available filters (status, type, dates, tags) with an example of active filters applied -->

Du kan snabbt hitta utmaningar med hjälp av sökning och filter:

**Sök:**

* Använd sökfältet för att hitta problem genom att ange nyckelord från utmaningsnamnet eller beskrivningen. Sökningen uppdateras i realtid medan du skriver.

**Filter:**

* Använd ett eller flera filter för att begränsa resultatet:
   * **Status**: Filtrera efter utmaningsstatus (Utkast, Schemalagd, Live, Slutförd, Stoppad, Arkiverad)
   * **Typ**: Filtrera efter utmaningstyp (Standard, Streak, Sequential)
   * **Datum**: Filtrera efter startdatum eller slutdatumintervall
   * **Taggar**: Filtrera efter taggar som används i problem

Du kan kombinera flera filter samtidigt. Filtrera till exempel efter Live Standard-utmaningar som taggas med&quot;Sommaren 2024&quot; för att snabbt hitta aktiva säsongskampanjer.

Om du vill ta bort filter väljer du **[!UICONTROL Clear all]** eller tar bort enskilda filter.

### Utmaningar {#inventory-actions}

<!-- SCREENSHOT: More actions menu (three dots) expanded showing options: Edit, Duplicate, Stop, Archive, Delete -->

På fliken Utmaningar kan du utföra snabba åtgärder på utmaningar:

* **Visa information om utmaning**: Välj utmanarnamnet för att öppna informationssidan
* **Redigera en utmaning**: Välj menyn **[!UICONTROL More actions]** (tre punkter) och välj **[!UICONTROL Edit]**
* **Duplicera en utmaning**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Duplicate]**
* **Stoppa en aktiv utmaning**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Stop]**
* **Arkivera en utmaning**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Archive]**
* **Ta bort ett utkast**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Delete]** (endast tillgängligt för utkast)

Detaljerad information om hur du hanterar problem efter skapande, inklusive redigeringsbegränsningar, dupliceringsstrategier, prestandaövervakning och felsökning finns i [Hantera utmaningar](manage-challenges.md).

## Aktivitetslager {#tasks-tab}

<!-- SCREENSHOT: Tasks tab showing the inventory table with columns: Task name, Task type, Description, Created by, Last modified, Used in challenges -->

Fliken Uppgifter visar alla återanvändbara uppgifter som kan användas för flera utmaningar. Uppgifter som skapas här blir tillgängliga för markering när du skapar eller redigerar utmaningar.

I aktivitetslagret visas följande information:

* **[!UICONTROL Task name]**: Namnet som du tilldelade uppgiften
* **[!UICONTROL Task type]**: Typ av åtgärd (inköp, utgiftsbelopp, besök, engagemang, anpassad händelse)
* **[!UICONTROL Description]**: En kort beskrivning av vad aktiviteten kräver
* **[!UICONTROL Created by]**: Användare som skapade uppgiften
* **[!UICONTROL Last modified]**: Datum och tid för senaste ändring
* **[!UICONTROL Used in challenges]**: Antal utmaningar som för närvarande använder den här aktiviteten

### Vidta åtgärder för uppgifter {#tasks-actions}

På fliken Åtgärder kan du utföra åtgärder för uppgifter:

* **Visa aktivitetsinformation**: Välj aktivitetsnamnet om du vill visa fullständig konfiguration
* **Redigera en uppgift**: Välj menyn **[!UICONTROL More actions]** (tre punkter) och välj **[!UICONTROL Edit]**
* **Duplicera en uppgift**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Duplicate]**
* **Ta bort en uppgift**: Välj menyn **[!UICONTROL More actions]** och välj **[!UICONTROL Delete]** (endast om den inte används i några aktiva utmaningar)
* **Visa användning**: Se vilka utmaningar som för närvarande använder uppgiften

## Nästa steg {#next-steps}

Nu när du vet hur man hittar och navigerar i lagret Lojalitetsutmaningar:

* [Skapa utmaningar](create-challenges.md) - Lär dig hur du skapar din första utmaning och konfigurerar uppgifter
* [Skapa aktiviteter](create-tasks.md) - Lär dig definiera återanvändbara uppgifter för utmaningar
* [Hantera utmaningar](manage-challenges.md) - Lär dig redigera, övervaka och optimera utmaningar
