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
source-git-commit: fd10a600cb54b8c35e2d195be7379b0dd120b6a7
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---


# Roller och ansvarsområden

Med Adobe Journey Optimizer kan varumärken leverera sammankopplade, kontextuella och personaliserade upplevelser under hela kundresan. Journey Optimizer har byggts med ett heltäckande fokus på skala, hastighet och flexibilitet och kombinerar tre viktiga drivrutiner i ett enhetligt program:

* **Kundinsikter och engagemang i realtid** som drivs av Adobe kundprofil i realtid
* **Modern flerkanalsmarknadsföring** genom enhetliga kanvaser för både realtidsresor och batchkampanjer, plus en modern meddelandedesigner
* **Intelligent beslutsfattande och personalisering** med hjälp av beslutshantering och AI/ML-funktioner

Journey Optimizer erbjuder två orkestreringsstrategier för olika marknadsföringsbehov:

* **Resor**: Passar bäst för 1:1-engagemang i realtid där varje kund går igenom i sin egen takt, triggas av beteende eller händelser
* **Samordnade kampanjer**: Passar bäst för batch-, en-till-många-kampanjer där målgrupper går samman i arbetsflöden i flera steg enligt ett schema - idealiskt för säsongskampanjer, produktlanseringar och kontobaserad kommunikation

Med denna enhetliga upplevelse kan ni implementera hela användningsfall på ett och samma ställe, från att definiera målgrupper och utforma resor till att skapa personaliserat innehåll och analysera resultat. I den här dokumentationen förklaras de viktigaste rollerna när det gäller att använda Journey Optimizer effektivt, deras ansvarsområden och hur man kommer igång.

**Viktigt!** Adobe Journey Optimizer definierar distinkta roller med specifika ansvarsområden. En enskild person kan utföra flera roller eller alla roller beroende på organisationens struktur.

## Rollbaserade snabbstartsguider

För att förenkla implementeringen organiserar Adobe Journey Optimizer uppgifter i specifika roller baserat på expertis. Varje roll fokuserar på viktiga uppgifter som krävs för att leverera en smidig kundupplevelse.

| Roll | Primärt ansvar | Viktiga färdigheter | Vanliga uppgifter |
|-------------------|----------------------------------|--------------------------------|-----------------------------------------------|
| **Administratör** | Miljöinställningar och åtkomsthantering | Systemkonfiguration, användarhantering, säkerhet | Konfigurera sandlådor, hantera användarbehörigheter, konfigurera kanaler och meddelandeförinställningar |
| **Datatekniker** | Kundprofildata och datakällor | Datamodellering, XDM-scheman, källkopplingar | Modellprofil och affärsdata till scheman, konfigurera källanslutningar, övervaka datainmatning |
| **Utvecklare** | Teknisk implementering och integrering | Mobile/Web SDK, API:er, händelsestyrd arkitektur | Integrera SDK:er, implementera händelser, skapa anpassade åtgärdsslutpunkter |
| **Marketer** | Resedesign och personaliserade upplevelser | Resesamordning, innehållsskapande, målgruppsanpassning | Utforma kundresor, skapa och personalisera meddelanden, hantera erbjudanden och beslutskomponenter, definiera målgrupper |

Varje roll hanterar en viss fas av Adobe Journey Optimizer implementering och säkerställer en strukturerad och effektiv driftsättningsprocess.

## Implementeringsordning och rollberoenden

En lyckad Journey Optimizer-implementering följer vanligtvis den här sekvensen, som visar beroenden mellan roller:

1. **Administratör**: Konfigurerar miljön\
   Administratören lägger grunden genom att konfigurera sandlådor, konfigurera åtkomstkontroller och förbereda kanalkonfigurationer. Detta måste ske först för att andra team ska kunna arbeta.
   * Konfigurera sandlådor för utveckling, staging och produktion
   * Ställ in roller, behörigheter och åtkomstkontroll på objektnivå (OLAC)
   * Konfigurera kanalkonfigurationer (e-post, SMS, push, web push, in-app, webb, direktreklam, innehållskort)
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
   * Implementera Web SDK för webbupplevelser och push-meddelanden på webben
   * Skicka händelser från program för att utlösa resor
   * Skapa anpassade åtgärdsslutpunkter för integration med externa system
   * Övervaka anpassade åtgärder, hälsa och prestanda
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

Som marknadsförare eller affärsadministratör utformar ni kundresor för att leverera personliga, sammanhangsbaserade upplevelser över alla kontaktytor. Du arbetar i ett enhetligt gränssnitt för att implementera hela användningsexempel från början till slut.

**Nyckelfunktioner du kommer att använda:**

* **Journey Orchestration**: Skapa ett-till-ett-kundengagemang i realtid där varje person går igenom i sin egen takt, triggas av beteende eller händelser över flera kanaler. Använd aktiviteten för enhetliga åtgärder för alla kanalaktiviteter, aktiviteten för innehållsbeslut för att integrera erbjudanden i resor och Journey Agent för att skapa resor från naturliga språk
* **Kampanjsamordning**: Designa och automatisera komplexa flerstegskampanjer i stor skala med en visuell arbetsyta. Perfekt för varumärkesinitierade kampanjer som säsongskampanjer, produktlanseringar och kontobaserad kommunikation. Utnyttja segmentering av flera enheter för att skapa exakta målgrupper genom att koppla kunddata till relaterade enheter (konton, inköp, bokningar). Använd vågsändning för att leverera meddelanden i kontrollerade batchar
* **Modern Message Designer**: Designa och anpassa e-post och mobilmeddelanden med dra-och-släpp-gränssnitt. Redigera färdiga mallar för att korta time-to-market
* **Beslutshantering**: Skapa och hantera erbjudanden, berättiganderegler och andra komponenter i ett centraliserat bibliotek som kan bäddas in i e-postmeddelanden och kundkontaktytor. Använd beslut för push- och SMS-personalisering
* **Resurshantering**: Få tillgång till Adobe Experience Manager Assets Essentials som är inbäddade i Journey Optimizer för smidig åtkomst och leverans av resurser
* **Målgruppsdefinition**: Skapa målgrupper på begäran med direktförfining med hjälp av relationsfrågor, med synlighet före sändning för korrekt antal målgrupper
* **AI/ML-tjänster**: Utnyttja optimering och prediktiva engagemangsmätningar för att rikta sig till värdefulla kunder och minimera risken för bortfall
* **Leveranskontroll**: Använd tysta timmar (tidsbaserade undantag) och konflikthantering för att ta hänsyn till kundernas önskemål och förhindra överkommunikation

**Börja med:** Använd fallmallar och guider för att enkelt skapa och distribuera nya kundresor. Använd Journey Agent för att skapa resor från naturliga språk.

[Kom igång som marknadsförare →](path/marketer.md)

### För datatekniker {#for-data-engineers}

Som dataarkitekt eller ingenjör kan ni skapa och underhålla kundprofildata och andra datakällor som stöder upplevelser som samordnas av Journey Optimizer.

**Viktiga ansvarsområden:**

* **Kundprofildata**: Modellera kundprofildata och affärsdata till scheman för att skapa en enhetlig helhetsbild av kunden i 360 grader
* **Relationell datamodellering**: För samordnade kampanjer skapar du relationsscheman för att aktivera segmentering av flera enheter, som kopplar kunddata till relaterade entiteter som konton, inköp, prenumerationer och bokningar för att skapa flexibla målgrupper
* **Source Connectors**: Konfigurera källanslutningar för import av data från webben, CRM, offlinedata och andra källor till Adobe Experience Platform
* **Identitetsupplösning**: Konfigurera identitetsnamnutrymmen för att kontinuerligt uppdatera profiler och flytta kunder in och ut ur segment och resor i realtid
* **Datakällor**: Konfigurera datakällor för att i realtid lyssna på externa signaler under kundresan
* **Profilhantering**: Aktivera datauppsättningar för kundprofil i realtid för att stärka personaliserade upplevelser
* **Datakvalitet**: Övervaka datainmatning för att säkerställa att allt flyter smidigt in i Journey Optimizer

**Börja med:** Modellera ditt första kundprofilschema och konfigurera en källkoppling för att börja inhämta data.

[Kom igång som datatekniker →](path/data-engineer.md)

### För administratörer {#for-administrators}

Som administratör konfigurerar du Journey Optimizer-miljön så att dina team kan arbeta effektivt och säkert.

**Viktiga ansvarsområden:**

* **Sandlådor**: Skapa och hantera sandlådor för att partitionera data och resor för olika användargrupper (utveckling, testning, produktion)
* **Användarhantering**: Konfigurera användargrupper och behörigheter för att styra åtkomsten till olika funktioner
* **Kanalinställning**: Konfigurera leveranskanaler och meddelandeförinställningar för att säkerställa enhetlig märkning av meddelanden och resurser som levereras via Journey Optimizer
* **Säkerhet och styrning**: Använd åtkomstkontroll på objektnivå (OLAC), konfigurera medgivandeprinciper och implementera datastyrningsprinciper
* **Leveransbarhet**: Delegera underdomäner, migrera underdomäner till anpassad delegering vid behov, skapa IP-pooler och hantera undertryckningslistor och tillåtelselista
* **Resekonfiguration**: Konfigurera reseelement och konfigurationer för dina team
* **Kanalkonfiguration**: Konfigurera push-meddelanden på webben, direktreklam och meddelandeexport (e-post/SMS) vid behov

**Börja med:** Konfigurera sandlådor och användarbehörigheter och konfigurera sedan dina första kanalkonfigurationer och meddelandeförinställningar.

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

Framgångsrika Journey Optimizer-implementeringar kräver samarbete i alla roller. Varje roll samverkar med andra för att leverera sömlösa kundupplevelser:

>[!BEGINTABS]

>[!TAB Administratörer]

**Administratörer** aktiverar alla team genom att hantera åtkomst och konfigurationer. De arbetar med:

* **Datatekniker**: Bevilja behörigheter för datahantering, godkänna sandlådeåtkomst, koordinera för styrningsprinciper
* **Utvecklare**: Ange API-autentiseringsuppgifter, konfigurera testmiljöer, godkänna kanalkonfigurationer
* **Marknadsförare**: Tilldela behörigheter för resor/kampanjer, konfigurera kanaler, stödja testmiljöer

>[!TAB Datatekniker]

**Datatekniker** tillhandahåller en grund för alla. De arbetar med:

* **Administratörer**: Begär behörigheter för datahantering, koordinat för styrnings- och lagringsprinciper
* **Utvecklare**: Ange XDM-scheman och händelsestrukturer, definiera format för händelsenyttolast, testa datainmatning
* **Marknadsförare**: Skapa beräknade attribut för personalisering, skapa målgrupper, konfigurera relationsscheman

>[!TAB Utvecklare]

**Utvecklare** implementerar tekniska integreringar som driver resor. De arbetar med:

* **Datatekniker**: Hämta XDM-scheman och händelsestrukturer, anpassa efter datainsamlingsbehov, leverans av testhändelser
* **Administratörer**: Ange API-specifikationer, begär behörigheter och autentiseringsuppgifter, koordinera för testningsstrategi
* **Marknadsförare**: Förstå händelseutlösare, implementera spårning, supporttester, felsökning

>[!TAB Marknadsförare]

**Marknadsförare** utformar kundupplevelser och ger feedback. De arbetar med:

* **Datatekniker**: Begär beräknade attribut, koordinera för målgruppskrav, ge feedback om datakvaliteten
* **Utvecklare**: Justera mot händelseutlösare, testimplementeringar, validera spårning
* **Administratörer**: Begär kanalkonfigurationer, bekräfta funktionsåtkomst, koordinera vid aktivering

>[!ENDTABS]

**Bästa praxis:** Håll regelbundna funktionsövergripande möten för att anpassa sig till prioriteringar, dela framsteg och hantera blockerare i olika team.

## Instruktionsvideo {#video}

Titta på introduktionsvideon om du vill veta mer om Journey Optimizer nyckelfunktioner och personligheter. Videon går igenom användargränssnittet och markerar viktiga funktioner baserat på rollspecifika arbetsflöden.

>[!VIDEO](https://video.tv.adobe.com/v/3424995?quality=12)

## Ytterligare resurser

Utforska följande resurser om du vill veta mer om utbildning och uppdateringar:

>[!BEGINTABS]

>[!TAB Utbildning och dokumentation]

* [Självstudievideor](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=sv-SE){target="_blank"} - Självstudiekurser steg för steg för alla roller
* [Bibliotek för reseanvändningsexempel](../building-journeys/jo-use-cases.md) - Praktiska exempel och implementeringsmönster
* [AI och intelligenta funktioner](ai-features.md) - Läs mer om AI Assistant, optimering vid sändning och innehållsgenerering
* [Användargränssnittshandbok](user-interface.md) - Navigera effektivt i Journey Optimizer

>[!TAB Fortsätt vara uppdaterad]

* [Versionsinformation](../rn/release-notes.md) - Senaste funktioner, förbättringar och korrigeringar
* [Dokumentationsuppdateringar](../rn/documentation-updates.md) - Spåra senaste dokumentationsändringar
* [Produktmeddelanden](../rn/releases.md#staying-informed) - Lär dig hur du prenumererar på e-post och produktmeddelanden för Journey Optimizer-uppdateringar

>[!TAB Community och support]

* [Experience League Community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer?profile.language=sv){target="_blank"} - Kontakta andra användare och experter
* [Produktforum](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer?profile.language=sv){target="_blank"} - Ställ frågor och dela kunskap

>[!ENDTABS]
