---
solution: Journey Optimizer
product: journey optimizer
title: Felsöka din livesändning
description: Lär dig hur du felsöker fel vid körning av livesändningar
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: felsökning, felsökning, resa, kontroll, fel
exl-id: fd670b00-4ebb-4a3b-892f-d4e6f158d29e
version: Journey Orchestration
source-git-commit: 22c3c44106d51032cd9544b642ae209bfd62d69a
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 23%

---

# Felsöka din livesändning {#troubleshooting-execution}

I det här avsnittet får du lära dig hur du felsöker resehändelser, kontrollerar om profiler har registrerats på din resa, hur de navigerar genom den och om meddelanden skickas.

Du kan även felsöka innan du testar eller publicerar en resa. Lär dig hur [på den här sidan](troubleshooting.md).

Om du använder inkommande åtgärder kan du lära dig att felsöka dem [på den här sidan](troubleshooting-inbound.md).

## Kontrollera att händelser skickas korrekt {#checking-that-events-are-properly-sent}

Startpunkten för en resa är alltid en händelse. Du kan utföra tester med verktyg som Postman.

Du kan kontrollera om API-anropet som skickas via dessa verktyg skickas korrekt eller inte. Om du får tillbaka ett fel innebär det att ditt anrop har ett problem. Kontrollera nyttolasten igen, rubriken (och särskilt ditt organisations-ID) och destinationswebbadressen. Du kan fråga administratören om vilken webbadress som ska användas.

Händelser skjuts inte direkt från källan till resor. Resorna förlitar sig faktiskt på Adobe Experience Platform API:er för direktuppspelning. Om det gäller händelserelaterade problem kan du därför läsa [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=sv-SE){target="_blank"} för felsökning av API:er för direktuppspelning.

Om din resa inte kan aktivera testläge med felet `ERR_MODEL_RULES_16` kontrollerar du att händelsen som används innehåller ett [identitetsnamnutrymme](../audience/get-started-identity.md) när du använder en kanalåtgärd.

Identitetsnamnutrymmet används för att unikt identifiera testprofilerna. Om e-post till exempel används för att identifiera testprofilerna bör identitetsnamnområdet **E-post** markeras. Om den unika identifieraren är telefonnumret bör identitetsnamnområdet **Telefon** väljas.

## Kontrollera om personer kommer in på resan {#checking-if-people-enter-the-journey}

Reserapporter mäter människors inträde på en resa i realtid.

Om du lyckas skicka evenemanget men inte ser något inträde på resan innebär det att något går fel mellan det skickade evenemanget och det mottagande evenemanget under resan.

Du kan börja felsöka med frågorna nedan:

* Är du säker på att resan, där du förväntar dig att den inkommande händelsen ska vara, är i testläge eller live?
* Sparade du händelsen innan du kopierade nyttolasten från dess förhandsvisning?
* Innehåller händelsens nyttolast ett händelse-ID?
* Angav du rätt URL?
* Har du följt nyttolastens struktur gällande API:er för strömningsinmatning med hjälp av förhandsgranskningen av nyttolastens struktur i händelsens konfigurationsfönster? Läs [den här sidan](../event/about-creating.md#preview-the-payload).
* Använde du rätt nyckelvärdepar i huvudet på din händelse?

  ```
  X-gw-ims-org-id - your organization's ID
  Content-type - application/json
  ```

## Kontrollera hur människor navigerar genom resan {#checking-how-people-navigate-through-the-journey}

Reserapportering mäter enskilda personers framsteg inom en resa. Det är enkelt att identifiera var och varför en person stoppats.

Här följer några saker att kontrollera:

* Är det på grund av ett tillstånd som utesluter personen i fråga? Villkoret kan till exempel vara &quot;kön = man&quot; och personen är en kvinna. Den här kontrollen kan utföras av en företagsanvändare om villkoret inte är för komplext.
* Är orsaken att ett anrop till en datakälla inte svarar? När resan är i testläge kan denna information visas i testlägets loggar. När resan är live kan en administratör testa direktanrop till datakällan och kontrollera svaret som tas emot. En administratör kan även göra dubbletter av resan och testa den.

## Kontrollera att meddelanden har skickats {#checking-that-messages-are-sent-successfully}

Om enskilda personer flödar rätt väg på resan men inte får meddelanden som de ska ta emot, kan du kontrollera om:

* [!DNL Journey Optimizer] har tagit hänsyn till begäran om att skicka meddelandet. Affärsanvändare kan komma åt meddelandet som ska skickas och kontrollera om tidpunkten för den senaste körningen motsvarar körningstiden för din resa. De kan även kontrollera de senaste API-anropen/händelserna som tagits emot.
* [!DNL Journey Optimizer] har skickat meddelandet. Kontrollera reserapporteringen för att se till att det inte finns några fel.

Om ett meddelande skickas via en anpassad åtgärd är det enda som kan kontrolleras under resan att anropet till den anpassade åtgärdens system leder till ett fel eller inte. Om anropet till det externa system som är kopplat till den anpassade åtgärden inte leder till ett fel, men inte leder till att ett meddelande skickas, bör vissa undersökningar utföras på den externa datorns sida.

## Duplicerade poster i resestegshändelser {#duplicate-step-events}

### Varför ser jag flera poster med samma reseinstans, profil, nod och begärande-ID?

När du frågar efter data om steg för resa kan du ibland se vad som verkar vara dubblettposter för samma körning. De här posterna har samma värden för:

* `profileID` - Profilens identitet
* `instanceID` - Identifieraren för reseinstansen
* `nodeID` - Den specifika resenoden
* `requestID` - Begärandeidentifieraren

De här posterna har dock **olika `_id` värden**, vilket är nyckelindikatorn som skiljer det här scenariot från faktisk datatypsduplicering.

### Vad orsakar detta beteende?

Detta inträffar på grund av autoskalningsåtgärder i bakomliggande system (kallas även&quot;ombalansering&quot;) i Adobe Journey Optimizer mikrotjänstarkitektur. Under perioder med hög belastning eller systemoptimering:

1. En händelse i ett steg på resan börjar bearbetas och loggas till datamängden för händelser i ett steg på resan
2. En automatisk skalning omfördelar arbetsbelastningen över tjänstinstanser
3. Samma händelse kan bearbetas om av en annan tjänstinstans, vilket skapar en andra loggpost med en annan `_id`

Det här är ett förväntat systembeteende och **fungerar som avsett**.

### Påverkar det körningen av resan eller budskapet?

**Nej.** Effekten är begränsad till enbart loggning. Adobe Journey Optimizer har inbyggda funktioner för borttagning av dubbletter i meddelandekörningslagret som säkerställer:

* Endast ett meddelande (e-post, SMS, push-meddelanden osv.) skickas till varje profil
* Åtgärder utförs bara en gång
* Körningen av resan fortskrider korrekt

Du kan verifiera detta genom att fråga `ajo_message_feedback_event_dataset` eller kontrollera körningsloggarna för åtgärder - du kommer att se att endast ett meddelande faktiskt skickades, trots de duplicerade händelseposterna för steg för resan.

### Hur kan jag identifiera de här fallen i mina frågor?

Vid analys av data för resesegmenthändelser:

1. **Kontrollera `_id` field**: True system-level-duplicates skulle ha samma `_id`. Olika `_id`-värden indikerar separata loggposter från det ombalanseringsscenario som beskrivs ovan.

2. **Verifiera meddelandeleverans**: Korsreferens med meddelandefeeddata för att bekräfta att endast ett meddelande skickades:

   ```sql
   SELECT
     timestamp,
     _experience.customerJourneyManagement.messageExecution.messageExecutionID,
     _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus
   FROM ajo_message_feedback_event_dataset
   WHERE
     _experience.customerJourneyManagement.messageExecution.journeyVersionID = '<journeyVersionID>'
     AND TO_JSON(identityMap) like '%<profileID>%'
   ORDER BY timestamp DESC;
   ```

3. **Gruppera efter unika identifierare**: När du räknar körningar använder du `_id` för att få korrekta antal:

   ```sql
   SELECT
     COUNT(DISTINCT _id) as unique_executions
   FROM journey_step_events
   WHERE
     _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>'
     AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID>'
   ```

### Vad ska jag göra om jag observerar det här?

Det här är normalt systembeteende och **ingen åtgärd krävs**. Dubblettloggningen tyder inte på något problem med konfigurationen av resan eller meddelandeleveransen.

Om du skapar rapporter eller analyser baserade på händelser i kundens steg:

* Använd `_id` som primärnyckel för att räkna unika händelser
* Korsreferens med datauppsättningar för meddelandefeedback vid analys av meddelandeleverans
* Observera att timinganalys kan visa poster grupperade inom några sekunder från varandra

Mer information om hur du frågar efter steg för resa finns i [Exempel på frågor](../reports/query-examples.md).
