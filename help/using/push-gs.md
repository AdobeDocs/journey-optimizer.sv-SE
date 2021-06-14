---
title: Kom igång med push-konfiguration
description: Förstå dataflöde och komponenter för push-meddelanden
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 0%

---

# Konfiguration för push-meddelanden {#get-started-push}

![](assets/do-not-localize/badge.png)

Push-meddelanden hjälper dig att nå mobilappsanvändare när som helst, särskilt när de inte aktivt använder din app. Push-meddelanden kan hjälpa dig att få en mängd olika användningsfall, som att tillhandahålla uppdateringar om tjänsten, be en användare att vidta åtgärder, varna användaren för ett nytt avtal osv. Enhetsplattformar kräver deltagande innan slutanvändarna kan ta emot eller visa dina meddelanden. Användaranmälan kan tas emot så snart appen startats för första gången efter installationen eller i en efterföljande session eller arbetsflöde, beroende på vad som är lämpligt. [!DNL Journey Optimizer] har stöd för push-meddelanden och hjälper dig att skicka mycket relevanta meddelanden med branschledande dataöverföringshastigheter. Push-meddelanden kan omfatta personalisering och resebaserade sammanhang för att utnyttja de datainsikter ert varumärke har med Adobe Experience Cloud.

Den här sidan hjälper dig att konfigurera och förstå viktiga tjänster och arbetsflöden som är kopplade till push-meddelanden i [!DNL Journey Optimizer].

## Ange push-meddelanden med Adobe Journey Optimizer

Om du vill skicka push-meddelanden med Adobe Journey Optimizer måste du utföra följande steg:

1. Följ dokumentationen för att få installationer med [Adobe Journey Optimizer &amp; Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/beta/adobe-journey-optimizer) i din app.
1. Skapa [förinställning för push-meddelandekanalen](configuration/message-presets.md)

## Push-meddelanden och Adobe Journey Optimizer

Följande bild visar vilka system och tjänster som är kopplade till tillhörande dataflöden och visar hur push-meddelanden levereras från en helhetslösning.

![](assets/push-flow.png)

1. Registrering av din varumärkesanpassade mobilapp (Android eller iOS) med Apples APN:er och Google FCM push-meddelandetjänster
1. Meddelandetjänster genererar en push-token, vilket är en identifierare som Adobe Journey Optimizer använder för att ange den specifika enheten som mål med ett push-meddelande.
1. Den tidigare genererade push-token skickas till Adobe Experience Platform och synkroniseras med kundprofilen i realtid. detta görs med OOTB med ett enkelt sätt att integrera klient-SDK
1. Push-meddelanden skapas i Adobe Journey Optimizer, push-meddelanden skapas mot en meddelandeförinställning
1. Push-meddelanden kan finnas på arbetsytan under orkestration i Journeys
1. Vid en Journey-publikation är kundprofiler baserade på resevillkor kvalificerade att ta emot push-meddelanden, push-meddelandenyttolaster personaliseras i det här steget
1. Personaliserade push-nyttolaster vidarebefordras till en intern push-meddelandeleveranstjänst
1. Den här interna tjänsten validerar sedan inloggningsuppgifterna för programmet som är kopplat till meddelandet, och
1. Skickar meddelandet till Apple &amp; Google Messaging Services för slutleverans
1. Feedback från meddelandetjänster noteras, fel och framgångar loggas för rapportering i Journey Live &amp; Global-rapporter
1. Push-meddelanden skickas till slutanvändarenheter
1. Interaktioner med push-meddelanden för slutanvändare skickas in som Experience Events från slutanvändarens klient via SDK-integrering

## Roller för nyckeltjänster i push-meddelanden

* **Leverantörer av push-** meddelandetjänster är de viktigaste webbtjänsterna för komponenter som levererar meddelanden från fjärrservrar till mobilappar.

   [!DNL Adobe Journey Optimizer]  har stöd för både Android- och iOS-plattformar och kan därför integreras med följande:
   * [Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging)  - skicka meddelanden till Android-mobilappen
   * [Apple Push Notification Service (APN:er)](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html)  - skicka meddelanden till iOS-mobilapp

* **Adobe Experience Platform Mobile** SDKsom tillhandahåller API:er för integrering på klientsidan för mobiler via Android- och iOS-kompatibla SDK:er. SDK har ett Adobe Journey Optimizer-tillägg som visar en rad olika API:er som är specifika för push-meddelanden och möjliggör dataflöden, som att registrera push-token eller skicka push-spårningshändelser eller andra anpassade upplevelsehändelser till Adobe Experience Platform. SDK innehåller också en mängd andra tillägg som möjliggör både andra Adobe Experience Cloud-funktioner och tredjepartspartners.

   SDK-integrering kräver även konfigurering av Adobe Experience Platform [datainsamling](https://experienceleague.adobe.com/docs/launch/using/home.html)-tjänster som:

   * Skapa ett datastream för att konfigurera de profil- och upplevelsehändelsedatamängder som data flödar mot i Adobe Experience Platform
   * Skapar mobil egenskap på klientsidan och lägger till tillägg. SDK är nära integrerat med dessa tillägg för att ge en smidig datainsamling.
   * Registrerar identifierare och appreferenser för mobilappspaket

* **Adobe Experience Platform kundprofiler i realtid**  ger en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive webben, mobiler, CRM och tredje part. Med hjälp av profilen kan ni sammanställa kunddata i en enhetlig vy som ger ett användbart, tidsstämplat konto för varje kundinteraktion. Push-token för en viss programanvändare lagras mot användarens profil som postdata medan de interaktioner som användaren gör med push-meddelanden spåras som händelsedata för tidsserier. [Läs mer om Adobe Experience Platform kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)

* **[!DNL Adobe Journey Optimizer]** : När era mobilappsintegreringar med ovan nämnda komponenter är på plats och era kundprofiler i Adobe Experience Platform kan ni skapa och samordna push-meddelanden i Adobe Journey Optimizer för att engagera era användare.

## Teknisk konfigurering och arbetsflöden för övrig personal

I följande bild visas de olika stegen, från början till slut, som används för att konfigurera komponenterna som utgör strukturen för push-dataflödet. Åtgärdsobjekten har kategoriserats baserat på rollen som utför konfigurationen och komponenten som konfigureras.

![](assets/user-flow.png)

