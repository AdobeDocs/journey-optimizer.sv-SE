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
source-git-commit: dbed4ffeb63ec3c58ff61845bbdb91fd2d51e69b
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 0%

---


# Hantera utmaningar {#manage-challenges}

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

### Utmaningens livscykel {#challenge-lifecycle}

<!-- VISUAL: Flowchart diagram showing challenge lifecycle with status transitions: Draft → Scheduled → Live → Completed/Stopped/Archived -->

Utmaningarna rör sig genom olika statusar under livscykeln:

* **Utkast**: Utmaningen skapas eller redigeras och är ännu inte tillgänglig för kunder
* **Schemalagd**: Utmaningen har publicerats och blir automatiskt aktiv det angivna startdatumet
* **Live**: Utmaningen är aktiv och kunderna kan delta
* **Slutförd**: Utmaningen har avslutats - antingen har slutdatumet passerats eller alla mål har uppfyllts
* **Stoppad**: Utmaningen stoppades manuellt innan den slutfördes naturligt
* **Arkiverad**: Utmaningen har arkiverats för organisationssyften och är inte längre synlig i huvudlagret

### Redigera utmaningar {#edit-challenges}

Du kan redigera utmaningar beroende på deras aktuella status:

* **Utmaningar**: Fullständig redigering - alla egenskaper kan ändras
* **Schemalagda/dynamiska utmaningar**: Begränsad redigering - du kan uppdatera innehåll, meddelanden och förlänga datum, men du kan inte ändra huvudstrukturen för utmaningar (typ, målgrupp eller aktivitetsdefinitioner)

Så här redigerar du en utmaning:

1. Gå till fliken **[!UICONTROL Challenges]** i lagret för lojalitetsutmaningar.

1. Leta reda på den utmaning som du vill redigera.

1. Markera utmaningsnamnet om du vill öppna det i redigeringsläge.

1. Gör dina ändringar baserat på utmaningsstatus:
   * **Utmaningar**: Ändra egenskaper, uppgifter, innehåll eller meddelanden
   * **Schemalagda/dynamiska utmaningar**: Uppdatera innehållskort, meddelanden eller utöka slutdatum efter behov

1. Spara ändringarna. För schemalagda eller aktiva utmaningar träder ändringarna i kraft omedelbart eller i enlighet med ditt uppdateringsschema.

>[!NOTE]
>
>För ändringar som kräver större ändringar (till exempel ändring av utmaningstyp, målgrupp eller uppgiftsstruktur), ska du duplicera utmaningen och skapa en ny version i stället för att redigera den befintliga.

### Duplicerade utmaningar {#duplicate-challenges}

Duplicera utmaningarna med:

* Kör om framgångsrika utmaningar för nya tidsperioder
* Skapa varianter för olika målgrupper
* Uppdatera uppgiftskrav eller belöningar
* Återaktivera stoppade eller slutförda problem

När du duplicerar en utmaning skapas en exakt kopia med alla uppgifter, allt innehåll och alla meddelanden intakta, så att du snabbt kan skapa nya versioner utan att börja om från början.

Så här duplicerar du en utmaning:

1. Gå till fliken **[!UICONTROL Challenges]** i lagret för lojalitetsutmaningar.

1. Leta reda på den utmaning som du vill duplicera.

1. Välj menyn Fler åtgärder (tre punkter) bredvid den utmaningen.

1. Välj **[!UICONTROL Duplicate]**.

1. En kopia av utmaningen skapas med &quot;[Kopiera]&quot; tillagd i namnet.

1. Öppna den duplicerade utmaningen och ändra de nödvändiga egenskaperna:
   * Uppdatera utmaningsnamnet
   * Justera start- och slutdatum
   * Ändra målgruppen vid behov
   * Ändra uppgifter, belöningar, innehåll eller meddelanden efter behov

1. Granska och publicera den duplicerade utmaningen.

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

1. Välj menyn Fler åtgärder (tre punkter) bredvid uppgiften.

1. Välj **[!UICONTROL Delete]**.

1. Bekräfta borttagningen i dialogrutan.

>[!NOTE]
>
>Om en uppgift används i en utmaning (utkast, schemalagd eller live) måste du först ta bort den från alla utmaningar innan du kan ta bort den. Överväg att arkivera eller duplicera uppgifter i stället för att ta bort dem om du behöver dem i framtiden.
