---
solution: Journey Optimizer
product: journey optimizer
title: Förstå lojalitetsutmaningar
description: Läs mer om lojalitetsfunktioner, arbetsflöden och funktioner i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: 419c7b3913ca4da50c69ed36ffc1a8c8520607b4
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---


# Förstå lojalitetsutmaningar {#understand-loyalty-challenges}

>[!CONTEXTUALHELP]
>id="ajo_loyalty_challenges_overview"
>title="Om lojalitetsutmaningar"
>abstract="Lojalitetsutmaningar gör att ni kan skapa personaliserade engagemangserbjudanden som motiverar kunderna att slutföra specifika åtgärder och få belöningar."

Med lojalitetsutmaningar kan ni utforma och driftsätta personaliserade engagemangserbjudanden som motiverar kunderna att slutföra specifika åtgärder och tjäna pengar.

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](gs-loyalty-challenges.md) - snabböversikt och nästa steg
* **Förstå lojalitetsproblem** {2 }︎ ◀Du är här **- Funktioner, arbetsflöde, förutsättningar**
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

## Översikt {#overview}

Lojalitetsutmaningar är en komplett lösning för att skapa storskaliga lojalitetsprogram, från att definiera uppgifter och milstolpar till att leverera innehåll och spåra prestanda i olika kanaler. Ni kan skapa tre olika typer av utmaningsupplevelser, konfigurera belöningar, skicka meddelanden i flera kanaler under viktiga livscykelsteg och övervaka prestanda via automatiskt genererade resor - allt med bibehållen integrering med ert externa lojalitetshanteringssystem.

## Så fungerar det {#how-it-works}

När du skapar och startar en lojalitetsutmaning följer du det här arbetsflödet:

1. **Ställ in datainmatning** - Konfigurera Experience Platform-källanslutningar (som Capillary) för att importera lojalitetshändelsedata som spårar kundaktiviteter och kundframsteg.

2. **Skapa en utmaning** - Definiera grundläggande utmaningsegenskaper, inklusive namn, typ (Standard, Streak eller Sequential), målgrupp och datumintervall.

3. **Lägg till aktiviteter** - Definiera de specifika åtgärder som kunder måste utföra, inklusive aktivitetstyper (inköp, utgifter, besök, osv.), kvantiteter, produktfilter och belöningar.

4. **Utforma innehållskort** - Skapa den visuella representationen av din utmaning med Journey Optimizer innehållskort som visas på kundenheter.

5. **Konfigurera meddelanden** (valfritt) - Konfigurera flerkanalsmeddelanden (i programmet, e-post, push) för nyckelstadier: start, pågående och slutförande.

6. **Granska och publicera** - Testa din utmaning med testprofiler och publicera den sedan för att göra den tillgänglig för målgruppen.

7. **Automatiskt genererad resa** - När du publicerar skapar Journey Optimizer automatiskt en resa som ordnar leverans av innehållskort och meddelanden.

8. **Aktivera resa** - Den automatiskt genererade resan aktiveras på startdatumet för din utmaning och hanterar alla kundinteraktioner.

9. **Övervaka prestanda** - Spåra deltagande, slutförandegrad, belöningsdistribution och meddelandeengagemang via inbyggda rapporter och arbetsytan.

>[!NOTE]
>
>Den automatiskt genererade resan visas i kundreseinventeringen och kan anpassas vid behov. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen.

## Viktiga funktioner {#key-capabilities}

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

### Inställning av datainmatning {#data-ingestion}

Lojalitetsutmaningar bygger på data som hämtas via Experience Platform källanslutningar för att spåra kundens framsteg och slutförande av uppgifter.

1. **Konfigurera en källanslutning som stöds**: För närvarande är den kapillära kopplingen allmänt tillgänglig. Ytterligare anslutningar planeras.

2. **Validera datainmatning**: Kontrollera att lojalitetshändelser och kunddata följer med till Experience Platform och är tillgängliga i Journey Optimizer.

Detaljerade instruktioner finns i:

* [Experience Platform-källdokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)
* [Konfigurera källanslutningar i Journey Optimizer](../start/get-started-sources.md)

### Nödvändiga behörigheter {#required-permissions}

Om du vill använda lojalitetsutmaningar måste du ha rätt behörigheter i Journey Optimizer. Kontakta administratören om du inte kan komma åt funktionen.

## Utmaningar om lojalitet {#access}

Så här kommer du åt lojalitetsutmaningar:

1. I Adobe Journey Optimizer väljer du **[!UICONTROL Loyalty challenges]** i den vänstra navigeringsmenyn.

2. I lagret Lojalitetsutmaningar visas alla befintliga utmaningar med information som:
   * Namn och beskrivning av utmaning
   * Status (utkast, live, stoppad osv.)
   * Utmaningstyp (Standard, Streak, Sequential)
   * Start- och slutdatum
   * Senaste ändringsdatum

3. Välj **[!UICONTROL Create challenge]** om du vill börja skapa en ny utmaning.

### Söka efter och filtrera problem {#search-filter}

Använd sök- och filtreringsfunktionerna för att snabbt hitta specifika utmaningar:

* **Sök**: Ange utmaningsnamn eller nyckelord i sökfältet
* **Filtrera efter status**: Utkast, Schemalagt, Live, Slutfört, Stoppat eller Arkiverat
* **Filtrera efter typ**: Utmaningar av standardtyp, strömning eller sekventiell typ
* **Filtrera efter datum**: Utmaningar inom ett visst datumintervall
* **Filtrera efter taggar**: Problem med att använda särskilda taggar

## Nästa steg {#next-steps}

Nu när ni förstår lojalitetsutmaningarna kan ni lära er hur ni skapar er första utmaning:

* [Skapa utmaningar](create-challenges.md)
* [Hantera utmaningar](manage-challenges.md)
