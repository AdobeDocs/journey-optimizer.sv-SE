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
source-git-commit: a3c95497fb7304ddd0aa26435f5d0279ff8fdb0f
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---

# Förbättringar av anpassade funktionsmakron

Nu kan du utnyttja API-anropssvar i anpassade åtgärder och samordna dina resor baserat på dessa svar.

Den här funktionen var bara tillgänglig när du använde datakällor. Nu kan du använda den med anpassade åtgärder.

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande tillgänglig som en privat beta.

>[!WARNING]
>
>Anpassade åtgärder bör endast användas med privata eller interna slutpunkter och användas med en lämplig begränsning för begränsning eller begränsning. Läs [den här sidan](../configuration/external-systems.md).

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

   ![](assets/action-response3.png){width="80%" align="left"}

1. Klistra in ett exempel på nyttolasten som returneras av anropet. Kontrollera att fälttyperna är korrekta (sträng, heltal osv.). Här är ett exempel på nyttolast för svar som fångats in under anropet. Vår lokala slutpunkt skickar antalet förmånspoäng och statusen för en profil.

   ```
   {
   "customerID" : "xY12hye",    
   "status":"gold",
   "points": 1290 }
   ```

   ![](assets/action-response4.png){width="80%" align="left"}

   Varje gång API:et anropas hämtas alla fält som ingår i exemplets nyttolast.

1. Vi lägger också till customerID som frågeparameter.

   ![](assets/action-response9.png){width="80%" align="left"}

1. Klicka **Spara**.

## Utnyttja svarsalternativen under en resa

Lägg bara till den anpassade åtgärden på en resa. Du kan sedan utnyttja svarsnyttolastfälten under förhållanden, andra åtgärder och meddelandepersonalisering.

Du kan till exempel lägga till ett villkor för att kontrollera antalet förmånspoäng. När personen kommer in på restaurangen skickar din lokala slutpunkt ett samtal med profilens lojalitetsinformation. Du kan skicka en push-funktion om profilen är en guldkund. Om ett fel upptäcks i samtalet skickar du en anpassad åtgärd till systemadministratören.

![](assets/action-response5.png)

1. Lägg till din händelse och den anpassade lojalitetsåtgärden som skapades tidigare.

1. I den anpassade lojalitetsåtgärden kopplar du frågeparametern för kund-ID till profil-ID:t. Markera alternativet **Lägg till en alternativ sökväg vid timeout eller fel**.

   ![](assets/action-response10.png)

1. Lägg till ett villkor i den första grenen och använd den avancerade redigeraren för att utnyttja åtgärdssvarsfälten, under **Kontext** nod.

   ![](assets/action-response6.png)

1. Lägg sedan till push-meddelanden och anpassa meddelandet med svarsfälten. I vårt exempel personaliserar vi innehållet med hjälp av antalet kundpoäng och kundens status. Åtgärdssvarsfälten är tillgängliga under **Sammanhangsberoende attribut** > **Journey Orchestration** > **Åtgärder**.

   ![](assets/action-response8.png)

   >[!NOTE]
   >
   >Varje profil som anger den anpassade åtgärden utlöser ett anrop. Även om svaret alltid är detsamma kommer Journey fortfarande att ringa ett samtal per profil.

1. Lägg till ett villkor och utnyttja det inbyggda **jo_status_code** fält. I vårt exempel använder vi
   **http_400** feltyp. Se [det här avsnittet](#error-status).

   ```
   @action{ActionLoyalty.jo_status_code} == "http_400"
   ```

   ![](assets/action-response7.png)

1. Lägg till en anpassad åtgärd som ska skickas till din organisation.

   ![](assets/action-response11.png)

## Felstatus{#error-status}

The **jo_status_code** -fältet är alltid tillgängligt även när ingen svarsnyttolast har definierats.

Här är möjliga värden för det här fältet:

* http-statuskod: http_`<HTTP API call returned code>`, till exempel http_200 eller http_400
* timeout-fel: **tidsgränsen**
* capping-fel: **mappad**
* internt fel: **internalError**

Ett åtgärdsanrop hanteras av fel när den returnerade http-koden är större än 2xx eller om ett fel inträffar. I sådana fall skickas resan till den särskilda tidsgränsen eller felavdelningen.

>[!WARNING]
>
>Endast nya anpassade åtgärder innehåller **jo_status_code** fältet är körklart. Om du vill använda den med en befintlig anpassad åtgärd måste du uppdatera åtgärden. Du kan till exempel uppdatera beskrivningen och spara den.

## Uttryckssyntax

Här är syntaxen:

```json
#@action{myAction.myField} 
```

Här är några exempel:

```json
 // action response field
 @action{<action name>.<path to the field>}
 @action{ActionLoyalty.status}
```

```json
 // action response field
 @action{<action name>.<path to the field>, defaultValue: <default value expression>}
 @action{ActionLoyalty.points, defaultValue: 0}
 @action{ActionLoyalty.points, defaultValue: @{myEvent.newPoints}}
```

Mer information om fältreferenser finns i [det här avsnittet](../building-journeys/expression/field-references.md).
