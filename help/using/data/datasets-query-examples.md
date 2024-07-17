---
solution: Journey Optimizer
product: journey optimizer
title: Exempel på datauppsättningsfrågor
description: Exempel på datauppsättningsfrågor
feature: Journeys, Reporting, Use Cases, Datasets, Data Management
topic: Content Management
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: datauppsättning, optimering, användningsfall
exl-id: 26ba8093-8b6d-4ba7-becf-b41c9a06e1e8
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%

---

# Användningsexempel för datauppsättning {#tracking-datasets}

På den här sidan hittar du en lista över Adobe Journey Optimizer datamängder och relaterade användningsfall:

[Händelsedatauppsättning för e-postspårning](#email-tracking-experience-event-dataset)
[ Händelsedatauppsättning för meddelandefeedback ](#message-feedback-event-dataset)
[Push Tracking Experience, händelsedatauppsättning](#push-tracking-experience-event-dataset)
[Resestegshändelse](#journey-step-event)
[Information om beslutningshändelse](#ode-decisionevents)
[BCC Feedback Event DataSet](#bcc-feedback-event-dataset)
[Entitetsdatauppsättning ](#entity-dataset)

Om du vill visa en fullständig lista över fält och attribut för varje schema kan du läsa [Journey Optimizer schemaordlista](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html){target="_blank"}.

## Händelsedatauppsättning för e-postspårning{#email-tracking-experience-event-dataset}

_Namn i gränssnittet: AJO händelsedatauppsättning för e-postspårning_

Systemdatauppsättning för inhämtning av e-postspårningshändelser från Journey Optimizer.

Det relaterade schemat är AJO händelseschema för e-postspårning.

Den här frågan visar antalet olika e-postinteraktioner (öppnas, klickas) för ett visst meddelande:

```sql
select
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from ajo_email_tracking_experience_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageInteraction.interactionType
```

Den här frågan visar fördelningen av antal olika e-postinteraktioner (öppningar, klick) efter meddelande för en viss resa:

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from ajo_email_tracking_experience_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
group by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType
order by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType
limit 100;
```

## Händelsedatauppsättning för meddelandefeedback{#message-feedback-event-dataset}

_Namn i gränssnittet: AJO Message Feedback Event Dataset_

Datauppsättning för inmatning av e-post och push-meddelanden från Journey Optimizer.

Det relaterade schemat är AJO Message Feedback Event Schema.

Den här frågan visar antalet olika e-postfeedbackstatusar (skickade, avhoppade osv.) för ett visst meddelande:

```sql
select
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from ajo_message_feedback_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus;
```

Den här frågan visar fördelningen av antalet olika e-postfeedbackstatusar (skickade, avhoppade osv.) efter meddelande för en viss resa:

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from ajo_message_feedback_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
group by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus
order by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus
limit 100;
```

På aggregeringsnivå, domännivårapport (sorterad efter de översta domänerna): Domännamn, Skickat meddelande, Begränsningar

```sql
SELECT split_part(_experience.customerJourneyManagement.emailChannelContext.address, '@', 2) AS recipientDomain, SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END)AS sentCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' THEN 1 ELSE 0 END )AS bounceCount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY recipientDomain ORDER BY sentCount DESC;
```

E-postmeddelanden skickas dagligen:

```sql
SELECT date_trunc('day', TIMESTAMP) AS rolluptimestamp, SUM( CASE WHEN _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent' THEN 1 ELSE 0 END) AS deliveredcount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY date_trunc('day', TIMESTAMP) ORDER BY rolluptimestamp ASC;
```

Kontrollera om ett visst e-post-ID har fått ett e-postmeddelande eller inte och om inte, vad var felet, studskategori, kod:

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.emailchannelcontext.address = 'user@domain.com' AND TIMESTAMP >= now() - INTERVAL '7' DAY ORDER BY status ASC
```

Hitta en lista med alla enskilda e-post-ID:n som har haft ett visst fel, studs-kategori eller kod de senaste x timmarna/dagarna eller som har kopplats till en viss meddelandeleverans:

```sql
SELECT _experience.customerjourneymanagement.emailchannelcontext.address AS emailid, _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus != 'sent' AND TIMESTAMP >= now() - INTERVAL '10' HOUR AND _experience.customerjourneymanagement.messageexecution.messageexecutionid = 'BMA-45237824' ORDER BY emailid
```

Hård studs på aggregerad nivå:

```sql
select hardBounceCount, case when sentCount > 0 then(hardBounceCount/sentCount)*100.0 else 0 end as hardBounceRate from ( select SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' AND _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.type = 'Hard' THEN 1 ELSE 0 END)AS hardBounceCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END )AS sentCount from ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' )
```

Permanenta fel grupperade efter studskod:

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, COUNT(*) AS hardbouncecount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type = 'Hard' AND _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY failurereason
```

### Identifiera adresser i karantän efter ett avbrott i en Internet-leverantör{#isp-outage-query}

Om en Internet-leverantör skulle råka ut för ett avbrott måste du identifiera e-postadresser som felaktigt markerats som studsar (i karantän) för specifika domäner under en tidsram. Använd följande fråga om du vill hämta adresserna:

```sql
SELECT
    _experience.customerJourneyManagement.emailChannelContext.address AS RecipientAddress,
    timestamp AS EventTime,
    _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.reason AS "Invalid Recipient"
FROM ajo_message_feedback_event_dataset
WHERE
    eventtype = 'message.feedback' AND
    DATE(timestamp) BETWEEN '<start-date-time>' AND '<end-date-time>' AND
    _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND
    _experience.customerJourneyManagement.emailChannelContext.address ILIKE '%domain.com%'
ORDER BY timestamp DESC;
```

där datumformatet är: `YYYY-MM-DD HH:MM:SS`.

Ta bort adresserna från listan över Journey Optimizer-adresser när de har identifierats. [Läs mer](../configuration/manage-suppression-list.md#remove-from-suppression-list).

## Händelsedatauppsättning för push-spårning {#push-tracking-experience-event-dataset}

_Namn i gränssnittet: AJO Push Tracking Experience Event-datauppsättning_

Datauppsättning för inhämtning av upplevelsehändelser för mobilspårning för push från Journey Optimizer.

Det relaterade schemat är AJO Push Tracking Experience Event Schema.

Frågeexempel:

```sql
select _experience.customerJourneyManagement.pushChannelContext.platform, sum(pushNotificationTracking.customAction.value)  from ajo_push_tracking_experience_event_dataset
group by _experience.customerJourneyManagement.pushChannelContext.platform

select  _experience.customerJourneyManagement.pushChannelContext.platform, SUM (_experience.customerJourneyManagement.messageInteraction.offers.offerCount) from ajo_email_tracking_experience_event_dataset
  group by _experience.customerJourneyManagement.pushChannelContext.platform
```

## Resestegshändelse{#journey-step-event}

_Internt namn: Resestegshändelser (systemdatauppsättning)_

Datauppsättning för att importera steghändelser under resan.

Det relaterade schemat är schemat för resesegmenthändelser för Journey Orchestration.

Den här frågan visar hur antalet lyckade åtgärder per åtgärdsetikett för en viss resa har fördelats:

```sql
select
    _experience.journeyOrchestration.stepEvents.actionName AS actionLabel,
    count(1) actionSuccessCount
from journey_step_events
where
     _experience.journeyOrchestration.stepEvents.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
     AND _experience.journeyOrchestration.stepEvents.actionID IS NOT NULL
     AND _experience.journeyOrchestration.stepEvents.actionType IS NOT NULL
     AND _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode IS NULL
group by
    _experience.journeyOrchestration.stepEvents.actionName;   
```

Den här frågan visar den uppdelning av antalet steg som anges av nodeId &amp; nodeLabel för en viss resa. nodeId inkluderas här eftersom nodeLabel kan vara samma för olika kundnoder.

```sql
select
    _experience.journeyOrchestration.stepEvents.nodeID AS nodeID,
    _experience.journeyOrchestration.stepEvents.nodeName AS nodeLabel,
    count(1) stepEnteredCount
from journey_step_events
where
     _experience.journeyOrchestration.stepEvents.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
     AND _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = TRUE
     AND _experience.journeyOrchestration.stepEvents.eventID IS DISTINCT FROM 'createInstance'
group by
    _experience.journeyOrchestration.stepEvents.nodeID,
    _experience.journeyOrchestration.stepEvents.nodeName; 
```

## Datamängd för beslutshändelse{#ode-decisionevents}

_Namn i gränssnittet: ODE DecisionEvents (systemdatauppsättning)_

Datauppsättning för inhämtning av erbjudandeförslag för användarna.

Det relaterade schemat är ODE DecisionEvents.

Den här frågan visar alla erbjudanden som returnerades föregående dag:

```sql
SELECT date_format(Decision.Timestamp, 'MM/dd/yyyy') as Date
,HOUR(Decision.timestamp) as Hour
,COUNT(*)  as Count
FROM ode_decisionevents_b699fa78_efec_41b1_99fa_78efecc1b1ef_decision AS Decision
WHERE date_format(Decision.timestamp, 'MM/dd/yyyy') = date_format(CURRENT_DATE, 'MM/dd/yyyy') and Decision._experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:13ab41890a335ad6'
GROUP BY date_format(Decision.Timestamp, 'MM/dd/yyyy')
,HOUR(Decision.timestamp)
ORDER BY 1, 2 DESC;
```

Den här frågan visar hur många erbjudanden som har föreslagits under de senaste 30 dagarna för en viss aktivitet/ett visst beslut och dess associerade erbjudandeprioritet.

```sql
select proposedOffers.id,proposedOffers.name, po._experience.decisioning.ranking.priority, count(proposedOffers.id) as ProposedCount from (
select explode(propositionexplode.selections) AS proposedOffers from
(select explode(_experience.decisioning.propositionDetails) AS propositionexplode,timestamp FROM ode_decisionevents_itca_decisioning_20230925_235340_379  where date_format(timestamp, 'MM/dd/yyyy') >= date_format(DATE_ADD(CURRENT_DATE, -30), 'MM/dd/yyyy') and _experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:12ae6f35a055c6f0')) a, decision_object_repository_personalized_offers po where proposedOffers.id LIKE 'xcore:personalized-offer%' and po._id=proposedOffers.id
group by proposedOffers.id, proposedOffers.name, po._experience.decisioning.ranking.priority;
```

<!--
## Consent Service Dataset{#consent-service-dataset}

_Name in the interface: CJM Consent Service Dataset (system dataset)_

Dataset for Journey Optimizer Consent service.

The related schema is CJM Consent Service Schema.

Query to list email IDs that have consented to receive email:

```sql
select key as email FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
)
where value.marketing.email.val == 'y'
```

Query to return consent value for an email ID where email ID would be the input:

```sql
select value.marketing.email.val FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
```
-->

## BCC Feedback, händelsedatauppsättning{#bcc-feedback-event-dataset}

_Namn i gränssnittet: AJO BCC Feedback Event Dataset (systemdatauppsättning)_

Datauppsättning som lagrar information för BCC-meddelanden.

Fråga för alla BCC-meddelanden inom 2 dagar (för en viss kampanj):

```sql
SELECT bcc.*
FROM ajo_bcc_feedback_event_dataset AS bcc
WHERE 
    bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID = '<message-execution-id>' AND 
    bcc.timestamp >= now() - INTERVAL '2' day; 
```

Fråga med feedbackdatauppsättning för att visa användare som inte har tagit emot (alla studsar och undertryckningar) och som har en BCC-post för ett visst meddelande:

```sql
SELECT 
    distinct bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS OriginalRecipientAddress 
FROM ajo_bcc_feedback_event_dataset  AS bcc 
WHERE 
    bcc.timestamp > now() - INTERVAL '2' DAY AND     bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND      bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress != '' AND
    ( 
            bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress NOT IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM ajo_message_feedback_event_dataset AS mfe 
        WHERE 
            mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent'
        )  
    OR     bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM ajo_message_feedback_event_dataset AS mfe 
        WHERE 
        mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND 
            mfe._experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category = 'async' AND 
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus
```

## Enhetsdatauppsättning{#entity-dataset}

_Namn i gränssnittet: ajo_entity_dataset (system dataset)_

Datauppsättning som lagrar entitetsmetadata för meddelanden som skickas till slutanvändaren.

Det relaterade schemat är AJO entitetsschema.

Den här datauppsättningen ger er tillgång till marknadsföringsdefinierade metadata som gör att ni får bättre rapportinsikter när Journey Optimizer datauppsättningar exporteras ut för att rapportera visualisering i externa verktyg. Detta uppnås med messageID-attributet som hjälper till att sammanfoga olika datauppsättningar, t.ex. datauppsättningar för meddelandefeedback och datauppsättningar för uppföljning av upplevelsehändelser, för att få information om en meddelandeleverans från sändning till spårning på profilnivå.

**Viktiga anteckningar**

* En post för ett meddelande skapas först när resan eller kampanjen har publicerats.

* Du kan se bidraget 30 minuter efter att kampanjen/resan har publicerats.

>[!NOTE]
>
>För närvarande finns det två poster för varje meddelandepublikation i entitetsdatauppsättningen för framtida kompatibilitetsorsaker. Detta påverkar inte din möjlighet att använda kopplingsfrågor efter behov i datauppsättningar för att hämta önskad information.

Om du vill sortera, i dina rapporter, de e-postmeddelanden som skickas av en viss resa enligt den åtgärd som har skickat dem. du kan ansluta till datamängden för meddelandefeedback med entitetsdatauppsättningen. De fält som ska användas är: `_experience.decisioning.propositions.scopeDetails.correlationID` och `_id field in entity dataset`.

Följande fråga hjälper dig att hämta den associerade meddelandemallen för en viss kampanj:

```sql
SELECT
  AE._experience.customerJourneyManagement.entities.channelDetails.template
from
  ajo_entity_dataset AE
    WHERE AE._experience.customerJourneyManagement.entities.campaign.campaignVersionID = 'd7a01136-b113-4ef2-8f59-b6001f7eef6e'
```

Följande fråga hjälper dig att få fram information om resan och e-post som är kopplad till alla feedback-händelser:

```sql
SELECT 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionName, 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionID, 
  AE._experience.customerJourneyManagement.entities.journey.journeyVersionID, 
  AE._experience.customerJourneyManagement.entities.channelDetails.email.subject 
from 
  ajo_entity_dataset AE 
  INNER JOIN ajo_message_feedback_event_dataset MF ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```

Du kan sätta ihop steg-händelser för resan, meddelandefeedback och spårningsdata för att få statistik för en viss profil:

```sql
SELECT 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionName, 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionID, 
  AE._experience.customerJourneyManagement.entities.journey.journeyVersionID, 
  AE._experience.customerJourneyManagement.entities.channelDetails.email.subject,
    JE._EXPERIENCE.JOURNEYORCHESTRATION.STEPEVENTS.PROFILEID,
    JE._EXPERIENCE.JOURNEYORCHESTRATION.STEPEVENTS.NODENAME
from 
  ajo_entity_dataset AE 
  INNER JOIN ajo_message_feedback_event_dataset MF 
    ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
    INNER JOIN journey_step_events JE
    ON AE._experience.customerJourneyManagement.entities.journey.journeyActionID = JE._experience.journeyOrchestration.stepEvents.actionID
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```
