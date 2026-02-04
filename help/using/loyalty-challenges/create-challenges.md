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
source-git-commit: e978d075efbbcb42e7500d921bd8cc3ed1eee890
workflow-type: tm+mt
source-wordcount: '1430'
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

1. Välj fliken **[!UICONTROL Challenges]** och välj **[!UICONTROL Create Challenge]**.

   ![](assets/challenge-create.png)

1. Välj typen av utmaning:

   * **[!UICONTROL Standard]**: Kunderna utför ett angivet antal uppgifter i valfri ordning
   * **[!UICONTROL Streak]**: Kunder slutför samma uppgift flera gånger i följd
   * **[!UICONTROL Sequential]**: Kunder slutför uppgifter i en definierad ordning

## Konfigurera utmaningsstrukturen {#structure}

På fliken Struktur definierar du hur utmaningen ska ordnas: egenskaper, schema, uppgifter som ska slutföras och belöningar som ska tilldelas.

### Definiera utmaningsegenskaperna och använd anpassade metadata {#properties}

1. Definiera utmaningsinställningarna i rutan Utmaningsegenskaper:

   ![](assets/challenge-create-properties.png)

   **Namn**: Ange ett beskrivande namn för utmaningen. Det här namnet visas i listan över utmaningar.

   **Beskrivning**: Ange en beskrivning som förklarar syftet och målen med utmaningen.

1. Använd avsnittet **[!UICONTROL Custom metadata]** om du vill lägga till anpassade metadata med hjälp av nyckel/värde-par. Dessa metadata kan användas för att spåra, segmentera eller integrera med externa system.

### Schemalägg utmaningen {#schedule}

Konfigurera när utmaningen ska köras genom att välja ikonen ![](assets/do-not-localize/schedule-icon.svg) **[!UICONTROL Open schedule]**:

* **Startdatum och starttid**: Ange när utmaningen blir tillgänglig för kunder

* **Slutdatum och sluttid**: Ange när utmaningen upphör att gälla och accepterar inte längre nya slutföranden

* **Tidszon**: Utmaningen använder mottagarens lokala tidszon som standard

* **Aktiviteter måste slutföras**: Välj när kunder kan slutföra uppgifter:

   * **[!UICONTROL Any time during challenge]**: Kunder kan slutföra uppgifter när som helst mellan utmaningens start- och slutdatum
   * **[!UICONTROL During specific hours of the day]**: Begränsa aktivitetsslutförandet till specifika dagliga timmar genom att ange **[!UICONTROL Start Time]** och **[!UICONTROL End Time]**

Utfrågningsschemat har konfigurerats. Nu kan du lägga till de uppgifter som kunderna behöver för att slutföra.

### Lägga till uppgifter {#add-tasks}

Uppgifter definierar de specifika åtgärder som kunderna måste utföra för att få belöningar. Du kan konfigurera uppgiftstyper (inköp, utgifter), kvantiteter, produktfilter och andra attribut.

Beroende på vilken typ av utmaning du har kan kunderna utföra olika uppgifter på olika sätt:

* **Standardutmaningar**: Slutför ett angivet antal uppgifter i valfri ordning\
  *Exempel: Slutför 3 av 5 uppgifter - gör ett köp, skriv en recension, referera till en vän, dela på sociala medier eller uppdatera profilen*

* **Utmaningar för strömning**: Slutför samma uppgift flera gånger i följd\
  *Exempel: Gör ett köp under 7 dagar i följd för att få bonusbelöningar*

* **Sekventiella utmaningar**: Slutför uppgifter i en definierad ordning\
  *Exempel: Gör först ett köp, skriv en recension och dela sedan på sociala medier - aktiviteterna måste slutföras i just den här sekvensen*

Så här lägger du till uppgifter i en utmaning:

1. Välj **[!UICONTROL Tasks]** i avsnittet **[!UICONTROL Add task]**.

   ![](assets/challenge-create-add-task.png)

1. Aktivitetslagret öppnas. Markera en eller flera uppgifter i listan och välj **[!UICONTROL Add]**. Om du vill skapa en ny uppgift väljer du **[!UICONTROL New]**.

   [Lär dig hur du skapar och konfigurerar uppgifter](create-tasks.md).

1. I avsnittet **[!UICONTROL Task completion requirement]** anger du när utmaningen anses vara slutförd:

   * **[!UICONTROL Customer chooses 1 task to complete]**: Kunder kan välja och slutföra vilken uppgift som helst för att få belöningar
   * **[!UICONTROL Customer completes specific number of tasks]**: Kunderna måste slutföra ett definierat antal uppgifter. Ange önskat nummer.

1. Som standard tillåter utmaningar kunderna att slutföra uppgifter över flera transaktioner. Om du vill att alla uppgifter ska slutföras i en enda transaktion markerar du ikonen ![](assets/do-not-localize/settings-icon.svg) **[!UICONTROL Settings]** och växlar till alternativet **[!UICONTROL Single transaction]**.

   ![](assets/challenge-create-single-transaction.png)

### Konfigurera belöningar {#rewards}

Belöningar är de förmånspoäng eller fördelar kunderna får för att klara av utmaningar. Konfigurera när och hur belöningar levereras.

1. I listrutan **[!UICONTROL Reward delivery]** väljer du när du vill leverera belöningar:

   * **[!UICONTROL Deliver rewards when challenge is completed]**: Utmärkelsebelöningar när kunderna slutför hela utmaningen
   * **[!UICONTROL Deliver rewards at task completion milestones as challenge progress is made]**: Utmärkelsen belönas stegvis när kunderna utför enskilda uppgifter (endast tillgängligt för utmaningar som kräver mer än en uppgift)

1. Välj **[!UICONTROL Reward provider]** i listrutan. Det här är er lojalitetslösning som hanterar kundpoäng och belöningar.

1. Konfigurera belöningsbeloppen baserat på vald leveransmetod:

   +++Leverera belöningar när utmaningen är klar

   I fältet **Antal [lojalitetspunkter] vid slutförande av utmaning** anger du det totala belöningsbeloppet som ska ges när kunderna slutför hela utmaningen.

   Fältnamnet visar namnet på dina förmånspunkter enligt definitionen i den valda providern. Om din leverantör t.ex. använder&quot;Lumapunkter&quot; visas&quot;Antal lumapunkter vid provkörning&quot; i fältet.

   ![](assets/challenge-create-reward-total.png)

   **Exempel**: Kunder tilldelas 100 poäng när de slutför utmaningen.

   +++

   +++Leverera belöningar vid milstolpar för slutförande av uppgifter

   Ange belöningsbelopp för milstolpar för slutförande av uppgift. Med det här alternativet kan ni skapa progressiva belöningar som ökar kundens motivation när de går igenom utmaningen.

   För varje uppgift där du vill ge en belöning aktiverar du belöningsalternativet och anger hur många poäng som ska belönas när kunderna slutför den specifika uppgiften. Du kan välja att belöna endast vissa slutförda uppgifter. Om du t.ex. har 10 uppgifter kanske du bara belönar uppgifter 1, 5 och 10.

   ![](assets/challenge-create-reward-milestones.png)

   **Exempel**: Kunderna får 10 poäng när de slutför den första uppgiften, och sedan 50 ytterligare poäng när den andra uppgiften är slutförd, vilket ger totalt 60 poäng.

   >[!TIP]
   >
   >Överväg att öka belöningsvärdet för senare uppgifter för att behålla kundengagemanget under hela utmaningen.

   +++

>[!NOTE]
>
>Lojalitetsutmaningar inkluderar inte ett inbyggt redovisningssystem för att spåra belöningssaldon. Se till att din belöningsleverantör hanterar punktspårning och inlösen.

Utmaningsstrukturen är nu konfigurerad med uppgifter och belöningar. Nu kan du designa innehållskorten för att visa utmaningen för kunderna.

## Konfigurera innehållskort {#configure-content-cards}

Innehållskort utgör en visuell utmaning på kundenheter och visar information om utmaningar, framsteg och belöningar. [Läs mer om innehållskort](../content-card/create-content-card.md).

Så här konfigurerar du innehållskort för din utmaning:

1. Navigera till fliken **[!UICONTROL Content]**.

1. Ange **[!UICONTROL Name]** som innehållskort.

1. Markera **[!UICONTROL Channel configuration]**. Kanalkonfigurationer innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer om kanalkonfigurationer](../configuration/channel-surfaces.md).

1. Välj **[!UICONTROL Edit content]** om du vill designa ditt innehållskort.

   ![](assets/challenge-create-content.png)

[Lär dig hur du utformar och anpassar innehållskort](../content-card/design-content-card.md).

Innehållskortet är nu konfigurerat. Nu kan ni konfigurera meddelanden för att engagera kunderna under hela provperioden.

### Konfigurera meddelanden {#configure-messaging}

Skapa flerkanalsmeddelanden för att engagera kunderna i viktiga stadier av utmaningens livscykel. Meddelanden är valfria men rekommenderas för att maximera kundengagemanget.

1. Navigera till fliken **[!UICONTROL Messaging]**.

1. Konfigurera meddelanden för varje livscykelsteg:

   ![](assets/challenge-create-messaging.png)

   * **Starta**-meddelande: Meddela kunderna när utmaningen startar
   * **Pågående** meddelande: Håll kunderna engagerade med påminnelser och förloppsuppdateringar
   * **Slutförd** meddelande: Fira lyckade och bekräfta belöningsallokering

1. För varje fas väljer du **[!UICONTROL Add *stage *message]**för att skapa ett meddelande för den scenen.

1. Välj önskad kanal: **[!UICONTROL In-app]**, **[!UICONTROL Email]** eller **[!UICONTROL Push notification]** och välj den associerade kanalkonfigurationen.

1. Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Edit]** för att utforma meddelandeinnehållet.

   Lär dig hur du skapar meddelanden för specifika kanaler:

   * [Lär dig hur du skapar meddelanden i appen](../in-app/get-started-in-app.md)
   * [Lär dig hur du skapar e-postmeddelanden](../email/get-started-email.md)
   * [Lär dig hur du skapar push-meddelanden](../push/get-started-push.md)

1. Upprepa dessa steg för varje scen och kanal efter behov.

Meddelandekonfigurationen är nu klar. Nu kan ni definiera vilka kunder som är berättigade att delta i utmaningen.

## Välj den utmanande målgruppen {#audience}

Definiera vilka kunder som kan delta i er lojalitetsutmaning.

1. Navigera till fliken **[!UICONTROL Audience]** och välj **[!UICONTROL Select audience]**.

   ![](assets/challenge-create-audience.png)

1. Välj målgrupp i listan över tillgängliga Adobe Experience Platform-målgrupper.

1. Välj **[!UICONTROL Add audience]**.

Utmaningskonfigurationen är nu klar. Nu kan ni skapa den resa som kommer att leda till utmanande leveranser.

## Generera och aktivera resan {#review-and-publish}

När din utmaningskonfiguration är klar kan du generera den tillhörande resan som kommer att samordna utmaningsleveransen och kundinteraktionerna. Välj **[!UICONTROL Generate Journey]** om du vill göra det.

![](assets/challenge-create-generate-journey.png)

Journey Optimizer skapar automatiskt en [resa](../building-journeys/journey-gs.md) med statusen Utkast. Den automatiskt genererade resan visas i kundresearkivet med namnformatet Utmaning: [Utmaningsnamn].

Granska resekonfigurationen om det behövs och [aktivera resan](../building-journeys/publish-journey.md) för att göra utmaningen tillgänglig för kunderna.

Resan startar automatiskt på det angivna startdatumet för utmaningen och levererar innehåll och meddelanden enligt din konfiguration.

>[!NOTE]
>
>Den automatiskt genererade resan kan anpassas för att lägga till ytterligare logik eller meddelanden. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen. Om du redigerar utmaningen senare kommer eventuella anpassningar av resan att gå förlorade när resan återskapas.

## Nästa steg {#next-steps}

* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka och optimera dina utmaningar
