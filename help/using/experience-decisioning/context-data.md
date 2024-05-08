---
title: Utnyttja kontextdata i Experience Decision
description: Lär dig använda kontextdata i Experience Decision
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet"
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---

# Utnyttja kontextdata i Experience Decision {#context}

Med Experience Decision kan ni utnyttja all information som finns i Adobe Experience Platform för att utföra olika åtgärder, som att skapa [beslutsregler](rules.md) eller [rankningsformler](ranking.md). Du kan till exempel utforma en beslutsregel som kräver att det aktuella vädret är ≥80 grader när beslutsbegäran görs.

>[!NOTE]
>
>Kontextdata definieras i Adobe Experience Platform och skickas in när en beslutsbegäran görs. Den omfattar inte historiska data.

Om du vill använda kontextdata måste du först definiera de data som du vill göra tillgängliga i Experience Decision. När de är klara integreras dessa data smidigt i Experience Decision i **[!UICONTROL Context Data]** som är tillgängliga när du skapar en beslutsregel. Du kan också utnyttja data när du redigerar en rankningsformel.

![](assets/decision-rules-context.png)

Stegen för att mata Experience Decision med Adobe Experience Platform-data är följande:

1. Skapa en **Experience Event-schema**  i Adobe Experience Platform och tillhörande **datauppsättning**. [Lär dig skapa scheman](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. Skapa en ny Adobe Experience Platform-datastream:

   1. Navigera till **[!UICONTROL Datastreams]** meny och välj **[!UICONTROL New Datastream]**.

   1. I **[!UICONTROL Event Schema]** nedrullningsbar lista, välj det Experience Event-schema som skapades tidigare och klicka sedan på **[!UICONTROL Save]**.

      ![](assets/decision-rule-context-datastream.png)

   1. Klicka **[!UICONTROL Add service]** och väljer&quot;Adobe Experience Platform&quot; som tjänst. I **[!UICONTROL Event Dataset]** väljer du den händelsedatamängd som skapades tidigare och aktiverar **[!UICONTROL Adobe Journey Optimizer]** alternativ.

      ![](assets/decision-rules-context-datastream-service.png)

När datastream har sparats hämtas den markerade datauppsättningens information automatiskt och integreras i Experience Decision, som vanligtvis blir tillgänglig inom cirka 24 timmar.

Mer information om hur du arbetar med Adobe Experience Platform finns i följande resurser:

* [XDM-scheman (Experience Data Model)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [Datauppsättningar](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [Datastreams](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview){target="_blank"}
