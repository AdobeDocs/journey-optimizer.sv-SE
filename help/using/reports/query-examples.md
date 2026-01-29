---
solution: Journey Optimizer
product: journey optimizer
title: Exempel på frågor
description: Exempel på frågor
feature: Reporting, Journeys
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 26ad12c3-0a2b-4f47-8f04-d25a6f037350
source-git-commit: 4a15ee3ac4805880ce80f788e4619b501afb3d8b
workflow-type: tm+mt
source-wordcount: '3337'
ht-degree: 1%

---

# Exempel på frågor{#query-examples}

I det här avsnittet finns exempel som används ofta för att ställa frågor om händelser i resesteg i datasjön. Innan man går in på specifika användningsfall är det viktigt att förstå de nyckelidentifierare som används i data om resehändelser.

Se till att fälten som används i dina frågor har associerade värden i motsvarande schema.

## Nyckelidentifierare {#key-identifiers}

+++Vad är skillnaden mellan id, instanceID och profileID?

* id: unikt för alla steg-händelseposter. Två olika steghändelser kan inte ha samma ID.
* instanceID: instanceID är samma för alla steg-händelser som är kopplade till en profil inom en körning. Om en profil återgår till resan används ett annat instans-ID. Det nya instans-ID:t är samma för alla steg-händelser för den ommatade instansen (från start till slut).
* profileID: Profilens identitet motsvarar resenamnutrymmet.

>[!NOTE]
>
>I felsökningssyfte rekommenderar vi att du använder travelVersionID i stället för travelVersionName när du frågar efter resor. Läs mer om attribut för reseegenskaper [i det här avsnittet](../building-journeys/expression/journey-properties.md#journey-properties-fields).

+++

## Grundläggande användningsfall/vanliga frågor {#common-queries}

+++Hur många profiler som pågick en resa inom en viss tidsram

Den här frågan ger antalet distinkta profiler som har passerat den angivna resan under den angivna tidsramen.

_Datasjöfråga_

```sql
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>'
AND _experience.journeyOrchestration.stepEvents.nodeType='start'
AND _experience.journeyOrchestration.stepEvents.instanceType = 'unitary'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour);
```

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).

+++

+++Vilken regel gjorde att en profil inte gick in på en viss resa

Den här frågan returnerar den avvisade regeluppsättningen och regelinformationen när en profil hindras från att registrera en resa på grund av begränsningar eller behörighetskrav.

_Exempel_

```sql
SELECT 
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.ID AS RULESET_ID,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.name AS RULESET_NAME,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.rejectedRules.ID AS RULE_ID,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.rejectedRules.name AS RULE_NAME
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard'
AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID='3855072d-79c3-438a-a5c3-c77fd6843812'
AND
    timestamp >= to_date('2025-05-16')
```

+++

+++Vilken regel som gjorde att en profil inte tog emot en reseåtgärd

Den här frågan returnerar information om steghändelser för profiler som tagits bort under en resa och som inte fått någon reseåtgärd. Det hjälper till att identifiera varför profiler ignorerades på grund av affärsregler som tysta timbegränsningar.

_Datasjöfråga_

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.profileID,
    _experience.journeyOrchestration.stepEvents.instanceID,
    _experience.journeyOrchestration.stepEvents.journeyID,
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.actionExecutionError,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    DATE(timestamp),
    timestamp
FROM journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType = '<eventType>' AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>' AND
    _experience.journeyOrchestration.stepEvents.instanceID = '<instanceID>';
```

_Exempel_

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.profileID,
    _experience.journeyOrchestration.stepEvents.instanceID,
    _experience.journeyOrchestration.stepEvents.journeyID,
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.actionExecutionError,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    DATE(timestamp),
    timestamp
FROM journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'quietHours' AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID = '6f21a072-6235-4c39-9f6a-9d9f3f3b2c3a' AND
    _experience.journeyOrchestration.stepEvents.instanceID = 'unitary_089dc93a-1970-4875-9660-22433b18e500';
```


Frågeresultaten visar nyckelfält som hjälper till att identifiera orsaken till att en profil tas bort:

* **actionExecutionError** - Om värdet är `businessRuleProfileDiscarded` ignoreras profilen på grund av en affärsregel. Fältet `eventType` innehåller ytterligare information om vilken specifik affärsregel som orsakade borttagningen.

* **eventType** - Anger vilken typ av affärsregel som orsakade borttagningen:
   * `quietHours`: Profilen ignorerades på grund av konfigurationen för tysta timmar
   * `forcedDiscardDueToQuietHours`: Profilen tvingades ignoreras eftersom skyddsgränsen nåddes för profiler som hålls i tysta timmar

+++

+++Hur många fel som har inträffat på varje nod i en viss resa under en viss tid

Den här frågan räknar de distinkta profiler som upplevde fel vid varje nod i en resa, grupperade efter nodnamn. Den innehåller alla typer av körningsfel och hämtningsfel.

_Datasjöfråga_

```sql
SELECT
_experience.journeyOrchestration.stepEvents.nodeName,
count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour)
AND
  (_experience.journeyOrchestration.stepEvents.actionExecutionError is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionOriginCode is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionOriginError is not NULL
    OR _experience.journeyOrchestration.stepEvents.fetchError is not NULL
    OR _experience.journeyOrchestration.stepEvents.fetchErrorCode is not NULL
  )
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName;
```

+++

+++Hur många händelser som har tagits bort från en viss resa under en viss tidsperiod

Den här frågan räknar det totala antalet händelser som har tagits bort från en resa. Den filtrerar efter olika bortkastningshändelsekoder, inklusive fel i segmentexportjobb, borttagning av dispatcher och kassering av tillståndsdatorer.

_Datasjöfråga_

```sql
SELECT
count(_id) AS NUMBER_OF_EVENTS_DISCARDED
FROM journey_step_events
WHERE (
   _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'error'
   OR _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard'
   OR _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode = 'discard'
   OR _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode is not null
)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour);
```

+++

+++Vad som händer med en viss profil under en viss resa inom en viss tidsram

Den här frågan returnerar alla steg-händelser och tjänsthändelser för den angivna profilen och resan för den angivna tiden i kronologisk ordning.

_Datasjöfråga_

```sql
SELECT
timestamp,
_experience.journeyOrchestration.stepEvents.journeyVersionID,
_experience.journeyOrchestration.stepEvents.profileID,
_experience.journeyOrchestration.stepEvents.nodeName,
_experience.journeyOrchestration.stepEvents.journeyNodeProcessed,
_experience.journeyOrchestration.serviceType,
to_json(_experience.journeyOrchestration.profile),
to_json(_experience.journeyOrchestration.serviceEvents)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour)
AND
  (
    _experience.journeyOrchestration.stepEvents.profileID='<profileID>'
    OR _experience.journeyOrchestration.profile.ID='<profileID>'
  );
ORDER BY timestamp;
```

+++

+++Hur lång tid det tar mellan två noder 

Dessa frågor kan till exempel användas för att beräkna hur lång tid en vänteaktivitet tar. På så sätt kan du kontrollera att vänteaktiviteten är korrekt konfigurerad.

_Datasjöfråga_

```sql
WITH

START_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_START,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of node before wait activity>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
),

END_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_END,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of wait activity node>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
)

SELECT 

    T1.INSTANCE_ID AS INSTANCE_ID,
    T1.NODE_NAME AS START_NODE_NAME,
    T2.NODE_NAME AS END_NODE_NAME,
    DATEDIFF(millisecond,T1.TS_START,T2.TS_END) AS ELAPSED_TIME_MS
    
FROM

    START_NODE_INFO AS T1,
    END_NODE_INFO AS T2
    
WHERE

    T1.INSTANCE_ID = T2.INSTANCE_ID
```

_Datasjöfråga_

```sql
WITH

START_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_START,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of node before wait activity>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
),

END_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_END,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of wait activity node>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
)

SELECT 

    AVG(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS AVERAGE_ELAPSED_TIME,
    MIN(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS MIN_ELAPSED_TIME,
    MAX(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS MAX_ELAPSED_TIME
    
FROM

    START_NODE_INFO AS T1,
    END_NODE_INFO AS T2
    
WHERE

    T1.INSTANCE_ID = T2.INSTANCE_ID
```

+++

+++Så här kontrollerar du information om en serviceEvent 

Datauppsättningen för händelser i resesteg innehåller alla stepEvents och serviceEvents. stepEvents används vid rapportering, eftersom de avser aktiviteter (händelser, åtgärder osv.) i profiler under en resa. serviceEvents lagras i samma datauppsättning och de anger ytterligare information för felsökningsändamål, till exempel orsaken till att en upplevelsehändelse ignoreras.

Här är ett exempel på en fråga som kontrollerar detaljerna för en serviceEvent:

_Datasjöfråga_

```sql
SELECT

     _experience.journeyOrchestration.profile.ID, 
     _experience.journeyOrchestration.journey.versionID, 
     to_json(_experience.journeyOrchestration.serviceEvents) 

FROM journey_step_event 

WHERE _experience.journeyOrchestration.serviceType is not null;
```

## Meddelande-/åtgärdsfel {#message-action-errors}

+++Lista över alla fel som påträffats under resor

Med den här frågan kan du lista alla fel som påträffas under resor när ett meddelande/en åtgärd körs.

```sql
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) AS ERROR_COUNT 
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName = '<message-name>'
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
ORDER BY ERROR_COUNT DESC;
```

_Exempelutdata_

| actionExecutionError | ERROR_COUNT |
|---|---|
| TimedOut | 145 |
| ErrorConnecting | 87 |
| InvalidResponse | 23 |

Den här frågan returnerar alla olika fel som inträffade när en åtgärd kördes i en resa tillsammans med antalet gånger som varje fel inträffade, ordnade efter frekvens.

+++

## Profilbaserade frågor {#profile-based-queries}

+++Sök efter om en profil har angett en viss resa

Den här frågan kontrollerar om en viss profil har påbörjat en resa genom att räkna händelserna som är kopplade till den profilen och den aktuella kombinationen av resan.

```sql
SELECT count(distinct _id) AS EVENT_COUNT 
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' 
AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>';
```

_Exempelutdata_

| EVENT_COUNT |
|---|
| 3 |

Den här frågan returnerar det exakta antalet gånger en profil har påbörjat en resa. Ett resultat som är större än 0 bekräftar att profilen har passerat resan.

+++

+++Sök efter om en profil skickades ett visst meddelande

Metod 1: Om namnet på ditt meddelande inte är unikt i resan (det används på flera platser).

```sql
SELECT count(distinct _id) AS MESSAGE_SENT_COUNT 
FROM journey_step_events 
WHERE _experience.journeyOrchestration.stepEvents.nodeID = '<NodeId in the UI corresponding to the message>' 
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL 
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' 
AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>';
```

_Exempelutdata_

| MESSAGE_SENT_COUNT |
|---|
| 1 |

Ett resultat som är större än 0 bekräftar att meddelandeåtgärden har utförts. Den här frågan talar bara om för oss om meddelandeåtgärden har utförts på resans sida.

Metod 2: Om namnet på ditt meddelande är unikt under resan.

```sql
SELECT count(distinct _id) AS MESSAGE_SENT_COUNT 
FROM journey_step_events 
WHERE _experience.journeyOrchestration.stepEvents.nodeName = '<NodeName in the UI corresponding to the message>' 
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL 
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' 
AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>';
```

_Exempelutdata_

| MESSAGE_SENT_COUNT |
|---|
| 1 |

Frågan returnerar antalet gånger som meddelandet anropades för den valda profilen.

+++

+++Hitta alla meddelanden en profil har tagit emot de senaste 30 dagarna

Den här frågan hämtar alla slutförda meddelandeåtgärder för en viss profil under de senaste 30 dagarna grupperade efter meddelandenamn.

```sql
SELECT _experience.journeyOrchestration.stepEvents.nodeName AS MESSAGE_NAME, 
       count(distinct _id) AS MESSAGE_COUNT 
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL 
AND _experience.journeyOrchestration.stepEvents.nodeType = 'action' 
AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' 
AND timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
ORDER BY MESSAGE_COUNT DESC;
```

_Exempelutdata_

| MESSAGE_NAME | MESSAGE_COUNT |
|---|---|
| Välkomstmeddelande | 1 |
| Produktrekommendation | 3 |
| Cart Abandonment Reminder | 2 |
| Nyhetsbrev varje vecka | 4 |

Frågan returnerar listan med alla meddelanden tillsammans med antalet som anropats för den valda profilen.

+++

+++Hitta alla resor en profil har registrerat under de senaste 30 dagarna

Den här frågan returnerar alla resor som en viss profil har angivit under de senaste 30 dagarna, tillsammans med antalet poster för varje resa.

```sql
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName AS JOURNEY_NAME, 
       count(distinct _id) AS ENTRY_COUNT 
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeType = 'start' 
AND _experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' 
AND timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
ORDER BY ENTRY_COUNT DESC;
```

_Exempelutdata_

| JOURNEY_NAME | POST_COUNT |
|---|---|
| Welcome Journey v2 | 1 |
| Produktrekommendationer | 5 |
| Återengagemangskampanj | 2 |

Frågan returnerar listan med alla resenamn tillsammans med det antal gånger den efterfrågade profilen har angetts för varje resa.

+++

+++Antal profiler som är kvalificerade för en resa dagligen

Den här frågan ger en daglig uppdelning av antalet distinkta profiler som har passerat en resa under en viss tidsperiod.

```sql
SELECT DATE(timestamp) AS ENTRY_DATE, 
       count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS PROFILES_COUNT 
FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) DESC;
```

_Exempelutdata_

| POST_DATE | PROFILES_COUNT |
|---|---|
| 2024-11-25 | 1 245 |
| 2024-11-24 | 1 189 |
| 2024-11-23 | 15 340 |
| 2024-11-22 | 1 205 |
| 2024-11-21 | 1 167 |

Frågan returnerar, för den angivna perioden, antalet profiler som har angetts för resan varje dag. Om en profil anges via flera identiteter räknas den två gånger. Om återinträde är aktiverat kan antalet profiler dupliceras över olika dagar om det återgick till resan på en annan dag.

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).


+++

## Frågor relaterade till den lästa målgruppen {#read-segment-queries}

+++Tidsåtgång för att slutföra ett målgruppsexportjobb

Den här frågan beräknar varaktigheten för ett målgruppsexportjobb genom att hitta tidsskillnaden mellan när jobbet placerades i kö och när det slutfördes.

```sql
select DATEDIFF (minute,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'queued') ,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'finished')) AS export_job_runtime;
```

Frågan returnerar tidsskillnaden i minuter, mellan den tidpunkt då målgruppens exportjobb placerades i kö och den tidpunkt det slutligen avslutades.

+++

+++Antal profiler som har ignorerats under resan eftersom de var dubbletter

Den här frågan räknar antalet distinkta profiler som ignorerades på grund av instansdupliceringsfel under Läs publik-aktiviteten.

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_DUPLICATION'
```

Frågan returnerar alla profil-ID:n som ignorerades av resan eftersom de var dubbletter.

+++

+++Antal profiler som har ignorerats under resan på grund av ogiltigt namnutrymme

Den här frågan returnerar antalet profiler som ignorerades eftersom de hade ett ogiltigt namnutrymme eller saknades en identitet för det önskade namnutrymmet.

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_BAD_NAMESPACE'
```

Frågan returnerar alla profil-ID:n som ignorerades under resan eftersom de hade ett ogiltigt namnutrymme eller ingen identitet för det namnutrymmet.

+++

+++Antal profiler som har ignorerats under resan på grund av ingen identitetskarta

Den här frågan räknar de profiler som ignorerades eftersom de saknade en identitetskarta som krävs för körning av resan.

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NO_IDENTITY_MAP'
```

Frågan returnerar alla profil-ID:n som ignorerades under resan eftersom identitetskartan saknades.

+++

+++Antal profiler som ignorerades under resan eftersom resan var i testnoden och profilen inte var en testprofil

Den här frågan identifierar profiler som ignorerades när resan kördes i testläge, men profilen hade inte attributet testProfile inställt på true.

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NOT_A_TEST_PROFILE'
```

Frågan returnerar alla profil-ID:n som ignorerades under resan eftersom exportjobbet kördes i testläge, men profilen hade inte attributet testProfile inställt på true.

+++

+++Antal profiler som har ignorerats under resan på grund av ett internt fel

Den här frågan returnerar antalet profiler som ignorerades på grund av interna systemfel under körningen.

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_INTERNAL'
```

Frågan returnerar alla profil-ID:n som ignorerades av resan på grund av ett internt fel.

+++

+++Översikt över Läs målgrupp för en viss reseversion

Den här frågan innehåller en omfattande översikt över aktiviteten Läs målgrupp, inklusive information om segmentexportjobb, händelsekoder, status och antal profiler för alla faser i målgruppsexportprocessen.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator'
```

Den returnerar alla servicehändelser som hör till den angivna reseversionen. Vi kan följa verksamhetskedjan:

* ämnesskapande
* skapa exportjobb
* avslutande av exportjobb (med mätvärden för exporterade profiler)
* arbetarens avslutande av bearbetningen

Vi kan också upptäcka problem som:

* fel i ämne eller skapande av exportjobb (inklusive timeout för API-anrop för målgruppsexport)
* exporteringsjobb som kan fastna (när det gäller en viss reseversion har vi ingen händelse om att exportjobbet avslutas)
* arbetarutleveranser, om vi har tagit emot en händelse om att exportjobben har avslutats, men ingen arbetare har avslutat

VIKTIGT! Om ingen händelse returneras av frågan kan det bero på någon av följande orsaker:

* transportversionen inte har nått schemat
* Om reseversionen ska ha utlöst exportjobbet genom att anropa orchestrator, gick något fel i det överordnade flödet: problem vid resedistribution, affärshändelse eller problem med schemaläggare.

+++


+++Få läsfel för en viss reseversion

Den här frågan filtrerar efter specifika felhändelsekoder som är relaterade till fel i läsningen av målgrupper, t.ex. ämnesfel, API-anropsfel, timeout och misslyckade exportjobb.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
        'ERROR_TOPIC_CREATION',
        'ERROR_EXPORTJOB_APICALL',
        'ERROR_EXPORTJOB_APICALL_TIMEOUT',
        'ERROR_EXPORTJOB_FAILED'
    )
```

+++

+++Hämta bearbetningsstatus för exportjobb

Den här frågan hämtar bearbetningsstatus för målgruppsexportjobb, och visar om de lyckades eller misslyckades tillsammans med profilexportstatistik.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT 
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
        'INFO_EXPORTJOB_SUCCEEDED',
        'ERROR_EXPORTJOB_FAILED'
    )
```

Om ingen post returneras betyder det att antingen:

* ett fel uppstod när ämnet eller exportjobbet skapades
* exportjobbet fortfarande körs

+++

+++Få mätvärden för exporterade profiler, inklusive utkast och exportjobbstatistik för varje exportjobb

I den här frågan kombineras antalet ignorerade profiler med exportjobbstatistik för att ge en fullständig bild av målgruppens exportresultat för varje enskilt exportjobb.

_Datasjöfråga_

```sql
WITH
  
DISCARDED_EXPORTED_PROFILES AS (
  
    SELECT
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID AS EXPORTJOB_ID,
        count(distinct _experience.journeyOrchestration.profile.ID) AS DISCARDED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'ERROR_INSTANCE_DUPLICATION',
            'ERROR_INSTANCE_BAD_NAMESPACE',
            'ERROR_INSTANCE_NO_IDENTITY_MAP',
            'ERROR_INSTANCE_NOT_A_TEST_PROFILE',
            'ERROR_INSTANCE_INTERNAL'
        )
    GROUP BY
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID
 
),
  
SEGMENT_EXPORT_METRICS AS (
  
    SELECT
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID AS EXPORTJOB_ID,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal) AS TOTAL_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized) AS SUCCESS_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed) AS FAILED_EXPORTED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'INFO_EXPORTJOB_SUCCEEDED',
            'ERROR_EXPORTJOB_FAILED'
        )
    GROUP BY
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID
  
)
  
SELECT
    sum(T2.TOTAL_EXPORTED_PROFILES_COUNT),
    sum(T2.SUCCESS_EXPORTED_PROFILES_COUNT),
    sum(T2.FAILED_EXPORTED_PROFILES_COUNT),
    sum(T1.DISCARDED_PROFILES_COUNT)
FROM
    DISCARDED_EXPORTED_PROFILES AS T1,
    SEGMENT_EXPORT_METRICS AS T2
WHERE T1.EXPORTJOB_ID = T2.EXPORTJOB_ID
```

+++

+++Få aggregerade mätvärden (målgruppsexportjobb och utkast) för alla exportjobb

Den här frågan sammanställer övergripande mätvärden för alla exportjobb för en viss reseversion, vilket är användbart för återkommande resor eller affärsutlösta resor med återanvändning av ämnen.

_Datasjöfråga_

```sql
WITH
  
DISCARDED_EXPORTED_PROFILES AS (
  
    SELECT
        _experience.journeyOrchestration.journey.versionID AS JOURNEYVERSION_ID,
        count(distinct _experience.journeyOrchestration.profile.ID) AS DISCARDED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'ERROR_INSTANCE_DUPLICATION',
            'ERROR_INSTANCE_BAD_NAMESPACE',
            'ERROR_INSTANCE_NO_IDENTITY_MAP',
            'ERROR_INSTANCE_NOT_A_TEST_PROFILE',
            'ERROR_INSTANCE_INTERNAL'
        )
    GROUP BY
        _experience.journeyOrchestration.journey.versionID
),
  
SEGMENT_EXPORT_METRICS AS (
  
    SELECT
        _experience.journeyOrchestration.journey.versionID AS JOURNEYVERSION_ID,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal) AS TOTAL_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized) AS SUCCESS_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed) AS FAILED_EXPORTED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'INFO_EXPORTJOB_SUCCEEDED',
            'ERROR_EXPORTJOB_FAILED'
        )
    GROUP BY
          _experience.journeyOrchestration.journey.versionID
 
)
  
SELECT
    sum(T2.TOTAL_EXPORTED_PROFILES_COUNT),
    sum(T2.SUCCESS_EXPORTED_PROFILES_COUNT),
    sum(T2.FAILED_EXPORTED_PROFILES_COUNT),
    sum(T1.DISCARDED_PROFILES_COUNT)
FROM
    DISCARDED_EXPORTED_PROFILES AS T1,
    SEGMENT_EXPORT_METRICS AS T2
WHERE T1.JOURNEYVERSION_ID = T2.JOURNEYVERSION_ID
```

Den här frågan skiljer sig från den föregående.

Den returnerar den totala mätningen för en viss reseversion, oavsett vilka jobb som kan ha körts för den (vid återkommande resor utlöstes affärshändelser som utnyttjar återanvändning av ämnet).

+++

## Frågor relaterade till målgruppskvalifikation {#segment-qualification-queries}

+++Profilen ignoreras på grund av en annan målgruppsimplementering än den konfigurerade

Den här frågan identifierar profiler som har ignorerats eftersom deras status för målgruppsrealisering inte matchade kundens konfiguration för målgruppskvalifikation (t.ex. konfigurerad för &quot;enter&quot; men profilen &quot;avslutad&quot;).

_Datasjöfråga_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID
FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version id>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SEGMENT_REALISATION_CONDITION_MISMATCH'
```

_Exempel_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID
FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = 'a868f3c9-4888-46ac-a274-94cdf1c4159d' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SEGMENT_REALISATION_CONDITION_MISMATCH'
```

Den här frågan returnerar alla profil-ID:n som ignorerades av reseversionen på grund av felaktig målgruppsrealisering.

+++

+++Publikkvalificeringshändelser som ignorerats av någon annan orsak för en viss profil

Den här frågan hämtar alla målgruppsklassificeringar eller externa händelser som har tagits bort för en viss profil på grund av interna tjänstfel.

_Datasjöfråga_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID, _experience.journeyOrchestration.serviceEvents.dispatcher.projectionID
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID = '<profile-id>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

_Exempel_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID, _experience.journeyOrchestration.serviceEvents.dispatcher.projectionID
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID = 'mandee@adobe.com' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

Den här frågan returnerar alla händelser (externa händelser/målgruppsklassificeringshändelser) som har ignorerats på grund av någon annan anledning till en profil.

+++

## Händelsebaserade frågor {#event-based-queries}

+++Kontrollera om en affärshändelse har tagits emot för en resa

Den här frågan räknar antalet gånger en affärshändelse har tagits emot av en resa, grupperad efter datum, inom en angiven tidsram.

```sql
SELECT DATE(timestamp), count(distinct _id)
FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.nodeName = '<node-name-corresponding-to-business-event>' AND
_experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
WHERE DATE(timestamp) > (now() - interval '<last x hours>' hour)
```

+++

+++Kontrollera om en extern händelse för en profil ignorerades eftersom ingen relaterad resa hittades

Den här frågan identifierar när en extern händelse för en viss profil ignorerades eftersom ingen aktiv eller matchande resa har konfigurerats för att ta emot händelsen.

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp) FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID = '<eventId>' AND
_experience.journeyOrchestration.profile.ID = '<profileID>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'EVENT_WITH_NO_JOURNEY'
```

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).

+++

+++Kontrollera om en extern händelse för en profil har ignorerats av någon annan anledning

Den här frågan hämtar externa händelser som ignorerats för en viss profil på grund av interna tjänstfel, tillsammans med händelse-ID och felkod.

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp), _experience.journeyOrchestration.serviceEvents.dispatcher.eventID, _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID='<profileID>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID='<eventID>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).

+++

+++Kontrollera antalet händelser som ignoreras av stateMachine av errorCode

Den här frågan sammanställer alla händelser som ignoreras av transporttillståndsdatorn, grupperade efter felkod, för att hjälpa till att identifiera de vanligaste orsakerna till ignorering.

```sql
SELECT _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode, COUNT() FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' GROUP BY _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode
```

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).

+++

+++Kontrollera alla ignorerade händelser eftersom återinträde inte tillåts

Den här frågan identifierar alla händelser som har ignorerats eftersom en profil försökte att ange en resa igen när återinträde inte var tillåtet i resekonfigurationen.

```sql
SELECT DATE(timestamp), _experience.journeyOrchestration.profile.ID,
_experience.journeyOrchestration.journey.versionID,
_experience.journeyOrchestration.serviceEvents.stateMachine.eventCode 
FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' AND _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode='reentranceNotAllowed'
```

Lär dig hur du [felsöker ignorerade händelsetyper i travel_step_events](../reports/sharing-field-list.md#discarded-events).

+++

## Frågor för aktiveringsbara profiler {#engageable-profiles-queries}

Med hjälp av de här frågorna kan du övervaka och analysera hur många profiler du kan aktivera. En engagerande profil är en unik profil som har använts under resor eller kampanjer de senaste tolv månaderna. Läs mer om [Engagerbara profiler och licensanvändning](../audience/license-usage.md#what-is-engageable-profile).

>[!IMPORTANT]
>
>**Bästa tillvägagångssätt för att fråga efter engagerande profiler:**
>* Kontrollera att alla icke-aggregerade fält inkluderas i `GROUP BY`-satsen
>* Undvik att referera till datauppsättningar som inte finns i sandlådan - bekräfta datauppsättningsnamnen i plattformens användargränssnitt
>* Använd `distinct` när du räknar unika profiler för att undvika dubbletter i identitetsnamnutrymmen
>* När du använder `LIMIT` placerar du den i slutet av frågan efter `ORDER BY` -satser

+++Räkna unika profiler som används av en viss resa

Den här frågan returnerar antalet distinkta profiler som har använts under en viss resa, vilket ökar antalet profiler som kan aktiveras.

```sql
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS ENGAGED_PROFILES
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>'
AND timestamp > (now() - interval '12' month);
```

Den här frågan hjälper dig att förstå hur många unika profiler en viss resa har bidragit till antalet [aktiverbara profiler](../audience/license-usage.md) under de senaste 12 månaderna.

+++

+++Antal profiler per resa de senaste 12 månaderna

Den här frågan visar antalet unika profiler som använts av varje resa i din organisation under de senaste 12 månaderna, vilket hjälper dig att identifiera vilka resor som bidrar mest till ditt [engagerande profilantal](../audience/license-usage.md).

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.journeyVersionID AS JOURNEY_VERSION_ID,
    _experience.journeyOrchestration.stepEvents.journeyVersionName AS JOURNEY_NAME,
    count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS ENGAGED_PROFILES
FROM journey_step_events
WHERE timestamp > (now() - interval '12' month)
GROUP BY 
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.journeyVersionName
ORDER BY ENGAGED_PROFILES DESC;
```

_Exempelutdata_

| JOURNEY_VERSION_ID | JOURNEY_NAME | ENGAGED_PROFILES |
|---|---|---|
| 67b14482-143e-4f83-9cf5-cfec0fca3d26 | Välkomstkampanj v2 | 125 450 |
| a3c21b89-456d-4e21-b8f3-9a8e7c6d5432 | Produktlansering | 98 230 |
| f9e8d7c6-b5a4-3210-9876-543210fedcba | Återengagemang - flöde | 45 670 |

Detta hjälper er att identifiera vilka resor som engagerar de flesta profiler och som bidrar mest till att antalet engagerande profiler ökar.

>[!NOTE]
>
>Den här frågegruppen sorteras efter både `journeyVersionID` och `journeyVersionName`. Båda fälten måste inkluderas i `GROUP BY`-satsen eftersom de är markerade i frågan. Om du utelämnar fält från `GROUP BY`-satsen misslyckas frågan.

+++

+++Räkna profiler som använts av resor dagligen under de senaste 30 dagarna

Den här frågan ger en daglig uppdelning av nyligen engagerade profiler, vilket hjälper dig att identifiera toppar i [antal aktiverbara profiler](../audience/license-usage.md).

```sql
SELECT 
    DATE(timestamp) AS ENGAGEMENT_DATE,
    count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS ENGAGED_PROFILES
FROM journey_step_events
WHERE timestamp > (now() - interval '30' day)
GROUP BY DATE(timestamp)
ORDER BY ENGAGEMENT_DATE DESC;
```

_Exempelutdata_

| ENGAGEMENT_DATE | ENGAGED_PROFILES |
|---|---|
| 2024-11-25 | 8 450 |
| 2024-11-24 | 7 820 |
| 2024-11-23 | 125 340 |
| 2024-11-22 | 9 230 |
| 2024-11-21 | 8 670 |

Med den här typen av utdata kan du övervaka dagliga trender och identifiera när ett stort antal profiler används. I det här exemplet visar den 23 november en betydande topp (125 340 profiler) jämfört med det vanliga dagliga engagemanget (~8 000 profiler), vilket skulle göra det värt att undersöka vilken resa eller kampanj som orsakade ökningen av antalet [engagerande profiler](../audience/license-usage.md).

+++

+++Identifiera resor som nyligen engagerade stora målgrupper

Den här frågan hjälper dig att identifiera vilka resor som har engagerat ett stort antal nya profiler under de senaste tidsperioderna, vilket kan förklara plötsliga ökningar i antalet [aktiverbara profiler](../audience/license-usage.md).

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.journeyVersionID AS JOURNEY_VERSION_ID,
    _experience.journeyOrchestration.stepEvents.journeyVersionName AS JOURNEY_NAME,
    DATE(timestamp) AS ENGAGEMENT_DATE,
    count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS ENGAGED_PROFILES
FROM journey_step_events
WHERE timestamp > (now() - interval '7' day)
AND _experience.journeyOrchestration.stepEvents.nodeType = 'start'
GROUP BY 
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.journeyVersionName,
    DATE(timestamp)
HAVING count(distinct _experience.journeyOrchestration.stepEvents.profileID) > 1000
ORDER BY ENGAGEMENT_DATE DESC, ENGAGED_PROFILES DESC;
```

_Exempelutdata_

| JOURNEY_VERSION_ID | JOURNEY_NAME | ENGAGEMENT_DATE | ENGAGED_PROFILES |
|---|---|---|---|
| 67b14482-143e-4f83-9cf5-cfec0fca3d26 | Black Friday Campaign | 2024-11-23 | 125 340 |
| a3c21b89-456d-4e21-b8f3-9a8e7c6d5432 | Produktlansering | 2024-11-22 | 45 230 |
| f9e8d7c6-b5a4-3210-9876-543210fedcba | Nyhetsbrev - helgdag | 2024-11-21 | 32 150 |

Den här frågan filtrerar efter resor som använt mer än 1 000 profiler per dag de senaste 7 dagarna. Utdata visar vilka specifika resor och datum som ligger bakom stora profilåtaganden. Justera tröskelvärdet för `HAVING`-satsen baserat på dina behov (ändra t.ex. `> 1000` till `> 10000` för större tröskelvärden).

+++

+++Totalt antal unika profiler som använts under alla resor de senaste tolv månaderna

Den här frågan innehåller ett antal unika profiler som använts under alla resor de senaste 12 månaderna, vilket ger dig en översikt över ditt resebaserade engagemang.

```sql
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID) AS TOTAL_ENGAGED_PROFILES
FROM journey_step_events
WHERE timestamp > (now() - interval '12' month);
```

_Exempelutdata_

| TOTAL_ENGAGED_PROFILES |
|---|
| 2 547 890 |

Detta enda nummer representerar det totala antalet unika profiler som har använts av minst en resa under de senaste 12 månaderna.

>[!NOTE]
>
>Den här frågan räknar distinkta profil-ID:n i datauppsättningen för kundstegshändelser. Det faktiska antalet profiler som kan aktiveras och som visas på [kontrollpanelen för licensanvändning](../audience/license-usage.md) kan skilja sig något, eftersom den även innehåller profiler som används via kampanjer och andra Journey Optimizer-funktioner bortom resor.

+++

## Vanliga resebaserade frågor {#journey-based-queries}

+++Antal dagliga aktiva resor

Den här frågan returnerar ett dagligt antal unika reseversioner som har haft aktivitet, vilket hjälper dig att förstå mönster för körning av resan över tid.

```sql
SELECT DATE(timestamp) AS ACTIVITY_DATE, 
       count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) AS ACTIVE_JOURNEYS
FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) DESC;
```

_Exempelutdata_

| ACTIVITY_DATE | ACTIVE_JOURNEYS |
|---|---|
| 2024-11-25 | 12 |
| 2024-11-24 | 15 |
| 2024-11-23 | 14 |
| 2024-11-22 | 11 |
| 2024-11-21 | 13 |

Frågan returnerar, för den angivna perioden, antalet unika resor som utlöstes varje dag. En enda resa som utlöses på flera dagar räknas en gång om dagen.


+++

## Frågor om reseinstanser {#journey-instances-queries}

+++Antal profiler i ett specifikt tillstånd vid en viss tidpunkt

I den här frågan används CTE (Common Table Expressions) för att identifiera profiler som väntar på en viss nod i en resa genom att söka efter profiler som passerat genom noden men som ännu inte har gått vidare till nästa nod.

_Datasjöfråga_

```sql
WITH
 
INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS (
 
    SELECT
        STEP_EVENTS.timestamp AS TS,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID AS ID
    FROM
        journey_step_events AS STEP_EVENTS
    WHERE
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>'
 
),
 
INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS (
 
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME = '<specific node name>' AND
        <filter on time for profile in specific node>
 
),
 
INSTANCES_PASSED_IN_NEXT_NODES AS (
     
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME in (<list of next node names from the specific node>)
 
),
 
INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS (
 
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1
 
    EXCEPT
     
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NEXT_NODES AS T1
 
)
 
SELECT
    DATE_FORMAT(T1.TS,'<date pattern>') AS DATETIME,
    count(T1.ID) AS INSTANCES_COUNT
FROM
    INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1,
    INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS T2
WHERE
    T1.ID = T2.ID
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

_Exempel_

```sql
WITH
 
INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS (
 
    SELECT
        STEP_EVENTS.timestamp AS TS,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID AS ID
    FROM
        journey_step_events AS STEP_EVENTS
    WHERE
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009'
 
),
 
INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS (
 
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME = 'slack_bso_tests - test1' AND
        T1.TS > (now() - interval '18 hour')
 
),
 
INSTANCES_PASSED_IN_NEXT_NODES AS (
     
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME in ('slack_bso_tests - test2')
 
),
 
INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS (
 
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1
 
    EXCEPT
     
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NEXT_NODES AS T1
 
)
 
SELECT
    DATE_FORMAT(T1.TS,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(T1.ID) AS INSTANCES_COUNT
FROM
    INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1,
    INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS T2
WHERE
    T1.ID = T2.ID
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

+++

+++Hur många profiler som slutade resan under den angivna tidsperioden

Den här frågan räknar vilka resinstanser som avslutats under en angiven tidsperiod, inklusive avslut på grund av slutförande, fel, timeout eller fel vid capping.

_Datasjöfråga_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    <timestamp filter>
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

_Exempel_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    STEP_EVENTS.timestamp > (now() - interval '22 hour')
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

+++

+++Hur många profiler slutade resan under den angivna tidsperioden med nod/status

Den här frågan innehåller en detaljerad beskrivning av resans avslutningar, som visar nodnamnet och avslutningsstatusen för varje avslutad instans för att hjälpa till att identifiera var och varför profiler lämnade resan.

_Datasjöfråga_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus AS EXIT_STATUS,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    <timestamp filter>
GROUP BY
    DATETIME, NODE_NAME, EXIT_STATUS
ORDER BY
    DATETIME DESC
```

_Exempel_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus AS EXIT_STATUS,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    STEP_EVENTS.timestamp > (now() - interval '22 hour')
GROUP BY
    DATETIME, NODE_NAME, EXIT_STATUS
ORDER BY
    DATETIME DESC
```

+++

## Frågor relaterade till prestandamått för anpassade åtgärder {#query-custom-action}

+++ Totalt antal lyckade anrop, fel och begäranden per sekund för varje slutpunkt under en viss tidsperiod

Den här frågan innehåller prestandamått för anpassade HTTP-åtgärder, inklusive totalt antal anrop, slutförda anrop, antal fel per typ (4xx, 5xx, timeouts, cApped) och genomströmning i begäranden per sekund för varje slutpunkt.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (<actionExecutionOriginStartTime filter> OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND <timestamp filter>))
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND timestamp > (now() - interval '1' day)))
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++ Tidsserie med lyckade anrop, fel och genomströmning för varje slutpunkt under en viss tidsperiod

Den här frågan ger samma prestandamått som föregående fråga men är ordnad som en tidsserie, och visar hur slutpunktsprestanda varierar över tid med en minuts granularitet.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(COALESCE(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, timestamp), 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (<actionExecutionOriginStartTime filter> OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND
           <timestamp filter>))
GROUP BY 
    ENDPOINT, SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(COALESCE(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, timestamp), 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND
           timestamp > (now() - interval '1' day)))
GROUP BY 
    ENDPOINT, SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++Svarsfördröjning för varje slutpunkt vid 50, 95, 99 och 99,9:e percentilen under en specifik tidsperiod

Den här frågan beräknar responstidens för anpassade åtgärdsslutpunkter, vilket hjälper dig att förstå fördröjningsfördelningen och identifiera prestandavärden vid olika percentiltröskelvärden.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS SUCCESSFUL_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS SUCCESSFUL_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++Tidsserie för svarstidsfördröjning i procent för varje slutpunkt under en viss tidsperiod

Den här frågan tillhandahåller fördröjningspercentiler ordnade som en tidsserie, så att du kan spåra hur svarstiderna för slutpunkter ändras över tid på olika percentilnivåer.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,    
    COUNT(1) AS SUCCESSFUL_CALLS,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,    
    COUNT(1) AS SUCCESSFUL_CALLS,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++ Väntetid i kö på strypta slutpunkter vid 50:e och 95:e percentilen under en viss tidsperiod

Den här frågan analyserar köväntetider för begränsning av slutpunkter, vilket visar väntetiderna i 50 och 95:e percentilen så att du lättare kan förstå hur strypningen påverkar dina anpassade åtgärder.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++ Tidsserie med köväntetidpercentiler för varje strypt slutpunkt

Den här frågan tillhandahåller köns kötidspoängen som en tidsserie, vilket gör att du kan övervaka hur begränsning påverkar väntetiderna över tiden för varje slutpunkt.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++ Antal fel per typ och kod för en specifik slutpunkt under en viss tidsperiod

Den här frågan innehåller en detaljerad beskrivning av fel för en specifik slutpunkt, grupperade efter feltyp och felkod, inklusive information om nya försök.

_Datasjöfråga_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionExecutionError AS ERROR_TYPE,
    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode AS ERROR_CODE,
    COUNT(1) AS CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionOriginError IS NOT NULL THEN 1 END) AS CALLS_WITH_RETRY
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint = '<endpoint URI>' AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL AND
    (<actionExecutionOriginStartTime filter>) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND <timestamp filter>))
GROUP BY 
    ERROR_TYPE, ERROR_CODE
ORDER BY
    ERROR_TYPE, ERROR_CODE;
```

_Exempel_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionExecutionError AS ERROR_TYPE,
    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode AS ERROR_CODE,
    COUNT(1) AS CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionOriginError IS NOT NULL THEN 1 END) AS CALLS_WITH_RETRY
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint = 'https://example.com/my/endpoint' AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND timestamp > (now() - interval '1' day)))
GROUP BY 
    ERROR_TYPE, ERROR_CODE
ORDER BY
    ERROR_TYPE, ERROR_CODE;
```

+++

