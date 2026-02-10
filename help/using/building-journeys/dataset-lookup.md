---
solution: Journey Optimizer
product: journey optimizer
title: Använd  [!DNL Adobe Experience Platform] data i resor
description: Lär dig hur du använder datauppsättningsaktiviteten i [!DNL Adobe Journey Optimizer] för att förbättra kundresor med externa data från [!DNL Adobe Experience Platform].
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
version: Journey Orchestration
badge: label="Begränsad tillgänglighet" type="Informative"
exl-id: b6f54a79-b9e7-4b3a-9a6f-72d5282c01d3
source-git-commit: 70653bafbbe8f1ece409e3005256d9dff035b518
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# Använd [!DNL Adobe Experience Platform]-data i resor {#datalookup}

>[!CONTEXTUALHELP]
>id="ajo_journey_dataset_lookup"
>title="Uppslagsaktivitet för datauppsättning"
>abstract="Med aktiviteten **[!UICONTROL Dataset lookup]** kan du hämta data dynamiskt från [!DNL Adobe Experience Platform] postdatamängder under körning. Genom att utnyttja den här funktionen kan ni få tillgång till data som kanske inte finns i profilen eller händelsens nyttolast, vilket säkerställer att era kundinteraktioner är både relevanta och aktuella."

Med aktiviteten **[!UICONTROL Dataset lookup]** kan du hämta data dynamiskt från [!DNL Adobe Experience Platform] postdatamängder under körning. Genom att utnyttja den här funktionen kan ni få tillgång till data som kanske inte finns i profilen eller händelsens nyttolast, vilket säkerställer att era kundinteraktioner är både relevanta och aktuella.

Viktiga fördelar:

* **Realtidspersonalisering**: Skräddarsy kundupplevelser med hjälp av berikade data.
* **Dynamiskt beslutsfattande**: Använd externa data för att driva kundlogik och -åtgärder.
* **Förbättrad dataåtkomst**: Hämta produktmetadata, pristabeller eller relationsdata som är kopplade till specifika nycklar.

>[!AVAILABILITY]
>
>Den här aktiviteten är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

## Måste läsas {#must-read}

Granska dessa krav innan du konfigurerar datasökningar.

### Aktivera datauppsättning

Datauppsättningen måste aktiveras för sökning i [!DNL Adobe Experience Platform]. Detaljerad information finns i det här avsnittet: [Använd [!DNL Adobe Experience Platform] data](../data/lookup-aep-data.md).

### Begränsningar och begränsningar

* Maximalt 10 uppslagsaktiviteter för datauppsättningar per resa.
* Högst 20 markerade fält.
* Högst 50 nycklar i uppslagstangentarrayen.
* Förbättrad datastorlek är begränsad till 10 kB.

### Ytterligare prestandaöverväganden

Rekommendationerna nedan är riktlinjer för att undvika förseningar i leveransen:

| Övervägande | Rekommenderad gräns | Beskrivning |
| ------- | ------- | ------- |
| Attribut per sökning | Upp till 20 | Antal datafält som har hämtats per post i en enda sökningsaktivitet. |
| Uppslagsaktiviteter | Upp till 5 per resa | Varje resa kan innehålla upp till fem separata sökningsaktiviteter. Varje sökning kan ha en egen datauppsättning som mål. |

## Konfigurera datauppslagsaktiviteten {#configure}

Så här konfigurerar du aktiviteten **[!UICONTROL Dataset lookup]**:

1. Öppna kategorin **[!UICONTROL Orchestration]** och släpp en **[!UICONTROL Dataset lookup]**-aktivitet på arbetsytan.

   ![[!DNL Adobe Experience Platform]-datauppsättningssökningsaktivitet på resan &#x200B;](assets/aep-data-activity.png)

1. Lägg till en etikett och en beskrivning.

1. I fältet **[!UICONTROL Dataset]** väljer du datauppsättningen med de attribut du behöver.

   >[!NOTE]
   >
   >Om den datauppsättning du söker inte visas i listan kontrollerar du att du har aktiverat den för sökning. Mer information finns i avsnittet [Måste läsa](#must-read).

1. Markera de specifika fält som du vill hämta från datauppsättningen.

   * Du kan bara välja lövnoder (fält på den lägsta nivån i schemat). Fältet måste vara ett primitivt värde (sträng, tal, booleskt värde, datum osv.).

   * Det går inte att markera listor (arrayer) och kartor (nyckelvärdesobjekt).

   +++Exempel

   ![Markering av datauppsättningsfält med primitiva datatyper och struktur](assets/aep-data-leaf-primitive.png)

   +++

1. I fältet **[!UICONTROL Lookup key(s)]** väljer du en kopplingsnyckel som finns i både beslutsobjektattributen och datauppsättningen. Den här nyckeln används av systemet för att söka i den valda datauppsättningen.

   * Tangenter kan vara uttryck som härleds från kundresans kontext, t.ex. SKU:er, e-post-ID:n eller andra identifierare. Exempel: `@profile.email` eller `list(@event{purchase_event.products.sku})`.

   * Endast **strängar** eller **listor med strängar** stöds.

   +++Exempel

   ![Uttrycksredigeraren med sökning efter datauppsättningsfält och strängfunktioner](assets/aep-data-strings.png)

   +++

## Använd berikade data under resan

De data som hämtas av aktiviteten **[!UICONTROL Dataset lookup]** lagras i resekontexten som en array med objekt. Den finns i reseuttrycksredigeraren och personaliseringsredigeraren, vilket möjliggör villkorsstyrd logik och personaliserade meddelanden baserat på berikade data.

* **Resursuttrycksredigeraren**:

  Gå till redigeraren för **[!UICONTROL Advanced mode]** och använd syntaxen: `@datasetLookup{MyDatasetLookUpActivity1.entities}`. [Lär dig arbeta med den avancerade uttrycksredigeraren](../building-journeys/expression/expressionadvanced.md)

* **Personalization Editor**:

  Använd syntaxen: `{{context.journey.datasetLookup.1482319411.entities}}`.

>[!NOTE]
>
>Förbättrade data är tillfälliga och tillgängliga endast under körningen av resan och i personaliseringen av utgående aktiviteter (e-post, push, SMS etc.)

## Exempel på användningsexempel

+++Produktkategoribaserad filtrering

**Scenario**:Send en kupong för användare som spenderar mer än 40 USD på hushållsprodukter.

**Reseflöde**:

1. **Inköpshändelse**: Hämta SKU:er från användarens kundvagn.

1. **Datauppsättningssökningsaktivitet**:

   * Datauppsättning: `products-dataset` (SKU som primärnyckel).
   * Uppslagstangenter: `list(@event{purchase_event.products.sku})`.
   * Fält som ska returneras: `["SKU", "category", "price"]`.

1. **Villkorsaktivitet**:

   * Filtrera SKU:er där kategorin är&quot;hushåll&quot;.

     ```
     @event{purchase_event.products.all( in(currentEventField.sku, @datasetlookup{MyDatasetLookupActivity1.entities.all(currentDatasetLookupField.category == 'household').sku} ) )} 
     ```

   ELLER

   * Sammanfatta de totala utgifterna för hushållsprodukter och jämför dem med tröskelvärdet på 40 dollar.

     ```
     sum(@event{purchase_event.products.all( in(currentEventField.sku, @datasetlookup{MyDatasetLookUpActivity1.entities.all(currentDatasetLookupField.category == 'household').sku} ) )}.price}, ',', true ) > 40
     ```

1. **Personalization Editor**:

   Använd data som berikats för att anpassa e-postinnehållet:

   ```
   {% let householdTotal = 0 %}
   {{#each journey.datasetlookup.3709000.entities as |product|}}
   {%#if get(product, "category") = "household"%}
   {% let householdTotal = householdTotal + product.price %}{%/if%}
   {{/each}}
   "Hi, thanks for spending " + {%= householdTotal %} + " on household products. Here is your reward!"
   ```

+++

+++Personalization som använder externa lojalitetsdata

**Scenario**: Identifiera vilket e-postkonto för en profil som har lojalitetsstatusen Platinum. I det här scenariot är förmånskontot kopplat till ett e-post-ID och lojalitetsdata är inte tillgängliga i standardprofilsökningsarkivet.

**Reseflöde**:

1. **Profilhändelseutlösare**: Hämta e-post-ID:n från profilen eller händelsekontexten.

1. **Uppslagsaktivitet för datauppsättning**:
   * Datauppsättning: `loyalty-member-dataset` (e-post som primärnyckel).
   * Uppslagstangenter: `@profile.email`.
   * Fält som ska returneras: `["email", "loyaltyTier"]`.

1. **Villkorsaktivitet**:

   Fördela resan baserat på lojalitetsnivån:

   ```
   @datasetLookup{MyDatasetLookUpActivity1.entity.loyaltyMember.loyaltyTier} == 'Platinum'
   ```

1. **Personalization Editor**:

   Använd data från den förbättrade lojalitetsnivån för att personalisera utgående kommunikation:

   ```
   {{context.journey.datasetLookup.1482319411.entity.loyaltyMember.loyaltyTier}}
   ```
