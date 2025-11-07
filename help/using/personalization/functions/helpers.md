---
title: Hjälpmedel
description: Hjälpmedel
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 221368c7766e942143639fcd554b32f9de5ab0c9
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# Hjälpmedel {#gs-helpers}

## Standardvärde för reserv{#default-value}

Hjälpprogrammet `Default Fallback Value` används för att returnera ett standardreservvärde om ett attribut är tomt eller null. Den här mekanismen fungerar för profilattribut och resthändelser.

**Syntax**

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

I det här exemplet visas värdet `there` om attributet `firstName` för den här profilen är tomt eller null.

## Villkor{#if-function}

Hjälpprogrammet `if` används för att definiera ett villkorsblock.
Om uttrycksutvärderingen returnerar true återges blocket, i annat fall hoppas det över.

**Syntax**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

Efter hjälpen för `if` kan du ange en `else`-sats för att ange ett kodblock som ska köras, om samma villkor är falskt.
Programsatsen `elseif` anger ett nytt villkor som ska testas om den första programsatsen returnerar false.


**Format**

```sql
{
    {
        {%#if condition1%} element_1 
        {%else if condition2%} element_2 
        {%else%} default_element 
        {%/if%}
    }
}
```

**Exempel**

1. **Återge olika butikslänkar baserat på villkorsuttryck**

   ```sql
   {%#if profile.homeAddress.countryCode = "FR"%}
   <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
   {%else%}
   <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
   {%/if%}
   ```

1. **Fastställ e-postadresstillägg**

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **Lägg till en villkorlig länk**

   Följande åtgärd lägger till en länk till www.adobe.com/academia&#39; webbplats för profiler med e-postadresserna .edu, till www.adobe.com/org&#39; webbplats för profiler med e-postadresserna .org och standardwebbadressen www.adobe.com/users&#39; för alla andra profiler:

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **Villkorligt innehåll baserat på målgruppsmedlemskap**

   ```sql
   {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
   Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
   {%else if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

>[!NOTE]
>
>Mer information om målgrupper och segmenteringstjänsten finns i [det här avsnittet](../../audience/about-audiences.md).


## Om{#unless}

Hjälpprogrammet `unless` används för att definiera ett villkorsblock. Om uttrycksutvärderingen returnerar false återges blocket som motsatt `if`-hjälpen.

**Syntax**

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**Exempel**

Återge innehåll baserat på e-postadresstillägg:

```sql
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content
{%/unless%}
```

## Varje{#each}

Hjälpprogrammet `each` används för att iterera över en array.
Den hjälpandes syntax är ```{{#each ArrayName}}``` YourContent `{{/each}}`
Vi kan referera till de enskilda arrayobjekten genom att använda nyckelordet **this** inuti blocket. Index för arrayelementet kan återges med `{{@index}}`.

**Syntax**

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
{{/each}}
```

**Exempel**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**Exempel**

Visa en lista över produkter som den här användaren har i kundvagnen:

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
{{/each}}
```

>[!NOTE]
>
>Du kan också använda hjälpen för `each` för att iterera över arrayer som returneras från anpassade åtgärdssvar. Ett exempel på hur du itererar över kapslade arrayer från ett anpassat åtgärdssvar finns i [Använda anpassade åtgärdssvar i inbyggda kanaler](../../action/action-response.md#response-in-channels).

## Med{#with}

Hjälpprogrammet `with` används för att ändra utvärderingstoken för malldel.

**Syntax**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

Hjälpprogrammet `with` är också användbart för att definiera en genvägsvariabel.

**Exempel**

Använd med för att skapa alias för långa variabelnamn för kortare:

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

## Låt{#let}

Funktionen `let` tillåter att ett uttryck lagras som en variabel som kan användas senare i en fråga.

**Syntax**

```sql
{% let variable = expression %} {{variable}}
```

**Exempel**

I följande exempel kan du beräkna den totala summan av priserna för produkter i vagnen med priser mellan 100 och 1000.

```sql
{% let sum = 0%}
    {{#each profile.productsInCart as |p|}}
        {%#if p.price>100 and p.price<1000%}
            {%let sum = sum + p.price %}
        {%/if%}
    {{/each}}
{{sum}}
```

## Körningsmetadata {#execution-metadata}

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Hjälpprogrammet `executionMetadata` gör att du kan hämta och lagra anpassade nyckelvärdepar dynamiskt i meddelandekörningskontexten.

**Syntax**

```
{{executionMetadata key="your_key" value="your_value"}}
```

I den här syntaxen refererar `key` till metadatanamnet och `value` är de metadata som ska bevaras.

**Användningsfall**

Med den här funktionen kan ni lägga till sammanhangsbaserad information till alla inbyggda åtgärder från era kampanjer eller resor. På så sätt kan ni exportera sammanhangsbaserade data i realtid till externa system för olika syften, som spårning, analys, personalisering och nedladdning.

>[!NOTE]
>
>Funktionen för körningsmetadata stöds inte av [anpassade åtgärder](../../action/action.md).

Du kan till exempel använda hjälpen för metadata för körning för att lägga till ett specifikt ID för varje leverans som skickas till varje profil. Den här informationen genereras under körningen och de inbyggda körningsmetadata som sedan kan exporteras för avstämning i efterföljande led med en extern rapporteringsplattform.

**Så här fungerar det**

Välj ett element från ditt kanalinnehåll i en kampanj eller resa och lägg till `executionMetadata`-hjälpen i det här elementet med hjälp av anpassningsredigeraren.

>[!NOTE]
>
>Funktionen Metadata för körning visas inte när själva innehållet visas.


Vid körning läggs metadatavärdet till i befintliga **[!UICONTROL Message Feedback Event Dataset]** med följande schemaläggning:

```
"_experience": {
  "customerJourneyManagement": {
    "messageExecution": {
      "metadata": {
        "your_key": "your_value"
      }
    }
  }
}
```

>[!NOTE]
>
>Läs mer om datauppsättningar i [det här avsnittet](../../data/get-started-datasets.md).

**Begränsning**

Det finns en övre gräns på 2 kB för nyckelvärdepar per åtgärd.

Om gränsen på 2 kB överskrids levereras meddelandet fortfarande, men något av nyckelvärdeparen kan trunkeras.

**Exempel**

```
{{executionMetadata key="firstName" value=profile.person.name.firstName}}
```

I det här exemplet är den resulterande entiteten `profile.person.name.firstName` = &quot;Alex&quot;:

```
{
  "key": "firstName",
  "value": "Alex"
}
```

