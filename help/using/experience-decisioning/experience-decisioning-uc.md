---
title: Användningsfall vid beslut
description: Lär dig hur du skapar beslut med hjälp av experiment med den kodbaserade kanalen
feature: Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 09770df2-c514-4217-a71b-e31c248df543
source-git-commit: 83ad828a4d342bba10284cdd20d22eb325e3e1f7
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 3%

---

# Användningsfall vid beslut {#experience-decisioning-uc}

I det här användningsexemplet beskrivs alla steg som behövs för att använda Decisionering med den kodbaserade kanalen [!DNL Journey Optimizer].

<!--In this use case, you create a campaign where you define two delivery treatments - each containing a different decision policy in order to measure which one performs best for your target audience.-->

I det här fallet är du osäker på om en viss rankningsformel kommer att fungera bättre än de förtilldelade prioriteterna.

Om du vill mäta vilken som fungerar bäst för målgruppen skapar du en kampanj där du definierar två leveranssätt:

<!--Set up the experiment such that:-->

* Den första behandlingen innehåller en urvalsstrategi med prioritet som rangordningsmetod.
* Den andra behandlingen innehåller en annan urvalsstrategi där en formel är rangordningsmetoden.

## Skapa urvalsstrategier

Först måste du bygga två urvalsstrategier: en med prioritet som rangordningsmetod och en med en formel som rangordningsmetod.

### Skapa den första urvalsstrategin

I den första urvalsstrategin väljer du prioritet som rangordningsmetod. Följ stegen nedan.

1. Skapa ett beslutsobjekt. [Lär dig hur](items.md)

1. Ange **[!UICONTROL Priority]** för beslutsobjektet jämfört med andra. Om en profil kvalificerar för flera objekt ger en högre prioritet objektets prioritet framför andra.

   ![](assets/exd-uc-item-priority.png)

   >[!NOTE]
   >
   >Prioriteten är en heltalsdatatyp. Alla attribut som är heltalsdatatyper ska innehålla heltalsvärden (inga decimaler).

1. Definiera målgrupper eller regler för att begränsa objektet till enbart specifika profiler. [Lär dig hur du ställer in berättigandet för beslutsobjektet](items.md#eligibility)

1. Ange regler för begränsning för hur många gånger ett erbjudande får presenteras. [Lär dig hur](items.md#capping)

<!--1. If needed, repeat the steps above to create one or more additional decision items.-->

1. Skapa en **samling** där dina beslutsobjekt ska inkluderas. [Läs mer](collections.md)

1. Skapa en **urvalsstrategi**. [Lär dig hur](selection-strategies.md#create-selection-strategy)

1. Välj den [samling](collections.md) som innehåller de erbjudanden som ska beaktas.

1. [Välj den rangordningsmetod](#select-ranking-method) som du vill använda för att välja det bästa erbjudandet för varje profil. I så fall väljer du **[!UICONTROL Offer priority]**. [Läs mer](selection-strategies.md#offer-priority)

   ![](assets/exd-uc-strategy-priority.png)

   <!--If multiple offers are eligible for this strategy, the [Offer priority](#offer-priority) method uses the value defined in the offers.-->

### Skapa den andra urvalsstrategin

I den andra urvalsstrategin väljer du en formel som rangordningsmetod. Följ stegen nedan.

1. Skapa ett beslutsobjekt. [Lär dig hur](items.md)

<!--1. Set the same **[!UICONTROL Priority]** as for the first decision item. TBC?-->

1. Definiera målgrupper eller regler för att begränsa objektet till enbart specifika profiler. [Lär dig hur du ställer in berättigandet för beslutsobjektet](items.md#eligibility)

1. Ange regler för begränsning för hur många gånger ett erbjudande får presenteras. [Lär dig hur](items.md#capping)

<!--1. If needed, repeat the steps above to create one or more additional decision items.-->

1. Skapa en **samling** där dina beslutsobjekt ska inkluderas. [Läs mer](collections.md)

1. Skapa en **urvalsstrategi**. [Lär dig hur](selection-strategies.md#create-selection-strategy)

1. Välj den [samling](collections.md) som innehåller de erbjudanden som ska beaktas.

1. [Välj den rangordningsmetod](#select-ranking-method) som du vill använda för att välja det bästa erbjudandet för varje profil. I det här fallet väljer du **[!UICONTROL Formula]** om du vill använda en viss beräknad poäng för att välja vilket kvalificerat erbjudande som ska levereras. [Läs mer](selection-strategies.md#ranking-formula)

   ![](assets/exd-uc-strategy-formula.png)

<!--
## Create decision items and selection strategies

You first need to create items, group them together in collections, set up rules and ranking methods. These elements will allow you to build selection strategies.

1. Navigate to **[!UICONTROL Decisioning]** > **[!UICONTROL Catalogs]** and create several decision items. Set constraints using audiences or rules to restrict each item to specific profiles only. [Learn more](items.md)

1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)

1. Create **collections** to categorize and group your decision items according to your preferences. [Learn more](collections.md)

1. Create **decision rules** to determine to whom a decision item can be shown. [Learn more](rules.md)

1. Create **ranking methods** and apply them within decision strategies to determine the priority order for selecting decision items. [Learn more](ranking.md)

1. Build **selection strategies** that leverage collections, decision rules, and ranking methods to identify the decision items suitable for displaying to profiles. [Learn more](selection-strategies.md)
-->

## Skapa beslutsprofiler

<!--To present the best dynamic offer and experience to your visitors on your website or mobile app, add a decision policy to a code-based campaign.

Define two delivery treatments each containing a different decision policy.-->

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. Börja personalisera behandling A från fönstret **[!UICONTROL Edit content]**.

1. Välj ikonen **[!UICONTROL Decisions]**, klicka på **[!UICONTROL Create a decision]** och fyll i beslutsinformationen. [Läs mer](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. Välj den första strategi som du skapade. Klicka på **[!UICONTROL Add strategy]**.

1. Klicka på **[!UICONTROL Create]**. Det nya beslutet läggs till under **[!UICONTROL Decisions]**.

   ![](assets/decision-code-based-decision-added.png)

1. Klicka på ikonen för fler åtgärder (tre punkter) och välj **[!UICONTROL Add]**. Nu kan du lägga till alla beslutsattribut som du vill ha i det här.

   ![](assets/decision-code-based-add-decision.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Klicka på **[!UICONTROL Create experiment]** på kampanjsammanfattningssidan för att börja konfigurera ditt innehållsexperiment. [Läs mer](../content-management/content-experiment.md)

1. Välj behandling B i fönstret **[!UICONTROL Edit content]** och upprepa stegen ovan för att skapa ett annat beslut.

1. Välj den andra strategin som du skapade. Klicka på **[!UICONTROL Add strategy]**.

1. Spara innehållet.
