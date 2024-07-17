---
title: Rankningsmetoder
description: Lär dig hur du arbetar med rangordningsmetoder
feature: Experience Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet"
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 1%

---

# Rankningsmetoder {#rankings}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="Skapa rankningsformler"
>abstract="Med formler kan du definiera regler som bestämmer vilket objekt som ska presenteras först, i stället för att ta hänsyn till objektets prioritetspoäng. När en rangordningsmetod har skapats kan du tilldela den till en urvalsstrategi för att definiera vilka objekt som ska väljas först."

Med rangordningsmetoder kan du rangordna objekt som ska visas för en viss profil. När en rangordningsmetod har skapats kan du tilldela den till en urvalsstrategi för att definiera vilka objekt som ska väljas först.

Det finns två sorteringsmetoder:

* **Med formler** kan du definiera regler som avgör vilket objekt som ska presenteras först, i stället för att ta hänsyn till objektets prioritetspoäng.

* **AI-modeller** gör att du kan använda tränade modellsystem som utnyttjar flera datapunkter för att avgöra vilket objekt som ska presenteras först.

## Skapa rangordningsmetoder {#create}

Så här skapar du en rangordningsmetod:

1. Navigera till menyn **[!UICONTROL Strategy setup]** och välj sedan menyn **[!UICONTROL Formulas]** eller **[!UICONTROL AI models]** beroende på vilken typ av rankning du vill använda.

1. Klicka på knappen **[!UICONTROL Create formula]** eller **[!UICONTROL Create AI model]** i skärmens övre högra hörn.

   ![](assets/ranking-create.png)

1. Konfigurera formeln eller AI-modellen så att den passar dina behov och spara den sedan.

   Detaljerad information om hur du skapar rankningsformler och AI-modeller finns i dokumentationen för beslutshantering:

   * [Rankningsformler](../offers/ranking/create-ranking-formulas.md)
   * [AI-modeller](../offers/ranking/ai-models.md)


## Utnyttja attribut för beslutsunderlag i formler {#items}

Rankningsformler uttrycks i **PQL-syntax** och kan utnyttja olika attribut, t.ex. profilattribut, [kontextdata](context-data.md) och attribut relaterade till dina beslutsobjekt.

Om du vill använda attribut som hör till dina beslutsobjekt i formler måste du följa syntaxen nedan i din rankningsreceptas kod. Expandera varje avsnitt för mer information:

++ + utnyttja standardattribut för beslutsunderlag

![](assets/formula-attribute.png)

+++

+++utnyttja anpassade attribut för beslutsobjekt

![](assets/formula-attribute-custom.png)

+++
