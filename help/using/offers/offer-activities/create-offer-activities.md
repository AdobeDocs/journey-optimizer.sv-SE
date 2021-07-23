---
title: Skapa beslut
description: Lär dig hur du skapar beslut
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: 80451fcd012257c8648e751076ed668aa05c44c7
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 3%

---

# Skapa beslut {#create-offer-activities}

Besluten (tidigare kallade erbjudandeaktiviteter) är behållare för dina erbjudanden som utnyttjar beslutsmotorn för erbjudanden för att välja det bästa erbjudandet som ska levereras, beroende på leveransmålet.

➡️ [Upptäck den här funktionen i en video](#video)

Listan med beslut finns på fliken **[!UICONTROL Offers]** / **[!UICONTROL Decisions]**. Det finns filter som hjälper dig att hämta beslut utifrån status eller start- och slutdatum.

![](../../assets/activities-list.png)

Innan du bestämmer dig måste du kontrollera att komponenterna nedan har skapats i Erbjudandebiblioteket:

* [Placeringar](../offer-library/creating-placements.md)
* [Samlingar](../offer-library/creating-collections.md)
* [Personaliserade erbjudanden](../offer-library/creating-personalized-offers.md)
* [Reserverbjudanden](../offer-library/creating-fallback-offers.md)

## Skapa beslutet {#create-activity}

1. Gå till beslutslistan och klicka sedan på **[!UICONTROL Create decision]**.

1. Ange beslutets namn samt start- och slutdatum och sluttid och klicka sedan på **[!UICONTROL Next]**.

   ![](../../assets/activities-name.png)

## Lägg till beslutsomfattningar {#add-decision-scopes}

1. Dra och släpp en placering från listan för att lägga till den i beslutet och klicka sedan på **[!UICONTROL Add collection]**.

   ![](../../assets/activities-placement.png)

   >[!NOTE]
   >
   >Samma placering kan väljas flera gånger i beslutet.

1. Välj den samling som innehåller de erbjudanden som ska övervägas och klicka sedan på **[!UICONTROL Add]**.

   ![](../../assets/activities-collection.png)

1. De valda erbjudandena läggs till på placeringen. I det här exemplet valde vi två erbjudanden som ska visas i en JSON-typplacering i syfte att presentera erbjudanden i en call center-lösning.

   ![](../../assets/offers-added.png)

1. Om flera erbjudanden kan komma i fråga för den här placeringen kommer erbjudandena med högst prioritet att levereras till kunden.

   Om du vill använda en viss formel för att välja vilket erbjudande som ska levereras väljer du en rankningsformel i listrutan **[!UICONTROL Rank offers by]**. Mer information om detta finns i [det här avsnittet](../offer-activities/configure-offer-selection.md).

1. Fältet **[!UICONTROL Constraint]** begränsar valet av erbjudanden för den här placeringen. Den här begränsningen kan tillämpas med en beslutsregel eller ett eller flera Adobe Experience Platform-segment.

   Om du vill begränsa urvalet av erbjudanden till medlemmarna i ett Adobe Experience Platform-segment väljer du **[!UICONTROL Segments]** och klickar sedan på **[!UICONTROL Add segments]**.

   ![](../../assets/activity_constraint_segment.png)

   Lägg till ett eller flera segment från den vänstra rutan, kombinera dem med de logiska operatorerna **[!UICONTROL And]** / **[!UICONTROL Or]** och klicka sedan på **[!UICONTROL Select]** för att bekräfta.

   Mer information om hur du arbetar med segment finns på [den här sidan](../../segment/about-segments.md).

   ![](../../assets/activity_constraint_segment2.png)

   Om du vill lägga till en markeringsbegränsning för den här placeringen med en beslutsregel, markerar du alternativet **[!UICONTROL Decision rule]** och drar sedan den önskade regeln från den vänstra rutan till **[!UICONTROL Decision rule]**-området. Mer information om hur du skapar en beslutsregel finns i [det här avsnittet](../offer-library/creating-decision-rules.md).

   ![](../../assets/activity_constraint_rule.png)

## Lägg till ett reserverbjudande {#add-fallback}

Välj det reserverbjudande som ska presenteras som en sista utväg till kunder som inte matchar reglerna och begränsningarna för erbjudanden och klicka sedan på **[!UICONTROL Next]**.

![](../../assets/add-fallback-offer.png)

## Granska och spara beslutet {#review}

Om allt är korrekt konfigurerat visas en sammanfattning av beslutsegenskaperna.

1. Se till att beslutet är klart att användas för att presentera erbjudanden för kunderna.
1. Klicka på **[!UICONTROL Finish]**.
1. Välj sedan **[!UICONTROL Save and activate]**.

   ![](../../assets/save-activities.png)

   Du kan också spara beslutet som utkast för att redigera det och aktivera det senare.

Beslutet visas i listan med statusen **[!UICONTROL Live]** eller **[!UICONTROL Draft]**, beroende på om du aktiverade det eller inte i det föregående steget.

Den är nu klar att användas för att leverera erbjudanden till kunder.

## Beslutslista {#decision-list}

I beslutslistan kan du välja vilket beslut som ska visas. Därifrån kan du även redigera den, ändra dess status (**Utkast**, **Live**, **Fullständigt**, **Arkiverat**), duplicera beslutet eller ta bort det.

![](../../assets/decision_created.png)

Klicka på knappen **[!UICONTROL Edit]** för att gå tillbaka till beslutsversionsläget, där du kan ändra beslutsbeslutets [information](#create-activity), [beslutsomfattningar](#add-decision-scopes) och [reserverbjudande](#add-fallback).

Välj ett live-beslut och klicka på **[!UICONTROL Deactivate]** för att återställa beslutsstatusen till **[!UICONTROL Draft]**.

Om du vill ange status till **[!UICONTROL Live]** igen väljer du knappen **[!UICONTROL Activate]** som nu visas.

![](../../assets/decision_activate.png)

Knappen **[!UICONTROL More actions]** aktiverar de åtgärder som beskrivs nedan.

![](../../assets/decision_more-actions.png)

* **[!UICONTROL Complete]**: anger beslutets status till  **[!UICONTROL Complete]**, vilket innebär att beslutet inte längre kan anropas. Den här åtgärden är bara tillgänglig för aktiverade beslut. Beslutet är fortfarande tillgängligt i listan, men du kan inte ange tillbaka status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera, ta bort eller arkivera den.

* **[!UICONTROL Duplicate]**: skapar ett beslut med samma egenskaper, beslutsomfattningar och reserverbjudande. Som standard har det nya beslutet statusen **[!UICONTROL Draft]**.

* **[!UICONTROL Delete]**: tar bort beslutet från listan.

   >[!CAUTION]
   >
   >Beslutet och dess innehåll kommer inte längre att vara tillgängliga. Det går inte att ångra den här åtgärden.
   >
   >Om beslutet används i ett annat objekt kan det inte tas bort.

* **[!UICONTROL Archive]**: anger beslutsstatus till  **[!UICONTROL Archived]**. Beslutet är fortfarande tillgängligt i listan, men du kan inte ange tillbaka status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera eller ta bort den.

Du kan också ta bort eller ändra status för flera beslut samtidigt genom att markera motsvarande kryssrutor.

![](../../assets/decision_multiple-selection.png)

Om du vill ändra status för flera beslut med olika status, ändras bara statusen.

![](../../assets/decision_change-status.png)

När ett beslut har skapats kan du klicka på dess namn i listan.

![](../../assets/decision_click-name.png)

På så sätt kan du få tillgång till detaljerad information för det beslutet. Välj fliken **[!UICONTROL Change log]** för att [övervaka alla ändringar](../get-started/user-interface.md#changes-log) som har gjorts i beslutet.

![](../../assets/decision_information.png)

## Videokurs {#video}

>[!NOTE]
>
>Den här videon gäller för Offera decisioningens programtjänst som är byggd på Adobe Experience Platform. Det ger dock allmän vägledning om hur man använder Erbjudandet inom ramen för Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
