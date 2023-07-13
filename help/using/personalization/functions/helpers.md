---
title: Hjälpmedel
description: Hjälpmedel
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: b08dc0f8-c85f-4aca-85eb-92dc76b0e588
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 3%

---

# Hjälpmedel {#gs-helpers}

## Standardvärde för reservalternativ{#default-value}

The `Default Fallback Value` hjälpfunktionen används för att returnera ett standardreservvärde om ett attribut är tomt eller null. Den här mekanismen fungerar för profilattribut och resthändelser.

**Syntax**

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

I det här exemplet är värdet `there` visas om `firstName` Profilens attribut är tomt eller null.

## Villkor{#if-function}

The `if` hjälpfunktionen används för att definiera ett villkorsstyrt block.
Om uttrycksutvärderingen returnerar true återges blocket, i annat fall hoppas det över.

**Syntax**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

Efter `if` kan du ange en `else` -programsats för att ange ett kodblock som ska köras, om samma villkor är false.
The `elseif` -programsatsen anger ett nytt villkor som ska testas om den första programsatsen returnerar false.


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

1. **Lägga till en villkorlig länk**

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
>Mer information om målgrupper och segmenteringstjänsten finns i [section](../../audience/about-audiences.md).


## Om{#unless}

The `unless` hjälpfunktionen används för att definiera ett villkorsstyrt block. Genom att motsätta sig `if`  helper, om uttrycksutvärderingen returnerar false återges blocket.

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

The `each` helper används för att iterera över en array.
Hjälpens syntax är ```{{#each ArrayName}}``` Ditt innehåll {{/each}}
Vi kan referera till de enskilda arrayobjekten med hjälp av nyckelordet **this** inuti blocket. Index för arrayens element kan återges med {{@index}}.

**Syntax**

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
    </br>
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
   </br>
{{/each}}
```

## Med{#with}

The `with` hjälpfunktionen används för att ändra utvärderingstoken för malldel.

**Syntax**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

The `with` hjälpfunktionen är också användbar när du vill definiera en variabel för kortkommandon.

**Exempel**

Använd med för att skapa alias för långa variabelnamn för kortare:

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

## Låt{#let}

The `let` -funktionen tillåter att ett uttryck lagras som en variabel som kan användas senare i en fråga.

**Syntax**

```sql
{% let variable = expression %} {{variable}}
```

**Exempel**

I följande exempel tillåts alla produktsummor med transaktionen i USD där summan är större än 100 och mindre än 1 000 USD.

```sql
{% let variable = expression %} {{variable}}
```
