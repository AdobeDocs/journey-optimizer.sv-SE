---
solution: Journey Optimizer
product: journey optimizer
title: Felsöka live-aktiviteter
description: Lär dig hur du felsöker liveaktiviteter i Journey Optimizer för både enhetsanvändning och sändningsanvändning, inklusive problem med profiltoken, kampanjkonfiguration och leveransfel
role: User
level: Intermediate
source-git-commit: b71dbb0e4987cfc879a7b153d5c1453d6c220bf9
workflow-type: tm+mt
source-wordcount: '4503'
ht-degree: 0%

---


# Felsöka live-aktiviteter {#troubleshoot-mobile-live}

Med liveaktiviteter i Adobe Journey Optimizer kan du få dynamiska uppdateringar i realtid på iOS låsskärmar och Dynamic Islands. De kan bara aktiveras och hanteras via API-utlösta kampanjer.

**Använd ärendetyper:**

* **Enhet**: Individuellt riktade, transaktionella (API-utlösta transaktionskampanjer)
* **Sändning**: Målgruppsanpassad, massleverans (API-utlösta marknadsföringskampanjer)

En vanlig utmaning med Live Activity är när API-anropet för att utlösa eller uppdatera en Live Activity returnerar ett **lyckat svar (200 OK)**, men Live Activity inte visas eller uppdateras på användarens enhet. Den här frånkopplingen mellan API-bekräftelse och det faktiska enhetsbeteendet kan ske vid flera punkter i leveransflödet. Den här guiden ger en systematisk felsökningsmetod för att identifiera var leveransen misslyckas, där varje steg från API-förfrågningsvalidering till enhetsrendering undersöks.

## Förutsättningar

Innan du felsöker bör du kontrollera att du har:

* &#x200B;
  +++ Konfigurera en Assurance-session

  Konfigurera en **Assurance-session** för att hämta SDK-händelser och inspektera leveransflödet. Assurance ger synlighet i

   * Edge Network förfrågningar och svar
   * Profilkvalificeringshändelser
   * Push-tokenregistrering
   * Livscykelhändelser för aktiv aktivitet

  Lär dig hur du konfigurerar Assurance i [Adobe Experience Platform Assurance-dokumentationen](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/assurance).

  **Obs!** För iOS Live Activity kontrollerar du att appen körs på en fysisk iOS-enhet (iOS 16.1 eller senare) eller en Xcode-simulator (iOS 16.1 eller senare).

  +++

* &#x200B;
  +++ Samla in API-utlöst kampanjinformation

  Navigera till API Triggered Campaign i Journey Optimizer och hämta:

   * Kampanjnamn
   * Kampanj-ID hittades i URL:en eller kampanjegenskaperna
   * Kampanjversion, om tillämpligt
   * Surface configuration, iOS app surface used for Live Activity

  +++

* &#x200B;
  +++ Samla in API-begärandeinformation

  Spara följande när du gör ett API-anrop för att aktivera den aktiva aktiviteten:

   * Nyttolast för API-begäran, inklusive profilidentifierare och liveaktivitetsdata
   * API-svar inklusive statuskod, meddelande-ID, begäran-ID
   * Tidsstämpel för när API anropades
   * Slutpunkt används, t.ex. `/campaign/{CAMPAIGN_ID}/execute`

  +++

* &#x200B;
  +++ Identifiera testprofilen

  Hämta följande från din API-begäran:

   * Profilnamnrymd, t.ex. ECID, e-post, kund-ID
   * Profil-ID som används i API-anropet

  Se till att du kan slå upp den här profilen i Adobe Experience Platform. Lär dig hur du [söker efter en profil i Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide.html).

  +++

* &#x200B;
  +++ Enhet- och appinformation

  Samla följande från din testenhet:

   * Enhetsmodell, t.ex. iPhone 14 Pro
   * iOS
   * Programpaketidentifierare
   * APN:s push-token
   * Nätverksanslutningsstatus vid testning

  +++

## Vanliga scenarier

### Profil- eller push-tokenproblem {#profile-issue}

[!BADGE Gäller både enhetsanvändning och sändningsanvändning]{type=Positive}

API:t returnerar HTTP 200, men den aktiva aktiviteten visas inte. Vanliga orsaker:

* Profilen finns inte i Adobe Experience Platform.
* Push-token för aktiv aktivitet har inte synkroniserats med profilen.
* push-information för aktiv aktivitet synkroniseras men innehåller felaktig konfiguration, t.ex. fel `appId` eller `attributeType`.

**Obs! Exempel på sändningsanvändning**: Om vissa profiler i din publik saknar token kommer endast de profilerna inte att kunna ta emot den aktiva aktiviteten. Ta prov på flera profiler från er målgrupp för att diagnostisera tokenproblem. Detta gäller endast fjärrstarthändelser, inte uppdaterings- eller sluthändelser.

#### Förkontroller

* Krav för iOS-program:
   * iOS 16.1+
   * `NSSupportsLiveActivities` inställd på `YES` i `Info.plist`
   * `ActivityAttributes` har implementerats korrekt.
* SDK-integrering för mobiler:
   * Adobe Experience Platform Mobile SDK (messaging SDK 5.11.0+)
   * `Messaging.registerLiveActivities` implementerades och anropades med push-token för Live-aktivitet.

#### Felsökningssteg

1. &#x200B;
   +++ Verifiera att profilen finns i Adobe Experience Platform

   1. I Journey Optimizer går du till **Kund** `>` **Profiler**.
   1. Sök med namnutrymme och identitetsvärde från API-begäran.
   1. Om profilen inte hittas finns den inte eller så är intag inte slutfört. Skapa profilen eller vänta på intag innan Live-aktiviteten aktiveras.
   1. Om en profil hittas fortsätter du till steg 2 nedan för att kontrollera om push-token är synkroniserad.

      +++

1. &#x200B;
   +++ Kontrollera om push-token för aktiv aktivitet har synkroniserats

   Du kan använda Assurance för att verifiera tokenregistrering:

   1. I Assurance filtrerar eller söker du efter händelser **från listan** Händelser`eventType = "liveActivity.pushToStart"`.
   1. Markera **Händelsen** och kontrollera nyttolasten.
   1. Kontrollera att värden för token, appId och attributeType finns.
   1. Bekräfta om händelsen har skickats.

   Du kan även checka in Adobe Experience Platform-profilen.

   1. Gå till fliken **Händelser** från din **profil** i Adobe Experience Platform.
   1. Sök efter `liveActivity.pushToStart` händelser.
   1. Kontrollera den jämna tidsstämpeln och nyttolasten.

   Om inga händelser hittas kommer din mobilapp inte att anropa `Messaging.registerLiveActivity` korrekt. Du måste åtgärda integreringen med SDK.

   +++

1. &#x200B;
   +++ Validera tokeninformation i profil

   1. Gå till fliken **Attribut** från din **profil**.
   1. Sök efter `liveActivityPushNotificationDetails`.
   1. Verifiera tokenkonfigurationen:

      ```json
      {
        "liveActivityPushNotificationDetails": [
          {
            "appId": "com.example.myapp",
            "token": "abc123def456...",
            "platform": "apns",
            "denylisted": false,
            "attributeType": "OrderTrackingAttributes",
            "identity": {}
          }
        ]
      }
      ```

   **Verifiera varje fält:**

   | Fält | Krav | Vanligt problem |
   |-|-|-|
   | `appId` | Måste exakt matcha iOS bundle-ID | Felmatchning mellan dev/prod bundle-ID:n |
   | `attributeType` | Måste exakt matcha Swift `ActivityAttributes`-strukturnamnet (skiftlägeskänsligt) | Typo eller felaktigt strukturnamn |
   | `platform` | Måste vara `"apns"` eller `"apnsSandbox"` | Fel plattformsvärde |
   | `denylisted` | Måste vara `false` | Token markerad som ogiltig eller användaren avböjde |
   | `token` | Giltig APN:s push-token | Token har gått ut eller appen har installerats om |

   Om något fält är felaktigt: Uppdatera mobilappen, registrera om med `Messaging.registerLiveActivities`, vänta 5-10 minuter och kontrollera igen.

   Om `liveActivityPushNotificationDetails` saknas: Token har inte synkroniserats än. Vänta 5-10 minuter efter att händelsen `liveActivity.pushToStart` har visats i Assurance.

   +++

### Kampanjkonfiguration och nyttolastproblem {#payload-issues}

[!BADGE Gäller både enhetsanvändning och sändningsanvändning]{type=Positive}

Profilen finns med giltiga tokens, men Live Activity (Aktivitet) visas inte. Detta kan orsakas av:

* Fel konfiguration av yta eller kanal.
* Felaktig API-nyttolaststruktur.
* `content-state` och `attributes` matchar inte implementeringen av iOS `ActivityAttributes`.
* Inaktuell `timestamp` (kritisk för uppdatering/slut).

**Obs! Kampanjen måste vara** API-utlöst marknadsföring **(inte Transactional).** Nyttolasten använder `audience` i stället för den enskilda `profile`. I [det här avsnittet](#broadcast-config) finns information om den sändningsspecifika nyttolaststrukturen och i [Adobe Developer-dokumentationen](https://developer.adobe.com/journey-optimizer-apis/references/messaging#operation/postIMAudienceMessageExecution) för fullständiga API-specifikationer.

#### Förkontroller

* Campaign är **API-utlöst Transactional** (Unitary) eller **API-utlöst Marketing** (broadcast) och alternativet **High Throttput** måste **inte** vara aktiverat eftersom det är inkompatibelt med Live Activity.
* Kontrollera att profilen finns och att tokens synkroniseras korrekt med scenariot [ovan](#profile-issue).

#### Felsökningssteg

1. &#x200B;
   +++ Verifiera konfiguration av kampanjyta

   1. Öppna din **kampanj** i Journey Optimizer och gå till **Åtgärder** -menyn.
   1. Kontrollera din **Live-aktivitetskonfiguration**. Ytan måste konfigureras för iOS-appen med en källidentifierare som matchar `appId` i din profils `liveActivityPushNotificationDetails`. Om din profil till exempel har `"appId": "com.example.myapp"` måste ytan ha samma app som mål.
   1. Kontrollera att **aktivitetstypen** i kampanjkonfigurationen matchar exakt `attributeType` i din profils `liveActivityPushNotificationDetails`. Om din profil till exempel har `"attributeType": "FoodDeliveryLiveActivityAttributes"` måste kampanjen ange samma aktivitetstyp.

      +++

1. &#x200B;
   +++Validera API-nyttolaststruktur

   Kontrollera att nyttolasten följer rätt struktur när kampanjen körs via API.

   **Unitär nyttolast:**

   ```json
   {
     "campaignId": "your-campaign-id",
     "recipients": [{
       "type": "aep",
       "userId": "user@example.com",
       "namespace": "email",
       "context": {
         "requestPayload": {
           "aps": {
             "content-available": 1,
             "timestamp": 1756984054,
             "event": "start",
             "attributes-type": "FoodDeliveryLiveActivityAttributes",
             "content-state": { ... },
             "attributes": { ... }
           }
         }
       }
     }]
   }
   ```

   **Vanliga nyttolastproblem:**

   | Fält | Krav | Vanligt problem |
   |-|-|-|
   | `attributes-type` | Måste matcha kampanjaktivitetstyp och profil `attributeType` | Felmatchning eller stavfel |
   | `campaignId` | Måste matcha aktiverat kampanj-ID | Fel eller saknat kampanj-ID |
   | `content-available` | Måste vara `1` | Saknat eller felaktigt värde |
   | `event` | Måste vara `"start"`, `"update"` eller `"end"` | Ogiltig händelsetyp |
   | `timestamp` | Måste alltid vara den aktuella/senaste Unix-epoken i sekunder | Använda gammal/cachelagrad tidsstämpel |
   | `userId` / `namespace` | Måste matcha en befintlig profil i AEP | Profilidentifieraren matchar inte |

   **Kritisk: Använd alltid den senaste tidsstämpeln**

   * Fältet `timestamp` måste **alltid** vara den **aktuella Unix-epoken** (i sekunder) när varje API-anrop görs.
   * Detta gäller **alla händelsetyper**: `start`, `update` och **särskilt`end`**.
   * **Påverkan på uppdateringar/slutbegäranden**: Om en gammal eller gammal tidsstämpel används misslyckas uppdaterings- och slutbegäranden eller ignoreras av enheten.
   * Återanvänd **INTE** tidsstämplar från tidigare begäranden eller använd cachelagrade värden.
   * Generera en ny tidsstämpel för varje API-anrop.

   **Valfria fält (alla händelsetyper):**

   * `requestId`: Unik identifierare för spårning (rekommenderas).
   * `alert`: Objekt med `title` och `body` för meddelanden (användbart för att dra uppmärksamheten till uppdateringar).

   **Om `dismissal-date`:**

   * Valfritt fält som innehåller Unix epok-tid (sekunder).
   * **Endast relevant när`event: "end"`**.
   * Anger när den aktiva aktiviteten automatiskt ska tas bort från enheten.
   * Om den inte anges vid en sluthändelse förblir Live Activity synlig tills användaren stänger den.
   * Måste vara en framtida tidsstämpel (senare än `timestamp`).

     +++

1. &#x200B;
   +++ Justera nyttolast med iOS-implementering

   Kontrollera att API-nyttolasten matchar implementeringen av iOS-appen `ActivityAttributes`. Adobe SDK `LiveActivityAttributes`-protokollet utökar iOS `ActivityAttributes` och kräver en `liveActivityData`-egenskap.

   **Verifiera mappningen:**

   1. `ActivityAttributes` måste implementera Adobe `LiveActivityAttributes`-protokollet. Exempel:

      ```swift
      struct FoodDeliveryLiveActivityAttributes: LiveActivityAttributes {
       public struct ContentState: Codable, Hashable {
           var orderStatus: String
           var estimatedDeliveryTime: String
       }
      
       // Adobe SDK requirement
       var liveActivityData: LiveActivityData
      
       // Your custom attributes
       var restaurantName: String
      }
      ```

      **Obs!** Fältet `liveActivityData` är obligatoriskt för Adobe SDK och måste inkluderas i alla implementeringar.

   1. API-nyttolasten måste spegla iOS-strukturen:

      ```json
      {
        "aps": {
           "event": "start",
           "timestamp": 1756984054,
           "attributes-type": "FoodDeliveryLiveActivityAttributes",
           "content-state": {
           "orderStatus": "Preparing",
           "estimatedDeliveryTime": "20 mins"
        },
        "attributes": {
          "liveActivityData": {
            "liveActivityID": "order-12345"
          },
          "restaurantName": "Pizza Palace"
        }
        }
      }
      ```

   **Checklista för validering:**

   * Inkludera alla `ContentState`-fält i `content-state` (krävs för alla händelsetyper).
   * Inkludera alla `LiveActivityAttributes`-fält i `attributes` (endast starthändelser), inklusive:
      * `liveActivityData` (obligatoriskt; innehåller vanligen `liveActivityID` eller liknande identifierare)
      * Alla anpassade fält från din struktur
   * Matcha fältnamn exakt (skiftlägeskänsliga).
   * Matcha datatyper (String, Int, Bool, kapslade objekt).
   * Bevara den kapslade objektstrukturen.

   **Vanliga misstag:**

   | Problem | Effekt | Korrigera |
   |-------|--------|-----|
   | `liveActivityData` saknas i attribut | Aktiviteten kommer inte att starta | Inkludera alltid objektet `liveActivityData` i starthändelsen |
   | Obligatoriskt fält saknas i starthändelsen | Aktiviteten kommer inte att starta | Lägg till alla fält från iOS-struktur |
   | Fel fältnamn (typo/case) | Fältet ignorerades eller parsningsfel | Matcha iOS-fältnamn exakt |
   | Fel datatyp | Tolkningsfel | Matcha iOS-datatyper |
   | Saknat kapslat objekt | Ofullständiga data | Inkludera alla kapslade strukturer |
   | Inkluderar `attributes` i uppdatering/slut | Onödigt, men ignoreras vanligtvis | Inkludera bara `attributes` i starthändelsen |
   | Inaktuell tidsstämpel vid uppdatering/slut | Uppdatering/slut ignoreras av enheten | Generera alltid en ny tidsstämpel |

   Mer exempel finns på [Skapa Live-aktivitetssidan](create-mobile-live.md).

   +++

1. &#x200B;
   +++ Testa med Assurance

   Verifiera API-körning och nyttolast med Assurance:

   1. Öppna din Assurance-session.
   1. Kör API-anropet för att utlösa Live Activity.
   1. I **händelselistan** söker du efter:
      * Kampanjkörningshändelser.
      * Leveranshändelser för live-aktivitet.
      * Felhändelser för validering av nyttolast.
   1. Granska händelsenyttolaster för att verifiera:
      * Nyttolasten har bearbetats korrekt.
      * Inga valideringsfel inträffade.
      * Live Activity skickades till APN:er.

      +++

### Leveransfel och felanalys

[!BADGE Gäller både enhetsanvändning och sändningsanvändning]{type=Positive}

I det här scenariot har alla tidigare kontroller passerat:

* Det finns en profil med [giltiga push-tokens för Live-aktivitet](#profile-issue)
* Kampanjen är korrekt [konfigurerad med korrekt nyttolast](#payload-issues)
* [Uppdateringstoken synkroniseras](#token-not-synced) (endast för update/end-händelser, enhetsanvändning)

Men den aktiva aktiviteten visas, uppdateras eller avslutas fortfarande inte som förväntat. Problemet kan vara på Adobe leveranssystemnivå eller hos leverantören av push-meddelandetjänster (APN).

**Obs! Rapporter visar mätvärden för alla målgruppsmedlemmar.** Vissa profiler kan lyckas medan andra misslyckas.

**Förkontroller**

* **Tidigare scenarier har validerats:**
   * Profilen finns med rätt `liveActivityPushNotificationDetails`
   * Kampanjytan och aktivitetstypen är korrekta
   * API-nyttolasten är giltig med aktuell tidsstämpel
   * Uppdateringstoken synkroniseras (för update/end-händelser)

* **API-anrop har bekräftats:**

   * API-anropet returnerade HTTP 200 (lyckades)
   * Kampanj-ID och mottagarinformation är korrekta

#### Felsökningssteg

1. &#x200B;
   +++ Kontrollera kampanjrapporter

   1. Navigera till din **Live Activity Campaign**.
   1. Klicka på knappen **Rapporter**.
   1. Välj **Visa hela tidsrapporten**.
   1. Granska följande avsnitt:

      1. Kontrollera **Sending Statistics**-måtten för att förstå leveransframgången:

         | Mått | Vad det betyder | Vad du ska leta efter |
         |-|-|-|
         | Målinriktad | Antal profiler som är kvalificerade för målgruppen | Ska inkludera din testprofil |
         | Skickar | Totalt antal push-meddelanden har gjorts | Ska matcha dina API-anrop |
         | Levererat | Levereras till enheter | Jämför med Skicka för att se hur framgångsrik du är |
         | Skicka fel | Push-meddelanden som inte kunde skickas | Höga tal |
         | Skicka undantag | Profiler exkluderade av Adobe Journey Optimizer | Kontrollera om din profil har uteslutits |

      1. Om Skicka fel > 0, kontrollera tabellen **Felorsaker** för att se specifika felkoder och meddelanden:

         | Allmänt fel | Betydelse | Upplösning |
         |-|-|-|
         | Ogiltig token | Push-token är ogiltig eller har gått ut | Registrera om live-aktivitetstoken från enheten |
         | Token hittades inte | Ingen giltig token har associerats med profilen | Verifiera att `liveActivityPushNotificationDetails` finns |
         | APN avvisade | Tjänsten Apple Push Notification avvisade push | Kontrollera APN-certifikat, paket-ID, miljö |
         | Nätverkstimeout | Det går inte att nå APN:er | Ett tillfälligt problem. Försök med API-anropet igen |

      1. Om **Skicka undantag** > 0 kontrollerar du tabellen **Undantagna orsaker**:

         | Gemensamt undantag | Betydelse | Upplösning |
         |-|-|-|
         | Profilen har valts ut | Användaren har valt bort meddelanden | Kontrollera profilens medgivandestatus |
         | Token blocklist | Token markerad som ogiltig | Registrera om token eller kontrollera status för blockeringslista |
         | Profilen är inte giltig | Profilen uppfyller inte kampanjvillkoren | Granska regler för kampanjmålgrupper |

   Läs mer på rapportsidan för [Live-aktivitetskampanjen](../reports/campaign-global-report-cja-activity.md).

   +++

1. &#x200B;
   +++ Kontrollera meddelandefeedbackhändelser i profilen

   1. Navigera till **Kund** > **Profiler** i Journey Optimizer.
   1. Sök efter och öppna profilen.
   1. Välj fliken **Händelser**.
   1. Filtrera eller sök efter händelser med `eventType = "message.feedback"`.
   1. Sök efter feedbackhändelser som matchar typen `liveActivityID` och `event` för din Live Activity.
   1. Granska följande nyckelfält:

      | Fält | Möjliga värden | Vad det betyder |
      |-|-|-|
      | `feedbackStatus` | `sent`, `error`, `denylist` | Leveransresultat från tjänsteleverantör |
      | `serviceProvider` | `apns/apnsSandbox` | Bör vara APN för iOS Live Activity |
      | `errorCode` | Numerisk kod eller `null` | APN:er-specifik felkod om misslyckades |
      | `errorMessage` | Felbeskrivning eller `null` | Felmeddelande som kan läsas av människor |

   1. **Om `feedbackStatus: "error"`:**
      * Kontrollera `errorCode` och `errorMessage` för specifika APN-fel
      * Vanliga APN-fel inkluderar utgånen token, ogiltigt certifikat, fel paket-ID

   1. **Om ingen feedback-händelse hittades:**
      * Ett försök till push-meddelande har kanske inte gjorts
      * Kontrollera om profilen har uteslutits i kampanjrapporter enligt steg 1 ovan.

      +++

1. &#x200B;
   +++ Verifiera direktaktivitetsleverans till APN:er i Assurance

   1. Öppna din Assurance-session. Den måste vara aktiv under API-anropet.
   1. Kör API-anropet (starta, uppdatera eller avsluta).
   1. I **händelselistan** söker du efter leveranshändelser för Live-aktivitet.
   1. Sök efter händelser relaterade till APN:s push-leverans.
   1. Kontrollera om det finns följande indikatorer:
      * **Push-begäran till APN:er**: Bekräftar att Adobe har skickat push-åtgärden till Apple servrar
      * **APN-svar**: Visar om APN:er accepterade eller avvisade push-meddelanden
      * **Leveransstatus**: Indikation om slutförd eller fel
   1. Om problem hittas, se följande vanliga APN:s leveransproblem:

      | Problem | Symptom i Assurance | Upplösning |
      |-|-|-|
      | APN-certifikatet har upphört att gälla | Autentiseringsfel | Förnya och överföra nya APN-certifikat |
      | Fel miljö (dev vs prod) | Felmatchningsfel för token | Säkerställ att certifikatet matchar appens byggtyp |
      | Fel i paket-ID | Ogiltig källidentifierare | Verifiera att ID för certifikatpaket matchar app |
      | Token har upphört | InvalidToken-fel från APN:er | Registrera om live-aktivitetstoken |
      | Hastighetsbegränsning | För många förfrågningar | Minska API-anropsfrekvens |

      +++

1. &#x200B;
   +++ Fortsätt till ytterligare diagnostiska kontroller

   1. Kontrollera Live Activity Lifecycle-statistik i Campaign Report.

      Granska avsnittet **Live activity lifecycle** i kampanjrapporten:

      | Mått | Vad du ska kontrollera |
      |-|-|
      | Fjärrstart | Ska antalet API-utlösta starter visas |
      | Uppdateringar | Ska visa antal uppdateringshändelser |
      | Slutar | Ska visa antalet sluthändelser |
      | Antal summor | Generell volym för live-aktivitetshändelse |

      Om dessa värden är noll eller inte matchar dina API-anrop finns det ett leveransproblem mellan Adobe och APN.

   1. Om leveransen är klar men enheten inte visar den aktiva aktiviteten:

      * Kontrollera om det finns några aktivitetsfel i iOS enhetsloggar.
      * Kontrollera att programmet är i förgrunden eller i bakgrunden (inte avslutat).
      * Bekräfta att enheten är ansluten till nätverket.
      * Testa på flera enheter för att slippa enhetsspecifika problem.
      * Kontrollera att iOS är version 16.1 eller senare.

      +++

1. &#x200B;
   +++ Eskalering till Adobe Support

   Om du har slutfört alla steg och problemet inte är löst kontaktar du Adobe kundtjänst med:

   **Obligatorisk information:**

   * Kampanj-ID och namn
   * Namnutrymme för profil och ID
      * `liveActivityID` från API-nyttolast
   * Tidsstämplar för API-anrop
   * Skärmbilder av:
      * Kampanjrapporter (skicka statistik, felorsaker, orsaker som inte tagits med)
      * Profilhändelser (`liveActivity.updateToken`, `message.feedback`)
      * Assurance session med leveranshändelser
   * fullständig nyttolast för API-begäran
   * Information om APN-certifikat (utgångsdatum, miljö, paket-ID)

     +++

## Enhetliga scenarier

### Uppdateringstoken för aktiv aktivitet har inte synkroniserats{#token-not-synced}

Direktaktiviteten har startats på enheten, men efterföljande `update` eller `end` API-anrop (som returnerar HTTP 200) kan inte uppdatera eller stänga den aktiva aktiviteten. Detta inträffar när **token för uppdatering av Live Activity** inte synkroniseras korrekt till Adobe.

**Förstå uppdateringstokens**

När en Live Activity startas på en enhet genererar iOS en unik uppdateringstoken för den specifika Live Activity-instansen. Denna token krävs för:

* Skicka uppdateringar till den aktiva aktiviteten
* Fjärravsluta den aktiva aktiviteten

Varje instans av Live Activity har en egen unik uppdateringstoken. Adobe behöver denna token för att kunna leverera update- och end-händelser.

**Förväntat beteende**

För att update- och end-händelser ska fungera måste följande inträffa:

1. Aktiviteten har startats på enheten.
1. Enheten genererar en uppdateringstoken för den aktuella Live Activity-instansen.
1. Mobile SDK hämtar och skickar uppdateringstoken till Adobe.
1. Uppdateringstoken synkroniseras och lagras i Adobe.
1. Efterföljande API-anrop för uppdatering/slut använder denna token för leverans.

**Förkontroller:**

* **Användarbehörighet**: Första gången en Live-aktivitet startas på en enhet visas en systemfråga i iOS: &quot;Tillåt att [appnamn] tillhandahåller uppdateringar för Live-aktivitet?&quot; Användaren **måste trycka på Tillåt** för att uppdateringstoken ska genereras och synkroniseras. Om användaren trycker på&quot;Tillåt inte&quot; skapas inga uppdateringstokens och uppdatering/slut-begäranden misslyckas. Det här är en engångserbjudande per program.
* **Profil- och kampanjvalidering**: Fullständig [scenario 1](#profile-issue) och [scenario 2](#payload-issues) kontrollerar att profil, token och kampanjkonfiguration är korrekta.

#### Felsökningssteg

1. &#x200B;
   +++ Verifiera synkronisering av uppdateringstoken i Assurance

   1. Öppna din Assurance-session.
   1. Kontrollera att sessionen var aktiv när den aktiva aktiviteten startades på enheten.
   1. Filtrera eller sök efter händelser med `eventType = "liveActivity.updateToken"`.
   1. Markera händelsen och inspektera nyttolasten:

      * Kontrollera att fältet `token` innehåller en giltig uppdateringstokensträng.
      * Kontrollera att `liveActivityID` matchar din Live Activity-instans.
      * Bekräfta att `activityType` matchar din `attributes-type`.

   1. Om händelsen inte hittas:

      * Uppdateringstoken genererades eller hämtades inte av SDK.
      * Kontrollera om användaren har beviljat Live Activity-behörigheter.
      * Kontrollera att Live Activity faktiskt har startats på enheten.
      * Bekräfta att mobilen SDK är ordentligt integrerad för att hämta uppdateringstokens.

   1. Om en händelse hittas fortsätter du till steg 2.

      +++

2. &#x200B;
   +++ Verifiera uppdateringstoken i profilhändelser

   1. Navigera till **Kund** > **Profiler** i Journey Optimizer.
   1. Sök efter och öppna profilen.
   1. Välj fliken **Händelser**.
   1. Sök efter `liveActivity.updateToken` händelser.
   1. Kontrollera händelseinformationen:

      * Kontrollera att tidsstämpeln är aktuell (matchar när Live Activity startas).
      * Bekräfta att `token` och `liveActivityID` finns.
      * Kontrollera att `activityType` är korrekt.

   1. Om händelsen inte hittas i profilen:

      * Uppdateringstokenhändelsen kanske inte har importerats till profilen än.
      * Vänta 5-10 minuter och kontrollera igen.
      * Om det fortfarande saknas efter 15 minuter kan det bero på ett problem med att ta emot händelser.

   1. Om en händelse hittas har uppdateringstoken synkroniserats. Du kan fortsätta till steg 3.

      +++

3. &#x200B;
   +++ Kontrollera liveaktivitetens leveranshändelser i Assurance

   1. Kör ett uppdaterings- eller avslutnings-API-anrop i din Assurance-session.
   1. I **händelselistan** söker du efter leveranshändelser för live-aktivitet (APN:er push-händelser).
   1. Sök efter händelser som indikerar:
      * Push-meddelande har skickats till APN:er.
      * Svar från APN:er (lyckades eller fel).
      * Leveransbekräftelse.
   1. Om det finns en APN-leveranshändelse: push-meddelandet skickades. Om enheten fortfarande inte uppdateras kan problemet bero på enheten (appen hanterar inte push, nätverksproblem osv.).
   1. Om en APN:s leveranshändelse saknas: Uppdateringstoken kanske inte lagras korrekt eller är associerad med profilen i Adobe.
   1. Om det finns felhändelser: Sök i felinformationen efter specifika felorsaker (ogiltig token, APNs avvisade etc.).

      +++

## Sändningsspecifika scenarier

### Sändningskampanjkonfiguration och nyttolastproblem{#broadcast-config}

I det här avsnittet beskrivs felsökningsscenarier som är specifika för direktsändning av aktiviteter, som kräver andra felsökningsstrategier än enastående kampanjer.

När profiler har giltiga variabler men Live Activity inte visas, uppdateras eller fungerar som väntat för målgruppsmedlemmar beror problemet vanligtvis på något av följande:

* Kampanjen har inte konfigurerats som API-utlöst marknadsföring.
* API-nyttolasten använder en felaktig sändningsstruktur (`audience` eller `input-push-channel` saknas).
* Fälten `content-state` och `attributes` matchar inte implementeringen av iOS `ActivityAttributes`.
* `input-push-channel` skapades inte korrekt på Apple Developer Portal.

Det här felsökningsscenariot gäller för alla live-aktivitetshändelser i utsändningskampanjer: `start`, `update` och `end`.

**Förkontroller:**

* **Kampanjtyp**:
   * Verifiera att kampanjen har skapats som API-utlöst marknadsföring (krävs för utsändning/målgruppsbaserade kampanjer).
   * Bekräfta att en målgrupp har definierats i kampanjkonfigurationen.
* **Profil- och tokenvalidering**: Prova flera profiler från målgruppen för att verifiera att de har giltig `liveActivityPushNotificationDetails`. Följ [Scenario 1](#profile-issue) om du vill ha detaljerade valideringssteg.

#### Felsökningssteg

1. &#x200B;
   +++ Verifiera konfiguration av kampanjmålgrupp

   1. Öppna din **API-utlösta marknadsföringskampanj** i Journey Optimizer.
   1. Navigera till avsnittet **Målgrupp** och verifiera:
      * En målgrupp väljs ut för kampanjen.
      * Målgrupps-ID:t matchar det som används i API-nyttolasten.
      * Publiken innehåller de förväntade profilerna.
   1. Navigera till avsnittet **Åtgärder**.
   1. Kontrollera **Live-aktivitetskonfigurationen**:
      * Konfigurationen måste anges för iOS-programmet med rätt källidentifierare.
      * Aktivitetstypen måste matcha `attributes-type` i API-nyttolasten. Om nyttolasten till exempel innehåller `"attributes-type": "AirplaneTrackingAttributes"` måste kampanjen ange samma aktivitetstyp.

      +++

1. &#x200B;
   +++ Validera nyttolaststrukturen för broadcast API

   Nyttolaststrukturen för utsändning skiljer sig från enhetskampanjer. Kontrollera att nyttolasten följer rätt sändningsformat.

   **Obligatoriska fält för sändning:**

   ```json
   {
     "campaignId": "878a11d4-b519-47bd-8313-fecfee19857b",
     "audience": {
       "id": "8c3dbdea-2957-401f-acf0-3966fba1601e"
     },
     "context": {
       "requestPayload": {
         "aps": {
           "input-push-channel": "FEt0NgvLEfEAAOqA6AXdIQ==",
           "content-available": 1,
           "timestamp": 1771829292,
           "event": "update",
           "attributes-type": "AirplaneTrackingAttributes",
           "content-state": { ... },
           "attributes": { ... }
         }
       }
     }
   }
   ```

   **Vanliga nyttolastproblem:**

   | Fält | Krav | Vanligt problem |
   |-|-|-|
   | `campaignId` | Måste matcha det aktiverade ID:t för marknadsföringskampanj | Fel kampanj-ID eller transaktionskampanj |
   | `audience.id` | Måste matcha en befintlig målgrupp i AEP | Fel målgrupps-ID eller målgrupp finns inte |
   | `input-push-channel` | Krävs för sändning - Unik identifierare för den här sändningsinstansen | Saknas eller matchar inte `channelID` i `liveActivityData` |
   | `timestamp` | Måste alltid vara den aktuella/senaste Unix-epoken i sekunder | Använda gammal/cachelagrad tidsstämpel |
   | `event` | Måste vara `"start"`, `"update"` eller `"end"` | Ogiltig händelsetyp |
   | `attributes-type` | Måste matcha kampanjaktivitetstyp | Felmatchning eller stavfel |
   | `content-available` | Måste vara `1` | Saknat eller felaktigt värde |

   **Kritiska sändningsspecifika fält:**

   * **`input-push-channel`**:
      * Krävs för alla livesändningsaktiviteter.
      * Fungerar som en unik identifierare för den här specifika sändningsinstansen.
      * Alla profiler i målgruppen får liveaktiviteter som är länkade till den här kanalen.
      * Måste matcha `channelID` i `liveActivityData.channelID` (se steg 3).
      * Måste skapas för `appID` på Apple Developer Portal av klienten.
      * Endast kanaler som har skapats för den specifika `appID` kan användas för att sända direktaktivitet i den appen.

   * **`audience.id`**:
      * Måste referera till ett giltigt målgruppssegment som skapats i Adobe Experience Platform.
      * Alla profiler i den här målgruppen är avsedda för aktiviteten Live.
      * Publiken måste aktiveras och innehålla profiler med giltig `liveActivityPushNotificationDetails`.

   **Använd alltid den senaste tidsstämpeln:**

   * Fältet `timestamp` måste alltid vara den aktuella Unix-epoktiden (i sekunder) för varje API-anrop.
   * Detta krav gäller alla händelsetyper: `start`, `update` och `end`.
   * **Kritisk för uppdateringar/slut**: Om inaktuella tidsstämplar används misslyckas begäranden om uppdatering och slut.
   * Generera en ny tidsstämpel för varje broadcast API-anrop.

   **Valfria fält:**

   * `dismissal-date`: Unix-epok-tid för automatisk avstängning (endast relevant för `end` -händelser)
   * `alert`: Objekt med `title` och `body` för avisering

   Fullständiga API-specifikationer finns i [API-dokumentationen för Adobe Journey Optimizer Messaging](https://developer.adobe.com/journey-optimizer-apis/references/messaging).

   +++

1. &#x200B;
   +++ Justera innehållsläge, attribut och input-push-channel med iOS-implementering

   Kontrollera att nyttolastfälten matchar iOS-appens `ActivityAttributes`-implementering och att `input-push-channel` matchar `channelID` i `liveActivityData`.

   1. Granska din definition av iOS ActivityAttributes.

   Din anpassade `ActivityAttributes`-struktur måste implementera Adobe `LiveActivityAttributes`-protokoll:

   ```swift
   struct AirplaneTrackingAttributes: LiveActivityAttributes {
    public struct ContentState: Codable, Hashable {
        var journeyProgress: Int
    }
   
    // Adobe SDK requirement
    var liveActivityData: LiveActivityData
   
    // Your custom attributes
    var arrivalAirport: String
    var departureAirport: String
    var arrivalTerminal: String
   }
   ```

   1. Mappa iOS-fält för att sända API-nyttolast.

   Inkludera både `attributes` och `content-state` för alla händelser:

   ```json
         {
         "aps": {
          "input-push-channel": "FEt0NgvLEfEAAOqA6AXdIQ==",
          "event": "start",
          "timestamp": 1771829292,
          "attributes-type": "AirplaneTrackingAttributes",
          "content-state": {
            "journeyProgress": 0
          },
          "attributes": {
            "arrivalAirport": "DEL",
            "departureAirport": "MUM",
            "arrivalTerminal": "T1",
            "liveActivityData": {
              "channelID": "FEt0NgvLEfEAAOqA6AXdIQ=="
            }
          }
         }
         }
   ```

   **Kritisk: `input-push-channel` måste matcha`channelID`**

   * Värdet `input-push-channel` i roten av `aps` måste exakt matcha värdet `channelID` i `liveActivityData`.
   * I exemplet ovan är båda värdena `"FEt0NgvLEfEAAOqA6AXdIQ=="`.
   * Denna matchning länkar sändningsinstansen till liveaktivitetsdata.
   * En felmatchning orsakar leveransfel.

   **Nyckelvalideringspunkter:**

   * Inkludera alla `ContentState`-fält i `content-state` för alla händelsetyper.
   * Inkludera alla anpassade `LiveActivityAttributes`-fält i `attributes` endast för starthändelser.
   * För starthändelser måste `liveActivityData.channelID` matcha `input-push-channel`.
   * Fältnamnen är skiftlägeskänsliga och måste matcha exakt.
   * Datatyperna måste matcha (String, Int, Bool, kapslade objekt osv.).
   * Använd samma `input-push-channel` som den ursprungliga starthändelsen för update/end-händelser.

   **Vanliga misstag:**

   | Problem | Effekt | Korrigera |
   |-|-|-|
   | `input-push-channel` saknas | Sändningen fungerar inte | Lägg till ett unikt kanal-ID för varje sändning |
   | `input-push-channel` matchar inte `channelID` | Aktiviteten kommer inte att starta | Kontrollera att båda värdena är identiska |
   | Annat `input-push-channel` för uppdatering/slut | Uppdatering/slut når inte de aktiva aktiviteterna | Använd samma channel-id under hela livscykeln |
   | `liveActivityData.channelID` saknas | Live Activity kommer inte att länka till broadcast | Inkludera `channelID` i attribut för starthändelse |
   | Obligatoriskt fält saknas i starthändelsen | Aktiviteten kommer inte att starta | Lägg till alla fält från iOS-struktur |
   | Fel fältnamn (typo/case) | Fältet ignorerades eller parsningsfel | Matcha iOS-fältnamn exakt |
   | Inaktuell tidsstämpel vid uppdatering/slut | Uppdatering/slut ignoreras av enheter | Generera alltid en ny tidsstämpel |

   +++

1. &#x200B;
   +++ Testa med Assurance

   Verifiera API-körning och nyttolast med Assurance:

   1. Öppna din Assurance-session på en testenhet som ingår i publiken.
   1. Kör broadcast API-anropet.
   1. I **händelselistan** söker du efter:
      * Kampanjkörningshändelser.
      * Leveranshändelser för live-aktivitet.
      * Felhändelser som indikerar fel vid validering av nyttolast.
   1. Kontrollera händelsens nyttolaster för att bekräfta:
      * Nyttolasten bearbetades korrekt.
      * `input-push-channel` finns.
      * Inga valideringsfel inträffade.
      * Aktiva aktiviteter skickades till APN:er för målgruppsmedlemmar.

      +++

### Profilen finns inte i målgruppen eller i ögonblicksbilden av den gamla målgruppen

I det här scenariot är kampanjen och nyttolasten korrekt konfigurerade, men specifika profiler tar inte emot den aktiva aktiviteten. Detta inträffar vanligtvis när:

* Profilen är inte medlem i den målgrupp som är länkad till kampanjen.
* Publiken är en grupppublik och innehåller en föråldrad ögonblicksbild av profildata.
* Profilens Live Activity-token lades till nyligen men har ännu inte visats i målgruppsögonblicksbilden.

Detta felsökningsscenario gäller specifikt för utsändningar av kampanjer med målgruppsbaserad målinriktning.

**Förstå målgruppsutvärdering**

Adobe Experience Platform använder olika metoder för målgruppsutvärdering som avgör när profiluppdateringarna återspeglas i publiken:

| Metod | Utvärderingsfrekvens | Datahastighet | Bäst för |
|-|-|-|--|
| Grupp | En gång om dagen (schemalagd) | Kan vara upp till 24 timmar gammal | Stora målgrupper, icke-tidskänsliga |
| Direktuppspelning | Realtid (vid profiländringar) | Nästan i realtid för uppdaterade profiler | Tidskänslig, kräver profiluppdateringar |

**Förkontroller:**

* **Kampanj- och nyttolastvalidering**:
   * Slutför kontrollerna i [det här scenariot](#broadcast-config) för att säkerställa att kampanjen och nyttolasten är korrekta.
   * Kontrollera att `audience.id` i API-nyttolasten matchar kampanjkonfigurationen.
* **Profilen finns**: Bekräfta att profilen finns i AEP med giltig `liveActivityPushNotificationDetails`.

#### Felsökningssteg

1. &#x200B;
   +++ Verifiera att profilen finns i målgruppen

   Bekräfta först om den profil som ska ta emot den aktiva aktiviteten faktiskt är en del av målgruppen.

   1. Navigera till **Publiker** i Adobe Experience Platform.
   1. Sök efter och öppna målgruppen med hjälp av `audience.id` från din kampanj.
   1. Klicka på **Bläddra** eller **Exempelprofiler** för att visa målgruppsmedlemmar.
   1. Sök efter din testprofil med namnutrymmet och identitetsvärdet.
   1. **Om profilen inte hittas i målgruppen:**
      * Profilen uppfyller inte målgruppskriterierna eller segmentreglerna.
      * Granska målgruppsdefinitionen för att förstå kraven för medlemskap.
      * Uppdatera profildata eller målgruppsdefinition så att den inkluderar profilen.
      * Vänta tills publikutvärderingen är klar (se steg 2).
   1. **Om en profil hittas i målgruppen:** Gå till steg 2 för att kontrollera dataaktualitet.

      +++

2. &#x200B;
   +++ Kontrollera utvärderingstyp och schema för målgruppen

   Identifiera om publiken använder utvärdering av batch- eller direktuppspelning, eftersom detta avgör datans aktualitet.

   1. På sidan **Målgruppsinformation** ska du kontrollera **Utvärderingsmetoden**:
      * **Batch**: Utvärderades en gång om dagen enligt ett schema.
      * **Direktuppspelning**: Utvärderades i realtid när profiluppdateringar inträffar.
      * **Edge**: Utvärderades vid edge-platser i realtid.

   Följ felsökningsstegen som baseras på utvärderingsmetoden:

   **Om målgruppen använder batchutvärdering:**

   1. **Förstå begränsningar för gruppmålgrupper:**
      * Batchmålgrupper utvärderas en gång per dag (vanligen över natten).
      * Målgruppsbilden kan vara upp till 24 timmar gammal.
      * Om en profil nyligen har registrerat liveaktivitetstoken är det inte säkert att dessa tokens finns i den aktuella ögonblicksbilden.
      * Uppdateringar av profiler återspeglas inte förrän nästa grupputvärdering.

   1. **Kontrollera när senaste utvärdering utfördes:**
      * I målgruppsinformationen letar du efter tidsstämpeln **Senaste utvärdering**.
      * Om profilens `liveActivityPushNotificationDetails` uppdaterades efter den här tidsstämpeln har målgruppen inaktuella data.

   1. **Lös inaktuella data:**
      1. **Alternativ 1: Vänta på schemalagd batchutvärdering**
         * Nästa grupputvärdering innehåller uppdaterade profildata.
         * Detta sker automatiskt en gång om dagen.
         * Bäst för scenarier som inte är brådskande.

      1. **Alternativ 2: Utlös målgruppsutvärdering på begäran**
         1. Navigera till **Publiker** i AEP.
         1. Välj målgrupp.
         1. Klicka på **Utvärdera nu** eller **Aktivera vid behov**.
         1. Vänta tills utvärderingen är klar (detta kan ta flera minuter till timmar beroende på målgruppens storlek).
         1. Kontrollera att profilen nu har uppdaterat data i målgruppsögonblicksbilden.
         1. Försök igen med broadcast API-anropet.

   **Om målgruppen använder utvärdering av direktuppspelning:**

   1. **Förstå målgruppsbeteendet för direktuppspelning:**
      * Direktuppspelande målgrupper utvärderas i realtid när profiluppdateringar sker.
      * **Nya profiler**: Kvalificera kort efter att de har skapats om de uppfyller segmentvillkoren.
      * **Uppdaterade profiler**: Kvalificera eller diskvalificera kort efter att de har uppdaterats.
      * **Befintliga oförändrade profiler**: utvärderas inte igen om inte en uppdatering görs.

   1. **Identifiera problemet:**
      * Om en profil redan finns och uppfyller segmentvillkoren, men ingen uppdatering görs för den profilen, kanske den inte läggs till för en nyligen skapad målgrupp.
      * Profilen måste få en uppdatering (alla attributändringar) för att utlösa en ny utvärdering.

   1. **Lös problemet:**
      * **För nya profiler**: De kvalificerar sig automatiskt om villkoren uppfylls. Ingen åtgärd krävs.
      * **För befintliga profiler utan senaste uppdateringar:**
         * Gör en mindre uppdatering av profilen (t.ex. uppdatera ett tidsstämpelfält).
         * Detta utlöser utvärdering av direktuppspelning och lägger till profilen för publiken.
         * Alternativ: Använd en gruppmålgrupp eller en målgrupp för befintliga profiler.

      +++
