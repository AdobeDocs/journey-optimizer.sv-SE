---
solution: Journey Optimizer
product: journey optimizer
title: Push-meddelandeflöde i Adobe Journey Optimizer
description: Förstå dataflöde och komponenter för push-meddelanden
topic: Mobile
feature: Push, Overview
role: Admin
level: Intermediate
exl-id: 9718c4b6-2558-4dfd-9d8f-f8845def19ba
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 1%

---

# Dataflöde och komponenter för push-meddelanden {#get-started-push}

Den här sidan hjälper dig att konfigurera och förstå viktiga tjänster och arbetsflöden som är kopplade till push-meddelanden i [!DNL Journey Optimizer].


>[!AVAILABILITY]
>
>Det nya **snabbstartsarbetsflödet för mobil introduktion** är nu tillgängligt. Använd den här nya produktfunktionen för att snabbt konfigurera Mobile SDK för att börja samla in och validera mobilhändelsedata och skicka push-meddelanden till mobiler. Den här funktionen är tillgänglig via startsidan för datainsamling som en betaversion. [Läs mer](mobile-onboarding-wf.md)
>

Lär dig hur du skapar push-meddelanden på [den här sidan](create-push.md).

Steg för att konfigurera push-kanal i [!DNL Adobe Journey Optimizer] beskrivs på [den här sidan](push-configuration.md).

Följande bild visar vilka system och tjänster som är kopplade till tillhörande dataflöden och visar hur push-meddelanden levereras från en helhetslösning.

![](assets/push-flow.png)

1. Registrering av din varumärkesanpassade mobilapp (Android eller iOS) med Apple APN:er och Google FCM push messaging services
1. Meddelandetjänster genererar en push-token, vilket är en identifierare som [!DNL Adobe Journey Optimizer] använder för att ange den specifika enheten som mål med ett push-meddelande.
1. Den tidigare genererade push-token skickas till Adobe Experience Platform och synkroniseras med kundprofilen i realtid. Detta görs med OTB med en enkel integrering av klient-SDK
1. Push-meddelanden skapas i [!DNL Adobe Journey Optimizer], push-meddelanden skapas mot en kanalkonfiguration (t.ex. meddelandeförinställning)
1. Push-meddelanden kan finnas på arbetsytan under orkestration i Journeys
1. Vid en Journey-publikation är kundprofiler baserade på resevillkor kvalificerade att ta emot push-meddelanden, push-meddelandenyttolaster personaliseras i det här steget
1. Personaliserade push-nyttolaster vidarebefordras till en intern push-meddelandeleveranstjänst
1. Den här interna tjänsten validerar sedan inloggningsuppgifterna för programmet som är kopplat till meddelandet, och
1. Skickar meddelandet till Apple &amp; Google meddelandetjänster för slutleverans
1. Feedback från meddelandetjänster noteras, fel och framgångar loggas för rapportering i Journey Live &amp; Customer Journey Analytics-rapporten
1. Push-meddelanden skickas till slutanvändarenheter
1. Interaktioner med push-meddelanden för slutanvändare skickas in som Experience Events från slutanvändarens klient via SDK-integrering

## Roller för nyckeltjänster i push-meddelanden {#roles-of-key-services}

* **Leverantörer av push-meddelandetjänster** är de centrala webbtjänster för komponenter som levererar meddelanden från fjärrservrar till mobilappar.

  [!DNL Adobe Journey Optimizer] stöder både Android- och iOS-plattformar och kan därför integreras med följande:
   * [Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging) - för att skicka meddelanden till Android mobilapp
   * [Apple Push Notification Service (APN:er)](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html) - skicka meddelanden till iOS mobilapp

* **Adobe Experience Platform Mobile SDK** som tillhandahåller API:er för integrering på klientsidan för mobiler via Android och iOS-kompatibla SDK:er. SDK innehåller ett [!DNL Adobe Journey Optimizer]-tillägg som visar en mängd olika API:er som är specifika för push-meddelanden och aktivera dataflöden, som att registrera push-token eller skicka push-spårningshändelser eller andra anpassade upplevelsehändelser till Adobe Experience Platform. SDK innehåller också en mängd andra tillägg som möjliggör både andra Adobe Experience Cloud-funktioner och tredjepartspartners.

  SDK-integrering kräver även konfigurering av Adobe Experience Platform [datainsamlingstjänster](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=sv){target="_blank"}, till exempel:

   * Skapa ett datastream för att konfigurera de profil- och upplevelsehändelsedatamängder som data flödar mot i Adobe Experience Platform
   * Skapar mobil egenskap på klientsidan och lägger till tillägg. SDK är nära integrerat med dessa tillägg för att ge en smidig datainsamling.
   * Registrerar identifierare och appreferenser för mobilappspaket

* **Adobe Experience Platform kundprofil för realtid** ger en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive webben, mobiler, CRM och tredje part. Med hjälp av profilen kan ni sammanställa kunddata i en enhetlig vy som ger ett användbart, tidsstämplat konto för varje kundinteraktion. Push-token för en viss programanvändare lagras mot användarens profil som postdata medan de interaktioner som användaren gör med push-meddelanden spåras som händelsedata för tidsserier. [Läs mer om Adobe Experience Platform kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

* **[!DNL Adobe Journey Optimizer]** : När mobilappen har integrerats med de ovannämnda komponenterna och dina kundprofiler i Adobe Experience Platform kan du skapa och ordna push-meddelanden i [!DNL Adobe Journey Optimizer] för att interagera med dina användare.

## Teknisk konfigurering och arbetsflöden {#push-technical-setup}

I följande bild visas de olika stegen, från början till slut, som används för att konfigurera komponenterna som utgör strukturen för push-dataflödet. Åtgärdsobjekten har kategoriserats baserat på rollen som utför konfigurationen och komponenten som konfigureras.

![](assets/user-flow.png)

**Relaterade ämnen**

* [Konfigurera push-kanal](push-configuration.md)
* [Rapport om push-meddelanden](../reports/journey-global-report-cja-push.md)
* [Skapa ett push-meddelande](create-push.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)