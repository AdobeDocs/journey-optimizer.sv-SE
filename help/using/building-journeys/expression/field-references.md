---
solution: Journey Optimizer
product: journey optimizer
title: Fältreferenser
description: Läs mer om fältreferenser i avancerade uttryck
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: resa, fält, uttryck, händelse
exl-id: 2348646a-b205-4b50-a08f-6625e92f44d7
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 2%

---

# Fältreferenser {#field-references}

En fältreferens kan bifogas till en händelse eller en fältgrupp. Den enda meningsfulla informationen är fältets namn och sökväg.

Om du använder specialtecken i ett fält måste du använda dubbla citattecken eller enkla citattecken. Här är de fall där citattecken behövs:

* fältet börjar med numeriska tecken
* fältet börjar med tecknet &quot;-&quot;
* fältet innehåller något annat än: _a_-_z_, _A_-_Z_, _0_-_9_, _, _-_

Om fältet till exempel är _3h_: _#{OpenWeather.westData.rain.&#39;3h&#39;} > 0_

```json
// event field
@event{<event name>.<XDM path to the field>}
@event{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

I uttrycket refereras händelsefält till&quot;@&quot; och datakällfält refereras till med &quot;#&quot;.

En syntaxfärg används för att visuellt skilja händelsefält (gröna) från fältgrupper (blå).

## Standardvärden för fältreferenser {#default-value}

Ett standardvärde kan associeras med ett fältnamn. Syntaxen är följande:

```json
// event field
@event{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@event{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Fälttypen och standardvärdet måste vara samma. `@event{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2}` är till exempel ogiltigt eftersom standardvärdet är ett heltal medan det förväntade värdet ska vara en sträng.

Exempel:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @event{OrderEvent.orderId}                                    -> "12345"
- @event{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @event{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

Du kan lägga till vilken typ av uttryck som helst som standardvärde. Den enda begränsningen är att uttrycket måste returnera den förväntade datatypen. När du använder en funktion måste du kapsla in funktionen med ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Referens till ett fält i samlingar

De element som definieras i samlingar refereras med de specifika funktionerna `all`, `first` och `last`. För mer information om detta hittar du i [det här avsnittet](../expression/collection-management-functions.md).

Exempel:

```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Referens till ett fält som definieras i en karta

### Funktionen `entry`

För att kunna hämta ett element i en karta använder vi inmatningsfunktionen med en given nyckel. Det används till exempel när du definierar nyckeln för en händelse enligt det valda namnutrymmet. Mer information finns på [den här sidan](../../event/about-creating.md#select-the-namespace).

```json
@event{MyEvent.identityMap.entry('Email').first().id}
```

I det här uttrycket hämtar vi posten för nyckeln Email i fältet IdentityMap för en händelse. E-postposten är en samling från vilken vi tar ID:t i det första elementet med first(). Mer information finns på [den här sidan](../expression/collection-management-functions.md).

### Funktionen `firstEntryKey`

Om du vill hämta den första startnyckeln för en karta använder du funktionen `firstEntryKey`.

I det här exemplet visas hur du hämtar den första e-postadressen för prenumeranterna i en viss lista:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

I det här exemplet heter prenumerationslistan `daily-email`. E-postadresser definieras som nycklar i kartan `subscribers` som är länkad till prenumerationslistans karta.

### Funktionen `keys`

Använd funktionen `keys` om du vill hämta alla nycklar för en karta.

I det här exemplet visas hur du hämtar, för en viss profil, alla e-postadresser som är kopplade till prenumeranterna i en viss lista:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Parametervärden för en datakälla (dynamiska värden för datakälla)

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas, visas en ny flik till höger där du kan ange den här parametern. Läs [den här sidan](../expression/expressionadvanced.md).

Om du vill ta med parametrarna för datakällan i huvuduttrycket kan du definiera deras värden med nyckelordet _params_ för mer komplexa användningsområden. En parameter kan vara vilket giltigt uttryck som helst, även från en annan datakälla som även innehåller en annan parameter.

>[!NOTE]
>
>När du definierar parametervärdena i uttrycket försvinner fliken till höger.

Använd följande syntax:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: det exakta namnet på den första parametern från datakällan.
* **`<params-1-value>`**: värdet för den första parametern. Det kan vara vilket giltigt uttryck som helst.

Exempel:

```json
#{Weather.main.temperature, params: {localisation: @event{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @event{Profile.address.city}}}}}
```
