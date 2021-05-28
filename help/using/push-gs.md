---
title: Kom igång med push-konfiguration
description: Förstå dataflöde och komponenter för push-meddelanden
hide: true
hidefromtoc: true
source-git-commit: a2eee802f82552e56ced00f93e5e4c8a7b3feb7a
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Kom igång med push-konfiguration {#get-started-push}

![](assets/do-not-localize/badge.png)

Push-meddelanden fungerar som en snabb kommunikationskanal som gör att du kan förmedla meddelanden, erbjudanden och annan information till mobilappsanvändarna. I vanliga fall måste slutanvändaren avanmäla sig för att få push-meddelanden. Anmäl dig vanligtvis under installationsprocessen och slutanvändarna får ett sätt att hantera meddelanden om de ändrar sig senare. En viktig fördel med push-meddelanden inom mobil datoranvändning är att tekniken inte kräver att specifika program på en mobil enhet är öppna för att ett meddelande ska kunna tas emot. Detta gör att en smarttelefon kan ta emot och visa meddelanden även när enhetens skärm är låst och mobilappen är i bakgrunden eller stängd.

**[!DNL Adobe Journey Optimizer]**  kan ni skicka tidskänsliga, relevanta och personaliserade push-meddelanden i stor skala. Målgruppen för ett segment av kundprofiler är att få omfattande push-meddelanden på mobilenheterna i iOS och Android. Dessa segment kan skapas baserat på tidigare eller aktiva användarupplevelsehändelser, användarpostdata eller en kombination av användarinteraktioner och data. När en resa är live kan du visa detaljerade rapporter om hur många meddelanden som skickats, misslyckats av vilken anledning och även skicka spårningsinformation, som hur många användare som klickat på dem.

Det här dokumentet leder dig igenom ett grundläggande push-meddelandeflöde från början till slut med [!DNL Journey Optimizer] och ett användarflödesdiagram som förklarar hur varje roll uppfyller sitt ansvar och samarbetar för att föra push-dataflödet samman.


## Komponenter och tjänster

* **Cloud Messaging** Providers är tredjepartstjänster som gör att vi kan leverera meddelanden från fjärrservrar till mobilappar.

   [!DNL Adobe Journey Optimizer]  har stöd för både Android- och iOS-plattformar och hanterar två primära molnmeddelandetjänster:
   * Firebase Cloud Messaging (FCM) - för att skicka meddelanden till Android-mobilappen
   * Apple Push Notification Service (APN:er) - för att skicka meddelanden till iOS-mobilappen

* **Mobilappar som är integrerade med Adobe Mobile** SDK, som hjälper dig att integrera dina mobilappar med Adobe Experience Cloud Solutions. Mobile SDK består av olika Experience Cloud-tillägg som tillhandahåller funktioner som är specifika för den tjänst de representerar. Dessa tillägg visar olika API:er för att möjliggöra dataflöden, som att registrera push-token eller skicka push-spårningshändelser eller andra anpassade upplevelsehändelser till Adobe Experience Platform.

* **Adobe Launch**  (eller Data Collection) är nästa generation av SDK-hanteringsfunktioner för mobiler som möjliggör dataflöde från Mobile SDK till  [!DNL Adobe Experience Platform]. Här finns funktioner för att registrera tillägg, skapa regler och dataelement för att skicka data från din mobilapp till Adobe Experience Cloud-lösningar. När det gäller flödet av push-meddelanden är de primära konfigurationer som krävs i Adobe Launch följande:

   * Skapa ett datastream för att konfigurera de profil- och upplevelsehändelsedatamängder som data flödar mot till upplevelseplattformen.
   * Skapa en mobil egenskap på klientsidan och lägga till tillägg. Mobile SDK är nära integrerat med dessa tillägg för att ge en smidig datainsamling.
   * Registrering av identifierare och appreferenser för mobilappspaket som hjälper till att identifiera och validera programmets integritet när push-meddelanden skickas.

* **Kundprofiler** i realtid är den komponent i Adobe Experience Platform som gör att ni kan få en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive webben, mobiler, CRM och tredje part. Med hjälp av profilen kan ni sammanställa kunddata i en enhetlig vy som ger ett användbart, tidsstämplat konto för varje kundinteraktion. Statiska data som identifierar användaren av mobilappen, t.ex. en push-token, lagras mot användarens profil som postdata medan de interaktioner som användaren gör med push-meddelanden spåras som händelsedata i tidsserier.

* **[!DNL Adobe Journey Optimizer]** : När era mobilappar har integrerats med de ovannämnda komponenterna och kundprofilerna är tillgängliga som kundprofiler i realtid kan ni utnyttja de kraftfulla målgruppssegmenteringsfunktionerna  [!DNL Adobe Journey Optimizer]  för att optimera upplevelsen för varje person.


## Push-dataflöde

Bilden visar ett grundläggande dataflöde för push-meddelanden och ger en översikt över de olika Adobe-produkter och -komponenter som är inblandade i flödet.

![](assets/push-flow.png)


1. Kunden utvecklar en mobilapp för Android eller iOS som de skulle lansera för sina användare. För att kunna använda push-funktionerna från push-leverantörer, som APNS från Apple och FCM från Google, registrerar sig mobilappen och aktiverar push-funktionen.
1. Tryckerierna genererar och skickar en push-token till mobilappen. En push-token är en identifierare som avsändare använder för att ange specifika enheter med ett push-meddelande.
1. Mobilappen är integrerad med Adobe Mobile SDK som visar olika tillägg och API:er. Meddelandetillägget visar ett API för att registrera push-token i Adobe Experience Platform mot kundens profil.
1. När mobilappen är klar konfigureras den i **[!DNL Journey Launch]** `>` **App Configurations** tillsammans med autentiseringsuppgifterna.
Marknadsföraren skapar nu ett push-meddelande i **[!DNL Adone Journey Optimizer]** `>` **Meddelanden** mot den registrerade mobilappen.
1. Marknadsföraren organiserar en kundresa som definierar flödet av händelser och åtgärder. Om du vill skicka ett push-meddelande i ett skede av resan lägger marknadsföraren till en åtgärd av typen&quot;Meddelande&quot; och associerar den med det meddelande som skapades i föregående steg.
1. När en kundprofil kvalificerar sig för att ta emot ett push-meddelande av någon anledning, t.ex. om en händelse utlöser en händelse eller om ett segment kvalificeras, personaliseras meddelandet mot profilen, om tillämpligt.
1. Det personliga push-meddelandet skickas för vidare bearbetning till push-leveranstjänsten.
1. Tjänsten Push-leverans validerar autentiseringsuppgifterna för appen som är kopplad till meddelandet.
1. Meddelandet skickas till push-leverantörerna för leverans till mobilappen mot den specifika push-token och autentiseringsuppgifter.
1. Tryckerierna skickar en feedback som föreslår om meddelandet levererades till leverantören eller inte. Om det inte gör det är felmeddelandet en del av feedback. Den här feedback skickas till Adobe som kunden kan visa på sin resa [Live](reports/live-report.md) och [Globala rapporter](reports/global-report.md).
1. Under tiden skickar push-leverantörerna asynkront det slutförda push-meddelandet till mobilappen.
1. När kunden interagerar med meddelandet kan du spåra visningar som click/open som **Experience Events**. Tillägget Messaging visar API:er för att skicka spårningshändelser till Adobe Experience Platform mot kundens profil.

## Push-användarflöde

I det här diagrammet visas de olika stegen som ingår i konfigurationen av komponenterna som utgör strukturen för push-dataflödet. Åtgärdsobjekten har kategoriserats baserat på rollen som utför konfigurationen och komponenten som konfigureras. Som du ser måste du se till att konfigurationer och integreringar finns på plats i mobilappen **[!DNL Adobe Launch]** och **[!DNL Adobe Experience Platform]** innan du börjar skicka push-meddelanden med **[!DNL Adobe Journey Optimizer]**.

![](assets/user-flow.png)

Detaljerade steg för att konfigurera push-kanal och aktivera push-meddelanden i [!DNL Journey Optimizer] finns på [den här sidan](push-configuration.md).