---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Analytics-data
description: Lär dig utnyttja Adobe Analytics data
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: 9d842722-e5eb-4743-849d-b7ba9448062f
source-git-commit: a6735063ec68b40b1441b379a20cba8953b59447
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 3%

---

# Utnyttja Adobe Analytics data{#analytics-data}

Ni kan utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till Adobe Experience Platform för att utlösa resor och automatisera kundernas upplevelser.

>[!NOTE]
>
>Det här avsnittet gäller endast för regelbaserade händelser och kunder som behöver använda Adobe Analytics-data.

För att detta ska fungera måste du aktivera rapportsviten som du vill använda i Adobe Experience Platform. Följ stegen nedan för att göra detta:

1. Anslut till Adobe Experience Platform och gå till **[!UICONTROL Sources]**.
1. I Adobe Analytics väljer du **[!UICONTROL Add data]**: en lista över tillgängliga Adobe Analytics-rapportsviter visas.

1. Välj den rapportsvit som du vill aktivera, klicka på **[!UICONTROL Next]** och **[!UICONTROL Finish]**.

1. Dela källdata-ID:t med kontaktpunkten för betaprogrammet.

Detta aktiverar Analytics-källkopplingen för den rapportsviten. När informationen kommer in omvandlas den till en Experience-händelse och skickas till Adobe Experience Platform.

![](assets/jo-event9.png)

Läs mer om Adobe Analytics källanslutning i  [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html){target=&quot;_blank&quot;} och [självstudiekurs](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html){target=&quot;_blank&quot;}.
