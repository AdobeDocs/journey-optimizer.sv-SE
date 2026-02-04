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
source-git-commit: 831809b4c1dd19fdaeeb646695f606c02ec21265
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---


# Skapa utmaningar {#create-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* **Skapa utmaningar** ◀ &rbrace;︎ **Du är här** - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Så fungerar det {#how-it-works}

<!-- SCHEMA: Visual workflow showing the 5 main steps with icons: Create challenge → Add tasks → Design content cards → Configure messaging → Review and publish -->

När du skapar och startar en lojalitetsutmaning följer du det här arbetsflödet:

1. **Skapa en utmaning** - Definiera grundläggande utmaningsegenskaper, inklusive namn, typ (Standard, Streak eller Sequential), målgrupp och datumintervall.

1. **Lägg till aktiviteter** - Definiera de specifika åtgärder som kunder måste utföra, inklusive aktivitetstyper (inköp, utgifter, besök, osv.), kvantiteter, produktfilter och belöningar.

1. **Utforma innehållskort** - Skapa den visuella representationen av din utmaning med Journey Optimizer innehållskort som visas på kundenheter.

1. **Konfigurera meddelanden** (valfritt) - Konfigurera flerkanalsmeddelanden (i programmet, e-post, push, SMS) för nyckelstadier: start, pågående och slutförande.

1. **Granska och publicera** - Testa din utmaning med testprofiler och publicera den sedan för att göra den tillgänglig för målgruppen.

## Skapa utmaningen {#create-challenge}

<!-- SCREENSHOT: Challenge creation screen showing challenge properties form with fields for name, type, audience, dates -->

Så här skapar du en ny lojalitetsutmaning:

1. Navigera till **[!UICONTROL Loyalty challenges]** i Journey Optimizer.

1. Klicka på fliken **[!UICONTROL Challenges]**.  

1. Välj **[!UICONTROL Create challenge]**.

1. Konfigurera utmaningsegenskaperna:

   **Utmaningsnamn**: Ange ett beskrivande namn för utmaningen. Det här namnet visas i utmaningslagret och hjälper dig att identifiera utmaningen.

   **Utmaningstyp**: Välj en av följande typer:
   * **[!UICONTROL Standard]**: Kunderna utför ett angivet antal uppgifter i valfri ordning
   * **[!UICONTROL Streak]**: Kunder slutför samma uppgift flera gånger i följd
   * **[!UICONTROL Sequential]**: Kunder slutför uppgifter i en definierad ordning

   **Målgrupp**: Välj det målgruppssegment som definierar vem som kan delta i den här utmaningen. Du måste skapa målgrupper i Experience Platform innan du kan skapa utmaningar. Mer information finns i [Kom igång med målgrupper](../audience/about-audiences.md).

   **Startdatum**: Ange när utmaningen blir tillgänglig för kunder.

   **Slutdatum**: Ange när utmaningen upphör att gälla och inte längre accepterar nya slutföranden.

<!-- VISUAL: Comparison table or diagram showing the three challenge types (Standard, Streak, Sequential) with examples of each -->

### Lägga till uppgifter {#add-tasks}

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar. Du konfigurerar uppgiftstyper (inköp, utgifter, besök, engagemang, anpassade händelser), kvantiteter, produktfilter och belöningar.

Beroende på vilken typ av utmaning du har kan kunderna utföra olika uppgifter på olika sätt:

* **Standardutmaningar**: Slutför ett angivet antal uppgifter i valfri ordning
* **Utmaningar för strömning**: Slutför samma uppgift flera gånger i följd
* **Sekventiella utmaningar**: Slutför uppgifter i en definierad ordning

Om du vill lägga till uppgifter i din utmaning väljer du **[!UICONTROL Add task]** i aktivitetsavsnittet och konfigurerar uppgiftsegenskaperna.

Detaljerade instruktioner om hur du skapar och konfigurerar uppgifter finns i [Skapa uppgifter](create-tasks.md).

### Konfigurera innehållskort {#configure-content-cards}

<!-- SCREENSHOT: Content cards configuration section in the challenge editor -->

Innehållskort ger en visuell representation av utmaningen på kundenheter och visar utmaningsinformation, framsteg och belöningar. Läs mer om [innehållskort](../content-card/create-content-card.md).

<!-- VISUAL: Example content card designs showing different states: challenge start, in-progress with progress bar, completion with reward -->

Så här konfigurerar du innehållskort för din utmaning:

1. Gå till avsnittet **[!UICONTROL Content cards]** i utmaningsredigeraren.

1. Välj **[!UICONTROL Create content card]** eller välj en befintlig mall.

1. Designa ditt innehållskort:
   * Lägga till bilder, text och märkeselement
   * Inkludera [personaliseringstoken](../personalization/personalization-syntax.md) för att visa kundspecifik information
   * Visa förloppsindikatorer för utmaning
   * Visa belöningar och incitament

1. Konfigurera när innehållskortet visas:
   * **Utmaningen startar**: Visa när utmaningen blir tillgänglig
   * **Pågår**: Visas medan kunderna aktivt deltar
   * **Slutförande**: Visa efter att kunderna har slutfört alla uppgifter

1. Förhandsgranska innehållskortet på olika enheter för att se om det visas korrekt.

1. Spara konfigurationen för innehållskortet.

Mer information om hur du utformar och anpassar innehållskort finns i [Skapa innehållskort](../content-card/design-content-card.md).

### Konfigurera meddelanden {#configure-messaging}

<!-- SCREENSHOT: Messaging configuration section showing the three lifecycle stages: Launch, In-progress, Completion -->

Skapa flerkanalsmeddelanden för att engagera kunderna i viktiga stadier av utmaningens livscykel.

<!-- VISUAL: Timeline diagram showing when each message type is sent during the challenge lifecycle -->

Så här konfigurerar du meddelanden för din utmaning:

1. Gå till avsnittet **[!UICONTROL Messaging]** i utmaningsredigeraren.

1. Konfigurera meddelanden för varje livscykelsteg:

   **Startmeddelanden** - Meddela kunderna när problemet börjar:
   * Välj kanaler: [In-app](../in-app/get-started-in-app.md), [email](../email/get-started-email.md), [push-meddelanden](../push/get-started-push.md) eller [SMS](../sms/get-started-sms.md)
   * Designa budskapet med probleminformation och call-to-action
   * Ange timing: Skicka omedelbart när en utmaning publiceras eller schemaläggs för en viss tid

   **Pågående meddelanden** - Håll kunderna engagerade under utmaningen:
   * Definiera utlösarvillkor (till exempel 50 % slutförande, specifik uppgift slutförd)
   * Skapa påminnelsemeddelanden för att uppmuntra fortsatt deltagande
   * Inkludera förloppsuppdateringar och nästa steg

   **Slutförandemeddelanden** - Fira lyckade och leverera belöningar:
   * Grattis till att kunderna slutfört denna utmaning
   * Bekräfta belöningsallokering
   * Ange instruktioner för att begära belöningar
   * Föreslå nästa utmaningar eller åtgärder

Mer information om hur du skapar meddelanden för specifika kanaler finns i:

* [Dokumentation för meddelanden i appen](../in-app/get-started-in-app.md)
* [Dokumentation för e-postmeddelanden](../email/get-started-email.md)
* [Dokumentation för push-meddelanden](../push/get-started-push.md)
* [Dokumentation för SMS](../sms/get-started-sms.md)

## Granska och publicera utmaningen {#review-and-publish}

<!-- SCREENSHOT: Review screen showing summary of challenge configuration with all components listed -->

Innan du publicerar din utmaning:

1. **Granska alla komponenter**: Verifiera utmaningsegenskaper, uppgifter, belöningar, innehållskort och meddelandekonfigurationer.

1. **Testa upplevelsen**: Använd [testprofiler](../test-approve/test-profiles.md) för att validera hur innehållskortet visas och aktivitetsutlösaren fungerar.

1. **Publicera**: Välj **[!UICONTROL Publish]** om du vill att utmaningen ska vara tillgänglig för målgruppen.

<!-- SCREENSHOT: Journeys inventory showing the auto-generated journey in Draft status with name format "Challenge: [Challenge Name]" -->

När du publicerar en fråga skapas automatiskt en [resa](../building-journeys/journey-gs.md) i utkaststatus i Journey Optimizer. Den automatiskt genererade resan visas i kundresearkivet med namnformatet Utmaning: [Utmaningsnamn].

Så här gör du utmaningen tillgänglig för kunderna:

1. Navigera till **[!UICONTROL Journeys]**-lagret i Journey Optimizer.

1. Leta reda på den automatiskt genererade resan (den kommer att ha&quot;Problem:&quot; som ett prefix i sitt namn).

1. [Aktivera resan](../building-journeys/publishing-the-journey.md).

Resan startar automatiskt på det angivna utmaningsstartdatumet.

>[!NOTE]
>
>Den automatiskt genererade resan visas i kundreseinventeringen och kan anpassas vid behov. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen.

## Nästa steg {#next-steps}

* [Hantera utmaningar](manage-challenges.md) - Lär dig redigera, övervaka och optimera utmaningar
* [Förstå lojalitetsutmaningar](get-started.md) - Granska funktioner och funktioner

