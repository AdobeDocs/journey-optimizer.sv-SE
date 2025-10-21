---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med Marketo Engage
description: Lär dig använda Marketo Engage-åtgärden
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Developer, Admin
level: Intermediate
keywords: marknadsföring, marknadsföra, engagera integreringen
exl-id: 70d1ef5a-743b-4362-bb65-93a8c996209f
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Integrera med Marketo Engage {#integrating-with-marketo-engage}

Satsa på en resa med smidig dataintegrering med Marketo Engage. Det finns en specifik anpassad åtgärd att utföra på resor för att integrera Adobe Journey Optimizer och Marketo Engage. Den här anpassade åtgärden stöder inmatning av två viktiga datatyper:

* **Personer** (profiler): Marketo omvandlar profiler till åtgärdbara insikter.
* **Anpassade objekt**: Skräddarsy data med anpassade objekt, till exempel produkter, för en anpassad marknadsföring.

## Förhandskrav {#prerequisites}

Följande krav gäller för den här integreringen:

* Kundinstansen av Marketo Engage måste vara IMS-aktiverad
* Marketo Engage-instans och Adobe Experience Platform/Journey Optimizer-instans måste finnas i samma organisation
* Kunden måste etableras med **MktoSync: åtkomst till matningstjänsten**

## Konfigurera åtgärden {#configure-marketo-action}


I Journey Optimizer måste du konfigurera en anpassad åtgärd för Marketo Engage. Följ de här stegen:

1. Välj **[!UICONTROL Configurations]** i ADMINISTRATION-menyavsnittet.
1. Klicka på **[!UICONTROL Actions]** i avsnittet **[!UICONTROL Create Action]**. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.
1. Ange namn, beskrivning och välj **Adobe Marketo Engage** som **åtgärdstyp**
   ![](assets/engage-customaction-creation.png){width="40%" align="left"}
1. Klicka på ikonen **Redigera nyttolast** för dina **Request**- och **Response**-nyttolaster.
1. För båda delarna skapar du din nyttolast och klistrar in den i det dedikerade popup-fönstret.
   ![](assets/engage-customaction-payload.png){width="70%" align="left"}
1. Inspektera och konfigurera nyttolastvärden

   Obs! Om du vill skicka värden dynamiskt ändrar du **Konstant** till **Variabel** för varje fält.

   ![](assets/engage-customaction-payload-fields.png){width="70%" align="left"}

1. Klicka på **Spara** på konfigurationsskärmen för fält och **Spara** din anpassade åtgärd.

Nu kan du använda din anpassade åtgärd på arbetsytan på resan.

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


## Använda funktionsmakrot {#engage-using}

För varje konfigurerad åtgärd finns en Marketo Engage-åtgärd tillgänglig på paletten Resursdesigner.

Så här använder du den:

1. Dra den anpassade åtgärden till arbetsytan på resan.

1. Ange etiketten och beskrivningen för den här åtgärden.

1. I avsnittet **Begäranparametrar** klickar du på ikonen **Redigera** för var och en av parametrarna och väljer de dynamiska värden som du har konfigurerat i nyttolasten.

![](assets/engage-use-canvas.png){width="70%" align="left"}
