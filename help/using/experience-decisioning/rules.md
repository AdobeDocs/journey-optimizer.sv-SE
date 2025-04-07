---
title: Beslutsregler
description: Lär dig hur du arbetar med beslutsregler
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Beslutsregler {#rules}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_rules"
>title="Skapa beslutsregler"
>abstract="Med beslutsregler kan ni definiera målgruppen för beslutsposter genom att tillämpa begränsningar, antingen direkt på beslutspostnivå eller inom en viss urvalsstrategi. På så sätt kan du exakt kontrollera vilka objekt som ska presenteras för vem."

## Om beslutsregler {#about}

Med beslutsregler kan ni definiera målgruppen för beslutsposter genom att tillämpa begränsningar, antingen direkt på beslutspostnivå eller inom en viss urvalsstrategi. På så sätt kan du exakt kontrollera vilka objekt som ska presenteras för vem.

Låt oss titta på ett scenario där du har beslutsposter med Yoga-relaterade produkter som utformats för kvinnor. Med beslutsregler kan du ange att de här objekten endast ska visas för profiler vars kön är &quot;kvinna&quot; och som har angett &quot;punkt för intresse&quot; i &quot;Yoga&quot;.

>[!NOTE]
>
>Förutom beslutsregler på artikel- och urvalsstrateginivå kan ni också definiera er avsedda målgrupp på kampanjnivå. [Läs mer](../campaigns/create-campaign.md#audience)

Listan med beslutsregler finns på menyn **[!UICONTROL Strategy setup]**.

![](assets/decision-rules-list.png)

## Skapa en beslutsregel {#create}

Så här skapar du en beslutsregel:

1. Navigera till **[!UICONTROL Strategy setup]** / **[!UICONTROL Decision rules]** och klicka sedan på knappen **[!UICONTROL Create rule]**.

1. Skärmen för att skapa beslutsregler öppnas. Ge regeln ett namn och ange en beskrivning.

1. Bygg en beslutsregel som passar dina behov med Adobe Experience Platform Segment Builder. För att göra detta kan du utnyttja olika datakällor, t.ex. profilattribut, målgrupper eller kontextdata från Adobe Experience Platform. [Lär dig hur du använder kontextdata](#context-data)

   ![](assets/decision-rules-build.png)

   >[!NOTE]
   >
   >Segment Builder som används för att skapa beslutsregler har vissa särdrag jämfört med den som används i Adobe Experience Platform Segmentation Service.  Den globala process som beskrivs i dokumentationen är dock fortfarande giltig för att skapa beslutsregler. [Lär dig hur du skapar segmentdefinitioner](../audience/creating-a-segment-definition.md)

1. När du lägger till och konfigurerar nya fält på arbetsytan visas information om de beräknade profilerna som tillhör målgruppen i rutan **[!UICONTROL Audience properties]**. Klicka på **[!UICONTROL Refresh estimate]** för att uppdatera data.

   >[!NOTE]
   >
   >Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata.

1. När din beslutsregel är klar klickar du på **[!UICONTROL Save]**. Den skapade regeln visas i listan och är tillgänglig för användning i beslutsposter och urvalsstrategier som styr presentationen av beslutsposter i profiler.

   >[!NOTE]
   >
   >Inkapslingsdjupet i en berättiganderegel är begränsat till 30 nivåer. Detta mäts genom att räkna de `)` avslutande parenteserna i PQL-strängen. En regelsträng kan vara upp till 15 kB för UTF-8-kodade tecken. Detta motsvarar 15 000 ASCII-tecken (1 byte vardera), eller 3 750-7 500 icke-ASCII-tecken (2-4 byte vardera). [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)
