---
title: Decisioning use case
description: Learn how to create decisions using experiments with the code-based channel
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
badge: label="Begränsad tillgänglighet"
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 6%

---

# Decisioning use case {#experience-decisioning-uc}

In this use case, you define two delivery treatments each containing a different decision policy in order to measure which one performs best for your target audience.

## Create items and strategies

You first need to create items, group them together in collections, set up rules and ranking methods. These elements will allow you to build selection strategies.

1. **[!UICONTROL Decisioning]****[!UICONTROL  Catalogs]** Set constraints using audiences or rules to restrict each item to specific profiles only. [Läs mer](items.md)

   <!--
   1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)-->

1. **** [Läs mer](collections.md)

1. **** [Läs mer](rules.md)

1. **** [Läs mer](ranking.md)

1. **** [Läs mer](selection-strategies.md)

## Create decision policies

To present the best dynamic offer and experience to your visitors on your website or mobile app, add a decision policy to a code-based campaign.

Define two delivery treatments each containing a different decision policy.

1. **[!UICONTROL Code-base experience]** [Läs mer](../code-based/create-code-based.md)

1. **[!UICONTROL Create experiment]** [Läs mer](../content-management/content-experiment.md)

1. **[!UICONTROL Decisions]****[!UICONTROL Create a decision]** [Läs mer](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. Define the selection strategies for your decision. Klicka på **[!UICONTROL Add strategy]**.

1. Klicka på **[!UICONTROL Create]**. **[!UICONTROL Decisions]**

   ![](assets/decision-code-based-decision-added.png)

1. Klicka på ikonen för fler åtgärder (tre punkter) och välj **[!UICONTROL Add]**. Now you can add all the decision attributes you want inside this.

   ![](assets/decision-code-based-add-decision.png)

1. You can also add any other attribute available in the personalization editor, such as profile attributes.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Build treatment B and repeat the steps above to create another decision.

1. Save your content.


