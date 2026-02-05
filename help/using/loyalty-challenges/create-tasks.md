---
solution: Journey Optimizer
product: journey optimizer
title: Skapa uppgifter för lojalitetsutmaningar
description: Lär dig hur du skapar och konfigurerar uppgifter för lojalitetsutmaningar i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
mini-toc-levels: 1
source-git-commit: 342df0950622de1c4c246bf624d05843671e199f
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---


# Skapa uppgifter {#create-tasks}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md)
* [Få tillgång till och hantera utmaningar och uppgifter](access-loyalty-challenges.md)
* [Skapa utmaningar](create-challenges.md)
* **Skapa aktiviteter** {2 }︎ ◀Du är här **&#x200B;**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen finns för närvarande i **privat beta**. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar i en lojalitetsutmaning. Ni kan konfigurera uppgiftstyper, kvantiteter och produktkrav för att skapa engagerande och personaliserade lojalitetsupplevelser.

Varje uppgift representerar en mätbar åtgärd som bidrar till att slutföra en utmaning. Uppgifter är återanvändbara komponenter som kan skapas oberoende av varandra och sedan läggas till i en eller flera utmaningar, eller skapas direkt i en utmaning.

## Skapa en uppgift {#create-task}

Du kan skapa uppgifter från två startpunkter. Konfigurationsprocessen är densamma oavsett var du börjar.

>[!BEGINTABS]

>[!TAB Från aktivitetslagret]

Välj fliken **[!UICONTROL Tasks]** och välj **[!UICONTROL Create Task]**. Uppgifter som skapas från lagret sparas och är tillgängliga för återanvändning i flera olika utmaningar.

![](assets/task-create-inventory.png)

>[!TAB Från inom en utmaning]

Öppna en befintlig eller ny utmaning. Markera **[!UICONTROL Add task]** och klicka på knappen **[!UICONTROL New]**. Uppgifter som skapas på det här sättet läggs automatiskt till i din utmaning och sparas även i aktivitetslagret för återanvändning i andra utmaningar.

![](assets/task-create-challenge.png)

>[!ENDTABS]

## Välj kundaktivitet {#choose-activity}

Välj den typ av aktivitet som kunderna måste utföra för att slutföra den här uppgiften:

* **[!UICONTROL Purchase]**: Kunder måste köpa ett eller flera objekt för att kunna slutföra den här uppgiften
* **[!UICONTROL Spend]**: Kunder måste spendera ett angivet belopp för att slutföra den här uppgiften

Om du vill välja en aktivitet klickar du på ikonen **+** och väljer den kundaktivitet som bäst passar dina resultatmål. Varje aktivitetstyp har specifika konfigurerbara attribut som ytterligare definierar och formar uppgiftskraven.
![](assets/task-create-activity.png)

## Definiera uppgiftsattributen {#define-attributes}

Konfigurera aktivitetsattributen baserat på den valda aktivitetstypen. Bläddra bland flikarna nedan om du vill se tillgängliga attribut för varje aktivitetstyp:

>[!BEGINTABS]

>[!TAB Inköpsaktivitet]

Tillgängliga attribut för **Inköp**-aktiviteter:

* **[!UICONTROL Quantity]**: Ange antalet artiklar som måste köpas för att den här uppgiften ska kunna slutföras.
* **[!UICONTROL Eligible items & exclusions]**: Definiera objekt eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. [Läs mer om berättigade objekt och undantag &#x200B;](#eligible-items-exclusions)
* **[!UICONTROL Minimum spend value amount]**: Ange ett minimikrav för inköpsbelopp.
* **[!UICONTROL Maximum number of transactions]**: Begränsa hur många transaktioner som kan användas för att slutföra uppgiften.

![](assets/task-create-purchase.png)

>[!TAB Utgiftsaktivitet]

Tillgängliga attribut för **Utlägg**-aktiviteter:

* **[!UICONTROL Amount]**: Ange det totala utgiftsbeloppet som krävs för att slutföra uppgiften.
* **[!UICONTROL Eligible items & exclusions]**: Definiera objekt eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. [Läs mer om berättigade objekt och undantag &#x200B;](#eligible-items-exclusions)
* **[!UICONTROL Maximum number of transactions]**: Ange hur många transaktioner som tillåts för att uppfylla utgiftsbehovet. Du kan aktivera det här attributet från parameterikonen.

![](assets/task-create-spend.png)

>[!ENDTABS]

## Definiera kvalificerade artiklar och undantag {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

För både **Inköp**- och **Utgift**-aktiviteter kan du använda attributet **[!UICONTROL Eligible items & exclusions]** för att definiera vilka objekt och grupper som är kvalificerade och vilka som är uteslutna. På så sätt kan ni inrikta er på specifika produkter, kategorier eller platser för att passa in i era utmaningsmål.

Du kan t.ex. begränsa en utgiftsaktivitet till specifika produktkategorier eller utesluta presentkort eller kampanjartiklar från att räknas när aktiviteten är slutförd.

![](assets/tasks-create-eligible.png)

* Om du vill definiera kvalificerade objekt anger du specifika artikel-ID:n, kategorier eller mål-ID:n, avgränsade med kommatecken i fältet **[!UICONTROL Eligible task purchases are limited to the following]**. Om du lämnar fältet tomt är alla inköp berättigade som standard. Du kan också ange `*` för att explicit göra alla inköp giltiga.

  Exempel: `SKU001, SKU002, CategoryA`

* Om du vill utesluta objekt från aktiviteten anger du specifika artikel-ID:n, kategorier eller mål-ID:n i fältet **[!UICONTROL The following are excluded from this task]**.

  Exempel: `CLEARANCE01, GIFTCARD, SALE_CATEGORY`

## Definiera uppgiftsegenskaper {#define-task-properties}

Konfigurera grundläggande aktivitetsinformation i åtgärdsrutan **[!UICONTROL Properties]**:

* **[!UICONTROL Task name]**: Ange ett beskrivande namn för aktiviteten.
* **[!UICONTROL Task description]**: Beskrivningen genereras automatiskt baserat på den konfigurerade aktiviteten och attributen. Om du vill ange en egen beskrivning stänger du av det automatiska genereringsalternativet och anger din beskrivning i textfältet.

![](assets/tasks-create-properties.png)

När du har konfigurerat alla attribut och egenskaper väljer du **[!UICONTROL Create]** för att spara uppgiften. Uppgiften sparas i aktivitetslagret och läggs automatiskt till i den uppgiften om den skapas i en utmaning.
