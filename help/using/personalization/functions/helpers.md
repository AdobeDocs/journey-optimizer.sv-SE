---
title: Hjälpmedel
description: Hjälpmedel
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 4%

---


# Hjälpprogram {#gs-helpers}

![](../../assets/do-not-localize/badge.png)


## Villkor{#if-function}

Hjälpprogrammet `if` används för att definiera ett villkorsstyrt block.
Om uttrycksutvärderingen returnerar true återges blocket, i annat fall hoppas det över.

**Syntax**

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

Efter `if`-hjälpen kan du ange en `else`-sats för att ange ett kodblock som ska köras, om samma villkor är false.
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

1. **Lägga till en villkorlig länk**

   Följande åtgärd lägger till en länk till www.adobe.com/academia&#39; webbplats för profiler med e-postadresser endast med namnet .edu, till www.adobe.com/org&#39; webbplats för profiler med e-postadresserna .org och standardwebbadressen www.adobe.com/users&#39; för alla andra profiler:

   ```sql
   {%#if contains(profile.personalEmail.address, ".edu")%}
   <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
   {%else if contains(profile.personalEmail.address, ".org")%}
   <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
   {%else%}
   <a href="https://www.adobe.com/users">Checkout our page</a>
   {%/if%}
   ```

1. **Villkorligt innehåll baserat på segmentmedlemskap**

   ```sql
   {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
   Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
   {%else%} if 'profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"'%}
   Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
   {%/if%}
   ```

1. **Kontrollera om en profil redan är medlem**

   ```sql
   {%#if profile.segmentMembership.get(segments.`123e4567-e89b-12d3-a456-426614174000`.id)%}
       You're a member!
   {%else%}
       You should be a member! Sign up now!
   {%/if%}
   ```

>[!NOTE]
>
>Mer information om segmenterings- och segmenteringstjänster finns i det här [avsnittet](../../segment/about-segments.md).


## Om{#unless}

Hjälpprogrammet `unless` används för att definiera ett villkorsstyrt block. Om uttrycksutvärderingen returnerar &quot;false&quot; återges blocket som motsatt till hjälpfunktionen `if`.

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
Hjälpprogrammets syntax är ```{{#each ArrayName}}``` YourContent {{/each}}
Vi kan referera till de enskilda arrayobjekten genom att använda nyckelordet **this** inuti blocket. Indexvärdet för arrayelementet kan återges med {{@index}}.

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

Hjälpprogrammet `with` används för att ändra utvärderingstoken för malldel.

**Syntax**

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

Hjälpprogrammet `with` är också användbart för att definiera en variabel för genvägar.

**Exempel**

Använd med för att skapa alias för långa variabelnamn för kortare:

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

## Låt{#let}

Med funktionen `let` kan ett uttryck lagras som en variabel som senare kan användas i en fråga.

**Syntax**

```sql
{% let variable = expression %} {{variable}}
```

**Exempel**

I följande exempel tillåts alla produktsummor med transaktionen i USD där summan är större än 100 och mindre än 1 000 USD.

```sql
{% let variable = expression %} {{variable}}
```
