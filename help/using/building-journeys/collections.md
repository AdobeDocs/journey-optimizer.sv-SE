---
solution: Journey Optimizer
product: journey optimizer
title: Skicka samlingar till anpassade åtgärdsparametrar
description: Lär dig hur du skickar samlingar dynamiskt i Journey Optimizer med anpassade åtgärder
feature: Journeys, Use Cases, Custom Actions, Collections
topic: Content Management
role: Developer
level: Experienced
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
version: Journey Orchestration
source-git-commit: a67707e50960e4848197fa1bd39ce95af3ef14ab
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 0%

---


# Skicka samlingar till anpassade åtgärdsparametrar {#passing-collection}

Du kan skicka en samling i anpassade åtgärdsparametrar som fylls i dynamiskt vid körning.

Två typer av samlingar stöds:

* **Enkla samlingar**

  Använd enkla samlingar för listor med grundläggande värden, till exempel strängar, siffror eller booleska värden. Dessa är användbara när du bara behöver skicka en lista med objekt utan ytterligare egenskaper.

  En lista med enhetstyper:

  ```json
  {
   "deviceTypes": [
       "android",
       "ios"
   ]
  }
  ```

* **Objektsamlingar**

  Använd objektsamlingar när varje objekt innehåller flera fält eller egenskaper. De används vanligtvis för att skicka strukturerade data, t.ex. produktinformation, händelseposter eller objektattribut.

  Exempel:

  ```json
  {
  "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20.1
     },
     {
        "id":"productB",
        "name":"B",
        "price":10.0
     },
     {
        "id":"productC",
        "name":"C",
        "price":5.99
     }
   ]
  }
  ```

>[!NOTE]
>
>Kapslade arrayer i samlingar stöds bara delvis i nyttolaster för anpassade åtgärder. Mer information finns i [Begränsningar](#limitations).

## Allmänt förfarande {#general-procedure}

I det här avsnittet använder vi följande JSON-exempel på nyttolast. Det här är en array med objekt med ett fält som är en enkel samling.

```json
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

Du kan se att `products` är en array med två objekt. Du måste ha minst ett objekt.

1. Skapa en anpassad åtgärd. Läs mer på [den här sidan](../action/about-custom-action-configuration.md).

1. Klistra in JSON-exemplet i avsnittet **[!UICONTROL Action parameters]**. Den visade strukturen är statisk: när du klistrar in nyttolasten definieras alla fält som konstanter.

   ![Uttrycksredigeraren som visar samlingsfunktioner och åtgärder](assets/uc-collection-1.png)

1. Justera fälttyperna om det behövs. Följande fälttyper stöds för samlingar: listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >Fälttypen härleds automatiskt enligt exempel på nyttolast.

1. Om du vill skicka objekt dynamiskt måste du ange dem som variabler. I det här exemplet anger vi `products` som variabel. Alla objektfält i objektet ställs in automatiskt på variabler.

   >[!NOTE]
   >
   >Det första objektet i nyttolastexemplet används för att definiera fälten.

1. Definiera den etikett som ska visas på arbetsytan för varje fält.

   ![Filtersamlingsfunktion med villkorsbyggargränssnitt](assets/uc-collection-2.png){width="70%" align="left"}

1. Skapa din resa och lägg till den anpassade åtgärd du skapade. Läs mer på [den här sidan](../building-journeys/using-custom-actions.md).

1. I avsnittet **[!UICONTROL Action parameters]** definierar du arrayparametern (`products` i vårt exempel) med den avancerade uttrycksredigeraren.

   ![Uttryck för samlingsfiltrering med fältval](assets/uc-collection-3.png)

1. För vart och ett av följande objektfält anger du motsvarande fältnamn från XDM-källschemat. Om namnen är identiska behövs inte detta. I vårt exempel behöver vi bara definiera `product id` och&quot;color&quot;.

   ![Sorteringsfunktion för samling med beställningskonfiguration](assets/uc-collection-4.png){width="50%" align="left"}

För arrayfältet kan du även använda den avancerade uttrycksredigeraren för att utföra datamanipulering. I följande exempel använder vi funktionerna [filter](functions/list-functions.md#filter) och [intersect](functions/list-functions.md#intersect):

![Fullständigt samlingsuttryck med filtrerings-, sorterings- och begränsningsåtgärder](assets/uc-collection-5.png)

## Begränsningar {#limitations}

Samlingar i anpassade åtgärder ger flexibilitet när det gäller att skicka dynamiska data, men det finns vissa strukturella begränsningar som du bör vara medveten om:

* **Stöd för kapslade arrayer i anpassade åtgärder**

  Adobe Journey Optimizer stöder kapslade arrayer med objekt i den anpassade åtgärden **svarsnyttolaster**, men det här stödet är begränsat i **begärannyttolaster**.

  I begärandenyttolaster stöds bara kapslade arrayer när de innehåller ett fast antal objekt, enligt definitionen i den anpassade åtgärdskonfigurationen. Om en kapslad array till exempel alltid innehåller exakt tre objekt, kan den konfigureras som en konstant. När antalet objekt behöver vara dynamiskt kan bara icke-kapslade arrayer (arrayer på den nedersta nivån) definieras som variabler.

  Exempel:

   1. I följande exempel visas ett **användningsfall som inte stöds**.

      I det här exemplet innehåller arrayen products en kapslad array (`locations`) med ett dynamiskt antal objekt, vilket inte stöds i begärandenyttolaster.

      ```json
      {
      "products": [
         {
            "id": "productA",
            "name": "A",
            "price": 20,
            "locations": [
            { "name": "Paris" },
            { "name": "London" }
            ]
         }
      ]
      }
      ```

   2. Exempel: fasta objekt definieras som konstanter.

      I det här fallet ersätts de kapslade platserna med fasta fält (`location1`, `location2`), vilket gör att nyttolasten förblir giltig i den konfiguration som stöds.

      ```json
      {
      "products": [
         {
            "id": "productA",
            "name": "A",
            "price": 20,
            "location1": { "name": "Paris" },
            "location2": { "name": "London" }
         }
      ]
      }
      ```


* **Testar samlingar**: Om du vill testa samlingar i testläge måste du använda kodvyn. Observera att kodvisningsläget inte stöds för affärshändelser, så i så fall kan du bara skicka en samling som innehåller ett enskilt element.


## Särskilda fall{#examples}

För heterogena typer och arrayer av arrayer definieras arrayen med typen listAny. Du kan bara mappa enskilda objekt, men inte ändra arrayen till variabel.

![Heterogen samling med blandade datatyper och fältval](assets/uc-collection-heterogeneous.png){width="70%" align="left"}

Exempel på heterogen typ:

```json
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

Exempel på array med arrayer:

```json
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

## Ytterligare resurser

Bläddra i avsnitten nedan om du vill veta mer om hur du konfigurerar, använder och felsöker anpassade åtgärder:

* [Kom igång med anpassade åtgärder](../action/action.md) - Lär dig vad som är en anpassad åtgärd och hur de hjälper dig att ansluta till tredjepartssystem
* [Konfigurera dina anpassade åtgärder](../action/about-custom-action-configuration.md) - Lär dig hur du skapar och konfigurerar en anpassad åtgärd
* [Använd anpassade åtgärder](../building-journeys/using-custom-actions.md) - Lär dig hur du använder anpassade åtgärder på dina resor
* [Felsökning av anpassad åtgärd](../action/troubleshoot-custom-action.md) - Lär dig hur du felsöker en anpassad åtgärd
  <!--* [Iterate over contextual data](../personalization/iterate-contextual-data.md#arrays-in-journeys) - Learn how to work with arrays in Journey expressions and iterate over custom action responses, event data, and dataset lookups in message personalization-->

