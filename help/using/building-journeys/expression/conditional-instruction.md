---
product: adobe campaign
title: Villkorlig instruktion (if, then, else)
description: Läs om villkorlig instruktion
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5a5b35a7-e3b5-4dc0-8a87-e985956b04a4
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Villkorlig instruktion (if, then, else) {#conditional-instruction}

Den villkorliga instruktionen (if, then, else) stöds i den avancerade redigeraren. Det gör det möjligt att definiera mer komplexa uttryck. Den består av följande element:

* **[!UICONTROL if]**: villkoret som ska utvärderas först.
* **[!UICONTROL then]**: uttrycket som ska utvärderas om resultatet av villkorsutvärderingen är sant.
* **[!UICONTROL else]**: uttrycket som ska utvärderas om resultatet av villkorsutvärderingen är false.

>[!NOTE]
>
>Parenteser krävs runt alla uttryck.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` måste returnera en **boolesk**.

`<expression2>` och `<expression3>` måste ha samma typ eller kompatibla typer. De signaturer och returtyper som stöds är:

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Användning**

Med den villkorliga instruktionen kan du optimera arbetsflödet för resan genom att minska antalet villkorsaktiviteter. I samma åtgärdsaktivitet kan du till exempel ange två alternativ för en fältdefinition genom att bara använda ett villkorsuttryck.

Exempel för en åtgärdsaktivitet (för ett fält som förväntar en sträng som ett resultat av den villkorliga instruktionen):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```