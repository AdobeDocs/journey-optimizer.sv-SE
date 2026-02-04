---
solution: Journey Optimizer
product: journey optimizer
title: Skapa lojalitetsutmaningar
description: Lär dig hur du skapar och konfigurerar lojalitetsutmaningar i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: fd87aeabfae1f07d8f7bea7057f0c6dd0559d024
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 0%

---


# Skapa utmaningar {#create-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* **Skapa utmaningar** ◀ }︎ **Du är här** - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Så fungerar det {#how-it-works}

När du skapar och startar en lojalitetsutmaning följer du det här arbetsflödet:

1. **[Skapa utmaningen](#create-the-challenge)** - Välj den utmaningstyp (Standard, Streak eller Sequential) som bäst passar dina lojalitetsprogrammål.

1. **[Konfigurera utmaningsstrukturen](#structure)** - Definiera utmaningsegenskaperna, schemat, aktiviteter som kunderna måste slutföra och belöningar som de ska få.

1. **[Konfigurera innehållskort](#configure-content-cards)** - Utforma innehållskort som visuellt representerar din utmaning på kundenheter och visar information om utmaningar, framsteg och belöningar.

1. **[Konfigurera meddelanden](#configure-messaging)** (valfritt) - Konfigurera flerkanalsmeddelanden (i programmet, e-post, push) för nyckelstadier: start, pågående och slutförande.

1. **[Välj den utmanande målgruppen](#audience)** - Definiera vilka kunder som är berättigade att delta i utmaningen.

1. **[Generera och aktivera resan](#review-and-publish)** - Generera den associerade resan och aktivera den för att göra utmaningen tillgänglig för målgruppen.

## Skapa utmaningen {#create-the-challenge}

1. Navigera till **[!UICONTROL Loyalty Challenges (Beta)]** i Journey Optimizer.

1. Välj fliken **[!UICONTROL Challenges]** och välj **[!UICONTROL Create challenge]**.

   ![](assets/challenge-create.png)

1. Välj typen av utmaning:

   * **[!UICONTROL Standard]**: Kunderna utför ett angivet antal uppgifter i valfri ordning
   * **[!UICONTROL Streak]**: Kunder slutför samma uppgift flera gånger i följd
   * **[!UICONTROL Sequential]**: Kunder slutför uppgifter i en definierad ordning

## Konfigurera utmaningsstrukturen {#structure}

På fliken Struktur definierar du hur utmaningen ska ordnas: egenskaper, schema, uppgifter som ska utföras och belöningar som ska tilldelas.

### Definiera utmaningsegenskaperna och använd anpassade metadata {#properties}

1. Konfigurera utmaningsegenskaperna i rutan Utmaningsegenskaper:

   ![](assets/challenge-create-properties.png)

   **Namn**: Ange ett beskrivande namn för utmaningen. Det här namnet visas i utmaningslagret och hjälper dig att identifiera utmaningen.

   **Beskrivning**: Ange en beskrivning för din utmaning.

1. Använd avsnittet **[!UICONTROL Custom metadata]** om du vill lägga till anpassade metadata med hjälp av nyckel/värde-par. Dessa metadata kan användas för att spåra, segmentera eller integrera med externa system.

### Schemalägg utmaningen {#schedule}

Schemalägg utmaningen genom att välja ikonen ![](assets/do-not-localize/schedule-icon.svg) **[!UICONTROL Open schedule]** .

* **Startdatum och starttid**: Ange när utmaningen blir tillgänglig för kunder (format: mm/dd/åååå, —:— AM/PM).

* **Slutdatum och sluttid**: Ange när utmaningen upphör att gälla och acceptera inte längre nya slutföranden (format: mm/dd/yyyy, —:— AM/PM).

* **Tidszon**: Utmaningen använder mottagarens lokala tidszon som standard.

* **Aktiviteter måste slutföras**: Välj när kunder kan slutföra uppgifter:

   * **[!UICONTROL Any time during challenge]**: Kunder kan slutföra uppgifter när som helst mellan utmaningens start- och slutdatum
   * **[!UICONTROL During specific hours of the day]**: Begränsa aktivitetsslutförandet till specifika dagliga timmar genom att ange **[!UICONTROL Start Time]** och **[!UICONTROL End Time]**

Utfrågningsschemat har konfigurerats. Nu kan du lägga till de uppgifter som kunderna behöver för att slutföra.

### Lägga till uppgifter {#add-tasks}

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar. Du konfigurerar uppgiftstyper (inköp, utgifter, besök, engagemang, anpassade händelser), kvantiteter, produktfilter och belöningar.

Beroende på vilken typ av utmaning du har kan kunderna utföra olika uppgifter på olika sätt:

* **Standardutmaningar**: Slutför ett angivet antal uppgifter i valfri ordning
* **Utmaningar för strömning**: Slutför samma uppgift flera gånger i följd
* **Sekventiella utmaningar**: Slutför uppgifter i en definierad ordning

Så här lägger du till uppgifter i en utmaning:

1. Välj **[!UICONTROL Tasks]** i avsnittet **[!UICONTROL Add task]**.

   ![](assets/challenge-create-add-task.png)

1. Aktivitetslagret öppnas. Markera en eller flera uppgifter i listan och välj **[!UICONTROL Add]**. Om du vill skapa en ny uppgift väljer du **[!UICONTROL New]**.

   Detaljerade instruktioner om hur du skapar och konfigurerar uppgifter finns i [Skapa uppgifter](create-tasks.md).

1. I avsnittet **[!UICONTROL Task completion requirement]** anger du när utmaningen ska anses vara slutförd:

   * **[!UICONTROL Customer chooses 1 task to complete]**: Kunden kan välja och slutföra vilken uppgift som helst från utmaningen för att få belöningar
   * **[!UICONTROL Customer completes specific number of tasks]**: Kunden måste slutföra ett definierat antal uppgifter. Ange det antal slutförda uppgifter som krävs.

1. Som standard tillåter utmaningar kunderna att slutföra uppgifter över flera transaktioner. Om du vill att alla uppgifter ska slutföras i en enda transaktion markerar du ikonen ![](assets/do-not-localize/settings-icon.svg) **[!UICONTROL Settings]** och växlar till alternativet **[!UICONTROL Single transaction]**.

   ![](assets/challenge-create-single-transaction.png)

### Konfigurera belöningar {#rewards}

Belöningar är de förmånspoäng eller fördelar kunderna får för att klara av utmaningar. Konfigurera hur och när belöningar ska levereras för att motivera kundernas deltagande.

1. I listrutan **[!UICONTROL Reward delivery]** väljer du när belöningar ska levereras:

   * **[!UICONTROL Deliver rewards when challenge is completed]**: Betala alla belöningar när kunden slutför hela utmaningen
   * **[!UICONTROL Deliver rewards at task completion milestones as challenge progress is made]**: Utmärkelsen belönas stegvis när kunderna utför enskilda uppgifter (endast tillgängligt när utmaningen kräver att fler än en uppgift slutförs)

1. Välj belöningsleverantör i listrutan. Det här är er lojalitetslösning som hanterar kundpoäng och belöningar.

1. Konfigurera belöningsbeloppen baserat på vald leveransmetod:

   +++Leverera belöningar när utmaningen är klar

   I fältet **Antal [lojalitetspunkter] vid slutförande av utmaning** anger du det totala belöningsbeloppet som ska ges när kunden slutför hela utmaningen.

   Fältnamnet visar namnet på dina förmånspunkter enligt definitionen i den valda providern. Om din leverantör t.ex. använder&quot;Lumapunkter&quot; visas&quot;Antal lumapunkter vid provkörning&quot; i fältet.

   ![](assets/challenge-create-reward-total.png)

   **Exempel**: I skärmbilden ovan tilldelas kunderna 100 poäng när de slutför utmaningen.

   +++

   +++Leverera belöningar vid milstolpar för slutförande av uppgifter

   Ange belöningsbelopp för milstolpar för slutförande av uppgift. Med det här alternativet kan ni skapa progressiva belöningar som ökar kundens motivation när de går igenom utmaningen.

   För varje uppgift där du vill ge en belöning aktiverar du belöningsalternativet och anger hur många poäng som ska belönas när kunderna slutför den specifika uppgiften. Du kan välja att belöna endast vissa slutförda uppgifter. Om du t.ex. har 10 uppgifter kanske du bara belönar uppgifter 1, 5 och 10.

   ![](assets/challenge-create-reward-milestones.png)

   **Exempel**: I skärmbilden ovan tilldelas kunderna 10 poäng när de slutför den första aktiviteten och sedan 50 ytterligare poäng när den andra aktiviteten har slutförts, vilket ger totalt 60 poäng när utmaningen är klar.

   >[!TIP]
   >
   >Överväg att öka belöningsvärdet för senare uppgifter för att behålla kundengagemanget under hela utmaningen.

   +++

Utmaningsstrukturen är nu konfigurerad med uppgifter och belöningar. Nu kan du designa innehållskorten för att visa utmaningen för kunderna.

## Konfigurera innehållskort {#configure-content-cards}

Innehållskort ger en visuell representation av utmaningen på kundenheter och visar utmaningsinformation, framsteg och belöningar. Läs mer om [innehållskort](../content-card/create-content-card.md).

Så här konfigurerar du innehållskort för din utmaning:

1. Gå till fliken **[!UICONTROL Content]** i utmaningsredigeraren.

1. Ange **[!UICONTROL Name]** som innehållskort.

1. Välj associerad **[!UICONTROL Channel configuration]**. Kanalkonfigurationer definierar hur och var innehållet levereras till kunderna. Mer information finns i [Kanalkonfigurationer](../configuration/channel-surfaces.md).

1. Välj **[!UICONTROL Edit content]** om du vill designa ditt innehållskort.

   ![](assets/challenge-create-content.png)

Mer information om hur du utformar och anpassar innehållskort finns i [Skapa innehållskort](../content-card/design-content-card.md).

Innehållskortet är nu konfigurerat. Nu kan ni konfigurera meddelanden för att engagera kunderna under hela provperioden.

### Konfigurera meddelanden {#configure-messaging}

Skapa flerkanalsmeddelanden för att engagera kunderna i viktiga stadier av utmaningens livscykel.

1. Navigera till fliken **[!UICONTROL Messaging]**.

1. Konfigurera meddelanden för varje livscykelsteg:

   ![](assets/challenge-create-messaging.png)

   * **Startmeddelanden**: Meddela kunderna när utmaningen startar och ange inledande information
   * **Pågående meddelanden**: Håll kunderna engagerade under utmaningen med påminnelser, förloppsuppdateringar och uppmuntran att fortsätta
   * **Slutförandemeddelanden**: Fira lyckade, bekräfta belöningsallokering och föreslå nästa utmaningar eller åtgärder

1. För varje fas väljer du **[!UICONTROL Add *stage *message]**för att skapa ett meddelande för den scenen.

1. Välj önskad kanal: **[!UICONTROL In-app]**, **[!UICONTROL Email]** eller **[!UICONTROL Push notification]** och välj den associerade kanalkonfigurationen.

1. Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Edit]** för att utforma meddelandeinnehållet.

   Mer information om hur du skapar meddelanden för specifika kanaler finns i:

   * [Dokumentation för meddelanden i appen](../in-app/get-started-in-app.md)
   * [Dokumentation för e-postmeddelanden](../email/get-started-email.md)
   * [Dokumentation för push-meddelanden](../push/get-started-push.md)

1. Upprepa dessa steg för varje scen och kanal efter behov.

Meddelandekonfigurationen är nu klar. Nu kan ni definiera vilka kunder som är berättigade att delta i utmaningen.

## Välj den utmanande målgruppen {#audience}

Definiera vilka kunder som är berättigade att delta i er lojalitetsutmaning.

1. Navigera till fliken **[!UICONTROL Audience]** och klicka på knappen **[!UICONTROL Select audience]**.

   ![](assets/challenge-create-audience.png)

1. Alla tillgängliga Adobe Experience Platform-målgrupper visas. Välj önskad målgrupp i listan.

1. Välj **[!UICONTROL Add audience]** för att bekräfta ditt val.

Utmaningskonfigurationen är nu klar. Nu kan ni skapa den resa som kommer att leda till utmanande leveranser.

## Generera och aktivera resan {#review-and-publish}

När din utmaningskonfiguration är klar kan du generera den tillhörande resan som kommer att samordna utmaningsleveransen och kundinteraktionerna. Välj **[!UICONTROL Generate Journey]** om du vill göra det.

![](assets/challenge-create-generate-journey.png)

Journey Optimizer skapar automatiskt en [resa](../building-journeys/journey-gs.md) med statusen Utkast. Den automatiskt genererade resan visas i kundresearkivet med namnformatet Utmaning: [Utmaningsnamn].

Granska resekonfigurationen om det behövs och [aktivera resan](../building-journeys/publish-journey.md) för att göra utmaningen tillgänglig för kunderna.

Resan startar automatiskt på det angivna startdatumet för utmaningen och levererar innehåll och meddelanden enligt din konfiguration.

>[!NOTE]
>
>Den automatiskt genererade resan kan anpassas om det behövs för att lägga till ytterligare logik eller meddelanden. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen. Om du redigerar utmaningen senare kommer eventuella anpassningar av resan att gå förlorade när resan återskapas.

## Nästa steg {#next-steps}

* [Hantera utmaningar](manage-challenges.md) - Lär dig redigera, övervaka och optimera utmaningar
* [Förstå lojalitetsutmaningar](get-started.md) - Granska funktioner och funktioner
