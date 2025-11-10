---
title: Utnyttja anpassade uppladdningsmålgrupper för beslut
description: Lär dig hur du utnyttjar anpassade uppladdningsmålgrupper för beslut.
badge: label="Äldre" type="Informative"
feature: Decision Management
role: User
level: Intermediate
exl-id: bd950410-691b-49d8-8851-8c6c448c00fd
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Utnyttja anpassade uppladdningsmålgrupper för beslut {#custom-upload-decisioning}

Med Journey Optimizer kan ni utnyttja data från målgrupper som skapats med anpassad överföring (CSV-fil) till Adobe Experience Platform för att stödja era beslutsflöden. Detta är särskilt användbart när informationen inte behövs i profilen men ändå är viktig för att fatta beslut.

Data från anpassade uppladdningsgrupper kan utnyttjas i Beslutshantering för:

1. Kvalificeringskriterier i erbjudanden och beslut.
2. Anpassa innehåll i erbjudanderepresentationer.

Mer information om anpassade uppladdningsgrupper finns i avsnitten:

* [Kom igång med målgrupper och Journey Optimizer](../audience/about-audiences.md)
* [Importera en målgrupp i Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal#import-audience){target="_blank"}

## Måste läsas {#must-read}

* Den här funktionen stöds endast i **Beslutshantering**, inte i beslut (tidigare kallat Experience Decision).
* Den är exklusivt tillgänglig genom **Decisioning API (Hub)**-begäranden och stöds inte av **Edge Decisioning API** eller **batch-beslut**.

## Använd en anpassad publik som kvalificeringskriterier {#eligibilty}

Du kan använda en anpassad uppladdningspublik som kvalificeringskriterier både på erbjudande- och beslutsnivå. När de lagts till kan dessa kriterier utesluta erbjudanden eller uppsättningar av erbjudanden från berättigandet. Här är de olika platser där du kan utnyttja anpassade målgrupper för uppladdning för att förfina erbjudanden och beslut:

* Skapa en beslutsregel med hjälp av en anpassad uppladdningspublik:

   1. När du redigerar en regel öppnar du fliken **Publiker** och söker efter din CSV-målgrupp i listan. Dra och släpp publiken på regelarbetsytan.
   1. Använd fliken **Attribut** och navigera till anrikningsscheman som är länkade till den valda målgruppen för att komma åt alla data från CSV-filen och använda dem i regeln. Detta gör att du kan använda ett fält från CSV-filen för att förfina regeln. [Lär dig skapa en beslutsregel](../offers/offer-library/creating-decision-rules.md)
   1. Spara regeln. När regeln har skapats kan den användas både på erbjudande- och beslutsnivå för att förfina deras behörighet.

  ![](assets/csv-rule.png)

* Använd anpassade uppladdningsmålgrupper som begränsning för erbjudandet. [Lär dig lägga till begränsningar i ett erbjudande](../offers/offer-library/add-constraints.md)

  När du skapar ett erbjudande kan du i steget **Lägg till begränsningar** antingen:

   * Använd den anpassade uppladdningspubliken för att definiera kvalificeringen för erbjudandet,
   * Använd en regel som utnyttjar den anpassade uppladdningspubliken.

  ![](assets/csv-offer.png)

* Använd anpassade uppladdningsmålgrupper på beslutsnivå.

  När du ställer in ett beslut kan du i steget **Lägg till beslutsomfattning** använda anpassade uppladdningsmålgrupper som utvärderingskriterier för en samling med erbjudanden. [Lär dig definiera beslutsomfattning](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

  ![](assets/csv-decision.png)

## Anpassa offertrepresentationerna med en anpassad publik

Anpassade uppladdningsgrupper kan också användas för att anpassa innehållet i offertrepresentationer genom att referera till data från CSV-filen. [Lär dig hur du lägger till representationer i ett erbjudande](../offers/offer-library/add-representations.md)

För att kunna utnyttja en anpassad uppladdnings-målgrupps attribut för personalisering måste ni först lägga till den anpassade målgruppen som en begränsning. Om du vill göra det när du redigerar ett erbjudande lägger du till målgruppen som begränsningar i steget **Lägg till begränsningar** eller väljer en regel som utnyttjar den anpassade uppladdningsmålgruppen.

![](assets/csv-offer.png)

När målgruppen har lagts till som en begränsning kan du använda dess attribut för att anpassa återgivningsinnehållet. Om du vill göra det går du till fliken **Profilattribut** och söker efter den anpassade uppladdningsmålgruppen. Välj relevanta attribut från målgruppen för att anpassa erbjudandeinnehållet.

![](assets/csv-perso.png)
