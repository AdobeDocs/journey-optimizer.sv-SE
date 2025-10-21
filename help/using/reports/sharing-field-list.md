---
solution: Journey Optimizer
product: journey optimizer
title: Lista över steghändelsefält
description: Lista över steghändelsefält
feature: Journeys, Reporting
topic: Content Management
role: Engineer, Admin
level: Experienced
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 3%

---

# Lista över steghändelsefält {#sharing-field-list}

Fälten för steghändelser är ordnade efter kategori.

* Felsöka informationsfält
* Resefält
* Profilfält
* Tjänstehändelsefält

För attributet identityMap definieras den primära identiteten som standard som&quot;primär = true&quot;.

## debugInfo {#debuginfo-field}

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| requestId | Sträng | Begärande-ID som används av Journey Optimizer för att spåra flödet för en begäran. |

## resa {#journey-field}

Den här fältgruppen används i transportschemat (i relation till travelStepEvent). Den innehåller följande fält:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifierare för angiven resa |
| VersionID | Sträng | ID för reseversionen. Detta ID representerar identiteten på en resa |
| name | Sträng | Namn på resan |
| description | Sträng | Beskrivning av resan |
| version | Sträng | version, representerad som `major`.`minor` |

## profil {#profile-field}

Den här fältgruppen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profilens identitet, om sådan finns.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Profilidentifierare identifierar den profil som skickas/används under en resa. Exempel: foo@adobe.com. |
| namespace | Sträng | Det här fältet beskriver namnutrymmet som refereras av den profil som används i resan. Exempel: E-post, ECID |

## serviceEvents {#servicevents-field}

Den här mixinen innehåller alla fält som motsvarar ett profilexportjobb. Dessa händelser genereras per **Läs målgrupp**-aktivitet för att spåra livscykeln för målgruppsexportåtgärder (köade, startade, slutförda, fel). Till skillnad från vanliga steghändelser är serviceEvents inte knutet till enskilda profiler utan till själva Läs målnoden, vilket innebär att de kanske inte har någon associerad profilidentifierare.

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifieraren för det utlösta målgruppsexportjobbet |
| status | Sträng | Status för målgruppens exportjobb: köad, startad, avslutad |
| exportCountTotal | Heltal | Högsta möjliga värde för målgruppens exportjobb |
| exportCountRealized | Heltal | Det faktiska antalet målgrupper som exporterats via jobbet |
| exportCountFailed | Heltal | Antalet målgrupper som misslyckades vid export via jobbet |
| exportSegmentID | Sträng | Identifieraren för målgruppen som exporteras |
| eventType | Sträng | Händelsetypen anger om det är en felhändelse eller infohändelse: Info, Error |
| eventCode | Sträng | Felkoden som anger orsaken till motsvarande eventType |

Läs mer om eventTypes [i det här avsnittet](#discarded-events).

## stepEvents {#stepevents-field}

Den här kategorin innehåller de ursprungliga fälten för steghändelser. Se det här [avsnittet](../reports/sharing-legacy-fields.md).


## Felsöka ignorerade händelsetyper i steg om resan  {#discarded-events}

När du frågar efter steg för resa för poster med `eventCode = 'discard'` kan du stöta på flera eventTypes.

Nedan finns definitioner, vanliga orsaker och felsökningssteg för det vanligaste kastet `eventTypes`:

* **EXTERNAL_KEY_COMPUTATION_ERROR**: Det gick inte att beräkna en unik identifierare (extern nyckel) för kunden utifrån händelsedata.

  **Vanliga orsaker**: Kundidentifierare som saknas eller har fel format (t.ex. e-post, kund-ID) i händelsens nyttolast.

  **Felsökning**: Kontrollera händelsekonfigurationen för nödvändiga identifierare och se till att händelsedata är fullständiga och korrekt formaterade.

* **NO_INTERESTED_JOURNEYS_FOR_SEGMENTMEMBERSHIP_EVENT**: En segmentkvalificeringshändelse togs emot, men inga resor har konfigurerats för att svara på det här segmentet.

  **Vanliga orsaker**: Inga resor använder segmentet som utlösare, resor är i tillståndet Utkast/Stoppat eller segment-ID:n matchar inte.

  **Felsökning**: Kontrollera att minst en resa är aktiv och konfigurerad för segmentet och verifiera segment-ID:n.

* **JOURNEY_INSTANCE_ID_NOT_CREATE**: Det gick inte att skapa en reseinstans för kunden.

  **Vanliga orsaker**: Dubbletthändelser, hög händelsemängd, begränsningar för systemresurser.

  **Felsökning**: Implementera borttagning av dubbletter, undvik trafiktoppar, optimera resedesignen, kontakta supporten om den är permanent.

* **EVENT_WITH_NO_JOURNEY**: En händelse togs emot men ingen aktiv resa har konfigurerats för att svara på den

  **Vanliga orsaker**: Händelsenamn/ID matchar inte, resan har inte publicerats, fel sandlåda/organisation, testläge/profil matchar inte.

  **Felsökning**: Verifiera konfiguration av händelser och resor, kontrollera resans status och använd felsökningsverktyg.

* För utkast under pausade resor:

   * **PAUSED_JOURNEY_VERSION**: Ignorerar som inträffade vid ingången till resan
   * **JOURNEY_IN_PAUSED_STATE**: Ignorerar vilket som hände när profiler befinner sig på en resa

  Läs mer om de här händelserna och hur du felsöker dem i [Pausa en resa](../building-journeys/journey-pause.md#troubleshoot-profile-discards-in-paused-journeys).

## Ytterligare resurser

* [Datauppsättningsfrågeexempel - Resestegshändelse](../data/datasets-query-examples.md#journey-step-event).
* [Exempel på frågor - Händelsebaserade frågor](query-examples.md#event-based-queries).
* [Inbyggda schemaordlistor](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html)

