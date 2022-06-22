---
title: Exempel på datauppsättningsfrågor
description: Exempel på datauppsättningsfrågor
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 1de18fa479a54c09751324a67793ce50e5657ce3
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Användningsexempel för datauppsättning {#tracking-datasets}

På den här sidan hittar du en lista över Adobe Journey Optimizer datamängder och relaterade användningsfall:

[Händelsedatauppsättning för e-postspårning](../start/datasets-query-examples.md#email-tracking-experience-event-dataset)
[Händelsedatauppsättning för meddelandefeedback](../start/datasets-query-examples.md#message-feedback-event-dataset)
[Händelsedatauppsättning för push-spårning](../start/datasets-query-examples.md#push-tracking-experience-event-dataset)
[Resestegshändelse](../start/datasets-query-examples.md#journey-step-event)
[Datamängd för beslutshändelse](../start/datasets-query-examples.md#ode-decisionevents)
[Samtycketjänstens datauppsättning](../start/datasets-query-examples.md#consent-service-dataset)
[BCC Feedback, händelsedatauppsättning](../start/datasets-query-examples.md#bcc-feedback-event-dataset)

## Händelsedatauppsättning för e-postspårning{#email-tracking-experience-event-dataset}

_Namn i gränssnittet: CJM - händelsedatauppsättning för e-postspårning_

Systemdatauppsättning för inhämtning av e-postspårningshändelser från Journey Optimizer.

Det relaterade schemat är CJM-händelseschema för e-postspårning.

Den här frågan visar antalet olika e-postinteraktioner (öppnas, klickas) för ett visst meddelande:

```sql
select
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from cjm_email_tracking_experience_event_dataset
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
from cjm_email_tracking_experience_event_dataset
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

_Namn i gränssnittet: CJM-meddelandets feedbackhändelsedatauppsättning_

Datauppsättning för inmatning av e-post och push-meddelanden från Journey Optimizer.

Det relaterade schemat är händelseschema för CJM-meddelandefeedback.

Den här frågan visar antalet olika e-postfeedbackstatusar (skickade, avhoppade osv.) för ett visst meddelande:

```sql
select
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from cjm_message_feedback_event_dataset
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
from cjm_message_feedback_event_dataset
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

På aggregeringsnivå, domännivårapport (sorterad efter de översta domänerna): Domännamn, skickat meddelande, studsar

```sql
SELECT split_part(_experience.customerJourneyManagement.emailChannelContext.address, '@', 2) AS recipientDomain, SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END)AS sentCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' THEN 1 ELSE 0 END )AS bounceCount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY recipientDomain ORDER BY sentCount DESC;
```

E-postmeddelanden skickas dagligen:

```sql
SELECT date_trunc('day', TIMESTAMP) AS rolluptimestamp, SUM( CASE WHEN _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent' THEN 1 ELSE 0 END) AS deliveredcount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY date_trunc('day', TIMESTAMP) ORDER BY rolluptimestamp ASC;
```

Ta reda på om ett visst e-post-ID har fått ett e-postmeddelande eller inte, och om inte, vad var felet, studskategori, kod:

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.emailchannelcontext.address = 'user@domain.com' AND TIMESTAMP >= now() - INTERVAL '7' DAY ORDER BY status ASC
```

Hitta en lista med alla enskilda e-post-ID:n som har haft ett visst fel, studs-kategori eller kod de senaste x timmarna/dagarna eller som har kopplats till en viss meddelandeleverans:

```sql
SELECT _experience.customerjourneymanagement.emailchannelcontext.address AS emailid, _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus != 'sent' AND TIMESTAMP >= now() - INTERVAL '10' HOUR AND _experience.customerjourneymanagement.messageexecution.messageexecutionid = 'BMA-45237824' ORDER BY emailid
```

Hård studs på aggregerad nivå:

```sql
select hardBounceCount, case when sentCount > 0 then(hardBounceCount/sentCount)*100.0 else 0 end as hardBounceRate from ( select SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' AND _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.type = 'Hard' THEN 1 ELSE 0 END)AS hardBounceCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END )AS sentCount from cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' )
```

Permanenta fel grupperade efter studskod:

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, COUNT(*) AS hardbouncecount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type = 'Hard' AND _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY failurereason
```

## Händelsedatauppsättning för push-spårning {#push-tracking-experience-event-dataset}

_Namn i gränssnittet: CJM Push Tracking Experience, händelsedatauppsättning_

Datauppsättning för inhämtning av upplevelsehändelser för mobilspårning för push från Journey Optimizer.

Det relaterade schemat är CJM Push Tracking Experience Event Schema.

Frågeexempel:

```sql
select _experience.customerJourneyManagement.pushChannelContext.platform, sum(pushNotificationTracking.customAction.value)  from cjm_push_tracking_experience_event_dataset
group by _experience.customerJourneyManagement.pushChannelContext.platform

select  _experience.customerJourneyManagement.pushChannelContext.platform, SUM (_experience.customerJourneyManagement.messageInteraction.offers.offerCount) from cjm_email_tracking_experience_event_dataset
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

_Namn i gränssnittet: ODE-beslutshändelser (systemdatauppsättning)_

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
(select explode(_experience.decisioning.propositionDetails) AS propositionexplode,timestamp FROM ode_decisionevents_itca_decisioning_20200925_235340_379  where date_format(timestamp, 'MM/dd/yyyy') >= date_format(DATE_ADD(CURRENT_DATE, -30), 'MM/dd/yyyy') and _experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:12ae6f35a055c6f0')) a, decision_object_repository_personalized_offers po where proposedOffers.id LIKE 'xcore:personalized-offer%' and po._id=proposedOffers.id
group by proposedOffers.id, proposedOffers.name, po._experience.decisioning.ranking.priority;
```

## Samtycketjänstens datauppsättning{#consent-service-dataset}

_Namn i gränssnittet: CJM-sambandstjänstens datauppsättning (systemdatauppsättning)_

Datauppsättning för tjänsten Journey Optimizer Consent.

Det relaterade schemat är CJM Consent Service Schema.

Fråga för att lista e-post-ID som har samtyckt till att ta emot e-post:

```sql
select key as email FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
)
where value.marketing.email.val == 'y'
```

Fråga för att returnera medgivandevärde för ett e-post-ID där e-post-ID är indata:

```sql
select value.marketing.email.val FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
```

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
        FROM cjm_message_feedback_event_dataset AS mfe 
        WHERE 
            mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent'
        )  
    OR     bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM cjm_message_feedback_event_dataset AS mfe 
        WHERE 
        mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND 
            mfe._experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category = 'async' AND 
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus
```
