---
title: Utnyttja kontextdata i beslutet
description: Lär dig använda kontextdata i beslut
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: ddc4b681-020b-4433-b4b3-3791c41907c9
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Utnyttja kontextdata i beslutet {#context}

Med Decisioning kan du utnyttja all information som finns i Adobe Experience Platform för att utföra olika åtgärder, som att skapa [beslutsregler](rules.md) eller [rankningsformler](ranking/ranking.md).

Du kan till exempel utforma en beslutsregel som kräver att det aktuella vädret är ≥80 grader när beslutsbegäran görs.

>[!NOTE]
>
>Kontextdata definieras i Adobe Experience Platform och skickas in när en beslutsbegäran görs. Den omfattar inte historiska data.

Om du vill använda kontextdata måste du först definiera de data som du vill göra tillgängliga i Beslutsfattandet. När du är klar integreras dessa data sömlöst i beslut på fliken **[!UICONTROL Context Data]** som är tillgängliga när du skapar en beslutsregel. Du kan också utnyttja data när du redigerar en rankningsformel.

![](assets/decision-rules-context.png)

Stegen för att mata in beslut med Adobe Experience Platform-data är följande:

1. Skapa ett **Experience Event-schema** i Adobe Experience Platform och dess associerade **datauppsättning**. [Lär dig skapa scheman](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. Skapa en ny Adobe Experience Platform-datastream:

   1. Navigera till menyn **[!UICONTROL Datastreams]** och välj **[!UICONTROL New Datastream]**.

   1. I listrutan **[!UICONTROL Event Schema]** väljer du det Experience Event-schema som skapades tidigare och klickar sedan på **[!UICONTROL Save]**.

      ![](assets/decision-rule-context-datastream.png)

   1. Klicka på **[!UICONTROL Add service]** och välj&quot;Adobe Experience Platform&quot; som tjänst. I listrutan **[!UICONTROL Event Dataset]** markerar du händelsedatamängden som skapades tidigare och aktiverar alternativet **[!UICONTROL Adobe Journey Optimizer]**.

      ![](assets/decision-rules-context-datastream-service.png)

När datastream har sparats hämtas den markerade datauppsättningens information automatiskt och integreras i beslutet, som vanligtvis blir tillgänglig inom cirka 24 timmar.

Mer information om hur du arbetar med Adobe Experience Platform finns i följande resurser:

* [XDM-scheman (Experience Data Model)](https://experienceleague.adobe.com/sv/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [Datauppsättningar](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [Datastreams](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/overview){target="_blank"}
