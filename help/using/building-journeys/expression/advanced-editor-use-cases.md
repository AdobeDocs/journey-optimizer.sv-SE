---
product: adobe campaign
title: Använda den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 753ef9f4-b39d-4de3-98ca-e69a1766a78b
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Exempel på avancerade uttryck{#advanced-expression-examples}

Den avancerade uttrycksredigeraren kan användas för att skapa villkor som gör att du kan filtrera användare på dina resor. Dessa villkor gör att ni kan inrikta er på användare i tid, på datum, plats, varaktighet eller åtgärder som att köpa eller avstå från kundvagnar så att de kan återställas under resan.

>[!NOTE]
>
>Händelser börjar med @, datakällor med #.

## Bygga villkor för upplevelsehändelser

Den avancerade uttrycksredigeraren är obligatorisk för att utföra frågor på tidsserier som en lista över inköp eller tidigare klick på meddelanden. Sådana frågor kan inte utföras med den enkla redigeraren.

Erfarenhetshändelserna hämtas från Adobe Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att

* den första funktionen returnerar den senaste händelsen
* den sista funktionen returnerar den äldsta.

Låt oss till exempel säga att ni vill rikta er mot kunder som har övergett en kundvagn de senaste 7 dagarna för att skicka ett meddelande när kunden närmar sig en butik, med ett erbjudande på artiklar de vill ha som finns i butik.

**Du måste skapa följande villkor:**

Först och främst målkunder som surfar i onlinebutiken men inte slutfört beställningen de senaste sju dagarna.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Det här uttrycket söker efter alla händelser för den här användaren som har angetts under de senaste 7 dagarna:**

Sedan markeras alla tilläggshändelser som inte omvandlades till completePurchase.

>[!NOTE]
>
>Om du snabbt vill infoga fält i uttrycket dubbelklickar du på fältet på den vänstra panelen i redigeraren.

Den angivna tidsstämpeln fungerar som datum-/tidsvärde, den andra är antalet dagar.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Det här uttrycket returnerar ett booleskt värde.

**Nu ska vi skapa ett uttryck som kontrollerar att produkten finns i lager**

* I Inventory söker det här uttrycket efter kvantitetsfält för en produkt och anger att det ska vara större än 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Till höger anges de nödvändiga värdena, här måste vi hämta platsen för butiken som mappas från platsen för händelsen ArriveLumaStudio:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Och ange SKU med funktionen `first` för att hämta den senaste&quot;addToCart&quot;-interaktionen:

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

Därifrån kan ni lägga till ytterligare en väg på resan när produkten inte finns i butik och skicka meddelanden med engagemangserbjudandet. Konfigurera meddelandena därefter och använd personaliseringsdata för att förbättra meddelandets mål.

## Exempel på strängändringar med den avancerade uttrycksredigeraren

**I villkor**

Detta villkor hämtar endast geofence-händelser som utlöses i&quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Förklaring: Det här är en strikt strängjämförelse (skiftlägeskänslig), som motsvarar en fråga i enkelt läge som använder `equal to` med `Is sensitive` markerad.

Samma fråga med `Is sensitive` om du inte markerar det här alternativet genereras följande uttryck i avancerat läge:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**I funktionsmakron**

Följande uttryck gör att du kan definiera CRM-ID:t i ett åtgärdspersonaliseringsfält:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Förklaring: Det här exemplet använder `substr` och `lastIndexOf` funktioner för att ta bort klammerparenteser som omger det CRM-ID som skickas med en starthändelse för mobilappar.

Mer information om hur du använder den avancerade uttrycksredigeraren finns i [den här videon](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).