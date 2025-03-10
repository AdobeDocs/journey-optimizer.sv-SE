---
solution: Journey Optimizer
product: journey optimizer
title: Personalization-validering
description: Läs mer om validering av personalisering och felsökning.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, validering, fel, personalisering
exl-id: 7abeec5e-743f-48fb-a4a6-056665e8bfda
source-git-commit: 155ae8ef14e5482d94e54b15962afa09aa6826fc
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Personalization-validering {#personalization-validation}

## Valideringsmekanismer {#validation-mechanisms}

Använd knappen **Validera** på skärmen **personaliseringsredigerare** för att kontrollera din personaliseringssyntax.

>[!NOTE]
> Valideringen körs automatiskt när du klickar på knappen **Lägg till** för att stänga redigeringsfönstret.
>

![](assets/perso_validation1.png)

>[!IMPORTANT]
> Om personaliseringssyntaxen inte är giltig kan du inte stänga redigeringsfönstret för personalisering.
>

## Vanliga fel {#common-errors}

* **Sökvägen &quot;XYZ&quot; hittades inte**

När du försöker referera till ett fält som inte är definierat i schemat.

I det här fallet har **firstName1** inte definierats som attribut i profilschemat:

```
{{profile.person.name.firstName1}}
```

* **Typmatchningsfel för variabeln XYZ. Förväntad array. Hittade sträng.**

När du försöker iterera över en sträng i stället för en array:

I det här fallet är **product** inte en matris:

```
{{each profile.person.name.firstName as |product|}}
 {{product.productName}}
{{/each}}
```

* **Felaktig syntax för verktygsfält.`‘[XYZ}}’`** hittades

När ogiltig syntax för verktygsfält används.

Handlebars-uttryck omges av **{{expression}}**

```
   {{[profile.person.name.firstName}}
```

* **Ogiltig segmentdefinition**

```
No segment definition found for 988afe9f0-d4ae-42c8-a0be-8d90e66e151
```

## Specifika fel relaterade till erbjudanden {#specific-errors}

Felen som rör integrering av erbjudanden i ett e-postmeddelande eller push-meddelande har följande mönster:

```
Offer.<offerType>.[PlacementID].[ActivityID].<offer-attribute>
```

Valideringen utförs under innehållsvalideringen i personaliseringsredigeraren.

<table> 
 <thead> 
  <tr> 
   <th> Feltitel <br /> </th> 
   <th> Validering/upplösning <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Resurs med ID placementID och typen OfferPlacement hittades inte <br/>
Resurs med id activityID och typen OfferActivity hittades inte<br/></td> 
   <td>Kontrollera om ActivityID och/eller PlacementID är tillgängliga</td> 
  </tr> 
   <tr> 
   <td>Resursen kunde inte verifieras.</td> 
   <td>componentType i Placement ska matcha offerType-erbjudandet</td> 
  </tr> 
   <tr> 
   <td>Den offentliga URL:en finns inte i offerId.</td> 
   <td>Image Offers (all Personalized and fallback associated with the Decision and placement pair) should have public URL populated (deliveryURL should not be empty).</td> 
  </tr> 
  <tr> 
   <td>Beslutet innehåller attribut som inte är profiler.</td> 
   <td>Användning av modell för erbjudanden bör endast innehålla profilattributen.</td> 
  </tr> 
  <tr> 
   <td>Ett fel uppstod när beslutsanvändningen hämtades.</td> 
   <td>Detta fel kan uppstå när API:t försöker hämta erbjudandemodellen.</td> 
  </tr>
  <tr> 
   <td>Erbjudandeattributet offer-attribute är ogiltigt.</td> 
   <td>Kontrollera om erbjudandeattributet som refereras i erbjudandeofferten är giltigt. Följande attribut är giltiga: <br/>
Bild: deliveryURL, linkURL <br/>
Text: content <br/>
HTML: innehåll<br/></td> 
  </tr> 
 </tbody> 
</table>
