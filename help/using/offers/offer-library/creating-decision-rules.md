---
title: Skapa beslutsregler
description: Lär dig hur du skapar beslutsregler som definierar vilka erbjudanden som kan visas
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 401ce05b-412b-4fa0-a516-bf75727f6387
source-git-commit: 5596c851b70cc38cd117793d492a15fd4ce175ef
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%

---

# Skapa beslutsregler {#create-decision-rules}

Du kan skapa beslutsregler för erbjudanden baserat på data som är tillgängliga i Adobe Experience Platform. Beslutsregler avgör vem som kan visa ett erbjudande.

Du kan till exempel ange att du bara vill att ett &quot;Kloderbjudande för kvinnor&quot; ska visas när (Kön = &#39;kvinna&#39;) och (Region = &#39;Nordost&#39;).

➡️ [Upptäck den här funktionen i en video](#video)

Listan med skapade beslutsregler finns i **[!UICONTROL Components]** -menyn.

![](../assets/decision_rules_list.png)

Så här skapar du en beslutsregel:

1. Gå till **[!UICONTROL Rules]** tabbtangenten och sedan klicka **[!UICONTROL Create rule]**.

   ![](../assets/offers_decision_rule_creation.png)

1. Ge regeln ett namn och ange en beskrivning och konfigurera sedan regeln efter behov.

   För att göra detta **Segment Builder** är tillgängligt för att hjälpa dig att skapa regelns villkor. [Läs mer](../../segment/about-segments.md)

   I det här exemplet är regeln riktad till kunder som har lojalitetsnivån&quot;Gold&quot;.

   ![](../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >Segment Builder som tillhandahålls för att skapa beslutsregler har vissa särdrag jämfört med den som används med **[!UICONTROL Audience Destinations]** service. Till exempel **[!UICONTROL Segments]** -fliken är inte tillgänglig för användning. Den globala processen som beskrivs i dokumentationen för Segment Builder är dock fortfarande giltig för att skapa regler för offertbeslut.

1. Klicka **[!UICONTROL Save]** för att bekräfta.

1. När regeln har skapats visas den i regellistan. Du kan markera den för att visa dess egenskaper och redigera eller ta bort den.

   ![](../assets/rule_created.png)

>[!CAUTION]
>
>Händelsebaserade erbjudanden stöds för närvarande inte i [!DNL Journey Optimizer]. Om du skapar en beslutsregel baserad på en [event](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#events){target=&quot;_blank&quot;} kan du inte utnyttja erbjudandet.

## Videokurs {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)
