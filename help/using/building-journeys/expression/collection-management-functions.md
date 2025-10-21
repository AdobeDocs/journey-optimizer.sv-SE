---
solution: Journey Optimizer
product: journey optimizer
title: Funktioner för att hantera samlingar
description: Läs mer om datatyper i samlingshanteringsfunktioner
feature: Journeys
role: Engineer
level: Experienced
keywords: fråga, samlingar, funktioner, nyttolast, resa
exl-id: 09b38179-9ace-4921-985b-ddd17eb64681
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# Funktioner för att hantera samlingar {#collection-management-functions}


## Om funktioner för frågesamling

Uttrycksspråket innehåller även en uppsättning funktioner för att fråga efter samlingar. Dessa funktioner förklaras nedan.

I följande exempel använder vi händelsens nyttolast som innehåller en samling:

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

## Funktionen all(`<condition>`)

Funktionen **[!UICONTROL all]** aktiverar definitionen av ett filter för en given samling genom att använda ett booleskt uttryck.

```json
<listExpression>.all(<condition>)
```

Bland alla appanvändare kan du till exempel hämta de som använder IOS 13 (booleskt uttryck &quot;app used == IOS 13&quot;). Resultatet av den här funktionen är den filtrerade lista som innehåller objekt som matchar det booleska uttrycket (exempel: appanvändare 1, appanvändare 34, appanvändare 432).

I en Data Source Condition-aktivitet kan du kontrollera om resultatet av **[!UICONTROL all]**-funktionen är null eller inte. Du kan också kombinera den här **[!UICONTROL all]**-funktionen med andra funktioner som **[!UICONTROL count]**. Mer information finns i [Datavillkorsaktivitet för Source](../condition-activity.md#data_source_condition).


>[!CAUTION]
>
>Det finns inte stöd för att använda upplevelsehändelser i uttryck/villkor för resan. Om ditt användningsfall kräver att du använder upplevelsehändelser bör du överväga alternativa metoder. [Läs mer](../exp-event-lookup.md)

### Exempel 1

Vi vill kontrollera om en användare har installerat en specifik version av ett program. För detta får vi alla push-meddelandetoken som är associerade med mobilprogram som har version 1.0. Sedan utför vi ett villkor med funktionen **[!UICONTROL count]** för att kontrollera att den returnerade tokenlistan innehåller minst ett element.

```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Resultatet är sant.

### Exempel 2

Här använder vi funktionen **[!UICONTROL count]** för att kontrollera om det finns push-meddelandetoken i samlingen.

```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```


Resultatet är sant.


```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Resultatet av uttrycket är **3**.


>[!NOTE]
>
>* När filtervillkoret i funktionen **all()** är tomt returnerar filtret alla element i listan. **För att antalet element i en samling ska kunna räknas krävs dock inte funktionen all.**
>
>* `currentEventField` är bara tillgängligt när du hanterar händelsesamlingar, `currentDataPackField` när du ändrar datakällsamlingar och `currentActionField` när du ändrar anpassade åtgärdssvarssamlingar.
>
>  När vi bearbetar samlingar med `all`, `first` och `last` slingor för varje element i samlingen ett i taget. `currentEventField`, `currentDataPackField` och `currentActionField` motsvarar elementet som upprepas.


## Funktionerna first(`<condition>`) och last(`<condition>`)

Funktionerna **[!UICONTROL first]** och **[!UICONTROL last]** aktiverar även definitionen av ett filter i samlingen när det första/sista elementet i listan som uppfyller filtret returneras.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

### Exempel 1

Det här uttrycket returnerar den första push-meddelandetoken som är associerad med mobilprogram som versionen är 1.0 för.


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token}
```

Resultatet är `token_1`.

### Exempel 2

Det här uttrycket returnerar den senaste push-meddelandetoken som är associerad med mobilprogram för vilka versionen är 1.0.


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last(currentEventField.application.version == "1.0").token}
```

Resultatet är `token_2`.

## Funktionen at(`<index>`)

Med funktionen **[!UICONTROL at]** kan du referera till ett specifikt element i en samling enligt ett index.
Index 0 är samlingens första index.

_`<listExpression>`.at(`<index>`)_

### Exempel

Det här uttrycket returnerar listans andra push-meddelandetoken.


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Resultatet är `token_2`.