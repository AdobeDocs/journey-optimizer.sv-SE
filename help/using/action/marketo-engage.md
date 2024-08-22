---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med Marketo Engage
description: Lär dig hur du använder åtgärden Marketo Engage
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate
keywords: marknadsföring, marknadsföra, engagera integreringen
source-git-commit: 92591457d2189e3c43ea38c4a09d7cf565bb5d57
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---


# Integrera med Marketo Engage {#integrating-with-marketo-engage}

Satsa på en resa med smidig dataintegrering med Marketo Engage. Denna anpassade åtgärd i Journey Optimizer har stöd för två viktiga datatyper:

* Personer (profiler): Marketo omvandlar profiler till åtgärdbara insikter.
* Anpassade objekt: Skräddarsy data med anpassade objekt, som produkter, för en personaliserad marknadsföring.

## Förhandskrav {#prerequisites}

* Kundinstansen av Marketo Engage måste vara IMS-aktiverad.
* Marketo Engage-instansen och AEP/AJO-instansen måste finnas i samma IMS-organisation.
* Kunden måste etableras med **MktoSync: åtkomst till matningstjänsten**

## Konfigurera åtgärden {#configure-marketo-action}

* Navigera till Administration > Konfigurationer > Åtgärder och klicka på Hantera
* Klicka på Skapa åtgärd i listan Åtgärder. Läs mer om [Anpassade åtgärder](../building-journeys/using-custom-actions.md){target="_blank"}.
* Ange namn, beskrivning och välj Adobe Marketo Engage som åtgärdstyp

![](assets/engage-customaction-creation.png){width="40%" align="left"}

* Klicka på Redigera nyttolast för dina **Request**- och **Response**-nyttolaster.
* För båda delarna skapar du din nyttolast och klistrar in den i det dedikerade popup-fönstret.

![](assets/engage-customaction-payload.png){width="70%" align="left"}

* Inspect och konfigurera nyttolastvärden
Obs! Om du vill skicka värden dynamiskt ändrar du **Konstant** till **Variabel** för varje fält.

![](assets/engage-customaction-payload-fields.png){width="70%" align="left"}

* Klicka på **Spara** i fönstret Fältkonfiguration och sedan på **Spara** för din anpassade åtgärd.

Nu kan du använda din anpassade åtgärd på din dedikerade arbetsyta.


## Betalningssyntax {#payload-syntax}

### Person

![](assets/payload-person.png)

### CustomObject

![](assets/payload-customobject.png)


**Exempel på nyttolast för person**

```json
{
   "munchkinID": "388-KKG-245",  
   "person": {
    "priority": "normal",
    "partitionName": "XYZ",
    "dedupeFields": {
      "field1": "email",
      "field2": "firstName"
    },
    "objects": [
      {
        "email": "Email address",
        "firstName": "First name",
        "lastName": "Last name"
      }
    ]
  }
}
```

**Exempel på nyttolast för anpassat objekt**

```json
{
  "munchkinID": "388-KKG-245", 
  "customObject": {
    "priority": "normal",
    "objectName": "products",
    "objects": [
      {
        "email": "Email Address",
        "productName": "Product Name",
        "productQty": "Product Quantity",
        "priceTotal": "Price Total"
      }
    ]
  }
}
```


## Använda åtgärden {#engage-using}

* Dra den anpassade åtgärden till arbetsytan på resan.
* I avsnittet **Begäranparametrar** klickar du på Redigera för var och en av parametrarna med dynamiska värden som du har konfigurerat i nyttolasten.

![](assets/engage-use-canvas.png){width="70%" align="left"}

