---
title: Konfiguration av innehållskort
description: Krav för innehållskortskanaler
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
exl-id: df92e319-1e42-486f-b688-595964a762c9
source-git-commit: 1f9841ddd039a7591f396e38d8a93ed840d6879e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---

# Krav för innehållskort {#content-card-configuration-prereq}

För att Adobe Journey Optimizer ska kunna visa innehållskort på rätt sätt måste du konfigurera följande Adobe Experience Platform-inställningar:

* **Adobe Experience Platform-datainsamling**

  [Skapa en datastream](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/configure){target="_blank"} och [lägg till Experience Platform-tjänsten](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/configure#aep){target="_blank"}. Aktivera alternativen **[!UICONTROL Edge Segmentation]** och **[!UICONTROL Adobe Journey Optimizer]**. Detta säkerställer att Journey Optimizer-händelser hanteras av Adobe Experience Platform Edge Network.
Lägg till fältgruppen **Experience Event - Proposition Interaction** i datauppsättningen för att inkludera dessa data i dina rapporter. [Läs mer om datastreams](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/configure){target="_blank"}

* **Adobe Experience Platform**

  Kontrollera att standardprincipen för sammanslagning har **Aktiv-på-Edge-princip** aktiverad under **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform-menyn. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=sv-SE#configure){target="_blank"}

  >[!NOTE]
  >
  >När du använder en anpassad **[!UICONTROL Dataset preference]**-sammanfogningsprincip måste du lägga till **[!UICONTROL Journey Inbound]**-datauppsättningen i den angivna sammanfogningsprincipen.

* **Adobe Experience Platform Mobile eller Platform Web SDK**

  För mobil- och webbprogram måste du implementera [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/sv/docs/platform-learn/implement-web-sdk/overview){target="_blank"} på din webbplats eller [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/){target="_blank"} på dina mobilappar om du vill lägga till ändringar på dina webbsidor eller mobilappar.

* **Journey Optimizer**

  Skapa en [konfiguration för innehållskort](#content-card-configuration).

* **Felsökning**

  Använd vyn **Edge Delivery** i **Adobe Experience Platform Assurance** för att felsöka mobila upplevelser. Den kan granska förfrågningar, verifiera kantanrop och granska profildata. [Läs mer](https://experienceleague.adobe.com/sv/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}

* **Innehållsexperiment**

  Kontrollera att datauppsättningen som används i din apps [datastream](https://experienceleague.adobe.com/sv/docs/experience-platform/datastreams/overview#_blank){target="_blank"} också ingår i rapportkonfigurationen för ditt innehållsexperiment. Appdata visas inte i rapporter om datauppsättningarna inte matchar.

  Lär dig hur du lägger till datauppsättningar för rapportering av innehållsexperiment i [det här avsnittet](../reports/reporting-configuration.md).

>[!CAUTION]
>
>När du riktar in dig på pseudonyma profiler (oautentiserade besökare) med dina innehållskort bör du överväga att ställa in en TTL (Time-To-Live) för automatisk borttagning av profiler för att hantera ditt engagerande profilantal och tillhörande kostnader. [Läs mer](../start/guardrails.md#profile-management-inbound)