---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera en anpassad åtgärd
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Actions
topic: Administration
role: Admin
level: Experienced
badge: label="Beta" type="Informative"
keywords: åtgärd, tredje part, anpassad, resor, API
hide: true
hidefromtoc: true
source-git-commit: 1674eceb1b9ae4cf8cd3f19deda26a9e72290106
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# Förbättringar av anpassade funktionsmakron

Nu kan du utnyttja API-anropssvar i anpassade åtgärder och samordna din resa baserat på dessa svar.

Den här funktionen var bara tillgänglig när du använde datakällor. Nu kan du använda den med anpassade åtgärder.

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande tillgänglig som en privat beta.

## Definiera den anpassade åtgärden

När du definierar den anpassade åtgärden har två förbättringar gjorts tillgängliga: tillägget av GET-metoden och det nya nyttolastsvarsfältet. De andra alternativen och parametrarna ändras inte. Läs [den här sidan](../action/about-custom-action-configuration.md).

### Konfiguration av slutpunkt

The **URL-konfiguration** avsnittet har fått ett nytt namn **Konfiguration av slutpunkt**.

I **Metod** nedrullningsbar meny kan du nu välja **GET**.

![](assets/action-response1.png){width="70%" align="left"}

### Betalningar

The **Åtgärdsparametrar** avsnittet har fått ett nytt namn **Betalningar**. Två fält är tillgängliga:

* The **Begäran** fält: det här fältet är endast tillgängligt för anropsmetoder för POST och PUT.
* The **Svar** field: this is the new capabilities. Det här fältet är tillgängligt för alla anropsmetoder.

>[!NOTE]
> 
>Båda dessa fält är valfria.

![](assets/action-response2.png){width="70%" align="left"}

1. Klicka inuti **Svar** fält.

   ![](assets/action-response3.png){width="70%" align="left"}

1. Klistra in ett exempel på nyttolasten som returneras av anropet. Kontrollera att fälttyperna är korrekta (sträng, heltal osv.).

   ![](assets/action-response4.png){width="70%" align="left"}

1. Klicka **Spara**.

Varje gång API:et anropas hämtas alla fält som ingår i exemplets nyttolast. Obs! **Klistra in en ny nyttolast** om du vill ändra den nyttolast som har skickats.

Här är ett exempel på en svarsnyttolast som fångats in under anropet till en API-tjänst för väder:

```
{
    "coord": {
        "lon": 2.3488,
        "lat": 48.8534
    },
    "weather": [
        {
            "id": 800,
            "main": "Clear",
            "description": "clear sky",
            "icon": "01d"
        }
    ],
    "base": "stations",
    "main": {
        "temp": 29.78,
        "feels_like": 29.78,
        "temp_min": 29.92,
        "temp_max": 30.43,
        "pressure": 1016,
        "humidity": 31
    },
    "visibility": 10000,
    "wind": {
        "speed": 5.66,
        "deg": 70
    },
    "clouds": {
        "all": 0
    },
    "dt": 1686066467,
    "sys": {
        "type": 1,
        "id": 6550,
        "country": "FR",
        "sunrise": 1686023350,
        "sunset": 1686080973
    },
    "timezone": 7200,
    "id": 2988507,
    "name": "Paris",
    "cod": 200
}
```

## Utnyttja svarstiderna under en resa

Lägg bara till den anpassade åtgärden på en resa. Du kan sedan utnyttja svarsnyttolastfälten under förhållanden, andra åtgärder och meddelandepersonalisering.

### Villkor och åtgärder

Du kan till exempel lägga till ett villkor för att kontrollera vindhastigheten. När personen kommer in i surfaffären kan du skicka ett tryck om vädret är för blåsigt.

![](assets/action-response5.png){width="70%" align="left"}

I villkoret måste du använda den avancerade redigeraren för att utnyttja åtgärdssvarsfälten, under **Kontext** nod.

![](assets/action-response6.png){width="70%" align="left"}

Du kan också använda **jo_status** kod för att skapa en ny sökväg om ett fel uppstår.

![](assets/action-response7.png){width="70%" align="left"}

>[!WARNING]
>
>Endast nya anpassade åtgärder innehåller det här fältet. Om du vill använda den med en befintlig anpassad åtgärd måste du uppdatera åtgärden. Du kan till exempel uppdatera beskrivningen och spara den.

Här är möjliga värden för det här fältet:

* http-statuskod: till exempel **http_200** eller **http_400**
* timeout-fel: **tidsgränsen**
* capping-fel: **mappad**
* internt fel: **internalError**

### Skräddarsytt meddelande

Du kan anpassa dina meddelanden med hjälp av svarsfälten. I vårt exempel personaliserar vi innehållet med hjälp av hastighetsvärdet i push-meddelandet.

![](assets/action-response8.png){width="70%" align="left"}

>[!NOTE]
>
>Anropet utförs endast en gång per profil under en viss resa. Flera meddelanden kommer inte att utlösa nya anrop.

## Uttryckssyntax

Här är syntaxen:

```json
#@action{myAction.myField} 
```

Här är några exempel:

```json
// action response field
@action{<action name>.<path to the field>}
@action{OpenWeatherMap.main.temp}
```

```json
// action response field
@action{<action name>.<path to the field>, defaultValue: <default value expression>}
@action{OpenWeatherMap.main.temp, defaultValue: 273.15}
@action{OpenWeatherMap.main.temp, defaultValue: @{myEvent.temperature}} 
```


