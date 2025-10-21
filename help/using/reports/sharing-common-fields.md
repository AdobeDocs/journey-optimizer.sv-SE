---
solution: Journey Optimizer
product: journey optimizer
title: historikstegshändelser, vanliga fält
description: historikstegshändelser, vanliga fält
feature: Journeys, Reporting
topic: Content Management
role: Engineer, Admin
level: Experienced
exl-id: 42aec986-2352-456a-a725-7f1585ae01f8
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# historikstegshändelser, vanliga fält {#sharing-common-fields}

Den här fältgruppen delas av följande händelser: **travelStepEvent** och **travelStepProfileEvent**.

Det här är de vanliga XDM-fälten som [!DNL Journey Optimizer] skickar till Adobe Experience Platform. Vanliga fält skickas för varje steg som bearbetas under en resa. Mer specifika fält används för anpassade åtgärder och berikning.

Vissa av dessa fält är bara tillgängliga i specifika bearbetningsmönster (åtgärdskörning, datahämtning osv.) för att begränsa storleken på händelser.


>[!NOTE]
>
>Läs mer om attribut för reseegenskaper [i det här avsnittet](../building-journeys/expression/journey-properties.md#journey-propertoes-fields).


## entré {#entrance-field}

Anger om användaren har gått in i resan. Om det inte finns antar vi att värdet är falskt.

Typ: boolesk

Värden: true/false

## återinträde {#reentrance-field}

Anger om användaren har gjort om resan med samma instans. Om det inte finns antar vi att värdet är falskt.

Typ: boolesk

Värden: true/false

## instanceEnded {#instance-ended-field}

Anger om instansen har avslutats (utan fel eller inte).

Typ: boolesk

## eventID {#eventid-field}

Händelse-ID under bearbetning för stegbearbetning. Om händelsen är en extern händelse är värdet dess eventId. Om händelsen är en intern händelse är värdet det interna eventId (till exempel scheduleNotificationReceived, executionAction).

Typ: sträng

## nodeID {#nodeid-field}

Klientnod-ID (från arbetsytan).

Typ: sträng

## stepID {#stepdid-field}

Unikt ID för det steg som bearbetas just nu.

Typ: sträng

## stepName {#stepname-field}

Namnet på det steg som bearbetas just nu.

Typ: sträng

## stepType {#steptype-field}

Typ av steg.

Typ: sträng

Möjliga värden:

* Villkor
* Åtgärd
* Schemaläggare
* Timer

## stepStatus {#stepstatus-field}

Status för steget, som representerar status för steget, när bearbetningen har slutförts (och steghändelsen utlösts).

Typ: sträng

Status kan vara:

* avslutad: steget har ingen övergång och bearbetningen har slutförts.
* fel: stegbearbetningen har orsakat ett fel.
* övergångar: steget väntar på att en händelse ska övergå till ett annat steg.
* Mappat: steget har misslyckats på ett fel med begränsning, vilket uppstod under en åtgärd eller anrikning.
* timeout: steget misslyckades på ett timeout-fel, vilket uppstod under en åtgärd eller en anrikning.
* instanceTimedout: bearbetningen av steget har stoppats eftersom instansen har nått sin tidsgräns.

## travelID {#journeyid-field}

ID för resan.

Typ: sträng

## travelVersionID {#journeyversionid-field}

ID för reseversionen. Detta id representerar identitetsreferensen till resan, när det gäller travelStepEvent.

Typ: sträng

>[!NOTE]
>
>I felsökningssyfte rekommenderar vi att du använder travelVersionID i stället för travelVersionName när du frågar efter resor.

## travelVersionName {#journeyversionname-field}

Namn på reseversionen.

Typ: sträng

>[!NOTE]
>
>I felsökningssyfte rekommenderar vi att du använder travelVersionID i stället för travelVersionName när du frågar efter resor.

## travelVersion {#journeyversion-field}

Version av reseversionen.

Typ: sträng

## instanceID {#instanceid-field}

Internt ID för reseinstansen.

Typ: sträng

## externalKey {#externalkey-field}

Extern nyckel som extraherats från händelsen för att bearbeta den.

Typ: sträng

## parentStepID {#parenstepid-field}

Steg-ID för den överordnade för det aktuella bearbetade steget i instansen.

Typ: sträng

## parentStepName {#parentstepname-field}

Stegnamn för det överordnade steget i det aktuella steget.

Typ: sträng

## parentTransitionID {#parenttransitionid-field}

ID för övergången som har fört instansen till det bearbetade steget.

Typ: sträng

## parentTransitionName {#parenttransitionname-field}

Namnet på övergången som har fört instansen till det bearbetade steget.

Typ: sträng

## inTest {#intest-field}

Anger om den här resan är i testläge eller inte.

Typ: boolesk

## processingTime {#processingtime-field}

Total tid i millisekunder från instansstegsinkomsten till behandlingens slut.

Typ: lång

## instanceType {#instancetype-field}

Anger instanstypen, om den är batch eller unitary.

Typ: sträng

Värden: batch/enhet

## repeatIndex {#recurrenceindex-field}

Index för upprepningen om resan är batch och återkommande (den första körningen har recidiIndex = 1).

Typ: lång

## isBatchToUnitary {#isbatchtounitary-field}

Anger om den här enhetsförekomsten har utlösts från en gruppinstans.

Typ: boolesk

## batchExternalKey {#batchexternalkey-field}

Extern nyckel för batchhändelse.

Typ: sträng

## batchInstanceID {#batchinstanceid-field}

detta är batchförekomstens ID.

Typ: sträng

## batchUnitaryBranchID {#batchunitarybranchid-field}

om instansen har utlösts från en gruppinstans, ett enhetsförgrunds-ID.

Typ: sträng

## exitCriteriaID

ID för exitCriteria

Typ: sträng

## exitCriteriaName

Namn på exitCriteria

Typ: sträng