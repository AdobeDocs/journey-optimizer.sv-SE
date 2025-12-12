---
title: Kom igång för utvecklare
description: Som utvecklare kan du lära dig mer om hur du arbetar med Journey Optimizer
feature: Get Started
role: Developer
level: Experienced
exl-id: 5053dd4f-d050-415f-bc74-d6d061bdcbe1
source-git-commit: 2d699fe8a3320400dad2d5d962028d6e2a5425f8
workflow-type: tm+mt
source-wordcount: '1816'
ht-degree: 0%

---

# Kom igång för utvecklare {#get-started-developers}

Som **utvecklare** ansvarar du för att implementera och integrera [!DNL Adobe Journey Optimizer] i dina program och system. Du kan börja arbeta med [!DNL Adobe Journey Optimizer] när [systemadministratören](administrator.md) och [datateknikern](data-engineer.md) har gett dig åtkomst och förberett miljön.

## Din roll i Journey Optimizer ekosystem

Medan andra teammedlemmar konfigurerar Journey Optimizer via användargränssnittet fokuserar du på:

* **Implementera SDK:er** i mobil- och webbprogram
* **Skickar händelser** från dina program för att utlösa resor
* **Skapar API-slutpunkter** som Journey Optimizer kan anropa via anpassade åtgärder
* **Integrera** Journey Optimizer med befintliga system och befintlig infrastruktur
* **Testa och felsöka** dina implementeringar

Din [datatekniker](data-engineer.md) hanterar datamodeller, händelsekonfigurationer och datakällor. [Administratören](administrator.md) konfigurerar behörigheter och kanalkonfigurationer. [Marknadsförarna](marketer.md) utformar resorna och innehållet som använder implementeringarna.

Den här guiden beskriver de viktigaste tekniska implementeringsstegen för att komma igång med Journey Optimizer. Oavsett om du skapar mobilappar, webbupplevelser eller API-integreringar följer du avsnitten nedan för att konfigurera implementeringen.

## Förhandskrav {#prerequisites}

Innan du börjar implementeringen måste du se till att du har:

| Kategori | Krav |
|----------|-------------|
| **Tekniska färdigheter** | * Upplevelse med JavaScript (för Web SDK) eller Swift/Kotlin (för Mobile SDK)<br>* Förståelse av RESTful-API:er och JSON<br>* Förståelse med asynkron programmering och händelsestyrda arkitekturer<br>* Kunskap om organisationens programarkitektur |
| **Åtkomst och verktyg** | * Åtkomst till [Adobe Developer Console](https://developer.adobe.com){target="_blank"} för API-autentiseringsuppgifter<br>* Utvecklingsmiljö med tillgång till programmets kodbas<br>* Testverktyg som Postman för API-testning<br>* Webbläsarutvecklingsverktyg eller mobilfelsökningsverktyg |
| **Från andra teammedlemmar** | * Miljöåtkomst beviljas av [Administrator](administrator.md)<br>* XDM-scheman och händelsedefinitioner från [Data Engineer](data-engineer.md)<br>* Krav och användningsexempel från [Marketers](marketer.md) |

## Förstå den tekniska grunden {#technical-foundation}

Innan du börjar dyka upp i implementeringen bör du bekanta dig med de viktigaste tekniska begreppen:

1. **Adobe Experience Platform-integrering**: Journey Optimizer är inbyggt i Adobe Experience Platform. Genom att förstå den underliggande arkitekturen kan ni skapa mer effektiva implementeringar. Läs mer om [hur Journey Optimizer fungerar](../understanding-ajo.md).

1. **XDM-datamodeller**: Journey Optimizer använder Experience Data Model (XDM) för att strukturera händelse- och profildata. Som utvecklare måste du förstå hur du skickar data som överensstämmer med scheman som konfigurerats av [datateknikern](data-engineer.md). Läs mer om [XDM-scheman](../../data/get-started-schemas.md).

1. **Autentisering och säkerhet**: Alla implementeringar kräver korrekt autentisering. Lär dig hur du konfigurerar autentisering för SDK:er och API:er. Läs mer om [API-autentisering](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}.

## Konfigurera mobilappsintegreringar {#mobile-integration}

### Konfigurera Adobe Experience Platform Mobile SDK

Om du vill aktivera push-meddelanden, meddelanden i appen och andra mobilfunktioner integrerar du Adobe Experience Platform Mobile SDK i dina mobilappar.

1. **Installera och konfigurera Mobile SDK**: Följ [dokumentationen för Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} för att komma igång med SDK-integrering.

1. **Skapa en mobil egenskap**: Konfigurera en mobil egenskap i [!DNL Adobe Experience Platform Data Collection]. Lär dig hur du [skapar och konfigurerar en mobil egenskap](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

1. **Konfigurera push-meddelanden**:
   * För **iOS-appar**: Registrera din app med APN:er (Apple Push Notification service). Läs mer i [Apple dokumentation](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}.
   * För **Android-program**: Konfigurera Firebase Cloud Messaging för din Android-app. Läs mer i [Google dokumentation](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}.

1. **Testa din mobilintegration**: Använd [snabbstartsarbetsflödet för mobil introduktion](../../push/mobile-onboarding-wf.md) för att snabbt konfigurera och testa din mobilkonfiguration.

Detaljerade steg för att konfigurera push-meddelanden finns på [den här sidan](../../push/push-configuration.md).

### Implementera kodbaserade upplevelser (Mobile SDK)

För intern mobilappspersonalisering med kodbaserade upplevelser:

* Följ [den här självstudiekursen](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"} för implementering av Mobile SDK
* Granska exempelimplementeringar för [iOS](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"} och [Android](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"}

## Implementera webbupplevelser {#web-implementation}

### Konfigurera Adobe Experience Platform Web SDK

För webbaserade implementeringar är Web SDK den primära integrationspunkten:

1. **Installera SDK** för webben: Följ [implementeringshandboken för SDK för webben](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=sv-SE){target="_blank"} för att konfigurera SDK på webbplatsen.

1. **Konfigurera datastreams**: Skapa och konfigurera ett datastream i [!DNL Adobe Experience Platform Data Collection] med Journey Optimizer aktiverat. Läs mer i [datastreams-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=sv-SE){target="_blank"}.

1. **Aktivera push-meddelanden på webben** (valfritt): Konfigurera egenskapen [pushNotifications](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/pushnotifications){target="_blank"} i din SDK-webbkonfiguration och använd kommandot [sendPushSubscription](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendpushsubscription){target="_blank"} för att registrera push-prenumerationer.

### Implementera kodbaserade upplevelser (Web SDK)

Med kodbaserade upplevelser kan ni personalisera alla digitala kontaktytor:

1. **Välj implementeringsmetod**: Klient, server eller hybridserver. Granska [implementeringsexempel](../../code-based/code-based-implementation-samples.md) för varje metod.

1. **Definiera ytor**: Identifiera de platser i programmet där du vill leverera personaliserat innehåll. Läs mer om [ytkonfiguration](../../code-based/code-based-surface.md).

1. **Implementera innehållsåtergivning**: Använd Web SDK för att hämta och använda personaliseringsinnehåll. Se [kodbaserade självstudiekurser för implementering](../../code-based/code-based-decisioning-implementations.md).

1. **Skicka visnings- och interaktionshändelser**: Spåra när innehåll visas och när användare interagerar med det för analys och optimering.

Utforska [exempelimplementeringar på GitHub](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} för att se hur kodbaserade upplevelser fungerar.

Läs mer om att [komma igång med kodbaserade upplevelser](../../code-based/get-started-code-based.md).

## Implementera händelseströmning {#event-streaming}

### Skicka händelser för att utlösa resor

Som utvecklare implementerar du koden för att skicka händelser som utlöser resor. Din [datatekniker](data-engineer.md) konfigurerar händelsescheman och definitioner i Journey Optimizer.

1. **Förstå händelsens nyttolast**: Arbeta med din datatekniker för att hämta händelseschemat och den nödvändiga nyttolaststrukturen. Nyttolasten måste följa det XDM-schema som har konfigurerats. Lär dig mer om [schemakrav för händelser](../../event/experience-event-schema.md).

1. **Implementera händelsedirektuppspelning**: Skicka händelser till Adobe Experience Platform med [API:erna för direktuppspelning av inmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv){target="_blank"}. Lär dig [stegen för att skicka händelser](../../event/additional-steps-to-send-events-to-journey.md).

1. **Hantera händelsetyper**:
   * **Enhetshändelser**: Implementera händelse som skickas för personspecifika åtgärder (t.ex. knappklickning, slutförande av köp)
   * **Affärshändelser**: Skicka affärsrelaterade händelser (t.ex. lageruppdateringar, prisändringar)

1. **Testa händelseleverans**: Verifiera att händelser tas emot korrekt och utlösa resor som förväntat. Läs mer om [felsökning av händelser](../../building-journeys/troubleshooting-inbound.md).

**Exempelimplementering** för att skicka en händelse via API:

```javascript
POST https://{DATACOLLECTION_ENDPOINT}/collection/{DATASTREAM_ID}
Content-Type: application/json

{
  "header": {
    "datasetId": "{DATASET_ID}",
    "imsOrgId": "{ORG_ID}",
    "source": {
      "name": "Web SDK"
    }
  },
  "body": {
    "xdmMeta": {
      "schemaRef": {
        "id": "{SCHEMA_ID}"
      }
    },
    "xdmEntity": {
      "_id": "unique-event-id",
      "eventType": "purchase",
      "timestamp": "2024-01-01T12:00:00Z",
      // ... your event data
    }
  }
}
```

Lär dig mer om [att arbeta med resehändelser](../../event/about-events.md).

## Utveckla anpassade åtgärdsslutpunkter {#custom-actions}

Med anpassade åtgärder kan resor anropa API:er. Som utvecklare skapar du API-slutpunkterna som anpassade åtgärder anropar:

1. **Bygg din API-slutpunkt**: Skapa RESTful API-slutpunkter som Journey Optimizer anropar under körningen. Din slutpunkt bör:
   * Acceptera JSON-nyttolaster
   * Autentisera begäranden (OAuth, API-nyckel eller JWT)
   * Bearbeta begäranden inom lämpliga tidsgränser
   * Returnera svar i förväntat format

1. **Förstå anpassade åtgärdsfunktioner**: Anpassade åtgärder kan ansluta till tredjepartssystem som Epsilon, Slack, Firebase eller dina egna tjänster. Läs mer om [anpassade åtgärder](../../action/action.md).

1. **Arbeta med åtgärdskonfigurationer**: [Administratören](administrator.md) eller [Datateknikern](data-engineer.md) konfigurerar den anpassade åtgärden i Journey Optimizer och definierar API-slutpunkts-URL:en, autentiseringsmetoden och parametrarna. Du kommer att förse dem med din API-specifikation. Läs mer om [konfiguration för anpassad åtgärd](../../action/about-custom-action-configuration.md).

1. **Returnera användbara data**: Designa ditt API för att returnera data som kan användas i efterföljande steg. Läs mer om [åtgärdssvar](../../action/action-response.md).

1. **Implementeringsbegränsning**: Kontrollera att slutpunkterna kan hantera den förväntade volymen. Journey Optimizer har en gräns på 5 000 samtal/sekund, men systemet bör vara flexibelt. Läs om [begränsning och begränsning](../../configuration/external-systems.md).

**Exempel på användning**: [Skriva resehändelser till Experience Platform](../../building-journeys/custom-action-aep.md) med anpassade åtgärder.

## Arbeta med Journey Optimizer API:er {#apis}

Journey Optimizer erbjuder omfattande REST API:er för programmatisk åtkomst:

1. **Förstå API-funktioner**: Med Journey Optimizer API:er kan du skapa, läsa, uppdatera och ta bort olika resurser programmatiskt. Läs mer om [Journey Optimizer API:er](../../configuration/ajo-apis.md).

1. **Autentisering**: Följ [den här självstudiekursen](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} för att konfigurera API-autentisering med Adobe Developer Console.

1. **Utforska API-referenser**: Bläddra i den fullständiga API-dokumentationen och försök med API:er direkt i [API-referensen för Adobe Journey Optimizer](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}.

1. **API-utlösta kampanjer**: Skapa transaktionsmeddelanden med API-utlösta kampanjer. För scenarier med stora volymer (upp till 5000 TPS) kan du utforska [läget Högt dataflöde](../../campaigns/api-triggered-high-throughput.md) (kräver tilläggslicens).

1. **API:er för beslutshantering**: Använd specialiserade API:er för erbjudandehantering och beslutsfattande. Läs mer i [API-handboken för beslutshantering](../../offers/api-reference/getting-started.md).

## Testning och felsökning {#testing}

1. **Felsök SDK-implementering**: Använd Adobe Experience Platform Assurance för att inspektera SDK-händelser, validera datainsamling och felsöka integreringsproblem i realtid. [Läs mer om Assurance](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html?lang=sv-SE){target="_blank"}.

1. **Testa händelseleverans**: Verifiera att händelser från ditt program tas emot korrekt av Adobe Experience Platform och utlöser resor som förväntat. Övervaka händelseinmatning och validera nyttolaststrukturen.

1. **Validera API-integreringar**: Testa dina anpassade åtgärdsslutpunkter för att se till att de hanterar Journey Optimizer-begäranden korrekt, svarar inom tidsgränser och returnerar förväntade dataformat.

1. **Använd testläge med testprofiler**: Arbeta med din [datatekniker](data-engineer.md) för att få åtkomst till testprofiler och validera sedan implementeringen med testläge för resan. Lär dig hur du [testar resor](../../building-journeys/testing-the-journey.md).

1. **Övervaka SDK-loggar**: Aktivera felsökningsloggning i din SDK-implementering för att felsöka problem under utveckling:
   * **Mobile SDK**: Aktivera loggning för att visa SDK-händelser och API-anrop
   * **Webb-SDK**: Använd webbläsarkonsolen för att övervaka SDK-aktivitet

1. **Verifiera dataströmskonfiguration**: Kontrollera att dataströmmen är korrekt konfigurerad för att skicka data till Journey Optimizer. Kontrollera att händelser flödar genom datastream till rätt mål.

1. **Fråga efter resedata för analys**: Använd SQL-frågor på Data Lake för att analysera resesegmentshändelser, felsöka problem och övervaka prestanda för anpassade åtgärder. Utforska [frågeexempel för reseanalys](../../reports/query-examples.md) inklusive:
   * Orsaker till att ange/avsluta profil och kassera
   * Mätvärden för anpassade åtgärder (latens, genomströmning, fel)
   * Leverans av händelser och felmönster
   * Resursinstanstillstånd

## Avancerade ämnen för utvecklare {#advanced-topics}

### Arbeta med kontextuella data och berikning

* **Iterera över arrayer**: Använd Handlebars-syntax för att visa dynamiska listor från händelser, anpassade åtgärdssvar och datasetuppslag i meddelanden. Lär dig mer om [att iterera sammanhangsbaserade data](../../personalization/iterate-contextual-data.md).
* **Datauppsättningssökning**: Implementera datauppsättningssökningar för att berika resedata från Adobe Experience Platform-datauppsättningar. Samarbeta med din datatekniker när det gäller konfiguration. Lär dig mer om [datasökning](../../building-journeys/dataset-lookup.md).

### Arbeta med samtycke och styrning

Implementera policyer för datastyrning och samtycke i era integreringar:

* **Datastyrning**: Använd dataanvändningsprinciper för anpassade åtgärder. Läs mer om [datastyrning](../../action/action-privacy.md).
* **Hantering av samtycke**: Hantera inställningar för kundgodkännande i implementeringarna. Läs mer om [medgivande](../../action/consent.md).

### Optimering och bästa praxis

* **Takning och begränsning**: Förstå hastighetsbegränsningar och implementera lämplig begränsning. Läs mer om [externa system](../../configuration/external-systems.md).
* **Reseoptimering**: Följ bästa praxis för [reseoptimering](../../building-journeys/optimize.md).
* **Felhantering**: Implementera robust felhantering. Granska [felkoder](../../building-journeys/error-codes-reference.md) och [felsökningsguider](../../building-journeys/troubleshooting.md).

## Ytterligare resurser {#additional-resources}

* **Developer Console**: Använd [Adobe Developer Console](https://developer.adobe.com){target="_blank"} för att skapa integreringar och hantera API-autentiseringsuppgifter.
* **Exempelkod**: Utforska [exempelimplementeringar på GitHub](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"}.
* **Självstudievideor**: Lär dig med praktiska självstudiekurser på [Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=sv-SE){target="_blank"}.
* **Developer Community**: Kommunicera med andra utvecklare och få support i Adobe community-forum.

## Samarbeta mellan roller {#next-steps}

Implementeringsarbetet korsar med andra gruppmedlemmar:

>[!BEGINTABS]

>[!TAB Arbeta med datatekniker]

Samarbeta med [datatekniker](data-engineer.md) om data- och händelsekonfigurationer:

* Få de XDM-scheman och händelsestrukturer du behöver implementera
* Förstå vilka händelser du måste skicka och deras obligatoriska nyttolastformat
* Anpassa er efter datainsamlingskrav och standarder för datakvalitet
* Testa händelseleverans och datainmatning tillsammans

>[!TAB Arbeta med administratörer]

Samarbeta med [administratörer](administrator.md) om åtkomst och konfigurationer:

* Ange API-specifikationer för anpassade åtgärder som de konfigurerar
* Begär nödvändiga behörigheter och API-autentiseringsuppgifter
* Koordinera kanalkonfigurationskrav (t.ex. push-certifikat)
* Justera mot testmiljöer och sandlådestrategi

>[!TAB Arbeta med marknadsförare]

Samarbeta med [marknadsförare](marketer.md) om resekrav och testning:

* Förstå vilka användarinteraktioner som ska utlösa händelser
* Implementera spårning för innehållsprestanda och användarengagemang
* Stödja testning av resor med de implementerade funktionerna
* Felsöka problem med meddelandeleverans eller personalisering

>[!ENDTABS]

## Börja implementera

Vill du börja bygga? Välj ditt första implementeringsområde från avsnitten ovan:

1. **Mobilapp?** Börja med [Mobile SDK-integrering](#mobile-integration)
2. **Webbplats?** Börja med [Web SDK-konfiguration](#web-implementation)
3. **API-integrering?** Hoppa till [Arbeta med API:er](#apis)
4. **Anpassat system?** Kolla in [Anpassade åtgärder](#custom-actions)

Varje avsnitt innehåller länkar till detaljerad teknisk dokumentation, kodexempel och självstudiekurser som kan vägleda implementeringen.
