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
source-git-commit: 4ae9e908d259dbd266417242cf9e65d693227061
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 2%

---


# Roller och ansvarsområden

Med Adobe Journey Optimizer kan varumärken leverera sammankopplade och kontextualiserade kundresor under hela kundlivscykeln. Det gör det möjligt för team att personalisera interaktioner i stor skala och anpassa kundens förväntningar till affärsmålen. I den här dokumentationen förklaras de viktigaste rollerna när det gäller att använda Journey Optimizer effektivt, deras ansvarsområden och hur man kommer igång.

**Viktigt!** Adobe Journey Optimizer definierar distinkta roller med specifika ansvarsområden. En enskild person kan utföra flera roller eller alla roller beroende på organisationens struktur.

## Rollbaserade snabbstartsguider

För att förenkla implementeringen organiserar Adobe Journey Optimizer uppgifter i specifika roller baserat på expertis. Varje roll fokuserar på viktiga uppgifter som krävs för att leverera en smidig kundupplevelse.

| Roll | Primärt ansvar | Viktiga färdigheter | Vanliga uppgifter |
|-------------------|----------------------------------|--------------------------------|-----------------------------------------------|
| **Administratör** | Systeminstallation och behörighetshantering | Systemkonfiguration, användarhantering, säkerhet | Konfigurera sandlådor, hantera användare, konfigurera kanaler |
| **Datatekniker** | Konfigurera datastruktur och flöden | Datamodellering, schemadesign, API-integrering | Konfigurera scheman, hantera datauppsättningar, konfigurera datakällor |
| **Utvecklare** | Tekniska integreringar och anpassningar | Mobilutveckling, API-implementering, kodning | Integrera mobilappar, implementera API:er, skapa anpassade åtgärder |
| **Marketer** | Utforma och genomför kundresor | Marknadsföringsstrategi, innehållsskapande, resedesign | Skapa kampanjer, utforma resor, analysera rapporter |

Varje roll hanterar en viss fas av Adobe Journey Optimizer implementering och säkerställer en strukturerad och effektiv driftsättningsprocess.

## Implementeringsordning och rollberoenden

En lyckad Journey Optimizer-implementering följer vanligtvis den här sekvensen, som visar beroenden mellan roller:

1. **Administratör**: Konfigurerar miljön\
   Administratören lägger grunden för systemet och ser till att alla användare har korrekt åtkomst och konfiguration.
   * Konfigurera sandlådor och behörigheter
   * Konfigurera användaråtkomst
   * Konfigurera meddelandekanaler och tekniska inställningar

2. **Datatekniker**: Skapar datagrunden\
   Datatekniker definierar datastrukturen och dataflödet, som är avgörande för personaliserade upplevelser.
   * Utforma och implementera scheman
   * Konfigurera identitetsnamnutrymmen
   * Konfigurera datainmatning
   * Skapa testprofiler

3. **Utvecklare**: Hanterar tekniska integreringar\
   Utvecklarna gör det möjligt för Adobe Journey Optimizer att interagera med mobilappar, webbplatser och externa system genom att implementera tekniska integreringar. Push-meddelanden är till exempel beroende av utvecklarledda konfigurationer.
   * Integrera mobilappar för push-meddelanden
   * Implementera webb-SDK
   * Utveckla anpassade integreringar med API:er
   * Skapa anpassade åtgärder för tredjepartssystem

4. **Marketer**: Skapar och startar resor\
   Marknadsförarna använder grunden från andra roller för att utforma och distribuera kundupplevelser. De fokuserar på målgruppssegmentering, personaliserat innehåll och reseoptimering.
   * Utforma målgruppssegment
   * Skapa personaliserat innehåll
   * Bygga och testa resor
   * Analysera prestanda och optimera

**Obs!** Även om den här sekvensen är vanlig kan vissa aktiviteter förekomma parallellt. Utvecklare kan till exempel arbeta med appintegreringar medan datateknikerna konfigurerar scheman.

## Komma igång med rollen

Varje roll börjar med specifika uppgifter som är anpassade efter dess fokus. När du slutför dessa inledande steg får du smidigare introduktion och anpassning till den övergripande implementeringsprocessen:

1. **För marknadsförare**: Fokusera på att resa skapas, meddelandedesign och kampanjutförande.\
   Exempel: Börja med att skapa en välkomstkampanj för nya kunder.

2. **För datatekniker**: Upprätta datamängden, konfigurera scheman och integrera datakällor.\
   Exempel: Ställ in ett schema för att spåra kundens inköpshistorik för anpassade rekommendationer.

3. **För administratörer**: Konfigurera miljöer, hantera behörigheter och konfigurera meddelandekanaler.\
   Exempel: Konfigurera sandlådemiljöer för att testa olika meddelandestrategier.

4. **För utvecklare**: Integrera mobilappar, implementera API:er och skapa anpassade integreringar.\
   Exempel: Använd Adobe Journey Optimizer API för att utlösa push-meddelanden baserat på kundåtgärder i din mobilapp.

Klicka på din roll nedan för att få tillgång till specifik vägledning som är anpassad efter ditt ansvar:

* [Kom igång som marknadsförare](path/marketer.md)
* [Kom igång som datatekniker](path/data-engineer.md)
* [Kom igång som administratör](path/administrator.md)

## Instruktionsvideo {#video}

Titta på introduktionsvideon om du vill veta mer om Journey Optimizer nyckelfunktioner och personligheter. Videon går igenom användargränssnittet och markerar viktiga funktioner baserat på rollspecifika arbetsflöden.

>[!VIDEO](https://video.tv.adobe.com/v/3430318?captions=swe&quality=12)

## Ytterligare resurser

Utforska följande resurser om du vill veta mer om utbildning och uppdateringar:

* [Versionsinformation](../rn/release-notes.md)
* [Självstudievideor](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=sv-SE)