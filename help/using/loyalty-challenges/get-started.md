---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med lojalitetsutmaningar
description: Lär dig hur du skapar och hanterar lojalitetsproblem i Adobe Journey Optimizer för att skapa engagerande lojalitetsprogram.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: e98fe328b5a72a7091d48b5e2939a24e4ad6954c
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---


# Kom igång med lojalitetsutmaningar {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* **Kom igång med lojalitetsutmaningar** {2 }︎ ◀Du är här **- Översikt, arbetsflöde, förutsättningar**
* [Åtkomst till lojalitetsproblem](access-loyalty-challenges.md) - Lager och filtrering
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_loyalty_challenges_overview"
>title="Om lojalitetsutmaningar"
>abstract="Lojalitetsutmaningar gör att ni kan skapa personaliserade engagemangserbjudanden som motiverar kunderna att slutföra specifika åtgärder och få belöningar."

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst.

## Översikt {#overview}

Lojalitetsutmaningar är en komplett lösning för att skapa storskaliga lojalitetsprogram, från att definiera uppgifter och milstolpar till att leverera innehåll och spåra prestanda i olika kanaler. Ni kan skapa tre olika typer av utmaningsupplevelser, konfigurera belöningar, skicka meddelanden i flera kanaler under viktiga livscykelsteg och övervaka prestanda via automatiskt genererade resor - allt med bibehållen integrering med ert externa lojalitetshanteringssystem.

## Viktiga funktioner {#key-capabilities}

Använd lojalitetsutmaningar för att:

* **Skapa tre typer av utmaningar**:
   * **Standard**: Kunderna utför valfritt antal uppgifter för att få belöningar
   * **Strömma**: Kunder slutför samma uppgift flera gånger i följd
   * **Sekventiellt**: Kunder slutför uppgifter i en viss ordning

* **Utmaningsinnehåll**: Använd Journey Optimizer-innehållskort för att skapa en visuell representation av din utmaning på kundenheter. Innehållskort visar information om utmaningar, framsteg och belöningar.

* **Ange uppgiftskrav**: Definiera vad kunder måste göra för att få belöningar, inklusive:
   * Uppgiftstyper (inköp, utgiftsbelopp, besök, engagemang, anpassade händelser)
   * Kvantitetskrav
   * Inkluderingar/uteslutningar av produkter med SKU:er, kategorier eller attribut
   * Anpassade attribut och villkor

* **Konfigurera belöningar**: Definiera belöningar som kunder får när de har slutfört en uppgift (progressiva belöningar) eller efter att ha slutfört hela utmaningen (slutliga belöningar).

* **Skicka meddelanden i flera kanaler**: Leverera meddelanden i flera kanaler (i appen, e-post, push) i viktiga steg:
   * **Starta**: När utmaningen startar
   * **Pågår**: När kunderna är på väg genom
   * **Fullständigt**: När kunderna slutför utmaningen

* **Spåra prestanda**: Övervaka automatiskt genererade resor och granska utmaningsprestanda genom inbyggda rapporter.

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

## Förhandskrav {#prerequisites}

Innan du använder lojalitetsutmaningar måste du se till att du har:

### Inställning av datainmatning {#data-ingestion}

Lojalitetsutmaningar bygger på data som hämtas via Experience Platform källanslutningar för att spåra kundens framsteg och slutförande av uppgifter.

1. **Konfigurera en källanslutning som stöds**: För närvarande är den kapillära kopplingen allmänt tillgänglig. Ytterligare anslutningar planeras.

2. **Validera datainmatning**: Kontrollera att lojalitetshändelser och kunddata följer med till Experience Platform och är tillgängliga i Journey Optimizer.

Detaljerade instruktioner finns i:

* [Experience Platform-källdokumentation](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/home)
* [Konfigurera källanslutningar i Journey Optimizer](../start/get-started-sources.md)

### Nödvändiga behörigheter {#required-permissions}

Om du vill använda lojalitetsutmaningar måste du ha rätt behörigheter i Journey Optimizer. Kontakta administratören om du inte kan komma åt funktionen.

### Målgrupper {#target-audiences}

Skapa målgrupper i Experience Platform innan ni skapar utmaningar. Du kan välja befintliga målgrupper men inte skapa nya målgrupper med hjälp av användargränssnittet för lojalitetsutmaningar.

## Viktiga begränsningar {#limitations}

* **Inget redovisningssystem**: Lojalitetsproblem spårar inte monetära värden eller punktsaldon. När kunderna genomför en utmaning och får en belöning, anropar Journey Optimizer ditt externa lojalitetshanteringssystem för att hantera punktallokering.

* **Endast målgruppsval**: Du kan välja befintliga målgrupper men inte skapa nya målgrupper från användargränssnittet för lojalitetsutmaningar.

## Nästa steg {#next-steps}

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="access-loyalty-challenges.md">
    <!--<img alt="Access" src="../assets/do-not-localize/learn-more-button.svg">-->
    </a>
    <div>
    <a href="access-loyalty-challenges.md"><strong>Hitta lojalitetsproblem</strong></a>
    </div>
    <p>
    <em>Lär dig hur du får åtkomst till inventering och filtrering av utmaningar</em>
    <p>
  </td>
  <td>
    <a href="create-challenges.md">
      <!--<img alt="Create" src="../assets/do-not-localize/start-button.svg">-->
    </a>
    <div>
    <a href="create-challenges.md"><strong>Skapa utmaningar</strong></a>
    </div>
    <p>
    <em>Skapa och konfigurera din första lojalitetsutmaning</em>
    <p>
  </td>
  <td>
    <a href="manage-challenges.md">
    <!--<img alt="Manage" src="../assets/do-not-localize/monitor-button.svg">-->
    </a>
    <div>
    <a href="manage-challenges.md"><strong>Hantera utmaningar</strong></a>
    </div>
    <p>
    <em>Redigera, övervaka och optimera utmaningar</em>
    <p>
  </td>
</tr>
</table>
