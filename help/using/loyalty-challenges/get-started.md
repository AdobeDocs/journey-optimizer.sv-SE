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
mini-toc-levels: 1
source-git-commit: 6c6a1b31c81000877cea2af8bca0377264ec4833
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---


# Kom igång med lojalitetsutmaningar {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* **Kom igång med lojalitetsutmaningar** {2 }︎ ◀Du är här **&#x200B;**
* [Få tillgång till och hantera utmaningar och uppgifter](access-loyalty-challenges.md)
* [Skapa utmaningar](create-challenges.md)
* [Skapa uppgifter](create-tasks.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Den här funktionen finns för närvarande i **privat beta**. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Översikt {#overview}

Lojalitetsutmaningar gör att ni kan skapa engagerande, spelade lojalitetsprogram som driver kundbeteenden och fördjupar varumärkesrelationerna. Bygg utmaningar som belönar kunder för specifika åtgärder - från att göra köp och skriva recensioner till att engagera i sociala medier och referera till vänner.

Med lojalitetsutmaningar kan ni

* **Utforma flexibla utmaningstyper**: Skapa Standard, Streak eller Sequential-utmaningar för att matcha dina affärsmål
* **Konfigurera belöningar strategiskt**: Leverera poäng vid milstolpar för aktiviteter eller vid fullständigt slutförande för att behålla engagemanget
* **Anpassa upplevelsen**: Använd innehållskort och flerkanalsmeddelanden för att skapa engagerande, varumärkesanpassade upplevelser
* **Integrera sömlöst**: Anslut till dina befintliga lojalitetsleverantörer och utnyttja Experience Platform-data
* **Spåra automatiskt**: Övervaka kundens framsteg via automatiskt genererade resor utan anpassad utveckling

![](assets/challenges-gs.png)

Ni kan skapa tre typer av utmaningsupplevelser:

* **Standardutmaningar**: Kunderna utför ett angivet antal uppgifter i valfri ordning. Använd den här typen när du vill ha flexibilitet och flera banor för slutförande.\
  *Exempel:&quot;Sommarväldsutmaning&quot; - Slutför 3 av 5 uppgifter: köp hälsoprodukter, dela på sociala medier, hänvisa en kompis, skriva en recension eller delta i ett virtuellt event*

* **Utmaningar för strömning**: Kunderna utför samma uppgift flera gånger i följd. Använd den här typen för att uppmuntra konsekvent, upprepat beteende över tid.\
  *Exempel: &quot;Coffee Lover&#39;s Week&quot; - Köp kaffeprodukter under 7 dagar i följd för att låsa upp en belöning för kostnadsfri drink*

* **Sekventiella utmaningar**: Kunderna slutför uppgifter i en definierad ordning. Använd den här typen för att vägleda kunderna genom en viss resa eller introduktionsprocess.\
  *Exempel:&quot;Ny medlemsresa&quot; - Registrera dig för e-post → Gör ditt första köp → Skriv en produktrecension → Kontakta en vän (komplett i exakt den här ordern)*

## Så fungerar det {#how-it-works}

När du skapar och startar en lojalitetsutmaning följer du det här arbetsflödet:

1. **Ställ in datainmatning** - Konfigurera Experience Platform-källanslutningar (t.ex. [Capillary-kopplingen](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/home#loyalty)) för att importera lojalitetshändelsedata som spårar kundåtgärder och kundframsteg. Dessa data gör det svårt att spåra och slutföra uppgifter.

1. **Skapa en utmaning** - Definiera grundläggande utmaningsegenskaper, inklusive namn, typ (Standard, Streak eller Sequential) och datumintervall.

1. **Lägg till aktiviteter** - Definiera de specifika åtgärder som kunder måste utföra, inklusive aktivitetstyper (inköp, utgifter), kvantiteter, produktfilter och belöningar.

1. **Utforma innehållskort** - Skapa den visuella representationen av din utmaning med Journey Optimizer innehållskort som visas på kundenheter. Innehållskort visar information om utmaningar, framsteg och belöningar.

1. **Konfigurera meddelanden** (valfritt) - Konfigurera flerkanalsmeddelanden (i programmet, e-post, push) för nyckelstadier i livscykeln: start, pågående och slutförande.

1. **Välj målgrupp** - Definiera vilka kunder som kan delta i din utmaning genom att välja en målgrupp från Adobe Experience Platform.

1. **Starta utmaningen** - Publicera utmaningen och generera sedan en resa. Journey Optimizer skapar automatiskt en resa som klarar dina utmaningar. Publicera den autogenererade resan för att göra utmaningen tillgänglig för kunderna.

Detaljerade stegvisa instruktioner finns i [Skapa utmaningar](create-challenges.md).

## Förhandskrav {#prerequisites}

Innan du använder lojalitetsutmaningar måste du se till att du har:

+++Inställning av datainmatning

Lojalitetsutmaningar bygger på data som hämtas via Experience Platform källanslutningar för att spåra kundens framsteg och slutförande av uppgifter.

Konfigurera en källkoppling som stöds innan du startar programmet. Kapillärkopplingen är tillgänglig. Ytterligare anslutningar planeras för framtida releaser. [Läs mer om lojalitetskällanslutningar](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/home#loyalty).

+++

+++Nödvändiga behörigheter

Om du vill använda lojalitetsutmaningar måste du ha rätt behörigheter i Journey Optimizer. Nödvändiga behörigheter är:

* TBD
* TBD
* TBD

Kontakta administratören om du inte kan komma åt funktionen eller behöver ytterligare behörigheter.

+++

+++Målgrupper

Se till att målgruppen finns i Adobe Experience Platform innan du skapar en utmaning. Vid konfigurationen av en utmaning väljer du den målgrupp som definierar vilka kunder som är berättigade att delta. [Lär dig arbeta med målgrupper](../audience/about-audiences.md).

+++

## Nästa steg {#next-steps}

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="access-loyalty-challenges.md">
    <!--<img alt="Access" src="../assets/do-not-localize/learn-more-button.svg">-->
    </a>
    <div>
    <a href="access-loyalty-challenges.md"><strong>Få åtkomst till och hantera utmaningar och uppgifter</strong></a>
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
    <em>Lär dig hur du skapar och konfigurerar din första lojalitetsutmaning</em>
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
    <em>Lär dig hur du konfigurerar åtgärder som kunder utför för att hantera utmaningar</em>
    </p>
  </td>
</tr>
</table>
