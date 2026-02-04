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
source-git-commit: dbed4ffeb63ec3c58ff61845bbdb91fd2d51e69b
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---


# Skapa uppgifter {#create-tasks}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* **Skapa aktiviteter** ◀ }︎ **Du är här** - Definiera utmaningsaktiviteter
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Översikt {#overview}

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar i en lojalitetsutmaning. Ni kan konfigurera uppgiftstyper, kvantiteter, produktkrav och belöningsvärden för att skapa engagerande och personaliserade lojalitetsupplevelser.

Varje uppgift representerar en mätbar åtgärd som bidrar till att slutföra en utmaning. Uppgifter är återanvändbara komponenter som kan skapas oberoende av varandra och sedan läggas till i en eller flera utmaningar, eller skapas direkt i en utmaning.

### Så här fungerar uppgifter med olika typer av utmaningar {#task-overview}

<!-- VISUAL: Diagram showing how task completion works differently for Standard, Streak, and Sequential challenges with examples -->

Beroende på vilken typ av utmaning du använder (Standard, Streak eller Sequential) utför kunderna olika uppgifter:

* **Standardutmaningar**: Kunderna utför ett angivet antal uppgifter i valfri ordning
* **Utmaningar**: Kunderna utför samma uppgift flera gånger i följd
* **Sekventiella utmaningar**: Kunderna slutför uppgifter i en definierad ordning

## Skapa en uppgift {#create-task}

<!-- SCREENSHOT: Two screenshots side by side showing the two entry points: Tasks tab with "Create task" button, and challenge editor with "Add task" button -->

Du kan skapa uppgifter från två startpunkter. Konfigurationsprocessen är densamma oavsett var du börjar.

+++Från aktivitetslagret

1. Navigera till **[!UICONTROL Loyalty challenges]** i Journey Optimizer.

1. Klicka på fliken **[!UICONTROL Tasks]**.  

1. Välj **[!UICONTROL Create task]**.

Uppgifter som skapas från lagret sparas och är tillgängliga för återanvändning i flera olika utmaningar.

+++

+++Från en utmaning

1. Öppna en befintlig eller ny utmaning.

1. Navigera till avsnittet **[!UICONTROL Tasks]**.

1. Välj **[!UICONTROL Add task]** och sedan **[!UICONTROL Create new task]**.

Uppgifter som skapas på det här sättet läggs automatiskt till i din utmaning och sparas även i aktivitetslagret för återanvändning i andra utmaningar.

+++

### Definiera uppgiftsegenskaper {#define-task-properties}

<!-- SCREENSHOT: Task properties form showing Task name and Task description fields -->

Konfigurera grundläggande aktivitetsinformation:

* **Aktivitetsnamn**: Ange ett beskrivande namn för aktiviteten. Det här namnet är synligt för dig och ditt team, men det kanske inte visas för kunderna beroende på designen av ditt innehållskort.
* **Uppgiftsbeskrivning**: (Valfritt) Lägg till information om aktivitetens syfte eller krav.

### Välj kundaktivitet {#choose-activity}

<!-- SCREENSHOT: Activity type selection showing Purchase and Spend options with radio buttons -->

Välj den typ av kundaktivitet som kunderna måste utföra för att slutföra den här uppgiften:

* **[!UICONTROL Purchase]**: Kunder måste köpa ett eller flera objekt för att kunna slutföra den här uppgiften
* **[!UICONTROL Spend]**: Kunder måste spendera ett angivet belopp för att slutföra den här uppgiften

Välj den kundaktivitet som bäst passar era resultatmål. Varje aktivitetstyp har specifika konfigurerbara attribut som ytterligare definierar och formar uppgiftskraven.

### Definiera attribut {#define-attributes}

<!-- SCREENSHOT: Attributes form for Purchase activity showing Quantity field, Eligible items & exclusions field, and parameters icon for optional attributes -->

Konfigurera uppgiftsattributen baserat på den valda aktivitetstypen:

+++För inköpsaktivitet

Konfigurera följande attribut:

* **Kvantitet**: Ange antalet artiklar som måste köpas för att den här aktiviteten ska kunna slutföras
* **Berättigade artiklar och undantag**: Definiera artiklar eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. Läs mer om [att definiera kvalificerade objekt och undantag](#eligible-items-exclusions)

**Valfria attribut** (konfigurera via parameterikonen):

* **Minsta utgiftsbelopp**: Ange ett minimikrav för inköpsbelopp
* **Maximalt antal transaktioner**: Begränsa hur många transaktioner som kan användas för att slutföra uppgiften

+++

+++För utgiftsaktivitet

Konfigurera följande attribut:

* **Belopp**: Ange det totala utgiftsbeloppet som krävs för att slutföra aktiviteten
* **Maximalt antal transaktioner**: Ange hur många transaktioner som tillåts för att uppfylla utgiftsbehovet. Du kan inaktivera det här attributet från parameterikonen om du inte vill begränsa antalet transaktioner
* **Berättigade artiklar och undantag**: (Valfritt) Definiera artiklar eller artikelgrupper som räknas som slutförda aktiviteter och de som inte gör det. Läs mer om [att definiera kvalificerade objekt och undantag](#eligible-items-exclusions)

+++

När du har konfigurerat alla attribut väljer du **[!UICONTROL Create]** för att spara uppgiften. Uppgiften sparas i aktivitetslagret och läggs automatiskt till i den uppgiften om den skapas i en utmaning.

## Definiera kvalificerade artiklar och undantag {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

För både Inköp- och utgiftsaktiviteter kan du definiera kvalificerade artiklar och grupper samt även exkludera artiklar och grupper. På så sätt kan ni inrikta er på specifika produkter, kategorier eller platser för att passa in i era utmaningsmål.

**Användningsexempel:**

* Skapa en uppgift som belönar kunder för inköp av kaffeartiklar men inte rensningsprodukter
* Begränsa en utgiftsaktivitet till specifika produktkategorier
* Undanta presentkort eller kampanjartiklar från att räknas när aktiviteten är slutförd

### Konfigurera berättigade artiklar {#configure-eligible-items}

Använd avsnittet **[!UICONTROL Eligible task purchases are limited to the following]** om du vill definiera kvalificerade objekt:

* Ange specifika objekt-ID, kategorier eller mål-ID:n, avgränsade med kommatecken
* Exempel: `SKU001, SKU002, CategoryA, StoreLocation123`
* **Tips**: Ange `*` om du vill att alla inköp ska vara berättigade (standardbeteende om inget anges)

### Konfigurera undantag {#configure-exclusions}

Om du vill utesluta objekt från aktiviteten använder du avsnittet **[!UICONTROL The following are excluded from this task]**:

* Ange specifika artikel-ID:n, kategorier eller mål-ID:n som inte ska räknas med när aktiviteten slutförs
* Exempel: `CLEARANCE01, GIFTCARD, SALE_CATEGORY`
* Vanliga undantag: artiklar för försäljning eller clearing, presentkort, kampanjartiklar

>[!NOTE]
>
>Undantag har företräde framför berättigande artiklar. Om ett objekt matchar både ett kvalificerat objekt och ett undantag, kommer det att uteslutas från aktiviteten.

## Nästa steg {#next-steps}

Nu när du vet hur man skapar och konfigurerar uppgifter:

* [Skapa utmaningar](create-challenges.md) - Lär dig hur du skapar kompletta utmaningar och konfigurerar belöningar
* [Hantera utmaningar](manage-challenges.md) - Lär dig redigera, övervaka och optimera utmaningar
