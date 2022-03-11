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

Den avancerade uttrycksredigeraren kan användas för att skapa villkor som gör att du kan filtrera användare på dina resor. These conditions enable you to target users on time, date, location, duration, or actions such as purchase or abandonment of carts so that they can be retargeted in the journey.

>[!NOTE]
>
>Händelser börjar med @, datakällor med #.

## Bygga villkor för upplevelsehändelser

Den avancerade uttrycksredigeraren är obligatorisk för att utföra frågor på tidsserier som en lista över inköp eller tidigare klick på meddelanden. Sådana frågor kan inte utföras med den enkla redigeraren.

Erfarenhetshändelserna hämtas från Adobe Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att

* den första funktionen returnerar den senaste händelsen
* last function will return the oldest one.

For example, let&#39;s say you want to target customers with a cart abandonment in the last 7 days to send a message when the customer is getting near a store, with an offer on items they wanted that are in store.

**Du måste skapa följande villkor:**

Först och främst målkunder som surfar i onlinebutiken men inte slutfört beställningen de senaste sju dagarna.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Det här uttrycket söker efter alla händelser för den här användaren som har angetts under de senaste 7 dagarna:**

Sedan markeras alla tilläggshändelser som inte omvandlades till completePurchase.

>[!NOTE]
>
>To insert fields in the expression quickly, double-click the field in the left panel of the editor.

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

* And specify SKU, using the function `first` to retrieve the most recent &quot;addToCart&quot; interaction:

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

This condition retrieve only the geofence events triggered in &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explanation: This is a strict string comparison (case sensitive), equivalent to a query in simple mode that uses `equal to` with `Is sensitive` checked.

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
