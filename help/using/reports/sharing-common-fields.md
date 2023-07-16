---
solution: Journey Optimizer
product: journey optimizer
title: historikstegshändelser, vanliga fält
description: historikstegshändelser, vanliga fält
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 42aec986-2352-456a-a725-7f1585ae01f8
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---

# historikstegshändelser, vanliga fält {#sharing-common-fields}

Den här fältgruppen delas av travelStepEvent och travelStepProfileEvent.

Det här är de vanliga XDM-fälten som [!DNL Journey Optimizer] skickar till Adobe Experience Platform. Vanliga fält skickas för varje steg som bearbetas under en resa. Mer specifika fält används för anpassade åtgärder och berikning.

Vissa av dessa fält är bara tillgängliga i specifika bearbetningsmönster (åtgärdskörning, datahämtning osv.) för att begränsa storleken på händelser.

## entré {#entrance-field}

Anger om användaren har gått in på resan. Om det inte finns antar vi att värdet är falskt.

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

Typ: string

## nodeID {#nodeid-field}

Klientnod-ID (från arbetsytan).

Typ: string

## stepID {#stepdid-field}

Unikt ID för det steg som bearbetas just nu.

Typ: string

## stepName {#stepname-field}

Namnet på det steg som bearbetas just nu.

Typ: string

## stepType {#steptype-field}

Typ av steg.

Typ: string

Möjliga värden:

* Villkor
* Åtgärd
* Schemaläggare
* Timer

## stepStatus {#stepstatus-field}

Status för steget, som representerar status för steget, när bearbetningen har slutförts (och steghändelsen utlösts).

Typ: string

Status kan vara:

* avslutad: steget saknar övergång och bearbetningen har slutförts.
* fel: Stegbearbetningen har orsakat ett fel.
* övergångar: steget väntar på att en händelse ska övergå till ett annat steg.
* med tak: Steget har misslyckats på ett fel med begränsning, vilket uppstod under en åtgärd eller anrikning.
* tidsgräns: steget har misslyckats på ett timeout-fel som uppstod under en åtgärd eller en anrikning.
* instanceTimedout: steget har stoppat bearbetningen eftersom instansen har nått sin timeout.

## travelID {#journeyid-field}

ID för resan.

Typ: string

## travelVersionID {#journeyversionid-field}

ID för reseversionen. Detta id representerar identitetsreferensen till resan, när det gäller travelStepEvent.

Typ: string

>[!NOTE]
>
>I felsökningssyfte rekommenderar vi att du använder travelVersionID i stället för travelVersionName när du frågar efter resor.

## travelVersionName {#journeyversionname-field}

Namn på reseversionen.

Typ: string

>[!NOTE]
>
>I felsökningssyfte rekommenderar vi att du använder travelVersionID i stället för travelVersionName när du frågar efter resor.

## travelVersion {#journeyversion-field}

Version av reseversionen.

Typ: string

## instanceID {#instanceid-field}

Internt ID för reseinstansen.

Typ: string

## externalKey {#externalkey-field}

Extern nyckel som extraherats från händelsen för att bearbeta den.

Typ: string

## parentStepID {#parenstepid-field}

Steg-ID för den överordnade för det aktuella bearbetade steget i instansen.

Typ: string

## parentStepName {#parentstepname-field}

Stegnamn för det överordnade steget i det aktuella steget.

Typ: string

## parentTransitionID {#parenttransitionid-field}

ID för övergången som har fört instansen till det bearbetade steget.

Typ: string

## parentTransitionName {#parenttransitionname-field}

Namnet på övergången som har fört instansen till det bearbetade steget.

Typ: string

## inTest {#intest-field}

Anger om den här resan är i testläge eller inte.

Typ: boolesk

## processingTime {#processingtime-field}

Total tid i millisekunder från instansstegsinkomsten till behandlingens slut.

Typ: long

## instanceType {#instancetype-field}

Anger instanstypen, om den är batch eller unitary.

Typ: string

Värden: batch/unitary

## repeatIndex {#recurrenceindex-field}

Index för upprepningen om resan är batch och återkommande (den första körningen har recidiIndex = 1).

Typ: long

## isBatchToUnitary {#isbatchtounitary-field}

Anger om den här enhetsförekomsten har utlösts från en gruppinstans.

Typ: boolesk

## batchExternalKey {#batchexternalkey-field}

Extern nyckel för batchhändelse.

Typ: string

## batchInstanceID {#batchinstanceid-field}

detta är batchförekomstens ID.

Typ: string

## batchUnitaryBranchID {#batchunitarybranchid-field}

om instansen har utlösts från en gruppinstans, ett enhetsförgrunds-ID.

Typ: string
