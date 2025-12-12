---
solution: Journey Optimizer
product: journey optimizer
title: Roller och ansvarsområden
description: Läs om de olika roller som Adobe Journey Optimizer har och deras ansvarsområden
feature: Get Started
role: Admin, Developer, User
level: Beginner
exl-id: 71ab7369-fd84-46eb-95d2-941bd887d565
redpen-status: PASS_||_2025-04-28_15-13-07
source-git-commit: 5ff7987c00afda3263cb97654967c5b698f726c2
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%

---


# Roller och ansvarsområden

Med Adobe Journey Optimizer kan varumärken leverera sammankopplade och kontextualiserade kundresor under hela kundlivscykeln. Det gör det möjligt för team att personalisera interaktioner i stor skala och anpassa kundens förväntningar till affärsmålen. I den här dokumentationen förklaras de viktigaste rollerna när det gäller att använda Journey Optimizer effektivt, deras ansvarsområden och hur man kommer igång.

**Viktigt!** Adobe Journey Optimizer definierar distinkta roller med specifika ansvarsområden. En enskild person kan utföra flera roller eller alla roller beroende på organisationens struktur.

## Rollbaserade snabbstartsguider

För att förenkla implementeringen organiserar Adobe Journey Optimizer uppgifter i specifika roller baserat på expertis. Varje roll fokuserar på viktiga uppgifter som krävs för att leverera en smidig kundupplevelse.

| Roll | Primärt ansvar | Viktiga färdigheter | Vanliga uppgifter |
|-------------------|----------------------------------|--------------------------------|-----------------------------------------------|
| **Administratör** | Miljöinställningar och åtkomsthantering | Systemkonfiguration, användarhantering, säkerhet | Konfigurera sandlådor, hantera behörigheter, konfigurera kanalkonfigurationer |
| **Datatekniker** | Datagrund och -arkitektur | Datamodellering, XDM-scheman, datakvalitet | Skapa scheman och datauppsättningar, konfigurera datainmatning, hantera datalängd |
| **Utvecklare** | Teknisk implementering och integrering | Mobile/Web SDK, API:er, händelsestyrd arkitektur | Integrera SDK:er, implementera händelser, skapa anpassade åtgärdsslutpunkter |
| **Marketer** | Design och utförande av kundupplevelser | Resedesign, innehållsskapande, dataanalys | Skapa resor, skapa personaliserat innehåll, optimera kampanjer |

Varje roll hanterar en viss fas av Adobe Journey Optimizer implementering och säkerställer en strukturerad och effektiv driftsättningsprocess.

## Implementeringsordning och rollberoenden

En lyckad Journey Optimizer-implementering följer vanligtvis den här sekvensen, som visar beroenden mellan roller:

1. **Administratör**: Konfigurerar miljön\
   Administratören lägger grunden genom att konfigurera sandlådor, konfigurera åtkomstkontroller och förbereda kanalkonfigurationer. Detta måste ske först för att andra team ska kunna arbeta.
   * Konfigurera sandlådor för utveckling, staging och produktion
   * Ställ in roller, behörigheter och åtkomstkontroll på objektnivå (OLAC)
   * Konfigurera kanalkonfigurationer (e-post, SMS, push, in-app, webb, innehållskort)
   * Delegera underdomäner och konfigurera IP-pooler
   * Konfigurera inaktiveringslistor och medgivandeprinciper

2. **Datatekniker**: Skapar datagrunden\
   Datatekniker bygger upp den datainfrastruktur som driver personaliseringen, och definierar hur kunddata flödar in i och genom systemet.
   * Skapa identitetsnamnutrymmen för kundidentifiering
   * Utforma XDM-scheman (profil, upplevelsehändelser, relation)
   * Konfigurera datauppsättningar och aktivera dem för kundprofil i realtid
   * Konfigurera datainmatning (batch- och direktuppspelning)
   * Skapa beräknade attribut för komplexa beräkningar
   * Konfigurera händelser och datakällor för resor

3. **Utvecklare**: Implementerar tekniska integreringar\
   Utvecklare kopplar program till Journey Optimizer genom att integrera SDK:er, skicka händelser och bygga API-slutpunkter. Dessa implementeringar gör det möjligt att utlösa och genomföra resor.
   * Integrera Mobile SDK (iOS/Android) med inställningar för push-meddelanden
   * Implementera SDK för webben
   * Skicka händelser från program för att utlösa resor
   * Skapa anpassade åtgärdsslutpunkter för integration med externa system
   * Testa implementeringar med Adobe Experience Platform Assurance

4. **Marknadsförare**: Utformar och kör kundupplevelser\
   Marknadsförarna utnyttjar allt det grundläggande arbetet för att skapa resor, skapa innehåll och optimera kundupplevelser i alla kanaler.
   * Bygg målgrupper med segmentering, CSV-överföring eller målgruppskomposition
   * Designa personaliserat material med AI Assistant och mallar
   * Skapa flerkanaliga resor med event- och målgruppsutlösare
   * Testa med arbetsflöden för godkännande före start
   * Övervaka prestanda och optimera baserat på rapportinsikter

**Obs!** Även om den här sekvensen är vanlig kan vissa aktiviteter förekomma parallellt. Utvecklare kan till exempel arbeta med appintegreringar medan datateknikerna konfigurerar scheman.

## Komma igång med rollen

Varje roll börjar med specifika uppgifter som är anpassade efter dess fokus. När du slutför dessa inledande steg får du smidigare introduktion och anpassning till den övergripande implementeringsprocessen:

### För marknadsförare {#for-marketers}

Fokusera på att skapa personaliserade kundupplevelser i alla kanaler.

**Nyckelfunktioner du kommer att använda:**

* Skapa målgrupper och bygg segment med flera metoder (segmentdefinitioner, CSV-överföring, målgruppskomposition)
* Skapa material med AI Assistant för generering av text och bilder
* Skapa flerkanaliga kundresor med dra-och-släpp-designer
* Utnyttja optimering och konflikthantering vid sändning för att maximera engagemanget
* Testa innehåll och använd arbetsflöden för godkännande före publicering
* Övervaka prestanda med integrerade rapportpaneler

**Börja med:** Skapa en enkel välkomstresa eller en övergiven kundvagnsåterställningskampanj med färdiga mallar.

[Kom igång som marknadsförare →](path/marketer.md)

### För datatekniker {#for-data-engineers}

Upprätta en grund för de data som ligger till grund för personaliserade upplevelser.

**Viktiga ansvarsområden:**

* Skapa identitetsnamnutrymmen och konfigurera identitetsupplösning
* Utforma XDM-scheman för profil- och händelsedata (standard och relation)
* Konfigurera datauppsättningar och aktivera dem för kundprofil i realtid
* Konfigurera källanslutningar för import av batch- och direktuppspelningsdata
* Skapa beräknade attribut för att förenkla segmenteringen
* Konfigurera händelser och datakällor för körning av resan
* Hantera datakvalitet, styrning och livscykel

**Börja med:** Konfigurera identitetsnamnutrymmen och skapa ditt första profilschema med de obligatoriska fältgrupperna.

[Kom igång som datatekniker →](path/data-engineer.md)

### För administratörer {#for-administrators}

Konfigurera och hantera Journey Optimizer-miljön för er organisation.

**Viktiga ansvarsområden:**

* Skapa och hantera sandlådor för utveckling, testning och produktion
* Konfigurera roller och behörigheter med färdiga eller anpassade roller
* Använd åtkomstkontroll på objektnivå (OLAC) för att skydda resurser
* Konfigurera kanalkonfigurationer för e-post, SMS, push, in-app, webb och innehållskort
* Delegera underdomäner och skapa IP-pooler för e-postleverans
* Hantera undertryckningslistor och tillåtelselista
* Konfigurera policyer för samtycke och datahantering (med hälso- och sjukvård/sköld för skydd av privatlivet)

**Börja med:** Konfigurera sandlådor, konfigurera grundläggande roller och behörigheter och arbeta sedan med teamet i kanalkonfigurationer.

[Kom igång som administratör →](path/administrator.md)

### För utvecklare {#for-developers}

Implementera tekniska integreringar som kopplar Journey Optimizer till era applikationer.

**Viktiga ansvarsområden:**

* Integrera Adobe Experience Platform Mobile SDK (iOS/Android)
* Implementera Web SDK för webbupplevelser och push-meddelanden på webben
* Konfigurera autentiseringsuppgifter och certifikat för push-meddelanden
* Skicka händelser från program för att utlösa resor
* Skapa API-slutpunkter som Journey Optimizer anropar via anpassade åtgärder
* Implementera kodbaserade upplevelser för webben, mobiler och andra ytor
* Testa och felsöka implementeringar med Adobe Experience Platform Assurance
* Arbeta med Journey Optimizer API:er för programmatisk åtkomst

**Börja med:** Integrera Mobile eller Web SDK och implementera sedan din första händelse för att utlösa en resa.

[Kom igång som utvecklare →](path/developer.md)

## Collaboration med flera roller

Lyckade Journey Optimizer-implementeringar kräver samarbete i alla roller:

* **Administratörer** aktiverar andra roller genom att konfigurera sandlådor, behörigheter och kanalkonfigurationer
* **Datatekniker** tillhandahåller den datamöjligheter som utvecklare och marknadsförare bygger på
* **Utvecklare** implementerar de tekniska integreringar som marknadsförare använder för att utlösa resor
* **Marknadsförarna** ger feedback till alla team om datakvalitet, förslag på nya funktioner och användarupplevelser

**Bästa praxis:** Håll regelbundna funktionsövergripande möten för att anpassa sig till prioriteringar, dela framsteg och hantera blockerare i olika team.

## Instruktionsvideo {#video}

Titta på introduktionsvideon om du vill veta mer om Journey Optimizer nyckelfunktioner och personligheter. Videon går igenom användargränssnittet och markerar viktiga funktioner baserat på rollspecifika arbetsflöden.

>[!VIDEO](https://video.tv.adobe.com/v/3424995?quality=12)

## Ytterligare resurser

Utforska följande resurser om du vill veta mer om utbildning och uppdateringar:

**Utbildning och dokumentation:**

* [Självstudievideor](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html){target="_blank"} - Självstudiekurser steg för steg för alla roller
* [Bibliotek för reseanvändningsexempel](../building-journeys/jo-use-cases.md) - Praktiska exempel och implementeringsmönster
* [AI och intelligenta funktioner](ai-features.md) - Läs mer om AI Assistant, optimering vid sändning och innehållsgenerering
* [Användargränssnittshandbok](user-interface.md) - Navigera effektivt i Journey Optimizer

**Fortsätt vara uppdaterad:**

* [Versionsinformation](../rn/release-notes.md) - Senaste funktioner, förbättringar och korrigeringar
* [Dokumentationsuppdateringar](../rn/documentation-updates.md) - Spåra senaste dokumentationsändringar
* **Produktmeddelanden** - Aktivera aviseringar i din [Adobe Experience Cloud-profil](https://experience.adobe.com/preferences){target="_blank"} för att få meddelanden om nya releaser, underhållsperioder och viktiga meddelanden. Klicka på din profilikon > Inställningar > Meddelanden för att konfigurera.

**Community och support:**

* [Experience League Community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"} - Kontakta andra användare och experter
* [Produktforum](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"} - Ställ frågor och dela kunskap
