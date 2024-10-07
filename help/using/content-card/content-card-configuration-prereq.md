---
title: Konfiguration av innehållskort
description: Krav för innehållskortskanaler
feature: Channel Configuration
topic: Content Management
role: Admin
level: Experienced
source-git-commit: d4dce7b31d898d86c330048e6d0a1587e87a617c
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Krav för innehållskort {#content-card-configuration-prereq}

För att Adobe Journey Optimizer ska kunna visa innehållskort på rätt sätt måste du konfigurera följande Adobe Experience Platform-inställningar:

* **Adobe Experience Platform-datainsamling**

  [Skapa en datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) och [lägg till tjänsten Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#aep). Aktivera alternativen **[!UICONTROL Edge Segmentation]** och **[!UICONTROL Adobe Journey Optimizer]**. Detta säkerställer att Journey Optimizer-händelser hanteras av Adobe Experience Platform Edge Network.
Lägg till fältgruppen **Experience Event - Proposition Interaction** i datauppsättningen för att inkludera dessa data i dina rapporter. [Läs mer om datastreams](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)

* **Adobe Experience Platform**

  Kontrollera att **Aktiv-på-Edge-sammanslagningsprincip** är aktiverat i standardsammanslagningsprincipen under **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#configure){target="_blank"}

  >[!NOTE]
  >
  >När du använder en anpassad **[!UICONTROL Dataset preference]**-sammanfogningsprincip måste du lägga till **[!UICONTROL Journey Inbound]**-datauppsättningen i den angivna sammanfogningsprincipen.

* **Adobe Experience Platform Mobile eller Platform Web SDK**

  För mobil- och webbprogram måste du implementera [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/platform-learn/implement-web-sdk/overview) på din webbplats eller [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) på dina mobilappar om du vill lägga till ändringar på dina webbsidor eller mobilappar.

* **Journey Optimizer**

  Skapa en [konfiguration för innehållskort](#content-card-configuration).

* **Felsökning**

  Använd vyn **Edge Delivery** i **Adobe Experience Platform Assurance** för att felsöka mobila upplevelser. Den kan granska förfrågningar, verifiera kantanrop och granska profildata. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery)

* **Innehållsexperiment**

  Kontrollera att datauppsättningen som används i din apps [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview#_blank) också ingår i rapportkonfigurationen för ditt innehållsexperiment. Appdata visas inte i rapporter om datauppsättningarna inte matchar.

  Lär dig hur du lägger till datauppsättningar för rapportering av innehållsexperiment i [det här avsnittet](../reports/reporting-configuration.md).
