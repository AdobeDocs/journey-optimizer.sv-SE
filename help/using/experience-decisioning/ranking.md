---
title: Rankningsmetoder
description: Lär dig hur du arbetar med rangordningsmetoder
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 1%

---

# Rankningsmetoder {#rankings}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * [Skapa beslutsobjekt](items.md)
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * **[Skapa rangordningsmetoder](ranking.md)**
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
