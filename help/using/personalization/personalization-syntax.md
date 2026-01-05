---
solution: Journey Optimizer
product: journey optimizer
title: Personalization syntax
description: Lär dig hur du använder personaliseringssyntax.
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: uttryck, redigerare, syntax, personalisering
exl-id: 5a562066-ece0-4a78-92a7-52bf3c3b2eea
source-git-commit: 5e9ce28bf19d2f4406ab4fd395b44b72894928e6
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 1%

---

# Personalization syntax {#personalization-syntax}

Personalization i [!DNL Journey Optimizer] baseras på den mallsyntax som kallas Handlebars. En fullständig beskrivning av Handlebars syntax finns i [HandlebarsJS-dokumentationen](https://handlebarsjs.com/).

Den använder en mall och ett indataobjekt för att generera HTML eller andra textformat. Mallar för handtag ser ut som vanlig text med inbäddade handtagsuttryck.

Exempel på enkla uttryck:

`{{profile.person.name}}`

där:

* `profile` är ett namnutrymme.
* `person.name` är en token som består av attribut. Attributstrukturen definieras i ett Adobe Experience Platform XDM-schema. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

## Allmänna syntaxregler {#general-rules}

* Identifierare kan vara vilket Unicode-tecken som helst förutom följande specialtecken, som är reserverade för Handlebars-syntaxen:

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* Syntaxen är skiftlägeskänslig.

* Orden **true**, **false**, **null** och **undefined** tillåts bara i den första delen av ett sökvägsuttryck.

* I Handlebars är värdena som returneras av {{expression}} **HTML-escape**. Om uttrycket innehåller `&` genereras returnerade HTML-escape-utdata som `&amp;`. Om du inte vill att Handlebars ska hoppa över ett värde använder du &quot;trippelstreck&quot;.

  Anta att värdet för fältet `profile.person.name` är &quot;Mark &amp; Mary&quot;. Syntaxen `{{profile.person.name}}` visar `Mark &amp; Mary` medan `{{{profile.person.name}}}` visar `Mark & Mary`.

* När det gäller argument för literala funktioner saknar den mallande språkparsern stöd för ett omvänt snedstreck (`\`) av typen unescape. Det här tecknet måste föregås av ett ytterligare omvänt snedstreck (`\`). Exempel:

  `{%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}`

## Reserverade nyckelord {#reserved-keywords}

Vissa nyckelord är reserverade i Profile Query Language (PQL) och kan inte användas direkt som fält- eller variabelnamn i personaliseringsuttryck. Om XDM-schemat innehåller fält med namn som matchar reserverade nyckelord måste du undvika dem med hjälp av bakterier (`` ` ``) för att referera till dem i dina uttryck.

**Reserverade nyckelord är:**

* `next`
* `last`
* `this`

**Exempel:**

Om ditt profilschema har ett fält med namnet `next` måste du omsluta det med bakgrunder:

```
{{profile.person.`next`.name}}
```

Utan de här blocken misslyckas personaliseringsredigeraren med valideringen och ett fel inträffar.

## Tillgängliga namnutrymmen {#namespaces}

* **Profil**

  Med det här namnutrymmet kan du referera till alla attribut som definieras i profilschemat som beskrivs i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

  Attributen måste definieras i schemat innan de refereras i ett [!DNL Journey Optimizer]-anpassningsblock.

  Mer information om hur du återanvänder profilattribut i villkor finns i [det här avsnittet](functions/helpers.md#if-function).

  +++Exempelreferenser

   * `{{profile.person.name.fullName}}`
   * `{{profile.person.name.firstName}}`
   * `{{profile.person.gender}}`
   * `{{profile.personalEmail.address}}`
   * `{{profile.mobilePhone.number}}`
   * `{{profile.homeAddress.city}}`
   * `{{profile.faxPhone.number}}`

  +++

* **Målgrupp**

  Mer information om segmenteringstjänsten finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.

* **Erbjudanden**

  Med det här namnutrymmet kan du referera till befintliga offertbeslut.

  Om du vill hänvisa till ett erbjudande måste du deklarera en sökväg med den information som definierar ett erbjudande. Den här sökvägen har följande struktur:

  `offers.Type.[Placement Id].[Activity Id].Attribute`

  där:

   * `offers` identifierar sökvägsuttrycket som tillhör namnutrymmet offer
   * `Type` bestämmer typen av erbjudanderepresentation. Möjliga värden är: `image`, `html` och `text`
   * `Placement Id` och `Activity Id` är placerings- och aktivitetsidentifierare
   * `Attributes` erbjuder specifika attribut som är beroende av erbjudandetypen. Exempel: `deliveryUrl` för bilder

  Mer information om beslut-API och om offertrepresentationer finns på [den här sidan](../offers/api-reference/offer-delivery-api/decisioning-api.md)

  Alla referenser valideras mot offertschema med en valideringsmekanism som beskrivs på [den här sidan](../personalization/personalization-build-expressions.md)

  +++Exempelreferenser

   * Plats där bilden finns:

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

   * Mål-URL när du klickar på bilden:

     `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

   * Innehåll i det erbjudande som kommer från beslutsmotorn:

     `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

   * HTML innehåll i erbjudandet som kommer från beslutsmotorn:

     `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

  +++

## Hjälpmedel {#helpers-all}

Handtag-hjälpen är en enkel identifierare som kan följas av parametrar. Varje parameter är ett Handlebars-uttryck. Hjälpprogrammen kan nås från alla sammanhang i en mall.

Dessa blockhjälpare identifieras av en `#` före hjälpnamnet och kräver en matchande avslutande `/` med samma namn.

Blocken är uttryck som har ett blocköppning (`{{# }}`) och stängning (`{{/}}`).

    Mer information om hjälpfunktioner finns i [det här avsnittet](functions/helpers.md).

## Literala typer {#literal-types}

[!DNL Adobe Journey Optimizer] stöder följande literaltyper:

| Literal | Definition |
| ------- | ---------- |
| Sträng | En datatyp som består av tecken omgivna av dubbla citattecken. <br>Exempel: `"prospect"`, `"jobs"`, `"articles"` |
| Boolean | En datatyp som är antingen true eller false. |
| Heltal | En datatyp som representerar ett heltal. Den kan vara positiv, negativ eller noll. <br>Exempel: `-201`, `0`, `412` |
| Array | En datatyp som består av en grupp med andra literala värden. Här används hakparenteser för att gruppera och kommatecken för att avgränsa mellan olika värden. <br> **Obs!** Du kan inte komma åt egenskaper direkt för objekt i en array. <br> Exempel: `[1, 4, 7]`, `["US", "FR"]` |

>[!CAUTION]
>
>Det går inte att använda variabeln **xEvent** i personaliseringsuttryck. Alla referenser till xEvent resulterar i valideringsfel.
