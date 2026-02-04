---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med lojalitetsutmaningar
description: Lär dig hur du skapar och hanterar lojalitetsutmaningar i Adobe Journey Optimizer för att skapa engagerande lojalitetsprogram.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: f41c1ed8a2d9e74b9d8fe97e0bf9e565d326aec6
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---


# Kom igång med lojalitetsutmaningar {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* **Kom igång med lojalitetsutmaningar** {2 }︎ ◀Du är här **- Översikt, arbetsflöde, förutsättningar**
* [Få åtkomst till och hantera lojalitetsutmaningar](access-loyalty-challenges.md) - Hantering av inventeringar, utmaningar och uppgifter
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Översikt {#overview}

Lojalitetsutmaningar är en komplett lösning för att skapa storskaliga lojalitetsprogram, från att definiera uppgifter och milstolpar till att leverera innehåll och spåra prestanda i olika kanaler.

Ni kan skapa tre typer av utmaningsupplevelser:

* **Standardutmaningar**: Kunderna utför ett angivet antal uppgifter i valfri ordning
* **Utmaningar**: Kunderna utför samma uppgift flera gånger i följd
* **Sekventiella utmaningar**: Kunderna slutför uppgifter i en definierad ordning

Med lojalitetsutmaningar kan ni konfigurera belöningar, skicka meddelanden i flera kanaler i viktiga faser av livscykeln och övervaka prestanda via automatiskt genererade resor - allt med bibehållen integrering med ert externa lojalitetshanteringssystem.

## Så fungerar det {#how-it-works}

När du skapar och startar en lojalitetsutmaning följer du det här arbetsflödet:

1. **Ställ in datainmatning** - Konfigurera Experience Platform-källanslutningar (t.ex. Capillary-kopplingen) för att importera lojalitetshändelsedata som spårar kundaktiviteter och kundframsteg. Dessa data gör det svårt att spåra och slutföra uppgifter.

1. **Välj målgrupp** - Definiera vilka kunder som kan delta i din utmaning genom att välja en målgrupp från Adobe Experience Platform.

1. **Skapa en utmaning** - Definiera grundläggande utmaningsegenskaper, inklusive namn, typ (Standard, Streak eller Sequential) och datumintervall.

1. **Lägg till aktiviteter** - Definiera de specifika åtgärder som kunderna måste utföra, inklusive aktivitetstyper (inköp, utgifter, besök, engagemang, anpassade händelser), kvantiteter, produktfilter och belöningar.

1. **Utforma innehållskort** - Skapa den visuella representationen av din utmaning med Journey Optimizer innehållskort som visas på kundenheter. Innehållskort visar information om utmaningar, framsteg och belöningar.

1. **Konfigurera meddelanden** (valfritt) - Konfigurera flerkanalsmeddelanden (i programmet, e-post, push) för nyckelstadier i livscykeln: start, pågående och slutförande.

1. **Publiceringsresa** - Journey Optimizer genererar automatiskt en resa för din utmaning. Navigera till lagret Resor och publicera den automatiskt genererade resan för att göra utmaningen tillgänglig för kunderna.

Detaljerade stegvisa instruktioner finns i [Skapa utmaningar](create-challenges.md).

## Förhandskrav {#prerequisites}

Innan du använder lojalitetsutmaningar måste du se till att du har:

+++Inställning av datainmatning

Lojalitetsutmaningar bygger på data som hämtas via Experience Platform källanslutningar för att spåra kundens framsteg och slutförande av uppgifter.

1. **Konfigurera en källanslutning som stöds**: För närvarande är den kapillära kopplingen allmänt tillgänglig. Ytterligare anslutningar planeras för framtida releaser.

1. **Validera datainmatning**: Kontrollera att lojalitetshändelser och kunddata följer med till Experience Platform och är tillgängliga i Journey Optimizer. Verifiera att dataschemat innehåller de fält som behövs för att spåra kundåtgärder och -förlopp.

Detaljerade instruktioner finns i:

* [Experience Platform-källdokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)
* [Konfigurera källanslutningar i Journey Optimizer](../start/get-started-sources.md)

+++

+++Nödvändiga behörigheter

Om du vill använda lojalitetsutmaningar måste du ha rätt behörigheter i Journey Optimizer. Nödvändiga behörigheter är:

* Åtkomst till funktionen **[!UICONTROL Loyalty Challenges (Beta)]**
* Tillstånd att skapa och hantera resor
* Behörigheter för att skapa och hantera innehållskort
* Behörigheter att skapa och hantera målgrupper

Kontakta administratören om du inte kan komma åt funktionen eller behöver ytterligare behörigheter.

+++

+++Målgrupper

Definiera en målgrupp som specificerar vilka kunder som är berättigade att delta i era lojalitetsutmaningar. Du kan välja befintliga målgrupper eller skapa nya direkt från gränssnittet för att skapa utmaningar. [Lär dig arbeta med målgrupper](../audience/about-audiences.md).

+++

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
    </p>
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
    </p>
  </td>
  <td>
    <a href="create-tasks.md">
    <!--<img alt="Tasks" src="../assets/do-not-localize/start-button.svg">-->
    </a>
    <div>
    <a href="create-tasks.md"><strong>Skapa aktiviteter</strong></a>
    </div>
    <p>
    <em>Definiera åtgärder och belöningar för utmaningar</em>
    </p>
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
    </p>
  </td>
</tr>
</table>
