---
title: Anpassningssyntax
description: Lär dig använda personaliseringssyntax
source-git-commit: 7e20bef085d0fa6983f9ebd84f8cbc3bee2f4542
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Anpassningssyntax {#personalization-syntax}

![](../assets/do-not-localize/badge.png)

Personalisering i [!DNL Journey Optimizer] baseras på den mallsyntax som kallas Handlebars.
En fullständig beskrivning av Handlebars syntax finns i [HandlebarsJS-dokumentation](https://handlebarsjs.com/).

Den använder en mall och ett indataobjekt för att generera HTML eller andra textformat. Mallar för handtag ser ut som vanlig text med inbäddade handtagsuttryck.

Exempel på enkla uttryck:

```sql
{{profile.person.name}}
```

där:

* **profilen** är ett namnutrymme.
* **person.** name är en token som består av attribut. Attributstrukturen definieras i ett Adobe Experience Platform XDM-schema. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).

## Allmänna syntaxregler

Identifierare kan vara vilket Unicode-tecken som helst utom för följande:

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

Syntaxen är skiftlägeskänslig.

Orden **true**, **false**, **null** och **undefined** tillåts bara i den första delen av ett sökvägsuttryck.

I Handlebars är de värden som returneras av {{expression}} **HTML-escape**. Om uttrycket innehåller &amp; genereras returnerade HTML-escape-utdata som &amp;. Om du inte vill att Handlebars ska kringgå ett värde använder du &quot;trippelstreck&quot;.

## Profil

Med det här namnutrymmet kan du referera till alla attribut som definieras i det profilschema som beskrivs i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

Attributen måste definieras i schemat innan de refereras i ett [!DNL Journey Optimizer]-anpassningsblock.

Alla referenser valideras mot profilschema med en valideringsmekanism som beskrivs i [den här sidan](personalization-validation.md).

**Exempelreferenser:**

* ```{{profile.person.name.fullName}}```
* ```{{profile.person.name.firstName}}```
* ```{{profile.person.gender}}```
* ```{{profile.personalEmail.address}}```
* ```{{profile.mobilePhone.number}}```
* ```{{profile.homeAddress.city}}```
* ```{{profile.faxPhone.number}}```

>[!NOTE]
>
>Lär dig hur du använder profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

## Segment{#perso-segments}

Lär dig hur du använder profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

>[!NOTE]
>Mer information om segmenterings- och segmenteringstjänster finns i [det här avsnittet](../segment/about-segments.md).


## Erbjudanden

Med det här namnutrymmet kan du referera till befintliga offertbeslut.
Om du vill hänvisa till ett erbjudande måste du deklarera en sökväg med den information som definierar ett erbjudande.

Sökvägen har följande struktur:
0 - erbjudanden: identifierar det sökvägsuttryck som tillhör namnutrymmet offer
1 - Typ: fastställer typen av erbjudanderepresentation. Giltiga värden är image, html och text
2 - Placerings-ID
3 - Aktivitets-ID
4 - Erbjud specifika attribut. Beroende på erbjudandetypen kan attribut som stöds användas. Exempel för bilder `deliveryUrl`.

Mer information om API:t för beslut finns på [den här sidan](https://experienceleague.adobe.com/docs/offer-decisioning/using/api-reference/offer-delivery/deliver-offers.html?lang=en#deliver-offers-using-the-decisions-api).

Mer information om Erbjudanderepresentation finns på [den här sidan](https://experienceleague.adobe.com/docs/offer-decisioning/using/api-reference/offer-delivery/deliver-offers.html?lang=en#accept-and-content-type-headers).

Alla referenser valideras mot offertschema med en valideringsmekanism som beskrivs i [den här sidan](personalization-validation.md).

**Exempelreferenser:**

* Plats där bilden finns:

   ```offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl```

* Mål-URL när du klickar på bilden:

   ```offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl```

* Innehåll i det erbjudande som kommer från beslutsmotorn:

   ```offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content```

* HTML-innehåll i erbjudandet som kommer från beslutsmotorn:

   ```offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content```


## Hjälpprogram{#helpers-all}

Handtag-hjälpen är en enkel identifierare som kan följas av parametrar.
Varje parameter är ett Handlebars-uttryck. Hjälpprogrammen kan nås från alla sammanhang i en mall.

Dessa blockhjälpare identifieras av ett # före hjälpnamnet och kräver en matchande avslutande /, med samma namn.
Blocken är uttryck som har ett block som öppnas ({{# }}) och avslutas ({{/}}).


>[!NOTE]
>
>Hjälpfunktioner beskrivs i [det här avsnittet](functions/helpers.md).


## Literala typer

[!DNL Adobe Journey Optimizer] har stöd för följande literala typer:

| Literal | Definition |
| ------- | ---------- |
| Sträng | En datatyp som består av tecken omgivna av dubbla citattecken. <br>Exempel: `"prospect"`, `"jobs"`, `"articles"` |
| Boolean | En datatyp som är antingen true eller false. |
| Heltal | En datatyp som representerar ett heltal. Den kan vara positiv, negativ eller noll. <br>Exempel: `-201`, `0`, `412` |
| Array | En datatyp som består av en grupp med andra literala värden. Här används hakparenteser för att gruppera och kommatecken för att avgränsa mellan olika värden. <br> **Obs!** Du kan inte komma åt egenskaper direkt för objekt i en array. <br> Exempel: `[1, 4, 7]`, `["US", "FR"]` |

>[!CAUTION]
>
>Det går inte att använda variabeln **xEvent** i personaliseringsuttryck. Alla referenser till xEvent resulterar i valideringsfel.
