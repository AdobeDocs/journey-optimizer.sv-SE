---
title: Beslutsregler
description: Lär dig hur du arbetar med beslutsregler
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: 29228a17176421ccf29598d6ebba815b800db7a2
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---

# Beslutsregler {#rules}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_rules"
>title="Skapa beslutsregler"
>abstract="Med beslutsregler kan ni definiera målgruppen för beslutsposter genom att tillämpa begränsningar, antingen direkt på beslutspostnivå eller inom en viss urvalsstrategi. På så sätt kan du exakt kontrollera vilka objekt som ska presenteras för vem."

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsposter: [Konfigurera objektkatalogen](catalogs.md) - [Skapa beslutsobjekt](items.md) - [Hantera artikelsamlingar](collections.md)
* Konfigurera objektmarkering: **[Skapa beslutsregler](rules.md)** - [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

Med beslutsregler kan ni definiera målgruppen för beslutsposter genom att tillämpa begränsningar, antingen direkt på beslutspostnivå eller inom en viss urvalsstrategi. På så sätt kan du exakt kontrollera vilka objekt som ska presenteras för vem.

Låt oss titta på ett scenario där du har beslutsposter med Yoga-relaterade produkter som utformats för kvinnor. Med beslutsregler kan du ange att de här objekten endast ska visas för profiler vars kön är &quot;kvinna&quot; och som har angett &quot;punkt för intresse&quot; i &quot;Yoga&quot;.

>[!NOTE]
>
>Förutom beslutsregler på artikel- och urvalsstrateginivå kan ni också definiera er avsedda målgrupp på kampanjnivå. [Läs mer](../campaigns/create-campaign.md#audience)

Listan över beslutsregler finns i **[!UICONTROL Configuration]** / **[!UICONTROL Decisions rules]** -menyn.

![](assets/decision-rules-list.png)

## Skapa en beslutsregel {#create}

Så här skapar du en beslutsregel:

1. Navigera till **[!UICONTROL Configuration]** / **[!UICONTROL Decision rules]** klicka sedan på **[!UICONTROL Create rule]** -knappen.

1. Skärmen för att skapa beslutsregler öppnas. Ge regeln ett namn och ange en beskrivning.

1. Bygg en beslutsregel som passar dina behov med Adobe Experience Platform Segment Builder. För att göra detta kan du utnyttja olika datakällor, t.ex. profilattribut, målgrupper eller kontextdata från Adobe Experience Platform. [Lär dig använda kontextdata i beslutsregler](#context-data)

   ![](assets/decision-rules-build.png)

   >[!NOTE]
   >
   >Segment Builder som används för att skapa beslutsregler har vissa särdrag jämfört med den som används i Adobe Experience Platform Segmentation Service.  Den globala process som beskrivs i dokumentationen är dock fortfarande giltig för att skapa beslutsregler. [Lär dig hur du skapar segmentdefinitioner](../audience/creating-a-segment-definition.md)

1. När du lägger till och konfigurerar nya fält på arbetsytan visas **[!UICONTROL Audience properties]** visas information om de beräknade profilerna som tillhör målgruppen. Klicka **[!UICONTROL Refresh estimate]** för att uppdatera data.

   >[!NOTE]
   >
   >Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata.

1. När beslutsregeln är klar klickar du på **[!UICONTROL Save]**. Den skapade regeln visas i listan och är tillgänglig för användning i beslutsposter och urvalsstrategier som styr presentationen av beslutsposter i profiler.

## Utnyttja kontextdata i beslutsregler {#context-data}

Skärmen Skapa regel för Experience Decisioning gör att ni kan utnyttja all information som finns i Adobe Experience Platform för att skapa beslutsregler. Du kan till exempel utforma en beslutsregel som kräver att det aktuella vädret är ≥80 grader.

För att göra det måste ni först definiera de data som ska vara tillgängliga i Experience Decision. När de är klara integreras dessa data smidigt i Experience Decision i **[!UICONTROL Context Data]** som är tillgängliga när du skapar en beslutsregel.

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
