---
title: Rapport om beslut
description: Lär dig hur du rapporterar om beslut.
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 7c45cd8a-8e86-4646-ba0a-db393e92d9da
source-git-commit: 4c0605d6ccff5cd62ef7aeb04e0610342d7cc3d5
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---


# Rapport om beslut {#decisioning-report}

## Kodbaserad kampanjrapportering {#campaigns}

När de kodbaserade upplevelserna är live kan ni få tillgång till dedikerade rapporter för att övervaka nyckeltal (KPI) som en heltäckande kontrollpanel och leverera en analys av viktig statistik som är kopplad till kampanjen.

Detta innefattar information om resultaten av beslutsartiklar och hur användarna interagerade med dem. [Lär dig arbeta med kodbaserade upplevelserapporter](../reports/campaign-global-report-cja-code.md)

![](../reports/assets/cja-decisioning-item-performance.png)

## Rapportering i Customer Journey Analytics {#cja}

Om du arbetar med Customer Journey Analytics kan du skapa anpassade rapportinstrumentpaneler för kodbaserade kampanjer med hjälp av Beslutsfattande.

De huvudsakliga stegen visas nedan. Detaljerad information om hur du arbetar med Customer Journey Analytics finns i [Customer Journey Analytics-dokumentationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing){target="_blank"}.

1. Skapa och konfigurera en **anslutning** i Customer Journey Analytics. På så sätt kan du ansluta till den datauppsättning som du vill ha rapporter för. [Lär dig skapa en anslutning](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}

1. Skapa en **datavy** och koppla den till anslutningen som skapades tidigare. På fliken **[!UICONTROL Components]** väljer du de relevanta schemafält som du vill visa i rapporter. Kontrollera att du inkluderar fälten **propositionInteract** och **propositionDisplay** för beslut. [Lär dig hur du skapar och konfigurerar datavyer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}

1. Kombinera datakomponenter, tabeller och visualiseringar i **arbetsyteprojekt** för att skapa och dela rapporter för den kodbaserade kampanjen. [Lär dig skapa arbetsyteprojekt](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects){target="_blank"}
