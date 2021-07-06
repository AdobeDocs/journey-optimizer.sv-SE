---
title: Använd anpassade åtgärder
description: Lär dig hur du använder anpassade åtgärder
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%

---

# Använd anpassade åtgärder {#section_f2c_hbg_nhb}

Om du använder en anpassad åtgärd visas parametrarna **[!UICONTROL URL Configuration]** och **[!UICONTROL Authentication]** som definierats i åtgärdskonfigurationsskärmen i skrivskyddad version (se [den här sidan](../action/about-custom-action-configuration.md)).

>[!NOTE]
>
>Du kan inte skicka en samling i anpassade åtgärdsparametrar. Om den anpassade åtgärden förväntar sig samlingar fungerar den inte. Observera också att parametrarna har ett förväntat format (exempel: sträng, decimal osv.). Du måste vara försiktig med att ta hänsyn till dessa förväntade format.

I avsnittet **[!UICONTROL Action parameters]** ser du meddelandeparametrarna som är definierade som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (exempel: händelser, datakällor), skicka värden manuellt eller använd den avancerade uttrycksredigeraren för avancerade användningsområden. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. Mer information finns i [Adobe Journey Orchestration-dokumentation](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/expressionadvanced.html){target=&quot;_blank&quot;}.
