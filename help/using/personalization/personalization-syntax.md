---
solution: Journey Optimizer
product: journey optimizer
title: Personalization syntax
description: Lär dig hur du använder personaliseringssyntax.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, syntax, personalisering
exl-id: 5a562066-ece0-4a78-92a7-52bf3c3b2eea
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# Personalization syntax {#personalization-syntax}

Personalization i [!DNL Journey Optimizer] baseras på den mallsyntax som kallas Handlebars.
En fullständig beskrivning av Handlebars syntax finns i [HandlebarsJS-dokumentationen](https://handlebarsjs.com/).

Den använder en mall och ett indataobjekt för att generera HTML eller andra textformat. Mallar för handtag ser ut som vanlig text med inbäddade handtagsuttryck.

Exempel på enkla uttryck:

`{{profile.person.name}}`

där:

* `profile` är ett namnutrymme.
* `person.name` är en token som består av attribut. Attributstrukturen definieras i ett Adobe Experience Platform XDM-schema. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

## Allmänna syntaxregler {#general-rules}

Identifierare kan vara vilket Unicode-tecken som helst utom för följande:

```
Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
```

Syntaxen är skiftlägeskänslig.

Orden **true**, **false**, **null** och **undefined** tillåts bara i den första delen av ett sökvägsuttryck.

I Handlebars är värdena som returneras av {{expression}} **HTML-escape**. Om uttrycket innehåller `&` genereras returnerade utdata för HTML-escape som `&amp;`. Om du inte vill att Handlebars ska kringgå ett värde använder du &quot;trippelstreck&quot;.

När det gäller argument för literala funktioner saknar den mallande språkparsern stöd för ett omvänt snedstreck (`\`) av typen unescape. Det här tecknet måste föregås av ett ytterligare omvänt snedstreck (`\`). Exempel:

`{%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}`

## Profil

Med det här namnutrymmet kan du referera till alla attribut som definieras i profilschemat som beskrivs i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

Attributen måste definieras i schemat innan de refereras i ett [!DNL Journey Optimizer]-anpassningsblock.

>[!NOTE]
>
>Lär dig hur du utnyttjar profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

**Exempelreferenser:**

`{{profile.person.name.fullName}}`

`{{profile.person.name.firstName}}`

`{{profile.person.gender}}`

`{{profile.personalEmail.address}}`

`{{profile.mobilePhone.number}}`

`{{profile.homeAddress.city}}`

`{{profile.faxPhone.number}}`

## Målgrupper{#perso-segments}

Lär dig hur du utnyttjar profilattribut i villkoren i [det här avsnittet](functions/helpers.md#if-function).

>[!NOTE]
>Mer information om segmenteringstjänsten finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.

## Erbjudanden {#offers-syntax}

Med det här namnutrymmet kan du referera till befintliga offertbeslut.
Om du vill hänvisa till ett erbjudande måste du deklarera en sökväg med den information som definierar ett erbjudande.

Den här sökvägen har följande struktur:

`offers.Type.[Placement Id].[Activity Id].Attribute`

där:

* `offers` identifierar sökvägsuttrycket som tillhör namnutrymmet offer
* `Type` bestämmer typen av erbjudanderepresentation. Möjliga värden är: `image`, `html` och `text`
* `Placement Id` och `Activity Id` är placerings- och aktivitetsidentifierare
* `Attributes` erbjuder specifika attribut som är beroende av erbjudandetypen. Exempel: `deliveryUrl` för bilder

Mer information om besluts-API och offertrepresentation finns på [den här sidan](../offers/api-reference/offer-delivery-api/decisioning-api.md)

Alla referenser valideras mot offertschema med en valideringsmekanism som beskrivs i [den här sidan](personalization-validation.md)

**Exempelreferenser:**

* Plats där bilden finns:

  `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].deliveryUrl`

* Mål-URL när du klickar på bilden:

  `offers.image.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].linkUrl`

* Innehåll i det erbjudande som kommer från beslutsmotorn:

  `offers.text.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`

* Innehållet i HTML i erbjudandet från beslutsmotorn:

  `offers.html.[offers:xcore:offer-placement:126f767d74b0da80].[xcore:offer-activity:125e2c6889798fd9].content`


## Hjälpmedel{#helpers-all}

Handtag-hjälpen är en enkel identifierare som kan följas av parametrar.
Varje parameter är ett Handlebars-uttryck. Hjälpprogrammen kan nås från alla sammanhang i en mall.

Dessa blockhjälpare identifieras med # före hjälpnamnet och en matchande avslutande /, med samma namn krävs.
Block är uttryck som har ett blocköppningsblock ({{# }}) and closing ({{/}}).


>[!NOTE]
>
>Hjälpfunktioner beskrivs i [det här avsnittet](functions/helpers.md).
>

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

## URL PERSONALIZATION{#perso-urls}

Personaliserade URL:er tar mottagarna till specifika sidor på en webbplats eller till en personlig mikrowebbplats, beroende på profilattributen. I Adobe Journey Optimizer kan du lägga till personalisering i URL-adresser i ditt meddelandeinnehåll. URL-personalisering kan tillämpas på text och bilder och använda profildata eller kontextuella data.

Med Journey Optimizer kan du anpassa en eller flera URL-adresser i meddelandet genom att lägga till anpassningsfält till dem. Följ stegen nedan för att anpassa en URL-adress:

1. Skapa en länk i meddelandeinnehållet. [Läs mer](../email/message-tracking.md#insert-links)
1. Välj attribut från personaliseringsikonen. Ikonen för anpassning är bara tillgänglig för följande typer av länkar: **Extern länk**, **Avprenumerationslänk** och **Avanmäl dig**.

   ![](assets/perso-url.png)

>[!NOTE]
>
>När du redigerar en personlig URL i personaliseringsredigeraren inaktiveras hjälpfunktioner och målgruppsmedlemskap av säkerhetsskäl.
>

**Exempel på personliga URL:er**

* `https://www.adobe.com/users/{{profile.person.name.lastName}}`
* `https://www.adobe.com/users?uid={{profile.person.name.firstName}}`
* `https://www.adobe.com/usera?uid={{context.journey.technicalProperties.journeyUID}}`
* `https://www.adobe.com/users?uid={{profile.person.crmid}}&token={{context.token}}`

>[!CAUTION]
>
>Blanksteg stöds inte i personaliseringstoken som används i URL:er.
