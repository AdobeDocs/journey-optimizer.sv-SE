---
title: Om Adobe Analytics-data
description: Lär dig utnyttja Adobe Analytics data
feature: Händelser
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# Utnyttja Adobe Analytics data{#analytics-data}

Ni kan utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till plattformen för att utlösa resor och automatisera kundernas upplevelser.

>[!NOTE]
>
>Det här avsnittet gäller endast för regelbaserade händelser och kunder som behöver använda Adobe Analytics-data.

För att detta ska fungera måste du aktivera rapportsviten som du vill utnyttja i Adobe Experience Platform:

1. I Adobe Experience Platform väljer du **[!UICONTROL Sources]** och sedan **[!UICONTROL Add data]** i avsnittet Adobe Analytics. En lista över tillgängliga Adobe Analytics-rapportsviter visas.

1. Välj den rapportserie som du vill aktivera, klicka på **[!UICONTROL Next]** och klicka på **[!UICONTROL Finish]**.

1. Dela källdata-ID:t med kontaktpunkten för betaprogrammet.

Detta aktiverar Analytics-källkopplingen för den rapportsviten. När informationen kommer in omvandlas den till en Experience-händelse och skickas till Adobe Experience Platform.

![](../assets/jo-event9.png)

Läs mer om Adobe Analytics källanslutning i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html){target=&quot;_blank&quot;} och [självstudiekurs](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html){target=&quot;_blank&quot;}.
