---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett fragment
description: Lär dig hur du skapar fragment som kan återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 83997271d16e15fb0d7ccdd21aa8ac8b8221a0d5
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---


# Skapa ett fragment från grunden {#create-fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="Markera den visuella typen"
>abstract="Skapa ett fristående visuellt fragment för att göra innehållet återanvändbart i ett e-postmeddelande inom en resa eller kampanj, eller i en innehållsmall."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/email/design-email/add-content/use-visual-fragments.html" text="Lägg till visuella fragment i e-postmeddelanden"

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="Välj uttryckstyp"
>abstract="Skapa ett fristående uttrycksfragment som gör att innehållet kan återanvändas på flera resor och i flera kampanjer. När du använder personaliseringsredigeraren kan du utnyttja alla uttrycksfragment som har skapats i den aktuella sandlådan."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/expression-editor/use-expression-fragments.html" text="Utnyttja uttrycksfragment"

Fragment skapas från **[!UICONTROL Fragments]** vänster meny. Dessutom kan du spara en del av befintligt innehåll som fragment när du utformar innehåll. [Lär dig mer](#save-as-fragment)

När fragmentet har sparats är det tillgängligt för användning under en resa, en kampanj eller en mall. Du kan nu använda det här avsnittet när du skapar innehåll i [!DNL Journey Optimizer]. Se [Lägg till visuella fragment](../email/use-visual-fragments.md) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md)

Följ stegen nedan om du vill skapa ett fragment från grunden.

1. [Åtkomst till fragmentlistan](#access-manage-fragments) via **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny.

1. Välj **[!UICONTROL Create fragment]**.

1. Fyll i fragmentinformationen, dvs. namn och beskrivning (om det behövs).

   ![](assets/fragment-details.png)

1. Markera eller skapa Adobe Experience Platform-taggar från **[!UICONTROL Tags]** fält för att kategorisera fragmentet för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Välj fragmenttyp: [Visual fragment](#create-visual-fragment) eller [Uttrycksfragment](#create-expression-fragment).

   >[!NOTE]
   >
   >För närvarande endast för visuella fragment **E-post** kanalen stöds.

1. Om du skapar ett uttrycksfragment väljer du den typ av kod som du vill använda: **[!UICONTROL HTML]**, **[!UICONTROL JSON]** eller **[!UICONTROL Text]**.

   ![](assets/fragment-expression-type.png)

1. Om du vill tilldela egna eller grundläggande dataanvändningsetiketter till fragmentet väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Klicka **[!UICONTROL Create]**.

1. The [E-postdesigner](../email/get-started-email-design.md) eller så öppnas anpassningsredigeraren, beroende på vilken typ av fragment du skapar.

   * För visuella fragment kan du redigera ditt innehåll efter behov på samma sätt som för alla e-postmeddelanden som finns på en resa eller en kampanj.

     >[!NOTE]
     >
     >Du kan lägga till anpassningsfält och dynamiskt innehåll, men kontextuella attribut stöds inte i fragment.

     ![](assets/fragment-designer.png)

   * För uttrycksfragment använder du [!DNL Journey Optimizer] personaliseringsredigeraren med alla sina personaliserings- och redigeringsfunktioner för att skapa fragmentinnehåll. [Läs mer](../personalization/personalization-build-expressions.md)

     ![](assets/fragment-expression-editor.png)

1. När fragmentet är klart klickar du **[!UICONTROL Save]**.

Fragmentet läggs till i [fragmentlista](#access-manage-fragments). Den är nu klar att användas när du skapar innehåll i [!DNL Journey Optimizer] Email Designer eller personaliseringsredigerare.

* [Lär dig använda visuella fragment](../email/use-visual-fragments.md)
* [Lär dig använda uttrycksfragment](../personalization/use-expression-fragments.md)
