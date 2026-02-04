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
source-git-commit: e98fe328b5a72a7091d48b5e2939a24e4ad6954c
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 0%

---


# Skapa utmaningar {#create-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* **Skapa utmaningar** ◀ }︎ **Du är här** - Bygg och konfigurera utmaningar
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_loyalty_create_challenge"
>title="Skapa en lojalitetsutmaning"
>abstract="Skapa en lojalitetsutmaning för att definiera engagemangserbjudandet, konfigurera innehållskort för leverans, lägga till uppgifter, konfigurera belöningar och (valfritt) konfigurera meddelanden över olika kanaler."

## Innan du börjar {#before-you-start}

Innan du skapar en utmaning måste du se till att du har:

* Konfigurerad och validerad datainmatning via källanslutningar
* Skapade alla målgrupper som krävs i Experience Platform
* Förberett innehåll (bilder, text osv.) för din utmaning
* Definierade de uppgifter och belöningar du vill erbjuda

## Skapa en utmaning {#create-a-challenge}

Detaljerade steg för att skapa utmaningar:
* Konfiguration av utmaningsegenskaper
* Utmaningstyper (Standard, Streak, Sequential)
* Målgruppsval
* Datumkonfiguration

## Lägga till uppgifter {#add-tasks}

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

## Konfigurera innehållskort {#configure-content-cards}

Detaljerade anvisningar om hur du konfigurerar innehållskort, inklusive:
* Inställning av innehållskort
* Design och personalisering
* Förhandsgranska och testa

## Konfigurera meddelanden {#configure-messaging}

Detaljerade anvisningar om hur du konfigurerar meddelanden i flera kanaler, inklusive:
* Meddelandekanaler (i appen, e-post, push)
* Meddelandefaser (start, pågående, slutförd)
* Tidsinställning och utlösare för meddelanden

## Granska och publicera {#review-and-publish}

Innan du publicerar din utmaning:

1. **Granska alla komponenter**: Utmaningsegenskaper, uppgifter, belöningar, innehåll, meddelanden
2. **Testa upplevelsen**: Använd testprofiler för att validera innehåll och aktivitetsutlösare
3. **Publicera**: Gör utmaningen aktiv för målgruppen

Den automatiskt genererade resan aktiveras på det angivna startdatumet.

## Nästa steg {#next-steps}

* [Hantera utmaningar](manage-challenges.md) - Lär dig redigera, övervaka och optimera utmaningar
* [Förstå lojalitetsutmaningar](get-started.md) - Granska funktioner och funktioner
