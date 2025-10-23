---
title: Webbkanalskonfiguration
description: Skapa webbkanalskonfiguration
feature: Web Channel, Channel Configuration
topic: Content Management
role: Admin
level: Experienced
exl-id: 2161baf0-38b7-4397-bffe-083929e8033a
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 0%

---

# Konfigurera era webbupplevelser {#web-configuration}

## Skapa en webbkanalskonfiguration {#create-web-configuration}

En webbkonfiguration är en webbegenskap som identifieras av en URL där innehållet levereras. Den kan matcha en eller flera sidors URL-adresser så att du kan leverera ändringar för en eller flera webbsidor.

Följ stegen nedan för att skapa en webbkanalskonfiguration.

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/web_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

1. Välj **webbkanalen**.

   ![](assets/web_config_2.png)

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Välj något av följande alternativ i avsnittet **[!UICONTROL Web settings]**:

   * **[!UICONTROL Single page]** - Om du bara vill tillämpa ändringarna på en sida anger du **[!UICONTROL Page URL]**.

   * **[!UICONTROL Pages matching rule]** - Om du vill ha flera URL:er som matchar samma regel som mål skapar du en sidmatchningsregel och anger en **[!UICONTROL Default authoring and preview URL]**. [Läs mer](#web-page-matching-rule)

1. Klicka på **[!UICONTROL Submit]** om du vill spara ändringarna.

Du kan nu välja den här konfigurationen när du använder webbkanalen i dina kampanjer eller resor.

## Bygg en sidmatchningsregel {#web-page-matching-rule}

>[!CONTEXTUALHELP]
>id="ajo_admin_page_rule"
>title="Bygg en sidmatchningsregel"
>abstract="Skapa en regel för sidmatchning för att effektivt hantera och ange en grupp URL:er som delar samma villkor som mål. Med den här regeln kan du konsolidera flera URL:er under en riktlinje, vilket förenklar användningen av konsekventa inställningar och åtgärder på dessa sidor."

>[!CONTEXTUALHELP]
>id="ajo_admin_default_url"
>title="Definiera en URL för redigering och förhandsgranskning av innehåll"
>abstract="Det här fältet ser till att sidorna som genereras eller matchas av regeln har en angiven URL-adress, vilket är nödvändigt för att både skapa och förhandsgranska innehåll effektivt."

När du skapar en webb- eller [kodbaserad upplevelse](../code-based/get-started-code-based.md)-konfiguration kan du skapa en **[!UICONTROL Pages matching rule]** som mål för flera URL:er som matchar samma regel. Du kan därför använda samma innehållsändringar på flera sidor samtidigt.

Du kanske vill använda ändringarna på en hjältebanderoll på en hel webbplats, eller lägga till en översta bild som visas på alla produktsidor på en webbplats.

1. Välj [ när du konfigurerar din ](#web-configuration)webb[ eller ](../code-based/code-based-configuration.md)kodbaserade upplevelse **[!UICONTROL Pages matching rule]**.

1. Definiera dina villkor för fälten **[!UICONTROL Domain]** och **[!UICONTROL Page]**.

   >[!NOTE]
   >
   >Kontrollera tillgängliga operatorer i [det här avsnittet](#available-operators).

   Om du till exempel vill redigera element som visas på alla sidor med produkter för kvinnor på din Luma-webbplats väljer du **[!UICONTROL Domain]** > **[!UICONTROL Starts with]** > `luma` och **[!UICONTROL Page]** > **[!UICONTROL Contains]** > `women`.

   ![](assets/web_config_3.png)

1. Om ditt användningsfall inte kan modelleras med en regel kan du lägga till flera regler. Klicka på **[!UICONTROL Add another page rule]** och upprepa steget ovan.

   >[!NOTE]
   >
   >Du kan lägga till upp till 10 regler.

1. Du kan använda operatorerna **[!UICONTROL Or]** eller **[!UICONTROL Exclude]** mellan de olika reglerna.

   **[!UICONTROL Exclude]** är användbart när en av sidorna som matchar den definierade regeln inte ska ha något mål. Du kan till exempel ange alla `luma.com` sidor som innehåller `product` som mål, med undantag för följande sida: `https://luma.com/blogs/productinfo`.

   ![](assets/web_config_4.png)

1. Ange **[!UICONTROL Default authoring and preview URL]**. Detta steg säkerställer att sidorna som genereras eller matchas av regeln har en angiven URL-adress för både innehållsskapande och förhandsgranskning.

### Tillgängliga operatorer för att skapa sidmatchningsregler {#available-operators}

När du skapar en [regel som matchar flera sidor](#web-page-matching-rule) kan du använda olika operatorer i avsnitten **[!UICONTROL Domain]** och **[!UICONTROL Path]** för att skapa önskad regel. De tillgängliga operatorerna listas nedan.

* **Domän**

  | Operator  | Beskrivning  | Exempel  |
  |---|---|---|
  | Lika med  | Exakt domänmatchning.  | |
  | Börjar med  | Matchar alla domäner (inklusive underdomäner) som börjar med den angivna strängen.  | Exempel: &quot;Börjar med: dev&quot; -> matchar alla domäner och underdomäner som börjar med &quot;dev&quot;, som: dev.example.com, dev.products.example.com, developer.example.com  |
  | Slutar med  | Matchar alla domäner (inklusive underdomäner) som slutar med den angivna strängen.  | Exempel: &quot;Slutar med: example.com&quot; -> matchar alla domäner och underdomäner som slutar med &quot;example.com&quot;, som: stage.example.com, prod.example.com, myexample.com  |
  | Matchning av jokertecken  | Med operatorn &quot;Jokerteckenmatchning&quot; kan användaren definiera en jokerteckenmatchning mitt i strängen, som &quot;dev.*.example.com&quot;. Valideringsreglerna är att värdet måste innehålla ett och endast ett jokertecken (asterisk) när operatorn är&quot;jokerteckenmatchning&quot;.  | Exempel: &quot;Jokerteckenmatchning: dev.*.example.com&quot; -> matchar domäner som: dev.products.example.com, dev.mytest.products.example.com, dev.blog.example.com  |
  | Alla  | Matchar alla domäner - användbart när du testar en viss sökväg över domäner  |  |


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
