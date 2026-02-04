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
source-git-commit: e98fe328b5a72a7091d48b5e2939a24e4ad6954c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---


# Utmaningar om lojalitet {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* **Åtkomst till lojalitetsproblem** {2 }︎ ◀Du är här **- Lager och filtrering**
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

## Få tillgång till lagret med lojalitetsutmaningar {#access-inventory}

Så här kommer du åt lojalitetsutmaningar:

1. I Adobe Journey Optimizer väljer du **[!UICONTROL Loyalty challenges]** i den vänstra navigeringsmenyn under avsnittet **[!UICONTROL Customer journeys]**.

2. Sidan Loyalty Challenges visas med två flikar:
   * **[!UICONTROL Challenges]**: Visa och hantera alla lojalitetsutmaningar
   * **[!UICONTROL Tasks]**: Visa och hantera alla uppgifter som kan återanvändas i flera utmaningar

Som standard är fliken **[!UICONTROL Challenges]** markerad och visar alla befintliga utmaningar i organisationen.

## Fliken Utmaningar {#challenges-tab}

På fliken Utmaningar visas alla utmaningar sorterade efter senaste ändringsdatum, där de senast ändrade utmaningarna visas först.

### Förstå utmaningarna {#inventory-overview}

I inventeringen av utmaningar visas alla utmaningar med följande information:

* **[!UICONTROL Challenge name]**: Namnet som du tilldelade till utmaningen
* **[!UICONTROL Status]**: Aktuellt tillstånd för utmaningen (se statusbeskrivningar nedan)
* **[!UICONTROL Type]**: Utmaningstyp (Standard, Streak eller Sequential)
* **[!UICONTROL Start date]**: När utmaningen blir aktiv
* **[!UICONTROL End date]**: När utmaningen upphör
* **[!UICONTROL Created by]**: Användare som skapade utmaningen
* **[!UICONTROL Last modified]**: Datum och tid för senaste ändring
* **[!UICONTROL Tags]**: Alla taggar som har använts på utmaningen för organisationen

### Utmaningsstatus {#challenge-statuses}

Utmaningar kan ha följande status:

* **[!UICONTROL Draft]**: Utmaningen skapas eller redigeras men publiceras inte ännu
* **[!UICONTROL Scheduled]**: Utmaningen har publicerats och schemalagts att starta vid ett framtida datum
* **[!UICONTROL Live]**: Utmaningen är för närvarande aktiv och tillgänglig för målgruppen
* **[!UICONTROL Completed]**: Utmaningen har passerat sitt slutdatum eller så har alla mål uppfyllts
* **[!UICONTROL Stopped]**: Utmaningen stoppades manuellt innan den slutfördes
* **[!UICONTROL Archived]**: Utmaningen har arkiverats för organisatoriska syften

### Söka efter och filtrera problem {#search-challenges}

Använd sökfunktionen för att snabbt hitta specifika problem efter namn eller beskrivning.

Du kan också använda filter för att begränsa utmaningslistan baserat på specifika villkor. Du kan kombinera flera filter för att förfina sökningen.

Du kan filtrera utmaningar efter deras aktuella status, utifrån deras utmaningstyp, baserat på start- och slutdatum eller efter taggar som du har tillämpat för organisationen.

### Utmaningar {#inventory-actions}

På fliken Utmaningar kan du utföra snabba åtgärder på utmaningar:

* **Visa information om utmaning**: Välj ett utmanarnamn för att öppna informationssidan
* **Redigera en utmaning**: Välj menyn Fler åtgärder (tre punkter) och välj **[!UICONTROL Edit]**
* **Duplicera en utmaning**: Välj menyn Fler åtgärder och välj **[!UICONTROL Duplicate]**
* **Stoppa en aktiv utmaning**: Välj menyn för fler åtgärder och välj **[!UICONTROL Stop]**
* **Arkivera en utmaning**: Välj menyn Fler åtgärder och välj **[!UICONTROL Archive]**
* **Ta bort ett utkast**: Välj menyn Fler åtgärder och välj **[!UICONTROL Delete]** (endast tillgängligt för utkast)

### Skapa en ny utmaning {#create-from-inventory}

Så här skapar du en ny utmaning på fliken Utmaningar:

1. Välj **[!UICONTROL Create challenge]** i det övre högra hörnet.

2. Arbetsflödet för att skapa en utmaning börjar.

Mer information finns i [Skapa utmaningar](create-challenges.md).

## Fliken Uppgifter {#tasks-tab}

Fliken Uppgifter visar alla återanvändbara uppgifter som kan användas för flera utmaningar. Uppgifter som skapas här blir tillgängliga för markering när du skapar eller redigerar utmaningar.

### Förstå aktivitetslagret {#tasks-inventory-overview}

I aktivitetslagret visas alla uppgifter med följande information:

* **[!UICONTROL Task name]**: Namnet som du tilldelade uppgiften
* **[!UICONTROL Task type]**: Typ av åtgärd (inköp, utgiftsbelopp, besök, engagemang, anpassad händelse)
* **[!UICONTROL Description]**: En kort beskrivning av vad aktiviteten kräver
* **[!UICONTROL Created by]**: Användare som skapade uppgiften
* **[!UICONTROL Last modified]**: Datum och tid för senaste ändring
* **[!UICONTROL Used in challenges]**: Antal utmaningar som för närvarande använder den här aktiviteten

### Skapa uppgifter från fliken Uppgifter {#create-tasks-from-tab}

Du kan skapa uppgifter på två sätt:

1. **Från aktivitetsfliken** (rekommenderas för återanvändbara uppgifter):
   * Navigera till fliken **[!UICONTROL Tasks]**
   * Välj **[!UICONTROL Create task]**
   * Konfigurera uppgiftsegenskaperna (namn, typ, kvantitet, produktfilter, belöningar)
   * Spara uppgiften så att den blir tillgänglig för användning i alla utmaningar

2. **När du skapar en utmaning** (för utmaningsspecifika uppgifter):
   * Välj **[!UICONTROL Add task]** i aktivitetsavsnittet när du skapar en utmaning
   * Välj **[!UICONTROL Create new task]** eller välj bland befintliga uppgifter
   * Aktiviteter som skapas på det här sättet sparas också i aktivitetslagret och kan återanvändas

>[!TIP]
>
>Du bör skapa uppgifter från fliken Uppgifter när du tänker använda samma uppgift i flera olika utmaningar. Detta ger enhetlighet och gör det enklare att uppdatera uppgiftsdefinitionerna centralt.

### Vidta åtgärder för uppgifter {#tasks-actions}

På fliken Åtgärder kan du utföra åtgärder för uppgifter:

* **Visa aktivitetsinformation**: Välj ett aktivitetsnamn om du vill visa fullständig konfiguration
* **Redigera en aktivitet**: Välj menyn Fler åtgärder (tre punkter) och välj **[!UICONTROL Edit]**
* **Duplicera en uppgift**: Välj menyn Fler åtgärder och välj **[!UICONTROL Duplicate]**
* **Ta bort en uppgift**: Välj menyn Fler åtgärder och välj **[!UICONTROL Delete]** (endast om den inte används i några aktiva utmaningar)
* **Visa användning**: Se vilka utmaningar som för närvarande använder uppgiften

## Nästa steg {#next-steps}

Nu när du vet hur man hittar och navigerar i lagret Lojalitetsutmaningar:

* [Skapa utmaningar](create-challenges.md) - Lär dig hur du skapar din första utmaning
* [Hantera utmaningar](manage-challenges.md) - Lär dig hur du redigerar och övervakar utmaningar
