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
source-wordcount: '801'
ht-degree: 0%

---

# Skapa webbupplevelser {#create-web}

Med [!DNL Journey Optimizer] kan du anpassa webbupplevelsen som du levererar till dina kunder via inkommande webbkampanjer.

>[!CAUTION]
>
>I [!DNL Journey Optimizer] kan du för närvarande bara skapa webbupplevelser med **kampanjer**.

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

1. Välj åtgärden **[!UICONTROL Web]**.

1. Definiera en webbyta.

   >[!NOTE]
   >
   >En webbyta är en webbegenskap som identifieras av en URL där innehållet levereras. Den kan matcha en eller flera sidors URL-adresser så att du kan leverera ändringar för en eller flera webbsidor.

   Du kan antingen ange **[!UICONTROL Page URL]** om du bara vill tillämpa ändringarna på en sida.

   ![](assets/web-campaign-surface.png)

1. Eller så kan du skapa en **[!UICONTROL Pages matching rule]** som mål för flera URL:er som matchar samma regel, till exempel om du vill tillämpa ändringarna på en hjältebanderoll på en hel webbplats eller lägga till en toppbild som visas på alla produktsidor på en webbplats.

   Om du vill göra det väljer du **[!UICONTROL Pages matching rule]** och klickar på **[!UICONTROL Create rule]**.

   ![](assets/web-campaign-matching-rule.png)

1. Definiera dina villkor för fälten **[!UICONTROL Domain]** och **[!UICONTROL Page]**.

   Om du till exempel vill redigera element som visas på alla sidor med produkter för kvinnor på din Luma-webbplats väljer du **[!UICONTROL Domain]** > **[!UICONTROL Starts with]** > `luma` och **[!UICONTROL Page]** > **[!UICONTROL Contains]** > `women`.

   ![](assets/web-pages-matching-rule.png)

1. Spara ändringarna. Regeln visas på skärmen **[!UICONTROL Create campaign]**.

   ![](assets/web-pages-matching-rule-example.png)

1. När du har definierat webbytan väljer du **[!UICONTROL Create]**.

1. Slutför stegen för att skapa en webbkampanj, till exempel kampanjegenskaperna, [målgrupp](../audience/about-audiences.md) och [schema](../campaigns/create-campaign.md#schedule).

   ![](assets/web-campaign-steps.png)

Mer information om hur du konfigurerar en kampanj finns på [den här sidan](../campaigns/get-started-with-campaigns.md).

## Testa webbkampanjen {#test-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_preview"
>title="Förhandsgranska din webbupplevelse"
>abstract="Få en simulering av hur webbupplevelsen kommer att se ut."

När du [har skapat din webbupplevelse](edit-web-content.md) med webbdesignern kan du använda testprofiler för att förhandsgranska dina ändrade webbsidor. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas med hjälp av testprofilsdata.

Det gör du genom att klicka på **[!UICONTROL Simulate content]** på webbkampanjens redigeringsskärm eller webbdesignern och sedan lägga till en testprofil för att kontrollera din webbsida med hjälp av testprofildata.

![](assets/web-designer-preview.png)

Du kan även öppna den i standardwebbläsaren eller kopiera test-URL:en och klistra in den i valfri webbläsare. På så sätt kan ni dela länken med teamet och intressenter som kan förhandsgranska den nya webbupplevelsen i vilken webbläsare som helst innan kampanjen blir aktiv.

>[!NOTE]
>
>När du kopierar test-URL:en är det innehåll som visas anpassat för testprofilen som användes när innehållssimuleringen genererades i [!DNL Journey Optimizer].

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

## Aktivera webbkampanjen {#activate-web-campaign}

När du har definierat inställningarna för din [webbkampanj](#configure-web-campaign) och har redigerat ditt innehåll med [webbdesignern](edit-web-content.md#work-with-web-designer) kan du granska och aktivera din webbkampanj. Följ stegen nedan.

<!--
>[!NOTE]
>
>You can also preview your web campaign content before activating it. [Learn more](#test-web-campaign)-->

1. Välj **[!UICONTROL Review to activate]** från webbkampanjen.

1. Kontrollera och redigera vid behov innehåll, egenskaper, yta, målgrupp och schema.

1. Välj **[!UICONTROL Activate]**.

   ![](assets/web-campaign-activate.png)

   >[!NOTE]
   >
   >När du har klickat på **[!UICONTROL Activate]** kan det ta upp till 15 minuter innan webbkampanjer blir tillgängliga live på din webbplats.

Din webbkampanj har statusen **[!UICONTROL Live]** och är nu synlig för den valda målgruppen. Alla mottagare av kampanjen kan se de ändringar du har lagt till på webbplatsen med hjälp av webbdesignern [!DNL Journey Optimizer].

>[!NOTE]
>
>Om du har definierat ett schema för webbkampanjen har den statusen **[!UICONTROL Scheduled]** tills startdatumet och starttiden nås.
>
>Om du aktiverar en webbkampanj som påverkar samma sidor som en annan kampanj som redan är aktiv, tillämpas alla ändringar på dina webbsidor.

Läs mer om hur du aktiverar kampanjer i [det här avsnittet](../campaigns/review-activate-campaign.md).

## Stoppa en webbkampanj {#stop-web-campaign}

När en webbkampanj är aktiv kan ni stoppa den för att hindra publiken från att se ändringarna. Följ stegen nedan.

1. Välj en livekampanj i listan.

1. Välj **[!UICONTROL Stop campaign]** på den översta menyn.

   ![](assets/web-campaign-stop.png)

1. De ändringar du har lagt till visas inte längre för den målgrupp du har definierat.

>[!NOTE]
>
>När en webbkampanj har stoppats kan du inte redigera eller aktivera den igen. Du kan bara duplicera den och aktivera den duplicerade kampanjen.

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en webbkampanj, konfigurerar dess egenskaper, granskar och publicerar den.

>[!VIDEO](https://video.tv.adobe.com/v/3418800/?quality=12&learn=on)