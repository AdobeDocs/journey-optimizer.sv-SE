---
title: Skapa beslutsregler
description: Lär dig hur du skapar beslutsregler som definierar vilka erbjudanden som kan visas
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 401ce05b-412b-4fa0-a516-bf75727f6387
source-git-commit: ce0cba88c5649b3efd557d6d539ffd7dc2c8f193
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# Skapa beslutsregler {#create-decision-rules}

## Om beslutsregler {#about}

Du kan skapa beslutsregler för erbjudanden baserat på data som är tillgängliga i Adobe Experience Platform. Beslutsregler avgör vem som kan visa ett erbjudande.

Du kan t.ex. ange att du bara vill att ett &quot;Kläddererbjudande för kvinnor&quot; ska visas när (Kön = &quot;Kvinna&quot;) och (Region = &#39;Nordost&#39;).

➡️ [Upptäck den här funktionen i en video](#video)

Här följer en lista över begränsningar som ska vara kända när man arbetar med beslutsregler:

* När du skapar en regel kan du använda historiska händelser, men det finns begränsningar för när dessa regler kan användas.
* Edge-decimering använder kantprofilen som inte lagrar händelser, så alla regler som används i ett edge-beslut blir ogiltiga.
* Resor som använder offertbeslut kommer inte att undersöka historiska händelser, så dessa regler kommer att vara ogiltiga.
* Beslutsbegäranden som använder navprofilen kommer att undersöka de senaste 100 upplevelsehändelserna i profilen för att utvärdera regler som refererar till historiska upplevelsehändelser.

## Skapa en beslutsregel {#create}

Listan med skapade beslutsregler finns i **[!UICONTROL Components]** -menyn.

![](../assets/decision_rules_list.png)

Så här skapar du en beslutsregel:

1. Gå till **[!UICONTROL Rules]** tabbtangenten och klicka sedan på **[!UICONTROL Create rule]**.

   ![](../assets/offers_decision_rule_creation.png)

1. Ge regeln ett namn och ange en beskrivning och konfigurera sedan regeln efter behov.

   För att göra detta måste Adobe Experience Platform **Segment Builder** är tillgängligt för att hjälpa dig att skapa regelns villkor. [Lär dig hur du skapar segmentdefinitioner](../../audience/creating-a-segment-definition.md)

   <!--In this example, the rule will target customers that have the "Gold" loyalty level.-->

   ![](../assets/offers_decision_rule_creation_segment.png)

   >[!NOTE]
   >
   >Segment Builder som tillhandahålls för att skapa beslutsregler har vissa särdrag jämfört med den som används med **[!UICONTROL Segmentation]** service. Den globala processen som beskrivs i [Segment Builder](../../audience/creating-a-segment-definition.md) Dokumentationen kan fortfarande användas för att skapa beslutsregler för erbjudanden. Läs mer i [Dokumentation för Adobe Experience Platform Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html).

1. När du lägger till och konfigurerar nya fält på arbetsytan visas **[!UICONTROL Audience properties]** visas information om de beräknade profilerna som tillhör målgruppen. Klicka **[!UICONTROL Refresh estimate]** för att uppdatera data.

   ![](../assets/offers_decision_rule_creation_estimate.png)

   >[!NOTE]
   >
   >Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata. Exempel: en regel som kräver att det aktuella vädret är ≥80 grader.

1. Klicka på **[!UICONTROL Save]** för att bekräfta.

1. När regeln har skapats visas den i **[!UICONTROL Rules]** lista. Du kan markera den för att visa dess egenskaper och redigera eller ta bort den.

   ![](../assets/rule_created.png)

>[!CAUTION]
>
>Händelsebaserade erbjudanden stöds för närvarande inte i [!DNL Journey Optimizer]. Om du skapar en beslutsregel baserad på en [event](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html#events){target="_blank"}, kommer du inte att kunna utnyttja erbjudandet.

## Självstudievideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329373?quality=12)
