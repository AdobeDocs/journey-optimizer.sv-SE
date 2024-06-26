---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett fragment
description: Lär dig hur du skapar fragment som kan återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: da3ffe9c-a244-4246-b4b5-a3a1d0508676
source-git-commit: ffeaa49cde2871b28c85598469e62f4d9acbf060
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 0%

---

# Skapa ett fragment {#create-fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="Markera den visuella typen"
>abstract="Skapa ett fristående visuellt fragment för att göra innehållet återanvändbart i ett e-postmeddelande inom en resa eller kampanj, eller i en innehållsmall."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/email/design-email/add-content/use-visual-fragments" text="Lägg till visuella fragment i e-postmeddelanden"

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="Välj uttryckstyp"
>abstract="Skapa ett fristående uttrycksfragment som gör att innehållet kan återanvändas på flera resor och i flera kampanjer. När du använder personaliseringsredigeraren kan du utnyttja alla uttrycksfragment som har skapats i den aktuella sandlådan."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/expression-editor/use-expression-fragments.html" text="Utnyttja uttrycksfragment"

Fragment kan skapas från grunden från **[!UICONTROL Fragments]** vänster meny. Dessutom kan du spara en del av befintligt innehåll som fragment när du utformar innehåll. [Lär dig mer](#save-as-fragment)

När fragmentet har sparats är det tillgängligt för användning under en resa, en kampanj eller en mall. Du kan använda det här fragmentet när du skapar innehåll på resor och i kampanjer. Se [Lägg till visuella fragment](../email/use-visual-fragments.md) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md)

Följ stegen nedan för att skapa ett fragment.

## Definiera fragmentets egenskaper {#properties}

1. Åtkomst till fragmentlistan via **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny.

1. Välj **[!UICONTROL Create fragment]** och fyll i fragmentnamnet och beskrivningen (om det behövs).

   ![](assets/fragment-details.png)

1. Markera eller skapa Adobe Experience Platform-taggar från **[!UICONTROL Tags]** fält för att kategorisera fragmentet för förbättrad sökning. [Lär dig hur du arbetar med enhetliga taggar](../start/search-filter-categorize.md#tags)

1. Välj fragmenttyp: **Visual fragment** eller **Uttrycksfragment**. [Läs mer om visuella fragment och uttrycksfragment](../content-management/fragments.md#visual-expression)

   >[!NOTE]
   >
   >För närvarande finns visuella fragment tillgängliga för **E-post** endast kanal.

1. Om du skapar ett uttrycksfragment väljer du den typ av kod som du vill använda: **[!UICONTROL HTML]**, **[!UICONTROL JSON]** eller **[!UICONTROL Text]**.

   ![](assets/fragment-expression-type.png)

1. Klicka på knappen **[!UICONTROL Manage access]** i skärmens övre del. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Klicka **[!UICONTROL Create]** för att utforma fragmentets innehåll.

## Designa fragmentinnehållet {#content}

När du har konfigurerat fragmentets egenskaper öppnas e-post-Designer eller personaliseringsredigeraren, beroende på vilken typ av fragment du skapar.

* För visuella fragment kan du redigera ditt innehåll efter behov på samma sätt som för alla e-postmeddelanden som finns på en resa eller en kampanj. [Läs mer](../email/get-started-email-design.md)

  ![](assets/fragment-designer.png)

* För uttrycksfragment använder du [!DNL Journey Optimizer] personaliseringsredigeraren med alla sina personaliserings- och redigeringsfunktioner för att skapa fragmentinnehåll. [Läs mer](../personalization/personalization-build-expressions.md)

  ![](assets/fragment-expression-editor.png)

Klicka på **Spara** -knappen. Fragmentet skapas och läggs till i fragmentlistan med **Utkast** status. Ni kan förhandsgranska den och publicera den för att göra den tillgänglig på resor och i kampanjer.

>[!NOTE]
>
>Fragmentpublicering lanseras gradvis under flera dagar efter Journey Optimizer juni-utgåvan. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer. Om den här förbättringen ännu inte är tillgänglig i din miljö, observera att fragmentpublicering inte krävs för att använda fragment på era resor och i era kampanjer.

## Förhandsgranska och publicera fragmentet {#publish}

>[!NOTE]
>
>Om du vill publicera ett fragment måste du ha **Publish Fragment** relaterad behörighet. [Läs mer om behörigheter](../administration/ootb-permissions.md)

Om ditt fragment är klart att publiceras kan du förhandsgranska och publicera det så att det blir tillgängligt på dina resor och i kampanjer. Gör så här:

1. Gå tillbaka till skärmen för att skapa fragment när du har utformat dess innehåll, eller öppna den från listan med fragment.

1. En förhandsgranskning av fragmentet finns under **Taggar** -fält, så att återgivningen kan kontrolleras. Om du behöver göra några ändringar klickar du på **Redigera** i skärmens övre del för att öppna e-post-Designer eller anpassningsredigeraren beroende på fragmenttyp.

   ![](assets/fragment-preview.png)

1. Klicka på **Publish** i det övre högra hörnet för att publicera fragmentet.

   Om fragmentet används i en direktresa eller kampanj öppnas ett meddelande som informerar dig. Klicka på **Se mer** länk för att få tillgång till listan över resor och/eller kampanjer där det hänvisas till. [Lär dig hur du utforskar referenser till ett fragment](../content-management/manage-fragments.md#explore-references)

   Klicka **Bekräfta** för att publicera fragmentet och uppdatera det i de direktresor/kampanjer som använder det.

   ![](assets/fragment-publish.png){width="70%" align="center"}

Fragmentet är nu **Live**, och blir tillgängligt när du skapar innehåll i [!DNL Journey Optimizer] Skicka e-post till Designer eller en personaliseringsredigerare:

* [Lär dig använda visuella fragment](../email/use-visual-fragments.md)
* [Lär dig använda uttrycksfragment](../personalization/use-expression-fragments.md)
