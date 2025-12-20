---
solution: Journey Optimizer
product: journey optimizer
title: Använda den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
feature: Journeys
role: Developer
level: Experienced
hide: true
hidefromtoc: true
keywords: uttryck, villkor, användningsfall, händelser
exl-id: 753ef9f4-b39d-4de3-98ca-e69a1766a78b
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---


# Exempel på avancerade uttryck{#advanced-expression-examples}

Den avancerade uttrycksredigeraren kan användas för att skapa villkor som gör att du kan filtrera användare på dina resor. Dessa villkor gör att du kan rikta in dig på användare i tid, datum, plats, längd, så att de kan återställas under resan.

>[!CAUTION]
>
>Det finns inte stöd för att använda upplevelsehändelser i uttryck/villkor för resan. Om ditt användningsfall kräver att du använder upplevelsehändelser bör du överväga alternativa metoder. [Läs mer](../exp-event-lookup.md)


## Bygga villkor för upplevelsehändelser


>[!CAUTION]
>
>Det finns inte stöd för att använda upplevelsehändelser i uttryck/villkor för resan. Om ditt användningsfall kräver att du använder upplevelsehändelser bör du överväga alternativa metoder. [Läs mer](../exp-event-lookup.md)
>



Den avancerade uttrycksredigeraren är obligatorisk för att utföra frågor på tidsserier som en lista över inköp eller tidigare klick på meddelanden. Sådana frågor kan inte utföras med den enkla redigeraren.

>[!NOTE]
>
>Händelser börjar med @, datakällor med #.

Experience Events hämtas från Adobe Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att

* den första funktionen returnerar den senaste händelsen
* den sista funktionen returnerar den äldsta.

Låt oss till exempel säga att ni vill rikta er mot kunder som har övergett en kundvagn de senaste 7 dagarna för att skicka ett meddelande när kunden närmar sig en butik, med ett erbjudande på artiklar de vill ha som finns i butik.

**Du måste skapa följande villkor:**

Först och främst målkunder som surfar i onlinebutiken men inte slutfört beställningen de senaste sju dagarna.

**Det här uttrycket söker efter ett angivet värde i ett strängvärde:**

`In ("addToCart", #{field reference from experience event})`

**Det här uttrycket söker efter alla händelser för den här användaren som har angetts under de senaste 7 dagarna:**

Sedan väljs alla tilläggshändelser i kundvagnen som inte omvandlats till completePurchase.

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

**Låt oss nu skapa ett uttryck som kontrollerar att produkten finns i lager**

* I Inventory söker det här uttrycket efter kvantitetsfält för en produkt och anger att det ska vara större än 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Till höger anges de nödvändiga värdena, här måste vi hämta platsen för butiken som mappas från platsen för händelsen ArriveLumaStudio:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Ange SKU och använd funktionen `first` för att hämta den senaste addToCart-åtgärden:

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
        @event{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Förklaring: Detta är en strikt strängjämförelse (skiftlägeskänslig), som motsvarar en fråga i enkelt läge där `equal to` används med `Is sensitive` markerat.

Samma fråga med `Is sensitive` avmarkerat genererar följande uttryck i avancerat läge:

```json
        equalIgnoreCase(@event{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**I åtgärder**

Följande uttryck gör att du kan definiera CRM-ID:t i ett åtgärdspersonaliseringsfält:

```json
substr(
   @event{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @event{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Förklaring: I det här exemplet används funktionerna `substr` och `lastIndexOf` för att ta bort klammerparenteser som omger det CRM-ID som skickas med en starthändelse för en mobilapp.


Titta på [den här videon](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/introduction-to-building-a-journey.html?lang=sv-SE) om du vill veta mer om hur du använder den avancerade uttrycksredigeraren.
