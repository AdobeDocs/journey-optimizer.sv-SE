---
solution: Journey Optimizer
product: journey optimizer
title: Hantera lojalitetsutmaningar
description: Lär dig hantera, övervaka och optimera lojalitetsutmaningar i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: e978d075efbbcb42e7500d921bd8cc3ed1eee890
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---


# Hantera utmaningar och uppgifter {#manage-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter
* **Hantera utmaningar** ◀ &rbrace;︎ **Du är här** - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Hantera utmaningar {#manage-challenges-section}

### Utmaningstillstånd {#challenge-lifecycle}

Utmaningarna rör sig genom olika statusar under livscykeln:

* **Utkast**: Utmaningen skapas eller redigeras och är ännu inte tillgänglig för kunder
* **Publicerad**: Utmaningen är aktiv, den associerade resan har skapats.

### Redigera utmaningar {#edit-challenges}

Du kan redigera utmaningar genom att öppna dem i probleminventeringen. Redigeringsbeteendet varierar beroende på hur utmaningen fungerar:

**Utmaningar**: Du har fullständig redigeringsfunktion. Alla egenskaper, uppgifter, innehåll och meddelanden kan ändras utan begränsningar.

**Publicerade utmaningar**: När du öppnar en publicerad utmaning för redigering måste du först återställa den till utkaststatus.

* Alla anpassningar som gjorts direkt i den automatiskt genererade resan går förlorade
* Utmaningen återgår till utkastläget
* När du har gjort ändringarna måste du spara och publicera utmaningen igen
* Du måste återaktivera den associerade resan för att göra den uppdaterade utmaningen tillgänglig för kunderna

>[!IMPORTANT]
>
>Det går inte att ångra en publicerad utmaning till ett utkast. Fundera på vilken effekt din aktiva resa har innan du fortsätter.

### Duplicerade utmaningar {#duplicate-challenges}

När du duplicerar en utmaning skapas en exakt kopia med alla uppgifter, allt innehåll och alla meddelanden intakta, så att du snabbt kan skapa nya versioner utan att börja om från början.

Så här duplicerar du en utmaning:

1. Navigera till fliken **[!UICONTROL Challenges]** och leta reda på den fråga du vill duplicera.

1. Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) bredvid den utmaningen och välj **[!UICONTROL Duplicate]**.

1. En kopia av utmaningen skapas. Öppna den duplicerade utmaningen och ändra de nödvändiga egenskaperna.

1. Spara den duplicerade utmaningen och generera den tillhörande resan.

### Bildskärmsprestanda {#monitor-performance}

<!-- SCREENSHOT: Challenge Performance tab showing key metrics dashboard with participation, completion, reward, and engagement metrics -->

Spåra utmaningsprestanda med nyckeltal:

* **Deltagandestatistik**:
   * Registrering: Antal kunder som anslutit till utmaningen
   * Aktiva deltagare: Kunder som för närvarande är engagerade i utmaningen
* **Resultatmått**:
   * Slutförandefrekvens: Procentandel registrerade kunder som slutförde utmaningen
   * Genomsnittlig slutförandetid: Genomsnittlig tid för att slutföra alla uppgifter
* **Belöningsmått**:
   * Totalt antal fördelade belöningar: aggregerat värde för alla angivna belöningar
   * Belöningar per typ: Uppdelning av belöningar per belöningskategori
* **Interaktionsstatistik**:
   * Intryck av innehållskort: Antal gånger som visitkort visades
   * Meddelandeleverans: Antal meddelanden som skickats över alla kanaler

Så här får du åtkomst till prestandadata:

1. Gå till fliken **[!UICONTROL Challenges]** i lagret för lojalitetsutmaningar.

1. Välj den utmaning som du vill övervaka.

1. Öppna fliken **[!UICONTROL Performance]** om du vill visa realtidsstatistik och analyser.

<!-- SCREENSHOT: Journey report showing challenge performance data with graphs and tables -->

Du kan även få tillgång till detaljerade prestandadata i de [automatiskt genererade reserapporterna](../reports/journey-global-report-cja.md) som ger ytterligare insikter och historiska trender.

## Hantera uppgifter {#manage-tasks}

Aktiviteter är återanvändbara komponenter som kan användas i flera utmaningar. Att hantera uppgifter effektivt säkerställer enhetlighet i alla lojalitetsprogram och gör det enklare att uppdatera uppgiftsdefinitionerna centralt. Uppgifter som skapats i en utmaning kan återanvändas i andra utmaningar, vilket minskar dubbelarbete och upprätthåller standardiseringen.

### Redigera uppgifter {#edit-tasks}

Du kan redigera befintliga uppgifter från aktivitetslagret. Tänk på följande:

* **Uppgifter som inte används i aktiva utmaningar**: Kan redigeras fritt - alla egenskaper kan ändras utan påverkan
* **Uppgifter som används i live-utmaningar**: Var försiktig eftersom ändringar påverkar alla utmaningar som använder aktiviteten - ändringar tillämpas omedelbart på alla referensutmaningar

Så här redigerar du en uppgift:

1. Gå till fliken **[!UICONTROL Tasks]** i lagret för lojalitetsutmaningar.

1. Leta reda på uppgiften som du vill redigera.

1. Markera aktivitetsnamnet om du vill öppna det i redigeringsläge.

1. Ändra uppgiftsegenskaperna efter behov:
   * Uppdatera aktivitetsnamn eller beskrivning
   * Ändra aktivitetstyp eller attribut
   * Justera berättigande artiklar och undantag
   * Ändra kvantitet eller beloppskrav

1. Spara ändringarna.

>[!WARNING]
>
>När du redigerar en uppgift som används aktivt i aktiva utmaningar bör du överväga att skapa en dubblett med en ny version i stället för att ändra originalet. Detta förhindrar oavsiktliga ändringar av aktiva utmaningar och gör att du kan testa ändringarna innan du använder dem.

### Ta bort uppgifter {#delete-tasks}

Det går bara att ta bort uppgifter om de inte används för närvarande i några utmaningar. Innan du tar bort en uppgift:

* Kontrollera antalet **[!UICONTROL Used in challenges]** i aktivitetslagret
* Se till att inga utkast, schemalagda eller aktiva utmaningar refererar till uppgiften

Så här tar du bort en uppgift:

1. Gå till fliken **[!UICONTROL Tasks]** i lagret för lojalitetsutmaningar.

1. Leta reda på uppgiften som du vill ta bort.

1. Kontrollera att antalet **[!UICONTROL Used in challenges]** visar 0. Om antalet är större än 0 måste du först ta bort uppgiften från alla utmaningar innan du tar bort den.

1. Välj ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) bredvid uppgiften.

1. Välj **[!UICONTROL Delete]**.

1. Bekräfta borttagningen i dialogrutan.

>[!NOTE]
>
>Om en uppgift används i en utmaning (utkast, schemalagd eller live) måste du först ta bort den från alla utmaningar innan du kan ta bort den. Överväg att arkivera eller duplicera uppgifter i stället för att ta bort dem om du behöver dem i framtiden.
