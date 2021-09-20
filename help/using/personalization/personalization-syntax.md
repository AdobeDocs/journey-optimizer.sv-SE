---
title: Anpassningssyntax
description: Lär dig använda personaliseringssyntax
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: fe39570b-cbd2-4b24-af10-e12990a9a885
source-git-commit: 5a21ac0c199bf237972122ac46e58bf9f8d0f8ab
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Anpassningssyntax {#personalization-syntax}

Personalisering i [!DNL Journey Optimizer] baseras på den mallsyntax som kallas Handlebars.
En fullständig beskrivning av Handlebars syntax finns i [HandlebarsJS-dokumentation](https://handlebarsjs.com/).

Den använder en mall och ett indataobjekt för att generera HTML eller andra textformat. Mallar för handtag ser ut som vanlig text med inbäddade handtagsuttryck.

Exempel på enkla uttryck:

`{{profile.person.name}}`

där:

* `profile` är ett namnutrymme.
* `person.name` är en token som består av attribut. Attributstrukturen definieras i ett Adobe Experience Platform XDM-schema. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

## Allmänna syntaxregler

Identifierare kan vara vilket Unicode-tecken som helst utom för följande:

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

Syntaxen är skiftlägeskänslig.

Orden **true**, **false**, **null** och **undefined** tillåts bara i den första delen av ett sökvägsuttryck.

I Handlebars är de värden som returneras av {{expression}} **HTML-escape**. Om uttrycket innehåller `&` genereras de returnerade HTML-escape-utdata som `&amp;`. Om du inte vill att Handlebars ska kringgå ett värde använder du &quot;trippelstreck&quot;.

## Profil

Med det här namnutrymmet kan du referera till alla attribut som definieras i profilschemat som beskrivs i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target=&quot;_blank&quot;}.

Attributen måste definieras i schemat innan de refereras i ett [!DNL Journey Optimizer]-anpassningsblock.

>[!NOTE]
>
>Lär dig hur du använder profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

**Exempelreferenser:**

`{{profile.person.name.fullName}}`

`{{profile.person.name.firstName}}`

`{{profile.person.gender}}`

`{{profile.personalEmail.address}}`

`{{profile.mobilePhone.number}}`

`{{profile.homeAddress.city}}`

`{{profile.faxPhone.number}}`

## Segment{#perso-segments}

Lär dig hur du använder profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

>[!NOTE]
>Mer information om segmenterings- och segmenteringstjänster finns i [det här avsnittet](../segment/about-segments.md).

## Erbjudanden

Med det här namnutrymmet kan du referera till befintliga offertbeslut.
Om du vill hänvisa till ett erbjudande måste du deklarera en sökväg med den information som definierar ett erbjudande.

Sökvägen har följande struktur:

`offers.Type.[Placement Id].[Activity Id].Attribute`

där:

* `offers` identifierar det sökvägsuttryck som tillhör namnutrymmet offer
* `Type`  fastställer typen av erbjudanderepresentation. Möjliga värden är: `image`, `html` och `text`
* `Placement Id` och  `Activity Id` är placerings- och aktivitetsidentifierare
* `Attributes` är specifika attribut som är beroende av erbjudandetypen. Exempel: `deliveryUrl` för bilder

Mer information om besluts-API och offerterepresentation finns på [den här sidan](../../using/offers/api-reference/decisions-api/deliver-offers.md)

Alla referenser valideras mot offertschema med en valideringsmekanism som beskrivs i [den här sidan](personalization-validation.md)

**Exempelreferenser:**

* Plats där bilden finns:

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

* Mål-URL när du klickar på bilden:

   `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

* Innehåll i det erbjudande som kommer från beslutsmotorn:

   `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

* HTML-innehåll i erbjudandet som kommer från beslutsmotorn:

   `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`


## Hjälpmedel{#helpers-all}

Handtag-hjälpen är en enkel identifierare som kan följas av parametrar.
Varje parameter är ett Handlebars-uttryck. Hjälpprogrammen kan nås från alla sammanhang i en mall.

Dessa blockhjälpare identifieras med # före hjälpnamnet och en matchande avslutande /, med samma namn krävs.
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

## URL-anpassning{#perso-urls}

Med Journey Orchestration kan du anpassa en eller flera URL-adresser i meddelandet genom att lägga till anpassningsfält till dem. Så här gör du:

* Skapa en länk i ditt e-postinnehåll eller push-innehåll. Mer information om hur du skapar länkar finns på [den här sidan](../message-tracking#insert-links)).
* Klicka på personaliseringsikonen. Den här ikonen är tillgänglig för följande typer av länkar: **Extern länk**, **Ta bort prenumerationslänk** och **Avanmäl dig**.

![](assets/perso-url.png)

>[!NOTE]
>`
>När du redigerar en anpassad URL i uttrycksredigeraren inaktiveras hjälpfunktioner och segmentmedlemskap av säkerhetsskäl.

** Exempel på personaliserade URL:er **

* `https://www.adobe.com/users/{{profile.person.name.lastName}}`
* `https://www.adobe.com/users?uid={{profile.person.name.firstName}}`
* `https://www.adobe.com/usera?uid={{context.journey.technicalProperties.journeyUID}}`
* `https://www.adobe.com/users?uid={{profile.person.crmid}}&token={{context.token}}`

