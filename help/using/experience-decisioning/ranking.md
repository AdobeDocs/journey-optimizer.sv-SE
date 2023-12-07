---
title: Rankningsmetoder
description: Lär dig hur du arbetar med rangordningsmetoder
feature: Experience Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: c13cd73229b2fab80722663afae9fe24b660c0f9
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 1%

---

# Rankningsmetoder {#rankings}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="Skapa rankningsformler"
>abstract="Med formler kan du definiera regler som bestämmer vilket objekt som ska presenteras först, i stället för att ta hänsyn till objektets prioritetspoäng. När en rangordningsmetod har skapats kan du tilldela den till en beslutsstrategi för att definiera vilka objekt som ska väljas först."

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsposter: [Konfigurera objektkatalogen](catalogs.md) - [Skapa beslutsobjekt](items.md) - [Hantera artikelsamlingar](collections.md)
* Konfigurera objektmarkering: [Skapa beslutsregler](rules.md) - **[Skapa rangordningsmetoder](ranking.md)**
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

Med rangordningsmetoder kan du rangordna objekt som ska visas för en viss profil. När en rangordningsmetod har skapats kan du tilldela den till en beslutsstrategi för att definiera vilka objekt som ska väljas först.

Rankningsmetoderna är tillgängliga via **[!UICONTROL Configuration]** / **[!UICONTROL Ranking methods]** -menyn. Det finns två sorteringsmetoder:

* **Formler** gör att du kan definiera regler som avgör vilket objekt som ska presenteras först, i stället för att ta hänsyn till objektets prioritetspoäng.

* **AI-modeller** gör att du kan använda tränade modellsystem som utnyttjar flera datapunkter för att avgöra vilken artikel som ska presenteras först.

![](assets/ranking-create.png)

Detaljerad information om varje typ av rankningsmetod och hur du skapar dem finns i dokumentationen för beslutshantering som finns här:

* [Rankningsformler](../offers/ranking/create-ranking-formulas.md)
* [AI-modeller](../offers/ranking/ai-models.md)
