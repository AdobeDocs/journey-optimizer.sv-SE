---
solution: Journey Optimizer
product: journey optimizer
title: Lojalitetsutmaningar
description: Lär dig hur du skapar och hanterar lojalitetsproblem i Adobe Journey Optimizer för att skapa engagerande lojalitetsprogram.
feature: Loyalty challenges
topic: Journeys
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
version: Journey Orchestration
source-git-commit: ee67a1a9270c12fdf199bc378deaa6006553533c
workflow-type: tm+mt
source-wordcount: '4742'
ht-degree: 0%

---


# Lojalitetsutmaningar {#loyalty-challenges}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst.

Med lojalitetsutmaningar kan ni skapa personaliserade engagemangserbjudanden för era kunder, så att ni kan samordna lojalitetsprogram i stor skala. Du kan utforma utmaningar med specifika uppgifter och milstolpar, belöna kunder för att de fyllt i dem och leverera upplevelsen via Adobe Journey Optimizer-kanaler.

>[!BEGINSHADEBOX]
>
>**I den här guiden:**
>
>* [Översikt](#overview) - Förstå vad lojalitetsutmaningar erbjuder
>* [Förutsättningar](#prerequisites) - Konfigurera datahämtning och behörigheter
>* [Åtkomst till lojalitetsproblem](#access) - Öppna menyn och visa problem
>* [Skapa utmaningar](#create-challenges) - Bygg nya lojalitetsutmaningar
>* [Skapa aktiviteter](#create-tasks) - Definiera vad kunder måste göra
>* [Hantera utmaningar](#manage-challenges) - Redigera, övervaka och optimera
>
>[!ENDSHADEBOX]

## Översikt {#overview}

Med lojalitetsutmaningar kan ni utforma och driftsätta personaliserade engagemangserbjudanden som motiverar kunderna att slutföra specifika åtgärder och tjäna pengar. Funktionen är en komplett lösning för att skapa storskaliga lojalitetsprogram, från att definiera uppgifter och milstolpar till att leverera innehåll och spåra prestanda i alla kanaler. Ni kan skapa tre olika typer av utmaningsupplevelser, konfigurera belöningar, skicka meddelanden i flera kanaler under viktiga livscykelsteg och övervaka prestanda via automatiskt genererade resor - allt med bibehållen integrering med ert externa lojalitetshanteringssystem.

## Viktiga funktioner

Använd lojalitetsutmaningar för att:

* **Skapa tre typer av utmaningar**:
   * **Standard**: Kunderna utför ett valfritt antal uppgifter för att få belöningar.
   * **Streak**: Kunderna utför samma uppgift flera gånger.
   * **Sekventiellt**: Kunder slutför uppgifter i en viss ordning.

* **Utmaningsinnehåll**: Använd Journey Optimizer-innehållskort för att skapa en visuell representation av din utmaning på kundenheter. Innehållskort visar information om utmaningar, framsteg och belöningar på kundens enhet.

* **Ange uppgiftskrav**: Definiera vad kunder måste göra för att få belöningar, inklusive:
   * Uppgiftstyper (inköp, utgiftsbelopp, besök osv.)
   * Kvantitetskrav
   * Inkluderingar/uteslutningar av produkter med SKU:er
   * Anpassade attribut och villkor

* **Konfigurera belöningar**: Definiera belöningar som kunder får när de har slutfört en uppgift eller när hela utmaningen har slutförts

* **Skicka meddelanden**: Leverera meddelanden i flera kanaler (i appen, e-post, push) i viktiga steg:
   * **Starta**: När utmaningen startar
   * **Pågår**: När kunderna är på väg genom
   * **Fullständigt**: När kunderna slutför utmaningen

* **Spåra prestanda**: Övervaka automatiskt genererade resor och granska provprestanda

### Viktiga begränsningar {#limitations}

* **Inget redovisningssystem**: Lojalitetsproblem spårar inte monetära värden eller punktsaldon. När kunderna genomför en utmaning och får en belöning, anropar Journey Optimizer ditt externa lojalitetshanteringssystem för att hantera punktallokering.

* **Endast målgruppsval**: Du kan välja befintliga målgrupper men inte skapa nya målgrupper från användargränssnittet för lojalitetsutmaningar.

## Förhandskrav {#prerequisites}

Innan du använder lojalitetsutmaningar måste du se till att du har:

* Inställning av datainmatning

  Lojalitetsutmaningar bygger på data som hämtas via Experience Platform källanslutningar för att spåra kundens framsteg och slutförande av uppgifter.

   1. **Konfigurera en källanslutning som stöds**: För närvarande är den kapillära kopplingen allmänt tillgänglig. Ytterligare anslutningar planeras.

   2. **Validera datainmatning**: Kontrollera att lojalitetshändelser och kunddata följer med till Experience Platform och är tillgängliga i Journey Optimizer.

  Detaljerade instruktioner finns i:

   * [Experience Platform-källdokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)
   * [Konfigurera källanslutningar i Journey Optimizer](../start/get-started-sources.md)

* Nödvändiga behörigheter {#required-permissions}

Om du vill använda lojalitetsutmaningar måste du ha rätt behörigheter i Journey Optimizer. Kontakta administratören om du inte kan komma åt funktionen.

## Utmaningar om lojalitet {#access}

Så här kommer du åt lojalitetsutmaningar:

1. I Adobe Journey Optimizer väljer du **[!UICONTROL Loyalty challenges]** i den vänstra navigeringsmenyn.

   <!--![Loyalty challenges menu in left navigation](assets/loyalty-challenges-menu.png)-->

2. I lagret Lojalitetsutmaningar visas alla befintliga utmaningar med information som:
   * Namn och beskrivning av utmaning
   * Status (utkast, live, stoppad osv.)
   * Utmaningstyp (Standard, Streak, Sequential)
   * Start- och slutdatum
   * Senaste ändringsdatum

   <!--![Loyalty challenges inventory showing list of challenges](assets/loyalty-challenges-inventory.png)-->

3. Välj **[!UICONTROL Create challenge]** om du vill börja skapa en ny utmaning.

### Söka efter och filtrera problem {#search-filter}

Använd sök- och filtreringsfunktionerna för att snabbt hitta specifika utmaningar:

#### Sök {#search}

Ange utmaningsnamn eller nyckelord för att hitta matchande utmaningar i fältet **[!UICONTROL Search]**.

#### Filtrera efter status {#filter-by-status}

Visa problem med specifika statusvärden i **[!UICONTROL Filter by status]**:

* Utkast
* Schemalagd
* Live
* Slutförd
* Stoppad
* Arkiverad

#### Filtrera efter typ {#filter-by-type}

Visa endast Standard, Streak eller Sequential-utmaningar med **[!UICONTROL Filter by type]**.

#### Filtrera efter datum {#filter-by-date}

Visa utmaningar inom ett visst datumintervall med **[!UICONTROL Filter by date]**.

#### Filtrera efter taggar {#filter-by-tags}

Visa problem med specifika taggar som används med **[!UICONTROL Filter by tags]**.

## Skapa utmaningar {#create-challenges}

Skapa en lojalitetsutmaning för att definiera engagemangserbjudandet, konfigurera innehållskort för leverans, lägga till uppgifter, konfigurera belöningar och (valfritt) konfigurera meddelanden över olika kanaler.

### Innan du börjar {#before-you-start}

Innan du skapar en utmaning måste du se till att du har:

* Konfigurerad och validerad datainmatning via källanslutningar
* Skapade alla målgrupper som krävs i Experience Platform
* Förberett innehåll (bilder, text osv.) för din utmaning
* Definierade de uppgifter och belöningar du vill erbjuda

### Skapa en utmaning {#create-a-challenge}

Så här skapar du en ny lojalitetsutmaning:

1. I Journey Optimizer väljer du **[!UICONTROL Loyalty challenges]** i den vänstra navigeringsmenyn.

2. Välj **[!UICONTROL Create challenge]** i det övre högra hörnet.

   <!--![Create challenge button in loyalty challenges inventory](assets/create-challenge-button.png)-->

3. Konfigurera följande på skärmen för utmaningsegenskaper:

#### Grundläggande egenskaper {#basic-properties}

**[!UICONTROL Name]**: Ange ett beskrivande namn för utmaningen. Det här namnet visas i lagret och inkluderas i det automatiskt genererade resenamnet.

**[!UICONTROL Description]**: (Valfritt) Lägg till en beskrivning som hjälper dig och ditt team att förstå syftet och detaljerna med den här utmaningen.

**[!UICONTROL Challenge type]**: Välj den typ av utmaning som du vill skapa:

* **[!UICONTROL Standard]**: Kunder kan utföra valfritt antal angivna uppgifter i vilken ordning som helst för att få belöningen. Exempel:&quot;Gör fem inköp den här månaden.&quot;

* **[!UICONTROL Streak]**: Kunder måste slutföra samma uppgift flera gånger. Exempel:&quot;Besök vår butik tio gånger i rad.&quot;

* **[!UICONTROL Sequential]**: Kunder måste slutföra uppgifter i en viss ordning. Exempel:&quot;Gör först ett köp, skriv sedan en recension och hänvisa sedan till en vän.&quot;

<!--![Challenge type selection showing Standard, Streak, and Sequential options](assets/challenge-type-selection.png)-->

**[!UICONTROL Start date]**: Välj när utmaningen blir aktiv och tillgänglig för kunder.

**[!UICONTROL End date]**: Välj när utmaningen upphör. Kunder som inte har slutfört utmaningen vid det här datumet kommer inte längre att kunna tjäna på belöningen.

#### Målgruppsval {#audience-selection}

**[!UICONTROL Select audience]**: Välj den målgrupp som är berättigad för den här utmaningen. Du kan bara välja befintliga målgrupper. Du kan inte skapa nya målgrupper från användargränssnittet för lojalitetsutmaningar.

Mer information om hur du skapar eller förfinar målgrupper finns i [Skapa målgrupper i Journey Optimizer](../audience/about-audiences.md).

&#x200B;4. Välj **[!UICONTROL Save as draft]** om du vill fortsätta konfigurera din utmaning.

## Skapa uppgifter {#create-tasks}

Uppgifter definierar de specifika åtgärder eller milstolpar som kunderna måste slutföra för att få belöningar i en lojalitetsutmaning. Ni kan konfigurera uppgiftstyper, kvantiteter, produktkrav och belöningsvärden för att skapa engagerande och personaliserade lojalitetsupplevelser.

### Uppgiftsöversikt {#task-overview}

Varje uppgift representerar en mätbar åtgärd som bidrar till att slutföra en utmaning. Beroende på vilken typ av utmaning du använder (Standard, Streak eller Sequential) utför kunderna olika uppgifter:

* **Standardutmaningar**: Kunderna utför ett angivet antal uppgifter i valfri ordning
* **Utmaningar**: Kunderna utför samma uppgift flera gånger i följd
* **Sekventiella utmaningar**: Kunderna slutför uppgifter i en definierad ordning

### Lägg till en uppgift {#add-task}

Så här lägger du till en uppgift i en utmaning:

1. Öppna din utmaning eller skapa en ny.

2. Navigera till avsnittet **[!UICONTROL Tasks]**.

   <!--![Tasks section in challenge creation interface](assets/tasks-section.png)-->

3. Välj **[!UICONTROL Add task]** eller **[!UICONTROL Create new task]**.

4. Konfigurera följande egenskaper på skärmen för att skapa uppgifter.

### Uppgiftsegenskaper {#task-properties}

#### Grundläggande aktivitetsinformation {#basic-info}

**[!UICONTROL Task name]**: Ange ett beskrivande namn för aktiviteten. Det här namnet är synligt för dig och ditt team, men det kanske inte visas för kunderna beroende på designen av ditt innehållskort.

**[!UICONTROL Task description]**: (Valfritt) Lägg till information om aktivitetens syfte eller krav.

**[!UICONTROL Task type]**: Välj vilken typ av åtgärd som kunder måste utföra. Tillgängliga uppgiftstyper är:

* **[!UICONTROL Purchase]**: Kunden gör en inköpstransaktion
* **[!UICONTROL Spend amount]**: Kunden spenderar ett angivet penningbelopp
* **[!UICONTROL Visit]**: Kunden besöker en fysisk plats eller en digital egenskap
* **[!UICONTROL Engagement]**: Kunden engagerar sig i innehåll, som att visa en video eller läsa en artikel
* **[!UICONTROL Custom event]**: Kunden utlöser en anpassad händelse som spåras genom ditt databehov

<!--![Task type selection dropdown showing available task types](assets/task-type-selection.png)-->

#### Kvantitetskrav {#quantity-requirements}

**[!UICONTROL Required quantity]**: Ange hur många gånger kunden måste utföra uppgiften för att slutföra den.

Exempel:

* För en köpuppgift:&quot;Köp 2 artiklar&quot; (kvantitet = 2)
* Aktivitet för ett utgiftsbelopp: &quot;Utgift $50&quot; (kvantitet = 50)
* För en besöksuppgift: &quot;Besök 5 gånger&quot; (kvantitet = 5)

**[!UICONTROL Tracking period]**: (Valfritt) Definiera tidsfönstret för att slutföra den här uppgiften:

* Varaktighet per utmaning (standard)
* Per dag
* Per vecka
* Per månad
* Anpassat datumintervall

### Produkt- och artikelfiltrering {#product-filtering}

För Inköp- och Utgiftsbeloppsuppgifter kan du ange vilka produkter som är kvalificerade för att slutföra uppgiften.

#### Inkluderingar {#product-inclusions}

Definiera vilka produkter eller kategorier som räknas för uppgiften:

1. Välj **[!UICONTROL Add product criteria]**.

   <!--![Add product criteria button in task configuration](assets/add-product-criteria.png)-->

2. Välj hur du vill definiera kvalificerande produkter:
   * **[!UICONTROL By SKU]**: Ange specifika produkt-SKU-koder
   * **[!UICONTROL By category]**: Välj produktkategorier från din katalog
   * **[!UICONTROL By attribute]**: Filtrera efter produktattribut som märke, storlek, färg eller anpassade attribut

3. Ange eller välj produktidentifierare:

   **Exempel - av SKU**:

   ```text
   SKU001, SKU002, SKU003
   ```

   **Exempel - Efter kategori**:

   * Beverages > Coffee
   * Bageri > Pasterier

   **Exempel - Efter attribut**:

   * Märke = &quot;Premium Brand&quot;
   * Kategori = &quot;Säsongsobjekt&quot;
   * Pris > $20

4. Välj **[!UICONTROL Add]** om du vill spara produktvillkoren.

#### Undantag för produkter {#product-exclusions}

Om du vill kan du exkludera specifika produkter från att räknas in i uppgiften:

1. Välj **[!UICONTROL Add exclusions]**.

2. Använd samma filtreringsmetoder som produktinkluderingar för att ange vilka produkter som ska uteslutas.

3. Vanliga uteslutningsscenarier:

   * Försäljning eller clearing
   * Presentkort
   * Kampanjartiklar eller gratisartiklar
   * Specifika varumärken eller kategorier

>[!NOTE]
>
>**Inkluderings- och exkluderingslogik**: När både inkludering och exkludering har definierats:
>
>* Produkterna måste matcha inkluderingskriterierna
>* Produkter som matchar exkluderingsvillkor tas bort, även om de matchar inkluderingar
>* Om inga inkluderingar definieras kvalificerar sig alla produkter utom de som uttryckligen exkluderas

#### Exempel på produktfiltrering {#product-filtering-examples}

##### Exempel 1: Kaffeutmaning {#example-1}

* Uppgiftstyp: Inköp
* Obligatorisk kvantitet: 3
* Innehåll: Kategori = &quot;Dragningar > kaffe&quot;
* Resultat: Kunden måste köpa 3 kaffedrycker

##### Exempel 2: Premiumutgifter {#example-2}

* Aktivitetstyp: Utgiftsbelopp
* Obligatorisk kvantitet: $100
* Innehåll: Varumärke = &quot;Premium Brand&quot;
* Undantag: Kategori = &quot;Godkännande&quot;
* Resultat: Kunden måste spendera 100 dollar på Premium Brand-artiklar, exklusive rensningsartiklar

##### Exempel 3: Specifikt produktinköp {#example-3}

* Uppgiftstyp: Inköp
* Obligatorisk kvantitet: 1
* Innehåll: SKU = &quot;NEWPRODUCT2024&quot;
* Resultat: Kunden måste köpa den specifika produkten med SKU &quot;NEWPRODUCT2024&quot;

### Konfigurera belöningar {#configure-rewards}

Definiera vad kunderna tjänar på att utföra uppgifter. Belöningar kan beviljas på aktivitetsnivå eller på utmaningsnivå när alla uppgifter är slutförda.

#### Belöningstidning {#reward-timing}

Välj när kunderna ska få belöningar:

**[!UICONTROL After task completion]**: Kunderna får en belöning omedelbart efter att ha slutfört den här specifika uppgiften (kallas även&quot;progressiva belöningar&quot; eller&quot;milstolpebelöningar&quot;).

**[!UICONTROL After challenge completion]**: Kunder får en belöning endast efter att ha slutfört alla nödvändiga uppgifter i utmaningen (kallas även&quot;final rewards&quot; eller&quot;grand prizes&quot;).

>[!TIP]
>
>Ni kan kombinera båda belöningstyperna i en enda utmaning för att upprätthålla engagemanget under hela kundresan. Exempel:
>
>* Ge 10 poäng efter varje avslutad åtgärd (progressiv belöning)
>* Ge ytterligare 100 poäng när du är klar med hela utmaningen (slutbelöning)

#### Belöningstyper och värden {#reward-types}

**[!UICONTROL Points]**: Betala lojalitet som poäng för kundens konto.

* Ange antalet punkter (t.ex. 100)
* Poäng skickas till ert externa lojalitetshanteringssystem via API

**[!UICONTROL Discount]**: Ange en rabattkod eller ett rabattvärde.

* Ange rabattyp (procent eller fast belopp)
* Ange rabattvärde
* Ange rabattkoden eller låt systemet generera en

**[!UICONTROL Free item]**: Bevilja en kostnadsfri produkt eller tjänst.

* Ange artikelns SKU eller beskrivning
* Ange hur den kostnadsfria artikeln ska tas i anspråk

**[!UICONTROL Custom reward]**: Definiera en anpassad belöningstyp.

* Ange belöningsbeskrivning
* Ange relevanta koder eller identifierare
* Konfigurera hur belöningen ska levereras eller tas i anspråk

#### Exempel på konfiguration av belöning {#reward-example}

**Utmaning**: &quot;Kaffe-övertäckningsutmaning&quot;

**Aktivitet 1**: Köp 3 kassetter

* Belöning: 30 poäng (10 poäng per kaffe)
* Timing: När aktiviteten har slutförts

**Aktivitet 2**: Prova 2 nya säsongsbaserade drycker

* Belöning: 50 poäng
* Timing: När aktiviteten har slutförts

**Resultatbelöning för utmaning**:

* Belöning: Kaffe utan extra kostnad + 100 poäng
* Timing: När alla uppgifter har slutförts

**Totalt antal möjliga belöningar**: 180 poäng + 1 fritt kaffe

### Avancerade uppgiftsattribut {#advanced-attributes}

För avancerade användningsområden kan du konfigurera ytterligare uppgiftsattribut:

**[!UICONTROL Custom conditions]**: Lägg till anpassad logik eller anpassade villkor utöver standarduppgiftstyper med Experience Platform-segment eller regler.

**[!UICONTROL Geofencing]**: (För besöksuppgifter) Kräv besök på specifika platser som definieras av geografiska koordinater och radie.

**[!UICONTROL Time-based requirements]**: Kräv att aktiviteter ska slutföras under specifika timmar, dagar eller datumintervall.

**[!UICONTROL Cooldown period]**: Ange en minsta tid mellan slutförda uppgifter för att förhindra snabba upprepade åtgärder.

**[!UICONTROL Task dependencies]**: (För sekventiella utmaningar) Definiera krav som måste slutföras innan den här aktiviteten blir tillgänglig.

## Konfigurera innehållskort {#configure-content-cards}

Innehållskort är det viktigaste sättet som utmaningar visas för kunderna på deras enheter. Du måste konfigurera ett innehållskort för din utmaning.

1. Navigera till fliken **[!UICONTROL Content]** i din utmaning.

2. Välj **[!UICONTROL Edit content]** för att öppna innehållskortsredigeraren.

   <!--![Content tab with Edit content button](assets/content-tab-edit.png)-->

3. Konfigurera egenskaperna för innehållskortet:

   **[!UICONTROL Configuration name]**: Ange ett namn för den här innehållskortkonfigurationen.

   **[!UICONTROL Configuration]**: Välj eller skapa en konfiguration för innehållskort. Detta definierar de tekniska inställningarna för hur innehållskortet levereras.

4. Utforma ett utmaningskort i innehållskortsredigeraren:

   * Lägg till text som beskriver utmaningen, arbetsuppgifterna och belöningarna
   * Inkludera bilder eller andra visuella element
   * Använd personalisering för att inkludera kundspecifik information
   * Visa förloppsindikatorer om tillämpligt
   * Lägg till call-to-action-knappar

   Innehållskortsredigeraren har samma funktioner som andra Journey Optimizer-kanaler. Mer information finns i [Utforma innehållskort](../content-card/design-content-card.md).

5. Välj **[!UICONTROL Save]** om du vill spara konfigurationen för ditt innehållskort.

>[!NOTE]
>
>Innehållskortet levereras via den automatiskt genererade resan. Det visas för behöriga målgruppsmedlemmar när utmaningen är aktiv.

## Konfigurera meddelanden {#configure-messaging}

Du kan också konfigurera meddelanden som ska skickas till kunder i viktiga stadier av utmaningens livscykel. Meddelanden finns för tre faser:

* **[!UICONTROL Launch]**: Skicka ett meddelande när utmaningen blir aktiv
* **[!UICONTROL In progress]**: Skicka ett meddelande när kunderna är på väg genom utmaningen
* **[!UICONTROL Complete]**: Skicka ett meddelande när kunderna har slutfört utmaningen

### Lägg till meddelanden {#add-messages}

1. Navigera till fliken **[!UICONTROL Messaging]** i din utmaning.

   <!--![Messaging tab showing Launch, In progress, and Complete stages](assets/messaging-tab-stages.png)-->

2. Välj den scen där du vill lägga till ett meddelande: Starta, Pågår eller Slutför.

3. Välj **[!UICONTROL Add message]**.

4. Välj kanal för meddelandet:
   * **[!UICONTROL In-app]**: Visa ett meddelande i programmet
   * **[!UICONTROL Email]**: Skicka ett e-postmeddelande
   * **[!UICONTROL Push]**: Skicka ett push-meddelande

5. Välj **[!UICONTROL Edit content]** om du vill öppna innehållsredigeraren för den valda kanalen.

6. Designa ditt meddelande med standardredigeraren:
   * Lägga till text, bilder och andra innehållselement
   * Använd personalisering för att inkludera kundspecifik information
   * Inkludera information om utmaningar som framsteg eller belöningar
   * Lägg till dynamiskt innehåll baserat på kundattribut eller beteenden

   Mer information om kanalspecifik vägledning finns i:
   * [Skapa meddelanden i appen](../in-app/create-in-app.md)
   * [Skapa e-postmeddelanden](../email/create-email.md)
   * [Skapa push-meddelanden](../push/create-push.md)

7. Välj **[!UICONTROL Save]** om du vill spara meddelandet.

8. Upprepa dessa steg om du vill lägga till meddelanden för andra stadier eller kanaler efter behov.

>[!NOTE]
>
>Ni kan lägga till flera meddelanden per scen, så att ni kan nå kunder i olika kanaler. Du kan till exempel skicka både ett e-postmeddelande och ett push-meddelande när en utmaning startar.

### Tidsinställning och utlösare för meddelanden {#message-timing}

**Startmeddelanden**: Skickas när utmaningen blir aktiv för den berättigade publiken.

**Pågående meddelanden**: Utlöses när kunderna når en angiven förloppspunkt. Du kan konfigurera utlösarvillkoren baserat på:

* Antal slutförda uppgifter
* Procentandel slutförda försök
* Specifika uppgifter slutförs
* Förfluten tid sedan utmaningen startades

**Slutförda meddelanden**: Skickas när kunderna har slutfört alla nödvändiga uppgifter.

>[!TIP]
>
>**Bästa tillvägagångssätt för meddelanden**:
>
>* Håll budskapen koncisa och fokuserade på utmaningen
>* Förmedla värdet och belöningarna tydligt
>* Använd enhetlig profilering och ton
>* Inkludera tydliga uppmaningar att vidta åtgärder
>* Testa meddelanden innan du publicerar din utmaning

## Generera och anpassa resor {#generate-journey}

När du sparar en utmaning med innehåll och meddelanden konfigurerat, genererar Journey Optimizer automatiskt en resa i bakgrunden.

### Så här fungerar generering av resor {#journey-generation-process}

1. När du sparar en utmaning och väljer **[!UICONTROL Generate journey]** skapar Journey Optimizer en ny resa.

2. Resan namnges automatiskt baserat på utmaningsnamnet (t.ex. &quot;Utmaning: [Utmaningsnamn]&quot;).

3. På arbetsytan kan du:
   * **[!UICONTROL Read audience]** aktivitet med den valda målgruppen
   * **Leveransåtgärd för innehållskort**
   * **Meddelandeaktiviteter** för alla meddelanden som du har konfigurerat (Starta, Pågår, Slutförd)
   * **Vänta** och **Villkor** aktiviteter efter behov baserat på din konfiguration

   <!--![Auto-generated journey canvas showing content card and message activities](assets/generated-journey-canvas.png)-->

4. Resan visas i ert researkiv och är synlig för alla användare med rätt behörigheter.

### Visa den genererade resan {#view-journey}

Så här visar du den automatiskt genererade resan:

1. Navigera till **[!UICONTROL Journeys]** på den vänstra navigeringsmenyn.

2. Sök efter resan efter utmaningsnamn eller filtrera efter taggar om du har tilldelat dem.

3. Välj resan för att visa arbetsytan och konfigurationen.

### Anpassa resan {#customize-journey}

Du kan redigera den automatiskt genererade resan för att lägga till anpassad logik, ytterligare aktiviteter eller avancerade konfigurationer.

>[!IMPORTANT]
>
>**Viktigt att tänka på när du redigerar resor**:
>
>* Ändringar som gjorts på arbetsytan **för resan synkroniseras inte tillbaka** till gränssnittet för lojalitetsutmaningar
>* Utmaningen fortsätter att vara källan till sanning för definitionen av kärnerfarenhet
>* En varning visas i Journey Optimizer när du aktiverar anpassat redigeringsläge
>* Om du behöver göra ändringar i uppgifter, belöningar eller viktiga utmaningsegenskaper kan du redigera dem i användargränssnittet för lojalitetsutmaningar, inte på resan
>* Anpassade ändringar av kundresan passar för avancerad routning, timing eller integreringslogik

Så här anpassar du resan:

1. Öppna den genererade resan från reseinventeringen.

2. Journey Optimizer visar en varning om anpassad redigering. Läs varningen noggrant och bekräfta den.

3. Gör önskade ändringar med arbetsytan för resan:
   * Lägg till ytterligare aktiviteter (väntar, villkor, åtgärder)
   * Konfigurera avancerade timings- eller frekvensregler
   * Lägg till anpassade åtgärder eller integreringar
   * Ändra villkor för målgruppsinmatning

4. Testa ändringarna noggrant före publicering.

5. Publicera resan när det passar.

Detaljerad vägledning om redigering av resor finns i [Bygg resor](../building-journeys/journey-gs.md).

### Om arbetsytan i resan {#journey-considerations}

När du arbetar med automatiskt genererade resor:

* **Det går inte att redigera målgrupp i resan**: Om du behöver ändra målgrupp gör du det i användargränssnittet för lojalitetsutmaningar och återskapar resan.

* **Meddelandeinnehållsuppdateringar**: Ändringar av meddelandeinnehåll bör göras i användargränssnittet för lojalitetsutmaningar för att bibehålla konsekvensen.

* **Resursstatus**: Resursstatusen (Utkast, Live, Stoppad) hanteras oberoende av utmaningsstatusen.

* **Testa**: Testa hela utmaningsupplevelsen, inte bara resan, för att se till att alla komponenter fungerar tillsammans korrekt.

## Granska och publicera {#review-and-publish}

Innan du publicerar din utmaning:

1. **Granska alla komponenter**:
   * Utmaningsegenskaper och datum
   * Uppgifter och uppgiftskrav
   * Konfiguration av belöningar
   * Innehållskortsdesign
   * Meddelandeinnehåll och timing
   * Genererad resestruktur

2. **Testa upplevelsen**:
   * Använd testprofiler för att validera innehållsåtergivning
   * Kontrollera att aktiviteterna utlöses korrekt baserat på testdata
   * Verifiera logik för löneallokering
   * Testa meddelanden i alla konfigurerade kanaler
   * Granska reseutförandet med testmålgrupper

3. **Publicera din utmaning**:
   * Välj **[!UICONTROL Publish]** bland utmaningsegenskaperna när du är klar
   * Utmaningen blir aktiv på det angivna startdatumet
   * Den automatiskt genererade resan aktiveras
   * Berättigade målgruppsmedlemmar kan se och delta i utmaningen

## Hantera utmaningar {#manage-challenges}

När ni har skapat och publicerat lojalitetsutmaningar kan ni visa, redigera, övervaka och optimera dem för att säkerställa att de ger önskat resultat för ert lojalitetsprogram.

### Utmaningsstatus {#challenge-statuses}

Varje utmaning genomgår en livscykel som återspeglas av dess status:

**[!UICONTROL Draft]**: Utmaningen skapas eller redigeras, men publiceras ännu inte. Du kan göra ändringar i dina utkast.

**[!UICONTROL Scheduled]**: Utmaningen publiceras och blir aktiv på startdatumet. Kunder kan ännu inte se eller delta i schemalagda utmaningar.

**[!UICONTROL Live]**: Utmaningen är aktiv och kunder i den berättigade publiken kan se och delta i den. Den här statusen visas när det aktuella datumet ligger mellan start- och slutdatumet.

**[!UICONTROL Completed]**: Utmaningen har passerat sitt slutdatum eller så har alla mål uppfyllts. Kunderna kan inte längre delta, men ni kan visa historiska data och resultat.

**[!UICONTROL Stopped]**: Utmaningen stoppades manuellt innan den slutfördes. Kunderna kan inte längre delta. Om du vill återaktivera ett stoppat anrop måste du duplicera det och skapa en ny version.

**[!UICONTROL Archived]**: Utmaningen har arkiverats för organisatoriska syften. Arkiverade problem kan hämtas med hjälp av filter, men är dolda i standardvyn.

### Visa information om utmaning {#view-details}

Så här visar du detaljerad information om en utmaning:

1. Klicka på utmaningsnamnet i lagret eller välj menyn **[!UICONTROL More actions]** (tre punkter) och välj **[!UICONTROL View details]**.

   <!--![Challenge inventory with More actions menu highlighted](assets/challenge-more-actions.png)-->

2. Skärmen med information om utmaning visar:

   Fliken **[!UICONTROL Overview]**:
   * Grundläggande egenskaper (namn, beskrivning, typ, datum)
   * Aktuell status och livscykelinformation
   * Målgruppsinformation
   * Historik för att skapa och ändra

   Fliken **[!UICONTROL Tasks]**:
   * Lista över alla uppgifter i utmaningen
   * Uppgiftstyper, krav och villkor
   * Konfigurerade belöningar per uppgift

   Fliken **[!UICONTROL Content]**:
   * Konfiguration och förhandsgranskning av innehållskort
   * Visuell återgivning av hur utmaningen ser ut för kunderna

   Fliken **[!UICONTROL Messaging]**:
   * Konfigurerade meddelanden för stegen Starta, Pågår och Slutför
   * Kanaltilldelningar och förhandsgranskningar av innehåll

   Fliken **[!UICONTROL Performance]** (för Live och Slutfört-utmaningar):
   * Deltagandestatistik
   * Slutförandegrad
   * Belöningsfördelning
   * Statistik för meddelandeengagemang

### Redigera utmaningar {#edit-challenges}

Du kan redigera utmaningar beroende på deras aktuella status.

#### Redigera problem med utkast {#edit-draft}

För problem med statusen **[!UICONTROL Draft]**:

1. Klicka på utmaningsnamnet eller välj **[!UICONTROL Edit]** på Åtgärder-menyn.

2. Ändra någon aspekt av utmaningen:
   * Grundläggande egenskaper
   * Uppgifter och belöningar
   * Innehållskort
   * Meddelanden
   * Målgruppsval

3. Välj **[!UICONTROL Save as draft]** om du vill spara ändringar utan publicering eller **[!UICONTROL Publish]** om du vill aktivera utmaningen.

#### Redigera publicerade utmaningar {#edit-published}

För utmaningar som är **[!UICONTROL Scheduled]** eller **[!UICONTROL Live]**:

>[!IMPORTANT]
>
>**Effekter av redigering av live-utmaningar**: Ändringar av live-utmaningar kan påverka kunder som redan deltar. Tänk på följande innan du gör några ändringar:
>
>* Om du ändrar uppgiftskrav kan kundens förlopp bli ogiltigt
>* Om du ändrar belöningar kan det uppstå inkonsekvenser för kunder som redan har belönat
>* Målgruppsändringar kan utesluta kunder som tidigare varit berättigade
>* Innehållsändringarna visas omedelbart för kunderna
>
>Om du vill göra större ändringar bör du överväga att stoppa den aktuella utmaningen och skapa en ny version.

**Begränsad redigering för aktuella utmaningar**:

Du kan göra dessa ändringar av aktiva utmaningar utan att stoppa dem:

* Uppdatera utmaningsbeskrivning (intern)
* Ändra bilder och text på innehållskort
* Uppdatera meddelandeinnehåll
* Justera slutdatum (utöka endast, kan inte förkorta)
* Lägga till eller ändra taggar

**Ändringar som kräver utmaningsduplicering**:

Om du vill ändra dessa egenskaper måste du duplicera kontrollen och skapa en ny version:

* Utmaningstyp (Standard, Streak, Sequential)
* Uppgiftskrav och villkor
* Belöningsvärden och allokeringsregler
* Startdatum (för live-utmaningar)
* Målgrupp (större förändringar)

### Duplicera en utmaning {#duplicate-challenge}

När du duplicerar skapas en kopia av en befintlig utmaning som du kan ändra och publicera som en ny utmaning:

1. I lagret väljer du menyn **[!UICONTROL More actions]** (tre punkter) för den utmaning du vill duplicera.

2. Välj **[!UICONTROL Duplicate]**.

3. I dialogrutan Duplicera:
   * Ange ett nytt namn för den duplicerade utmaningen
   * Du kan också ändra beskrivningen
   * Välj om du vill kopiera målgruppsinställningar
   * Välj om du vill kopiera meddelandekonfigurationer

4. Välj **[!UICONTROL Duplicate]**.

5. Den duplicerade utmaningen öppnas i utkastläge, där du kan göra ändringar innan du publicerar.

**Vanliga dupliceringsscenarier**:

* Kör om en lyckad utmaning för en ny tidsperiod
* Skapa varianter av en utmaning för olika målgrupper
* Uppdatera uppgiftskrav eller belöningar för en ny version
* Återaktivera en stoppad eller slutförd utmaning

### Stoppa en utmaning {#stop-challenge}

Så här stoppar du en aktiv eller schemalagd utmaning före dess naturliga slutdatum:

1. Välj utmaning i lagret.

2. Välj **[!UICONTROL Stop challenge]** på Åtgärder-menyn.

3. Granska effekten i bekräftelsedialogrutan:
   * Kunder som deltar kan inte längre göra några framsteg
   * Kunder som har slutfört uppgifter men inte den fullständiga utmaningen får inte några slutbelöningar
   * Den associerade resan stoppas
   * Utmaningen kan inte startas om (måste dupliceras för att kunna återanvändas)

4. Bekräfta genom att välja **[!UICONTROL Stop]**.

>[!NOTE]
>
>**Stoppar jämfört med slutförande**: En stoppad utmaning avslutas för tidigt och följer inte den normala slutförandeprocessen. Kunderna får partiella belöningar som redan har tilldelats men inte är slutresultatet av en utmaning. Överväg att informera berörda kunder om det tidiga slutet.

### Arkivera utmaningar {#archive}

Arkivera slutförda eller stoppade utmaningar för att hålla ert lager organiserat:

1. Välj menyn **[!UICONTROL More actions]** (tre punkter) för utmaningen.

2. Välj **[!UICONTROL Archive]**.

3. Utmaningen övergår till arkiverad status och är dold från standardlagervyn.

Så här visar du arkiverade utmaningar:

1. Använd filtret **[!UICONTROL Status]** i lagret.

2. Välj **[!UICONTROL Archived]**.

3. Arkiverade utmaningar visas med samma information som aktiva utmaningar.

Så här avarkiverar du en utmaning:

1. Hitta den arkiverade utmaningen med filter.

2. Välj **[!UICONTROL Unarchive]** på Åtgärder-menyn.

3. Utmaningen återgår till sin tidigare status (Slutförd eller Stoppad).

### Ta bort utmaningar {#delete}

Ta bort utmaningar som inte längre behövs:

>[!IMPORTANT]
>
>**Borttagningen är permanent**: Det går inte att återställa borttagna problem. Ta bara bort utmaningar som du är säker på att du inte behöver i framtiden. Överväg arkivering i stället för att ta bort för att bevara historiska poster.

**Borttagningsregler**:

* Du kan bara ta bort utmaningar med statusen **[!UICONTROL Draft]**
* Utmaningar som publicerats, schemalagts, live eller slutförts kan inte tas bort
* Om du vill ta bort en publicerad utmaning måste du först stoppa den och sedan arkivera den

Så här tar du bort ett utkast:

1. Välj menyn **[!UICONTROL More actions]** (tre punkter) för utmaningen.

2. Välj **[!UICONTROL Delete]**.

3. Bekräfta borttagningen i bekräftelsedialogrutan.

## Bildskärmsprestanda {#monitor-performance}

Följ upp hur kunderna interagerar med era utmaningar med hjälp av inbyggda prestandamätningar.

### Prestandamått {#performance-metrics}

Fliken Prestanda visar viktiga mått för aktuella och slutförda utmaningar:

<!--![Performance metrics dashboard showing participation and completion data](assets/performance-metrics-dashboard.png)-->

**[!UICONTROL Participation metrics]**:

* **Totalt antal berättigade kunder**: Antal kunder i målgruppen
* **Registrerade kunder**: Antal kunder som visade eller interagerade med utmaningen
* **Registreringsfrekvens**: Procent berättigade kunder som registrerar sig
* **Aktiva deltagare**: Antal kunder som för närvarande gör framsteg

**[!UICONTROL Completion metrics]**:

* **Kunder som slutfört**: Antal kunder som slutfört alla aktiviteter
* **Slutförandefrekvens**: Procentandel registrerade kunder som slutförde utmaningen
* **Genomsnittlig slutförandetid**: Genomsnittlig tid från registrering till slutförande
* **Aktiviteter slutförda**: Totalt antal enskilda uppgifter som har slutförts för alla kunder

**[!UICONTROL Reward metrics]**:

* **Totalt antal distribuerade belöningar**: Summan av alla allokerade belöningar
* **Utmärkelser per typ**: Uppdelning efter poäng, rabatter, kostnadsfria artiklar osv.
* **Genomsnittlig belöning per kund**: Genomsnittligt belöningsvärde för deltagande kunder

**[!UICONTROL Engagement metrics]**:

* **Avvisningar av innehållskort**: Antal gånger som utmaningen visades
* **Klick på innehållskort**: Antal gånger som kunderna interagerat med utmaningskortet
* **Meddelandeleverans**: Antal meddelanden som skickats för faserna Starta, Pågår och Slutför
* **Meddelandeengagemang**: Öppna frekvenser, klickfrekvenser för meddelanden per fas och kanal

### Visa resultatrapporter {#view-reports}

Så här får du tillgång till detaljerade prestandadata:

1. Öppna utmaningen och gå till fliken **[!UICONTROL Performance]**.

2. Välj datumintervall för rapportering (I dag, Senaste 7 dagarna, Senaste 30 dagarna, Anpassat intervall).

3. Granska mätvärden efter:
   * **Översikt**: Sammanfattning av nyckeltal på hög nivå
   * **Tidslinje**: Prestandatender över tid
   * **Uppdelning**: Mätvärden segmenterade efter kundattribut, kanaler eller uppgifter

4. Exportera rapporter med knappen **[!UICONTROL Export]** för ytterligare analys.

### Övervaka den genererade resan {#monitor-journey}

Den automatiskt genererade resan innehåller värdefulla körningsdata:

1. Välj **[!UICONTROL View journey]** från utmaningsinformationen för att öppna den associerade resan.

2. Gå igenom följande på arbetsytan:
   * **Resursrapport**: Generell körningsstatistik
   * **Aktivitetsrapporter**: Prestanda för enskilda aktiviteter
   * **Mätvärden för in- och utträde**: Hur många kunder har gått in och avslutat
   * **Felloggar**: Eventuella körningsproblem eller fel

3. Använd övervakning av resan för att identifiera
   * Flaskhalsar där kunderna slutar svara
   * Tekniska problem som påverkar leveransen
   * Meddelandeprestanda per kanal
   * Optimeringsmöjligheter för timing

Detaljerad vägledning om reseövervakning finns i [Övervaka dina resor](../building-journeys/report-journey.md).

### Optimera utmaningarna {#optimize}

Använd prestandadata för att förbättra nuvarande och framtida utmaningar:

**[!UICONTROL Test variations]**: Skapa dubblettutmaningar med olika aktiviteter, belöningar eller meddelanden för att jämföra prestanda.

**[!UICONTROL Adjust timing]**: Ändra varaktighet för utmaning eller aktivitetsdeadlines baserat på slutförandemönster.

**[!UICONTROL Refine audience]**: Utöka eller begränsa urvalet av målgrupper baserat på engagemang och slutförandegrad.

**[!UICONTROL Update content]**: Uppdatera innehållskort och meddelanden för att behålla intresse och tydlighet.

**[!UICONTROL Reward optimization]**: Justera belöningsvärden för att balansera kostnad och deltagande.

**[!UICONTROL Task difficulty]**: Ändra uppgiftskraven om de är för enkla eller för svåra utifrån slutförandedata.

## Validering och testning av uppgifter {#validation-testing}

Innan du publicerar din utmaning ska du verifiera att uppgifterna är korrekt konfigurerade:

1. **Kontrollera aktivitetslogik**:
   * Verifiera att kvantitetskraven är realistiska
   * Kontrollera att produktfiltreringsvillkoren är korrekta
   * Bekräfta att belöningar är korrekt konfigurerade

2. **Testa med testprofiler**:
   * Skapa testprofiler som representerar olika kundscenarier
   * Skicka testhändelser via din pipeline för datainmatning
   * Verifiera att aktiviteterna utlöses korrekt
   * Bekräfta belöningar tilldelas som förväntat

3. **Granska datamappning**:
   * Se till att inkommande händelsedata mappas korrekt till uppgiftskraven
   * Verifiera att SKU:er, kategorier och attribut överensstämmer mellan källsystemet och Journey Optimizer
   * Testa kantfall (data saknas, ogiltiga värden osv.)

## Bästa praxis {#best-practices}

### Skapa problem

**Börja enkelt**: För den första utmaningen börjar du med en enkel standardutmaning för att bekanta dig med processen.

**Testa noggrant**: Testa alltid utmaningen med testprofiler och målgrupper innan du publicerar till din fullständiga kundbas.

**Tydlig kommunikation**: Se till att kunderna förstår vad de behöver göra, vad de kommer att tjäna och när de ska göra.

**Realistisk timing**: Ange lämpliga start- och slutdatum, så att kunderna får tillräckligt med tid för att slutföra utmaningen.

**Utmärkande belöningar**: Gör belöningar värdefulla och relevanta för er målgrupp för att öka deltagandet.

### Uppgiftskonfiguration

**Tydliga krav**: Gör uppgiftskraven tydliga och genomförbara. Undvik alltför komplicerade förhållanden.

**Lämplig svårighet**: Balansera aktivitetsproblem med belöningsvärde. Svårt att arbeta bör ge större belöningar.

**Noggrannhet vid produktfiltrering**: Dubbelkontrollera SKU:er, kategorier och attribut för att säkerställa korrekt produktmatchning.

**Progressiva belöningar**: Använd milstolpe-belöningar (efter slutförd uppgift) för att behålla kundengagemang under hela utmaningen.

**Flexibilitet**: För standardutmaningar kan du tillåta flexibilitet i hur kunder utför uppgifter för att anpassa olika beteenden och inställningar.

### Förvaltning och övervakning

**Regelbunden övervakning**: Kontrollera utmaningens prestanda minst en gång i veckan för att se om det finns problem att identifiera tidigt.

**Rensa namn**: Använd beskrivande namn som anger utmaningens syfte, målgrupp eller tidsperiod för enkel organisation.

**Använd taggar**: Använd konsekventa taggar för att kategorisera utmaningar efter kampanj, säsong, målgruppssegment eller andra relevanta attribut.

**Dokumentändringar**: Anteckna varför du har ändrat i utmaningar för framtida referens och inlärning.

**Arkivera konsekvent**: Arkivera slutförda utmaningar regelbundet för att hålla lagret hanterbart.

**Kommunicera ändringar**: Om du ändrar en aktiv utmaning ska du informera berörda kunder om ändringar som påverkar deras deltagande.

**Analysera efter slutförande**: Granska resultatet efter varje utmaning för att identifiera lärdomar för framtida utmaningar.

**Gradvis utrullning**: För nya utmaningstyper eller betydande ändringar bör du överväga att börja med en mindre publik före fullständig distribution.

**Versionskontroll**: Använd tydlig versionshantering i utmanarnamn när du skapar iterationer (t.ex.&quot;Holiday Challenge 2024 - v2&quot;).

## Felsökning {#troubleshooting}

**Utmaningen visas inte för kunder**:

* Verifiera att utmaningen har Live-status
* Kontrollera att kunderna är berättigade
* Bekräfta att konfigurationen för innehållskortet är korrekt
* Granska körningsloggarna för leveransproblem

**Låga deltagandefrekvenser**:

* Granska synlighet och tilltalande på innehållskortet
* Kontrollera att meddelanden tydligt förmedlar värde
* Se till att arbetsuppgifterna blir möjliga och att belöningarna är attraktiva
* Verifiera att målgruppsanpassning är lämplig

**Aktiviteter som inte utlöser**:

* Kontrollera att data har importerats korrekt från källanslutningar
* Kontrollera att händelseattributen matchar uppgiftskraven
* Granska målgruppsberättigande

**Utmärkelser som inte allokerar**:

* Bekräfta att belöningskonfigurationen är korrekt
* Verifiera anslutning till externt lojalitetshanteringssystem
* Kontrollera om det finns fel i belöningsleveransloggar

**Produktfiltrering fungerar inte**:

* Validera SKU-koder och kategorinamn
* Kontrollera att attributmappningen är korrekt
* Testa med exempelköpdata

**Resan genererar inte**:

* Bekräfta att all nödvändig konfiguration är slutförd
* Sök efter fel på fliken Meddelanden
* Kontrollera att innehållskortet är konfigurerat
* Granska systemfelloggar

**Prestandadata visas inte**:

* Tillåt tid för dataspridning (upp till 24 timmar)
* Verifiera att händelser spåras korrekt
* Kontrollera datainmatningsstatus
* Säkerställ att kunderna har börjat delta

## Beta feedback {#beta-feedback}

Under betaversionen är din feedback värdefull för att hjälpa oss att förbättra lojalitetsutmaningarna. Dela med dig av dina erfarenheter, frågor och förslag till din Adobe-representant eller via betaversionskanalerna som du får när du startar programmet.

## Relaterade ämnen {#related-topics}

* [Bygg målgrupper i Journey Optimizer](../audience/about-audiences.md)
* [Utforma innehållskort](../content-card/design-content-card.md)
* [Skapa meddelanden i appen](../in-app/create-in-app.md)
* [Skapa e-postmeddelanden](../email/create-email.md)
* [Skapa push-meddelanden](../push/create-push.md)
* [Bygg resor](../building-journeys/journey-gs.md)
* [Övervaka era resor](../building-journeys/report-journey.md)
* [Experience Platform-källdokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)
* [Konfigurera källanslutningar i Journey Optimizer](../start/get-started-sources.md)
