---
solution: Journey Optimizer
product: journey optimizer
title: Personalisering använder skiftläge&kolon; e-post om att kunden överger vagnen
description: Lär dig hur du anpassar brödtexten i ett e-postmeddelande med hjälp av ett användningsfall.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, hjälpprogram, användningsfall, personalisering
exl-id: 9c9598c0-6fb1-4e2f-b610-ccd1a80e516e
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 1%

---

# Personalisering - användningsfall: e-post om att kunden överger en varukorg {#personalization-use-case-helper-functions}

I det här exemplet anpassar du brödtexten i ett e-postmeddelande. Det här meddelandet riktar sig till kunder som har lämnat artiklar i kundvagnen men inte slutfört köpet.

Du använder följande typer av hjälpfunktioner:

* The `upperCase` strängfunktion, om du vill infoga kundens förnamn med versaler. [Läs mer](functions/string.md#upper).
* The `each` hjälper dig att lista objekten i kundvagnen. [Läs mer](functions/helpers.md#each).
* The `if` hjälper dig att infoga en produktspecifik anteckning om den relaterade produkten finns i varukorgen. [Läs mer](functions/helpers.md#if-function).
<!-- **Context**: personalization based on contextual data from the journey -->

➡️ [Lär dig hur du använder hjälpfunktioner i den här videon](#video)

Innan du börjar bör du kontrollera hur du konfigurerar de här elementen:

* En enastående händelse. [Läs mer](../event/about-events.md).
* En resa som börjar med ett evenemang. [Läs mer](../building-journeys/using-the-journey-designer.md).
* Ett e-postmeddelande under din resa. [Läs mer](../email/create-email.md)
* Innehållet i ett e-postmeddelande. [Läs mer](../email/content-from-scratch.md).

Följ de här stegen:

1. [Skapa det första evenemanget och resan](#create-context).
1. [Skapa ett e-postmeddelande](#configure-email).
1. [Infoga kundens förnamn med versaler](#uppercase-function).
1. [Lägg till kundvagnsinnehållet i e-postmeddelandet](#each-helper).
1. [Infoga en produktspecifik anteckning](#if-helper).
1. [Testa och publicera resan](#test-and-publish).

## Steg 1: Skapa den inledande händelsen och den relaterade resan {#create-context}

Kundvagnens innehåll är sammanhangsberoende information från resan. Därför måste du lägga till en första händelse och e-postmeddelandet till en resa innan du kan lägga till kundspecifik information i e-postmeddelandet.

1. Skapa en händelse vars schema innehåller `productListItems` array.
1. Definiera alla fält från den här arrayen som nyttolastfält för den här händelsen.

   Läs mer om produktlistans datatyp i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html){target="_blank"}.

1. Skapa en resa som börjar med det här evenemanget.
1. Lägg till en **E-post** till resan.

   ![](assets/personalization-uc-helpers-8.png)

## Steg 2: Skapa e-postmeddelandet{#configure-email}

1. I **E-post** aktivitet, klicka **[!UICONTROL Edit content]** och sedan klicka **[!UICONTROL Email Designer]**.

   ![](assets/personalization-uc-helpers-1.png)

1. Dra och släpp tre strukturkomponenter från den vänstra paletten på e-postdesignerns hemsida till meddelandets brödtext.

1. Dra och släpp en HTML-innehållskomponent på varje ny strukturkomponent.

   ![](assets/personalization-uc-helpers-2.png)

## Steg 3: Ange kundens förnamn med versaler {#uppercase-function}

1. På startsidan för e-postdesignern klickar du på komponenten HTML där du vill lägga till kundens förnamn.
1. I det sammanhangsberoende verktygsfältet klickar du på **[!UICONTROL Show the source code]**.

   ![](assets/personalization-uc-helpers-3.png)

1. I **[!UICONTROL Edit HTML]** fönster, lägga till `upperCase` strängfunktion:
   1. Välj **[!UICONTROL Helper functions]**.
   1. Använd sökfältet för att hitta &quot;versal case&quot;.
   1. Lägg till `upperCase` funktion. Det gör du genom att klicka på plustecknet (+) bredvid `{%= upperCase(string) %}: string`.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {%= upperCase(string) %}
      ```

      ![](assets/personalization-uc-helpers-4.png)

1. Ta bort platshållaren för strängen från uttrycket.
1. Lägg till token för förnamn:
   1. Välj **[!UICONTROL Profile attributes]**.
   1. Välj **[!UICONTROL Person]** > **[!UICONTROL Full name]**.
   1. Lägg till **[!UICONTROL First name]** -token till uttrycket.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {%= upperCase(profile.person.name.firstName) %}
      ```

      ![](assets/personalization-uc-helpers-5.png)

      Läs mer om personnamnets datatyp i [Dokumentation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/person-name.html){target="_blank"}.

1. Klicka **[!UICONTROL Validate]** och sedan klicka **[!UICONTROL Save]**.

   ![](assets/personalization-uc-helpers-6.png)

1. Spara meddelandet.

## Steg 4: Infoga listan med artiklar från vagnen {#each-helper}

1. Öppna meddelandeinnehållet igen.

1. På startsidan för e-postdesignern klickar du på komponenten HTML där du vill visa kundvagnens innehåll.
1. I det sammanhangsberoende verktygsfältet klickar du på **[!UICONTROL Show the source code]**.

   ![](assets/personalization-uc-helpers-3.png)

1. I **[!UICONTROL Edit HTML]** fönster, lägga till `each` hjälpare:
   1. Välj **[!UICONTROL Helper functions]**.
   1. Använd sökfältet för att hitta &quot;each&quot;.
   1. Lägg till `each` hjälpare.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {{#each someArray as |variable|}} {{/each}}
      ```

      ![](assets/personalization-uc-helpers-9.png)

1. Lägg till `productListItems` matris till uttrycket:

   1. Ta bort platshållaren &quot;someArray&quot; från uttrycket.
   1. Välj **[!UICONTROL Contextual attributes]**.

      **[!UICONTROL Contextual attributes]** är tillgängliga först efter att resekontexten har skickats till meddelandet.

   1. Välj **[!UICONTROL Journey Optimizer]** > **[!UICONTROL Events]** > ***[!UICONTROL event_name]*** och utöka sedan **[!UICONTROL productListItems]** nod.

      I detta exempel *event_name* representerar namnet på din händelse.

   1. Lägg till **[!UICONTROL Product]** -token till uttrycket.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems.product as |variable|}} {{/each}}
      ```

      I detta exempel *event_ID* representerar ID:t för din händelse.

      ![](assets/personalization-uc-helpers-10.png)

   1. Ändra uttrycket:
      1. Ta bort strängen &quot;.product&quot;.
      1. Ersätt platshållaren &quot;variable&quot; med &quot;product&quot;.

      I det här exemplet visas det ändrade uttrycket:

      ```handlebars
      {{#each context.journey.events.event_ID.productListItems as |product|}}
      ```

1. Klistra in koden mellan öppningarna `{{#each}}` -taggen och den avslutande `{/each}}` tagg:

   ```html
   <table>
      <tbody>
         <tr>
            <td><b>#name</b></td>
            <td><b>#quantity</b></td>
            <td><b>$#priceTotal</b></td>
         </tr>
      </tbody>
   </table>
   ```

1. Lägg till personaliseringstoken för artikelnamn, kvantitet och pris:

   1. Ta bort platshållaren &quot;#name&quot; från tabellen HTML.
   1. Lägg till **[!UICONTROL Name]** -token till uttrycket.

   Upprepa dessa steg två gånger:

   * Ersätt platshållaren &quot;#quantity&quot; med **[!UICONTROL Quantity]** token.
   * Ersätt platshållaren &quot;#priceTotal&quot; med **[!UICONTROL Total price]** token.

   I det här exemplet visas det ändrade uttrycket:

   ```handlebars
   {{#each context.journey.events.event_ID.productListItems as |product|}}
      <table>
         <tbody>
            <tr>
               <td><b>{{context.journey.events.event_ID.productListItems.name}}</b></td>
               <td><b>{{context.journey.events.event_ID.productListItems.quantity}}</b></td>
               <td><b>${{context.journey.events.event_ID.productListItems.priceTotal}}</b></td>
            </tr>
         </tbody>
      </table>
   {{/each}}
   ```

1. Klicka **[!UICONTROL Validate]** och sedan klicka **[!UICONTROL Save]**.

   ![](assets/personalization-uc-helpers-11.png)

## Steg 5: Infoga en produktspecifik anteckning {#if-helper}

1. På startsidan för E-postdesignern klickar du på den HTML-komponent där du vill infoga anteckningen.
1. I det sammanhangsberoende verktygsfältet klickar du på **[!UICONTROL Show the source code]**.

   ![](assets/personalization-uc-helpers-3.png)

1. I **[!UICONTROL Edit HTML]** fönster, lägga till `if` hjälpare:
   1. Välj **[!UICONTROL Helper functions]**.
   1. Använd sökfältet för att hitta &quot;if&quot;.
   1. Lägg till `if` hjälpare.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {%#if condition1%} render_1
         {%else if condition2%} render_2
         {%else%} default_render
      {%/if%}
      ```

      ![](assets/personalization-uc-helpers-12.png)

1. Ta bort det här villkoret från uttrycket:

   ```handlebars
   {%else if condition2%} render_2
   ```

   I det här exemplet visas det ändrade uttrycket:

   ```handlebars
   {%#if condition1%} render_1
      {%else%} default_render
   {%/if%}
   ```

1. Lägg till produktnamnstoken i villkoret:
   1. Ta bort platshållaren &quot;condition1&quot; från uttrycket.
   1. Välj **[!UICONTROL Contextual attributes]**.
   1. Välj **[!UICONTROL Journey Orchestration]** > **[!UICONTROL Events]** > ***[!UICONTROL event_name]*** och utöka sedan **[!UICONTROL productListItems]** nod.

      I detta exempel *event_name* representerar namnet på din händelse.

   1. Lägg till **[!UICONTROL Name]** -token till uttrycket.

      Uttrycksredigeraren visar följande uttryck:

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name%}
         render_1
         {%else%} default_render
      {%/if%}
      ```

      ![](assets/personalization-uc-helpers-13.png)

1. Ändra uttrycket:
   1. I uttrycksredigeraren anger du produktnamnet efter `name` token.

      Använd den här syntaxen där *product_name* representerar namnet på din produkt:

      ```javascript
      = "product_name"
      ```

      I det här exemplet är produktnamnet&quot;Juno Jacket&quot;:

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name = "Juno Jacket" %}
         render_1
         {%else%} default_render
      {%/if%}
      ```

   1. Ersätt platshållaren &quot;render_1&quot; med texten i anteckningen.

      Exempel:

      ```handlebars
      {%#if context.journey.events.`event_ID`.productListItems.name = "Juno Jacket" %}
         Due to longer than usual lead times on the Juno Jacket, please expect item to ship two weeks after purchase.
         {%else%} default_render
      {%/if%}
      ```

   1. Ta bort platshållaren &quot;default_render&quot; från uttrycket.
1. Klicka **[!UICONTROL Validate]** och sedan klicka **[!UICONTROL Save]**.

   ![](assets/personalization-uc-helpers-14.png)

1. Spara meddelandet.

## Steg 6: Testa och publicera resan {#test-and-publish}

1. Aktivera **[!UICONTROL Test]** växla och klicka sedan **[!UICONTROL Trigger an event]**.

   ![](assets/personalization-uc-helpers-15.png)

1. I **[!UICONTROL Event configuration]** anger du indatavärdena och klickar sedan **[!UICONTROL Send]**.

   Testläget fungerar bara med testprofiler.

   ![](assets/personalization-uc-helpers-16.png)

   E-postadressen skickas till testprofilens adress.

   I det här exemplet innehåller e-postmeddelandet en anteckning om Juno Jacket eftersom den här produkten finns i varukorgen:

   ![](assets/personalization-uc-helpers-17.png)

1. Kontrollera att det inte finns något fel och publicera sedan resan.


## Relaterade ämnen {#related-topics}

### Handtag, funktioner {#handlebars}

* [Hjälpmedel](functions/helpers.md)

* [Strängfunktioner](functions/string.md)

### Användningsfall {#use-case}

* [Personalisering med profilinformation, kontext och erbjudande](personalization-use-case.md)

* [Personalisering med beslutsbaserat erbjudande](../offers/offers-e2e.md)

## Instruktionsvideo{#video}

Lär dig hur du använder hjälpfunktioner.

>[!VIDEO](https://video.tv.adobe.com/v/334244?quality=12)
