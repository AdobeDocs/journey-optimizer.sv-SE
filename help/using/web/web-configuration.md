---
title: Webbkanalskonfiguration
description: Skapa webbkanalskonfiguration
feature: Web Channel, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 2161baf0-38b7-4397-bffe-083929e8033a
source-git-commit: 37e60e5d7c0ad164cde67015b72341e1f4eda6a9
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---

# Skapa webbkanalskonfiguration {#web-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_page_rule"
>title="Matchningsregel för sidor"
>abstract="Skapa en regel för sidmatchning för att effektivt hantera och ange en grupp URL:er som delar samma villkor som mål. Med den här regeln kan du konsolidera flera URL:er under en riktlinje, vilket förenklar användningen av konsekventa inställningar och åtgärder på dessa sidor."

>[!CONTEXTUALHELP]
>id="ajo_admin_default_url"
>title="URL för standardredigering och förhandsgranskning"
>abstract="Det här fältet ser till att sidorna som genereras eller matchas av regeln har en angiven URL-adress, vilket är nödvändigt för att både skapa och förhandsgranska innehåll effektivt."

En webbkonfiguration är en webbegenskap som identifieras av en URL där innehållet levereras. Den kan matcha en eller flera sidors URL-adresser så att du kan leverera ändringar för en eller flera webbsidor.

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/web_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj **Webbkanal**.

   ![](assets/web_config_2.png)

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Du kan antingen ange **[!UICONTROL Page URL]** om du bara vill tillämpa ändringarna på en sida.

1. Eller så kan du skapa en **[!UICONTROL Pages matching rule]** som mål för flera URL:er som matchar samma regel, till exempel om du vill tillämpa ändringarna på en hjältebanderoll på en hel webbplats eller lägga till en toppbild som visas på alla produktsidor på en webbplats.

   Välj **[!UICONTROL Pages matching rule]** om du vill göra det.

1. Definiera dina villkor för fälten **[!UICONTROL Domain]** och **[!UICONTROL Page]**.

   Om du till exempel vill redigera element som visas på alla sidor med produkter för kvinnor på din Luma-webbplats väljer du **[!UICONTROL Domain]** > **[!UICONTROL Starts with]** > `luma` och **[!UICONTROL Page]** > **[!UICONTROL Contains]** > `women`.

   ![](assets/web_config_3.png)

1. Om du har skapat en **[!UICONTROL Page matching rule]** måste du ange redigerings- och förhandsgransknings-URL:en **Standard** . Detta steg säkerställer att sidorna som genereras eller matchas av regeln har en angiven URL-adress för både innehållsskapande och förhandsgranskning. Läs mer om reglerna för sidmatchning i [avsnittet nedan](#web-page-matching-rule).

1. Spara ändringarna.

Nu kan du välja din konfiguration när du använder webbkanalen i kampanjer eller resor.

## Sidmatchningsregel {#web-page-matching-rule}

När du skapar en regel som matchar flera sidor så att du kan tillämpa samma innehållsändringar på flera sidor samtidigt, kan du använda olika operatorer i avsnitten **Domän** och **Sökväg** för att skapa önskad regel. Kontrollera tillgängliga operatorer nedan.

Tillgängliga operatorer för att skapa sidmatchningsregler:

* **Domän**

  | Operator  | Beskrivning  | Exempel  |
  |---|---|---|
  | Lika med  | Exakt domänmatchning.  |
  | Börjar med  | Matchar alla domäner (inklusive underdomäner) som börjar med den angivna strängen.  | Exempel: &quot;Börjar med: dev&quot; -> matchar alla domäner och underdomäner som börjar med &quot;dev&quot;, som: dev.example.com, dev.products.example.com, developer.example.com  |
  | Slutar med  | Matchar alla domäner (inklusive underdomäner) som slutar med den angivna strängen.  | Exempel: &quot;Slutar med: example.com&quot; -> matchar alla domäner och underdomäner som slutar med &quot;example.com&quot;, som: stage.example.com, prod.example.com, myexample.com  |
  | Matchning av jokertecken  | Med operatorn &quot;Jokerteckenmatchning&quot; kan användaren definiera en jokerteckenmatchning mitt i strängen, som &quot;dev.*.example.com&quot;. Valideringsreglerna är att värdet måste innehålla ett och endast ett jokertecken (asterisk) när operatorn är&quot;jokerteckenmatchning&quot;.  | Exempel: &quot;Jokerteckenmatchning: dev.*.example.com&quot; -> matchar domäner som: dev.products.example.com, dev.mytest.products.example.com, dev.blog.example.com  |
  | Alla  | Matchar alla domäner - användbart när du testar en viss sökväg över domäner  |


* **Sökväg**

<table>
    <thead>
    <tr>
        <th><strong>Operatör</th>
        <th><strong>Beskrivning</th>
        <th><strong>Exempel</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>Lika med</td>
        <td>Exakt matchning av sökvägen. </td>
        <td></td>
    </tr>
    <tr>
        <td>Börjar med</td>
        <td>Matchar alla sökvägar (inklusive delsökvägar) som börjar med den angivna strängen.</td>
        <td></td>
    </tr>
    <tr>
        <td>Slutar med</td>
        <td>Matchar alla sökvägar (inklusive delsökvägar) som slutar med den sträng som anges.</td>
        <td></td>
    </tr>
    <tr>
        <td>Alla</td>
        <td>Matchar alla sökvägar - användbart när du riktar in dig på alla sökvägar under en eller flera domäner.</td>
        <td></td>
    </tr>
    <tr>
        <td>Matchning av jokertecken</td>
        <td>Med operatorn"Jokerteckenmatchning" kan användaren definiera ett internt jokertecken inuti sökvägen, till exempel"/products/*/detail".  Jokertecknet * i komponenten Path ** matchar alla teckensekvenser tills det första / tecknet påträffas.  /*/ matchar alla teckensekvenser (inklusive underbanor)</td>
        <td>Exempel: "Jokerteckenmatchning: /products/*/detail", matchar alla sökvägar som: <ul><li>example.com/products/yoga/detail</li><li>example.com/products/surf/detail</li><li>example.com/products/tennis/detail</li><li>example.com/products/yoga/pants/detail</li></ul>Exempel: "Matchar: /prod*/detail, matchar alla sökvägar som: <ul><li>example.com/products/detail</li><li>example.com/production/detail</li></ul>matchar inte sökvägar som: <ul><li>example.com/products/yoga/detail</li></ul></td>
    </tr>
    <tr>
        <td>Innehåller</td>
        <td>"contains" översätts till ett jokertecken som "mystring" och matchar alla sökvägar som innehåller den här teckensekvensen.</td>
        <td>Exempel: "Innehåller: product", matchar alla sökvägar som innehåller strängprodukten, som: <ul><li>example.com/products</li><li>example.com/yoga/perfproduct</li><li>example.com/surf/productdescription</li><li>example.com/home/product/page</li></ul></td>
    </tr>
    </tbody>
</table>

Om ditt användningsfall inte kan modelleras med en regel har du möjlighet att lägga till flera sidregler och du kan använda operatorerna Eller eller Exkludera mellan dem. Exkludera är användbart när en av sidorna som matchar den definierade regeln inte ska ha något mål: till exempel alla exempel&quot;example.com&quot;-sidor som innehåller&quot;product&quot;, exklusive följande sida: `https://example.com/blogs/productinfo`.
