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
source-git-commit: 7b075996eebd03f0aa812da3ece9cfebef8c65fc
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---


# Kom igång med lojalitetsutmaningar {#get-started-loyalty-challenges}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst.

Med lojalitetsutmaningar kan ni skapa personaliserade engagemangserbjudanden för era kunder, så att ni kan samordna lojalitetsprogram i stor skala. Du kan utforma utmaningar med specifika uppgifter och milstolpar, belöna kunder för att de fyllt i dem och leverera upplevelsen via Adobe Journey Optimizer-kanaler.

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* **Kom igång med lojalitetsutmaningar** {2 }︎ ◀Du är här **- snabböversikt och nästa steg**
* [Förstå lojalitetsutmaningar](get-started.md) - Funktioner, arbetsflöde, förutsättningar
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Hantera utmaningar](manage-challenges.md) - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

## Snabb översikt {#quick-overview}

Använd lojalitetsutmaningar för att:

* **Skapa tre typer av utmaningar**: Standard (alla aktiviteter), Streak (upprepade aktiviteter) eller Sequential (ordnade aktiviteter)
* **Utmaningsinnehåll för design**: Använd innehållskort för att visa utmaningar på kundenheter
* **Ange uppgiftskrav**: Definiera åtgärder som inköp, besök eller anpassade händelser med belöningar
* **Skicka meddelanden i flera kanaler**: Leverera meddelanden via appar, e-post och push i viktiga steg
* **Spåra prestanda**: Övervaka genom automatiskt genererade resor och inbyggda rapporter

## Så fungerar det {#how-it-works-overview}

När du skapar en lojalitetsfråga följer du det här arbetsflödet:

1. **Konfigurera datainmatning** - Konfigurera källanslutningar för att spåra kundåtgärder
2. **Skapa en utmaning** - Definiera typ, målgrupp och datum
3. **Lägg till aktiviteter** - Konfigurera åtgärder och belöningar
4. **Designa innehåll** - Skapa innehållskort och valfria meddelanden
5. **Publicera** - Journey Optimizer genererar och aktiverar en resa automatiskt
6. **Bildskärm** - Spåra deltagande och prestanda

>[!NOTE]
>
>Den automatiskt genererade resan visas i kundreseinventeringen och kan anpassas vid behov. Ändringar som görs direkt på resan synkroniseras dock inte tillbaka till utmaningskonfigurationen.

## Förhandskrav {#prerequisites-overview}

Innan du använder lojalitetsutmaningar:

* Konfigurera Experience Platform-källanslutningar (t.ex. Kapillär) för att importera data om lojalitetshändelser
* Se till att du har rätt behörigheter i Journey Optimizer
* Skapa målgrupper i Experience Platform

Detaljerade krav finns i [Förstå lojalitetsproblem](get-started.md#prerequisites).

## Viktiga begränsningar {#limitations-overview}

* **Inget redovisningssystem**: Lojalitetsproblem spårar inte monetära värden eller punktsaldon. Journey Optimizer anropar det externa lojalitetshanteringssystemet för att hantera punktallokering.
* **Endast målgruppsval**: Du kan välja befintliga målgrupper men inte skapa nya målgrupper från användargränssnittet för lojalitetsutmaningar.

## Nästa steg {#next-steps}

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="get-started.md">
    <img alt="Förstå" src="../assets/do-not-localize/learn-more-button.svg">
    </a>
    <div>
    <a href="get-started.md"><strong>Förstå lojalitetsproblem</strong></a>
    </div>
    <p>
    <em>Läs om funktioner, arbetsflöde och funktioner</em>
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
