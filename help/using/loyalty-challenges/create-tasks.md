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
source-git-commit: f41c1ed8a2d9e74b9d8fe97e0bf9e565d326aec6
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---


# Skapa uppgifter {#create-tasks}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Få åtkomst till och hantera lojalitetsutmaningar](access-loyalty-challenges.md) - Hantering av inventeringar, utmaningar och uppgifter
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* **Skapa aktiviteter** ◀ }︎ **Du är här** - Definiera utmaningsaktiviteter

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar i en lojalitetsutmaning. Ni kan konfigurera uppgiftstyper, kvantiteter och produktkrav för att skapa engagerande och personaliserade lojalitetsupplevelser.

Varje uppgift representerar en mätbar åtgärd som bidrar till att slutföra en utmaning. Uppgifter är återanvändbara komponenter som kan skapas oberoende av varandra och sedan läggas till i en eller flera utmaningar, eller skapas direkt i en utmaning.

## Skapa en uppgift {#create-task}

Du kan skapa uppgifter från två startpunkter. Konfigurationsprocessen är densamma oavsett var du börjar.

>[!BEGINTABS]

>[!TAB Från aktivitetslagret]

Välj fliken **[!UICONTROL Tasks]** och välj **[!UICONTROL Create Task]**.

![](assets/task-create-inventory.png)

Uppgifter som skapas från lagret sparas och är tillgängliga för återanvändning i flera olika utmaningar.

>[!TAB Från inom en utmaning]

Öppna en befintlig eller ny utmaning. Markera **[!UICONTROL Add task]** och klicka på knappen **[!UICONTROL New]**.

![](assets/task-create-challenge.png)

Uppgifter som skapas på det här sättet läggs automatiskt till i din utmaning och sparas även i aktivitetslagret för återanvändning i andra utmaningar.

>[!ENDTABS]

## Välj kundaktivitet {#choose-activity}

Välj den typ av aktivitet som kunderna måste utföra för att slutföra den här uppgiften:

* **[!UICONTROL Purchase]**: Kunder måste köpa ett eller flera objekt för att kunna slutföra den här uppgiften
* **[!UICONTROL Spend]**: Kunder måste spendera ett angivet belopp för att slutföra den här uppgiften

Om du vill välja en aktivitetstyp klickar du på ikonen `+` och väljer den kundaktivitet som bäst passar dina resultatmål. Varje aktivitetstyp har specifika konfigurerbara attribut som ytterligare definierar och formar uppgiftskraven.

![](assets/task-create-activitiy.png)

## Definiera attribut {#define-attributes}

Konfigurera uppgiftsattributen baserat på den valda aktivitetstypen:

>[!BEGINTABS]

>[!TAB Inköpsaktivitet]

![](assets/task-create-purchase.png)

Konfigurera följande attribut:

* **[!UICONTROL Quantity]**: Ange antalet artiklar som måste köpas för att den här uppgiften ska kunna slutföras
* **[!UICONTROL Eligible items & exclusions]**: Definiera objekt eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. Läs mer om [att definiera kvalificerade objekt och undantag](#eligible-items-exclusions)

**Valfria attribut** (aktiveras via parameterikonen):

* **[!UICONTROL Minimum spend value amount]**: Ange ett minimikrav för inköpsbelopp
* **[!UICONTROL Maximum number of transactions]**: Begränsa hur många transaktioner som kan användas för att slutföra uppgiften

>[!TAB Utgiftsaktivitet]

![](assets/task-create-spend.png)

Konfigurera följande attribut:

* **[!UICONTROL Amount]**: Ange det totala utgiftsbeloppet som krävs för att slutföra uppgiften.
* **[!UICONTROL Maximum number of transactions]**: Ange hur många transaktioner som tillåts för att uppfylla utgiftsbehovet. Du kan inaktivera det här attributet från parameterikonen om du inte vill begränsa antalet transaktioner.
* **[!UICONTROL Eligible items & exclusions]**: (Valfritt) Definiera objekt eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. Läs mer om [att definiera kvalificerade objekt och undantag](#eligible-items-exclusions)

>[!ENDTABS]

## Definiera kvalificerade artiklar och undantag {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

För både **Inköp**- och **Utgift**-aktiviteter kan du använda attributet **[!UICONTROL Eligible items & exclusions]** för att definiera vilka objekt och grupper som är kvalificerade och vilka som är uteslutna. På så sätt kan ni inrikta er på specifika produkter, kategorier eller platser för att passa in i era utmaningsmål.

Användningsexempel: begränsa en utgift till specifika produktkategorier, eller utesluta presentkort eller kampanjartiklar från att räknas när en uppgift är slutförd.

![](assets/tasks-create-eligible.png)

* Använd avsnittet **[!UICONTROL Eligible task purchases are limited to the following]** om du vill definiera berättigade objekt. Ange specifika objekt-ID, kategorier eller mål-ID:n, avgränsade med kommatecken.

  Exempel: `SKU001, SKU002, CategoryA`

  Ange `*` om du vill att alla inköp ska vara berättigade (standardbeteende om inget anges).

* Om du vill utesluta objekt från aktiviteten använder du avsnittet **[!UICONTROL The following are excluded from this task]**. Ange specifika artikel-ID:n, kategorier eller mål-ID:n som inte ska räknas med när aktiviteten slutförs.

  Exempel: `CLEARANCE01, GIFTCARD, SALE_CATEGORY`

  >[!NOTE]
  >
  >Undantag har företräde framför berättigande artiklar. Om ett objekt matchar både ett kvalificerat objekt och ett undantag, kommer det att uteslutas från aktiviteten.

## Definiera uppgiftsegenskaper {#define-task-properties}

Konfigurera grundläggande aktivitetsinformation i åtgärdsrutan **[!UICONTROL Properties]**:

* **[!UICONTROL Task name]**: Ange ett beskrivande namn för aktiviteten. Det här namnet är synligt för dig och ditt team, men det kanske inte visas för kunderna beroende på designen av ditt innehållskort.
* **[!UICONTROL Task description]**: Beskrivningen genereras automatiskt baserat på aktivitetstypen och de attribut du konfigurerar för uppgiften. Du kan inaktivera automatisk generering och ange en egen beskrivning om det behövs.

![](assets/tasks-create-properties.png)

När du har konfigurerat alla attribut och egenskaper väljer du **[!UICONTROL Create]** för att spara uppgiften. Uppgiften sparas i aktivitetslagret och läggs automatiskt till i den uppgiften om den skapas i en utmaning.
