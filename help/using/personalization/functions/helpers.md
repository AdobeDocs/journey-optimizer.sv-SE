---
title: Hjälpmedel
description: Hjälpmedel
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 110c4895ac7f0b683a695e9705a8f8ac54d09637
workflow-type: tm+mt
source-wordcount: '362'
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
   {%else%} if 'profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"'%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

>[!NOTE]
>
>Mer information om målgrupper och segmenteringstjänsten finns i [avsnittet](../../audience/about-audiences.md).


## Om{#unless}

Hjälpprogrammet `unless` används för att definiera ett villkorsblock. Om uttrycksutvärderingen returnerar false återges blocket som motsatt till hjälpen `if`.

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
Some edu specific content Content
{%/unless%}
```

## Varje{#each}

Hjälpprogrammet `each` används för att iterera över en array.
Den hjälpandes syntax är ```{{#each ArrayName}}``` YourContent {{/each}}
Vi kan referera till de enskilda arrayobjekten genom att använda nyckelordet **this** inuti blocket. Index för arrayelementet kan återges med {{@index}}.

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
