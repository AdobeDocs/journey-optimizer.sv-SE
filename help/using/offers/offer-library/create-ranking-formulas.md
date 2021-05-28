---
title: Skapa rankningsformler
description: Lär dig hur du skapar rankningsformler i Adobe Experience Platform.
source-git-commit: db7fd318b14d01a0369c934a3e01c6e368d7658d
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 3%

---

# Skapa rankningsformler {#create-ranking-formulas}

## Om rankningsformler {#about-ranking-formulas}

**Med** rangordningsformler kan du definiera regler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att ta hänsyn till offertens prioritetspoäng.

Rankningsformler uttrycks i **PQL-syntax** och kan utnyttja profilattribut, kontextdata och attribut. Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html).

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut (som tidigare kallades erbjudandeaktivitet). Mer information finns i [Konfigurera erbjudandeurval i beslut](../offer-activities/configure-offer-selection.md).

## Skapa en rankningsformel {#create-ranking-formula}

Så här skapar du en rankningsformel:

* Gå till menyn **[!UICONTROL Components]** och välj sedan fliken **[!UICONTROL Rankings]**.

* Klicka på **[!UICONTROL Create formula]** för att skapa en ny rankningsformel.

   ![](../../assets/ranking-create-formula.png)

* Ange namn, beskrivning och formel för rankningsformeln.

   I det här exemplet vill vi prioritera alla erbjudanden med attributet&quot;hot&quot; om vädret är varmt. För att göra detta skickades **contextData.wall=hot** i beslutsanropet.

   ![](../../assets/ranking-syntax.png)

* Klicka på **[!UICONTROL Save]**. Din rankningsformel skapas. Du kan välja den i listan för att få information och redigera eller ta bort den.

   Det är nu klart att användas i ett beslut om att rangordna kvalificerade erbjudanden för en placering (se [Konfigurera val av erbjudanden i beslut](../offer-activities/configure-offer-selection.md)).

   ![](../../assets/ranking-formula-created.png)
