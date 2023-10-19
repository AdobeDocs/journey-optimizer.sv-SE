---
title: Skapa webbupplevelser
description: Lär dig skapa en webbsida och redigera dess innehåll i Journey Optimizer
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: e28c038b-49ed-4685-bfe6-514116eb0711
source-git-commit: 27447578dad6bd2612989d79cd0dc8ddbe78d629
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# Skapa webbupplevelser {#create-web}

[!DNL Journey Optimizer] gör att ni kan personalisera den webbupplevelse ni levererar till era kunder via inkommande webbkampanjer.

>[!CAUTION]
>
>Ingår [!DNL Journey Optimizer] kan du bara skapa webbupplevelser med **kampanjer**.

[Lär dig hur du skapar en webbkampanj i den här videon](#video)

## Skapa en webbkampanj {#create-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_surface"
>title="Definiera en webbyta"
>abstract="En webbyta kan matcha en eller flera sidor, vilket gör att du kan leverera innehållsändringar på en eller flera webbsidor."

>[!CONTEXTUALHELP]
>id="ajo_web_surface_rule"
>title="Bygg en sidmatchningsregel"
>abstract="En sidmatchningsregel gör det möjligt att ange flera URL:er som matchar samma regel som mål, t.ex. om du vill använda ändringarna på en hjältebanderoll på en hel webbplats eller lägga till en toppbild som visas på alla produktsidor på en webbplats."

Följ stegen nedan för att börja skapa en webbupplevelse genom en kampanj.

>[!NOTE]
>
>Om det här är första gången du skapar en webbupplevelse måste du följa de krav som beskrivs i [det här avsnittet](web-prerequisites.md).

1. Skapa en kampanj. [Läs mer](../campaigns/create-campaign.md)

1. Välj **[!UICONTROL Web]** åtgärd.

1. Definiera en webbyta.

   >[!NOTE]
   >
   >En webbyta är en webbegenskap som identifieras av en URL där innehållet levereras. Den kan matcha en eller flera sidors URL-adresser så att du kan leverera ändringar för en eller flera webbsidor.

   Du kan antingen ange en **[!UICONTROL Page URL]** om du bara vill tillämpa ändringarna på en sida.

   ![](assets/web-campaign-surface.png)

1. Du kan också skapa en **[!UICONTROL Pages matching rule]** om du vill ha flera URL-adresser som matchar samma regel, till exempel om du vill använda ändringarna på en hjältebanner på en hel webbplats eller lägga till en översta bild som visas på alla produktsidor på en webbplats.

   Om du vill göra det väljer du **[!UICONTROL Pages matching rule]** och klicka **[!UICONTROL Create rule]**.

   ![](assets/web-campaign-matching-rule.png)

1. Definiera villkor för **[!UICONTROL Domain]** och **[!UICONTROL Page]** fält.

   Om du till exempel vill redigera element som visas på alla sidor på Lumas webbplats för kvinnor väljer du **[!UICONTROL Domain]** > **[!UICONTROL Starts with]** > `luma` och **[!UICONTROL Page]** > **[!UICONTROL Contains]** > `women`.

   ![](assets/web-pages-matching-rule.png)

1. Spara ändringarna. Regeln visas i **[!UICONTROL Create campaign]** skärm.

   ![](assets/web-pages-matching-rule-example.png)

1. När du har definierat webbytan väljer du **[!UICONTROL Create]**.

1. Slutför stegen för att skapa en webbkampanj, t.ex. kampanjegenskaperna, [publik](../audience/about-audiences.md)och [schema](../campaigns/create-campaign.md#schedule).

   ![](assets/web-campaign-steps.png)

Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

## Testa webbkampanjen {#test-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_preview"
>title="Förhandsgranska din webbupplevelse"
>abstract="Få en simulering av hur webbupplevelsen kommer att se ut."

En gång [skapade din webbupplevelse](edit-web-content.md) med webbdesignern kan du använda testprofiler för att förhandsgranska de ändrade webbsidorna. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas med hjälp av testprofilsdata.

Det gör du genom att klicka **[!UICONTROL Simulate content]** från antingen webbkampanjens redigeringsskärm eller webbdesignern och lägg sedan till en testprofil för att kontrollera din webbsida med hjälp av testprofildata.

![](assets/web-designer-preview.png)

Du kan även öppna den i standardwebbläsaren eller kopiera test-URL:en och klistra in den i valfri webbläsare. På så sätt kan ni dela länken med teamet och intressenter som kan förhandsgranska den nya webbupplevelsen i vilken webbläsare som helst innan kampanjen blir aktiv.

>[!NOTE]
>
>När du kopierar test-URL:en är det innehåll som visas anpassat för testprofilen som användes när innehållssimuleringen genererades i [!DNL Journey Optimizer].

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehållet finns i [Innehållshantering](../content-management/preview-test.md) -avsnitt.

## Aktivera webbkampanjen {#activate-web-campaign}

När du definierat din [webbkampanjsinställningar](#configure-web-campaign) och du har redigerat innehållet efter behov med [webbdesigner](edit-web-content.md#work-with-web-designer)kan ni granska och aktivera webbkampanjen. Följ stegen nedan.

<!--
>[!NOTE]
>
>You can also preview your web campaign content before activating it. [Learn more](#test-web-campaign)-->

1. Välj **[!UICONTROL Review to activate]**.

1. Kontrollera och redigera vid behov innehåll, egenskaper, yta, målgrupp och schema.

1. Välj **[!UICONTROL Activate]**.

   ![](assets/web-campaign-activate.png)

   >[!NOTE]
   >
   >När du klickat **[!UICONTROL Activate]** kan det ta upp till 15 minuter innan webbkampanjer blir tillgängliga live på er webbplats.

Webbkampanjen tar **[!UICONTROL Live]** och nu visas för den valda publiken. Alla mottagare av kampanjen kan se de ändringar du har lagt till på webbplatsen med hjälp av [!DNL Journey Optimizer] webbdesigner.

>[!NOTE]
>
>Om du har definierat ett schema för webbkampanjen har den **[!UICONTROL Scheduled]** status tills startdatumet och starttiden nås.
>
>Om du aktiverar en webbkampanj som påverkar samma sidor som en annan kampanj som redan är aktiv, tillämpas alla ändringar på dina webbsidor.

Läs mer om att aktivera kampanjer i [det här avsnittet](../campaigns/review-activate-campaign.md).

## Stoppa en webbkampanj {#stop-web-campaign}

När en webbkampanj är aktiv kan ni stoppa den för att hindra publiken från att se ändringarna. Följ stegen nedan.

1. Välj en livekampanj i listan.

1. I den övre menyn väljer du **[!UICONTROL Stop campaign]**.

   ![](assets/web-campaign-stop.png)

1. De ändringar du har lagt till visas inte längre för den målgrupp du har definierat.

>[!NOTE]
>
>När en webbkampanj har stoppats kan du inte redigera eller aktivera den igen. Du kan bara duplicera den och aktivera den duplicerade kampanjen.

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en webbkampanj, konfigurerar dess egenskaper, granskar och publicerar den.

>[!VIDEO](https://video.tv.adobe.com/v/3418800/?quality=12&learn=on)