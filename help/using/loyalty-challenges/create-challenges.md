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
source-git-commit: f41c1ed8a2d9e74b9d8fe97e0bf9e565d326aec6
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 0%

---


# Skapa utmaningar {#create-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Få åtkomst till och hantera lojalitetsutmaningar](access-loyalty-challenges.md) - Hantering av inventeringar, utmaningar och uppgifter
* **Skapa utmaningar** ◀ &rbrace;︎ **Du är här** - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Skapa utmaningen {#create-the-challenge}

1. Navigera till **[!UICONTROL Loyalty Challenges (Beta)]** i Journey Optimizer.

1. Välj fliken **[!UICONTROL Challenges]** och välj **[!UICONTROL Create Challenge]**.

   ![](assets/challenge-create.png)

1. Välj typen av utmaning:

   * **[!UICONTROL Standard]**: Kunderna utför ett angivet antal uppgifter i valfri ordning\
     *Exempel: Slutför 3 av 5 tillgängliga uppgifter*

   * **[!UICONTROL Streak]**: Kunder slutför samma uppgift flera gånger i följd\
     *Exempel: Köp 7 dagar i följd*

   * **[!UICONTROL Sequential]**: Kunder slutför uppgifter i en definierad ordning\
     *Exempel: Inköp → Granska → Dela (måste slutföras i den här sekvensen)*

## Konfigurera utmaningsstrukturen {#structure}

På fliken **[!UICONTROL Structure]** definierar du hur utmaningen är organiserad: dess egenskaper, schema, uppgifter som ska slutföras och belöningar som ska levereras.

### Definiera utmaningsegenskaperna och använd anpassade metadata {#properties}

1. Definiera globala inställningar för utmaningen i rutan **[!UICONTROL Challenge properties]**:

   * **[!UICONTROL Name]**: Ange ett beskrivande namn för utmaningen. Det här namnet visas i listan över utmaningar.
   * **[!UICONTROL Description]**: Ange en beskrivning som förklarar syftet och målen med utmaningen.

   ![](assets/challenge-create-properties.png)

1. Använd avsnittet **[!UICONTROL Custom metadata]** om du vill lägga till anpassade metadata med hjälp av nyckel/värde-par. Dessa metadata kan användas för att spåra eller integrera med externa system.

### Schemalägg utmaningen {#schedule}

Konfigurera när utmaningen ska köras genom att välja ikonen ![](assets/do-not-localize/schedule-icon.svg) **[!UICONTROL Open schedule]**:

![](assets/challenge-create-properties.png)

* **[!UICONTROL Start date and time]**: Ange när utmaningen blir tillgänglig för kunder.
* **[!UICONTROL End date and time]**: Ange när utmaningen upphör att gälla och inte längre accepterar nya slutföranden.
   * **[!UICONTROL Time zone]**: Utmaningen använder mottagarens lokala tidszon som standard.
* **[!UICONTROL Tasks must be completed]**: Välj när kunder kan slutföra uppgifter:

   * **[!UICONTROL Any time during challenge]**: Kunder kan slutföra uppgifter när som helst mellan utmaningens start- och slutdatum.
   * **[!UICONTROL During specific hours of the day]**: Begränsa aktivitetsslutförandet till specifika dagliga timmar genom att ange **[!UICONTROL Start Time]** och **[!UICONTROL End Time]**.

Utfrågningsschemat har konfigurerats. Lägg sedan till de uppgifter kunderna behöver för att slutföra.

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

1. **[!UICONTROL Tasks Inventory]** öppnas. Markera en eller flera uppgifter i listan och välj **[!UICONTROL Add]**. Om du vill skapa en ny uppgift väljer du **[!UICONTROL New]**. [Lär dig hur du skapar och konfigurerar uppgifter](create-tasks.md).

1. I avsnittet **[!UICONTROL Task completion requirement]** anger du när utmaningen anses vara slutförd:

   * **[!UICONTROL Customer chooses 1 task to complete]**: Kunderna kan välja och slutföra vilken uppgift som helst för att få belöningar.
   * **[!UICONTROL Customer completes specific number of tasks]**: Kunderna måste slutföra ett definierat antal uppgifter.

1. Som standard tillåter utmaningar kunderna att slutföra uppgifter över flera transaktioner. Om du vill att alla uppgifter ska slutföras i en enda transaktion markerar du ikonen ![](assets/do-not-localize/settings-icon.svg) **[!UICONTROL Settings]** och aktiverar alternativet nedan.

   ![](assets/challenge-create-single-transaction.png)

När du har lagt till uppgifter i din utmaning kan du konfigurera belöningar som kunderna ska få för att slutföra dem.

### Konfigurera belöningar {#rewards}

Belöningar är de förmånspoäng eller fördelar kunderna får för att klara av utmaningar. Konfigurera när och hur belöningar levereras.

1. I listrutan **[!UICONTROL Reward delivery]** väljer du när du vill leverera belöningar:

   * **[!UICONTROL Deliver rewards when challenge is completed]**: Utmärkelsebelöningar när kunderna slutför hela utmaningen\
     *Exempel: Betala 100 poäng när du har slutfört alla fem aktiviteterna*

   * **[!UICONTROL Deliver rewards at task completion milestones as challenge progress is made]**: Utmärkelsen belönas stegvis när kunderna utför enskilda uppgifter (endast tillgängligt för utmaningar som kräver mer än en uppgift)\
     *Exempel: Ge 10 poäng efter uppgift 1, 20 poäng efter uppgift 2 och 50 poäng efter uppgift 3*

1. Välj belöningsleverantör. Det här är er lojalitetslösning som hanterar kundpoäng och belöningar.

1. Konfigurera belöningsbeloppen baserat på vald leveransmetod:

   +++Leverera belöningar när utmaningen är klar

   Ange det totala belöningsbeloppet som ska ges när kunderna slutför hela utmaningen.

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

När du har konfigurerat utmaningsstrukturen med uppgifter och belöningar kan du utforma innehållskorten så att de visar utmaningen för kunderna.

## Konfigurera innehållskort {#configure-content-cards}

Innehållskort utgör en visuell utmaning på kundenheter och visar information om utmaningar, framsteg och belöningar. [Läs mer om innehållskort](../content-card/create-content-card.md).

Så här konfigurerar du innehållskort för din utmaning:

1. Navigera till fliken **[!UICONTROL Content]** och ange en **[!UICONTROL Name]** för innehållskortet.

1. Markera **[!UICONTROL Channel configuration]**. Kanalkonfigurationer innehåller alla tekniska parametrar för att skicka meddelanden, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer om kanalkonfigurationer](../configuration/channel-surfaces.md).

1. Välj **[!UICONTROL Edit content]** om du vill designa ditt innehållskort. [Lär dig hur du utformar och anpassar innehållskort](../content-card/design-content-card.md).

   ![](assets/challenge-create-content.png)

När du har konfigurerat innehållskortet kan du konfigurera meddelanden för att engagera kunderna under hela provcykeln.

### Konfigurera meddelanden {#configure-messaging}

Skapa flerkanalsmeddelanden för att engagera kunderna i viktiga stadier av utmaningens livscykel. Meddelanden är valfria men rekommenderas för att maximera kundengagemanget.

1. Navigera till fliken **[!UICONTROL Messaging]** och konfigurera meddelanden för varje livscykelsteg:

   * **Starta**-meddelande: Meddela kunderna när utmaningen startar
   * **Pågående** meddelande: Håll kunderna engagerade med påminnelser och förloppsuppdateringar
   * **Slutförd** meddelande: Fira lyckade och bekräfta belöningsallokering

1. För varje fas väljer du **[!UICONTROL Add [stage] message]** (där [stage] representerar Starta, Pågår eller Slutfört) för att skapa ett meddelande för den scenen.

1. Välj önskad kanal: **[!UICONTROL In-app]**, **[!UICONTROL Email]** eller **[!UICONTROL Push notification]** och välj den associerade kanalkonfigurationen.

1. Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Edit]** för att utforma meddelandeinnehållet.

   ![](assets/challenge-create-messaging.png)

Lär dig hur du skapar meddelanden för specifika kanaler:

* [Meddelanden i appen](../in-app/get-started-in-app.md)
* [E-postmeddelanden](../email/get-started-email.md)
* [Push-meddelanden](../push/get-started-push.md)

När du är klar med meddelandekonfigurationen definierar du vilka kunder som är berättigade att delta i utmaningen.

## Välj den utmanande målgruppen {#audience}

Definiera vilka kunder som kan delta i er lojalitetsutmaning.

1. Navigera till fliken **[!UICONTROL Audience]** och markera knappen **[!UICONTROL Select audience]**.

   ![](assets/challenge-create-audience.png)

1. Välj målgrupp i listan över tillgängliga Adobe Experience Platform-målgrupper. [Lär dig arbeta med målgrupper](../audience/about-audiences.md).

1. Välj **[!UICONTROL Add audience]**.

Utmaningen är nu helt konfigurerad med sin struktur, sitt innehåll, sina meddelanden och sin målgrupp. Det sista steget är att generera och publicera resan.

## Generera och publicera resan {#review-and-publish}

Generera den resa som kommer att samordna er problemleverans och kundinteraktioner. Välj **[!UICONTROL Generate Journey]** om du vill göra det.

![](assets/challenge-create-generate-journey.png)

Journey Optimizer skapar automatiskt en [resa](../building-journeys/journey-gs.md) med statusen Utkast. Den automatiskt genererade resan visas i kundresearkivet med namnformatet Utmaning: [Utmaningsnamn].

![](assets/challenge-create-journey.png)

Granska konfigurationen av resan om det behövs och publicera sedan resan för att göra den tillgänglig för kunderna. [Lär dig publicera en resa](../building-journeys/publish-journey.md).

Resan startar automatiskt på det angivna startdatumet för utmaningen och levererar innehåll och meddelanden enligt din konfiguration.

>[!NOTE]
>
>Den automatiskt genererade resan kan anpassas för att lägga till ytterligare logik eller meddelanden. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen. Om du redigerar utmaningen senare kommer eventuella anpassningar av resan att gå förlorade när resan återskapas.
