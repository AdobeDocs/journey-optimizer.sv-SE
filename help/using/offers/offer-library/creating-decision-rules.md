---
title: Skapa beslutsregler
description: Lär dig hur du skapar beslutsregler i Adobe Experience Platform.
source-git-commit: 741fe2b614e3ded57c4a7ecd9b7333bdd99ab359
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 4%

---

# Skapa beslutsregler {#creating-decision-rules}

Du kan skapa beslutsregler för erbjudanden baserat på data som är tillgängliga i Adobe Experience Platform. Beslutsregler avgör vem som kan visa ett erbjudande.

Du kan till exempel ange att du bara vill att ett &quot;Kloderbjudande för kvinnor&quot; ska visas när (Kön = &#39;kvinna&#39;) och (Region = &#39;Nordost&#39;).

![](../../assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

Listan med skapade beslutsregler finns på **[!UICONTROL Components]**-menyn.

![](../../assets/decision_rules_list.png)

Så här skapar du en beslutsregel:

1. Gå till fliken **[!UICONTROL Rules]** och klicka sedan på **[!UICONTROL Create rule]**.

   ![](../../assets/offers_decision_rule_creation.png)

1. Ge regeln ett namn och ange en beskrivning och konfigurera sedan regeln efter behov.

   Det gör du genom att **Segment Builder** från Adobe Experience Platform är tillgänglig för att hjälpa dig att skapa regelns villkor. Mer information om hur du använder den finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html).

   I det här exemplet är regeln riktad till kunder som har lojalitetsnivån&quot;Gold&quot;.

   ![](../../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >Segment Builder som tillhandahölls för att skapa beslutsregler har vissa särdrag jämfört med den som används med tjänsten **[!UICONTROL Audience Destinations]**. Fliken **[!UICONTROL Segments]** är till exempel inte tillgänglig för användning. Den globala processen som beskrivs i dokumentationen för Segment Builder är dock fortfarande giltig för att skapa regler för offertbeslut.

1. Bekräfta genom att klicka på **[!UICONTROL Save]**.

1. När regeln har skapats visas den i regellistan. Du kan markera den för att visa dess egenskaper och redigera eller ta bort den.

   ![](../../assets/rule_created.png)

## Videokurs {#video}

>[!NOTE]
>
>Den här videon gäller för Offera decisioningens programtjänst som är byggd på Adobe Experience Platform. Det ger dock allmän vägledning om hur man använder Erbjudandet inom ramen för Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)
