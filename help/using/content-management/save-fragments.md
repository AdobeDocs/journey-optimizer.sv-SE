---
solution: Journey Optimizer
product: journey optimizer
title: Spara innehåll som fragment
description: Lär dig spara innehåll som fragment för att återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 83997271d16e15fb0d7ccdd21aa8ac8b8221a0d5
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Spara innehåll som fragment {#save-as-fragment}

När du redigerar innehåll i [!DNL Journey Optimizer]kan du spara hela eller delar av innehållet som fragment för framtida återanvändning.

## Spara innehåll som visuellt fragment {#save-as-visual-fragment}

När du utformar en [innehållsmall](content-templates.md) eller en [e-post](../email/get-started-email-design.md) i en kampanj eller en resa kan du spara en del av innehållet som ett visuellt fragment. Följ stegen nedan för att göra detta.

1. I [E-postdesigner](../email/get-started-email-design.md)klickar du på ellipsen högst upp till höger på skärmen.

1. Välj **[!UICONTROL Save as fragment]** i listrutan.

   ![](assets/fragment-save-as.png)

1. The **[!UICONTROL Save as fragment]** visas. Här väljer du de element som du vill inkludera i fragmentet, inklusive anpassningsfält och dynamiskt innehåll. Observera att kontextuella attribut inte stöds i fragment.

   >[!CAUTION]
   >
   >Du kan bara markera intilliggande avsnitt. Du kan inte markera en tom struktur eller ett annat fragment.

   ![](assets/fragment-save-as-screen.png)

1. Klicka **[!UICONTROL Create]**. Fyll i fragmentinformationen, dvs. namn och beskrivning (om det behövs).

1. Om du vill tilldela egna eller grundläggande dataanvändningsetiketter till fragmentet väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Markera eller skapa Adobe Experience Platform-taggar från **Taggar** fält för att kategorisera mallen för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Klicka **[!UICONTROL Create]** igen. Fragmentet sparas i [fragmentlista](#access-manage-fragments), kan du nå från [!DNL Journey Optimizer] egen meny.

   Det blir ett fristående fragment som kan [använd](#access-manage-fragments), [redigerad](#edit-fragments) och [arkiverad](#archive-fragments) som alla andra objekt i den listan.

Du kan nu använda det här fragmentet när du skapar [e-post](../email/get-started-email-design.md) eller [innehållsmall](content-templates.md) inom [!DNL Journey Optimizer]. [Lär dig mer](../email/use-visual-fragments.md)

>[!NOTE]
>
>Ändringar i det nya fragmentet sprids inte till e-postmeddelandet eller mallen som det kommer från. På samma sätt ändras inte det nya fragmentet när det ursprungliga innehållet redigeras i e-postmeddelandet eller mallen.

## Spara innehåll som uttrycksfragment {#save-as-expression-fragment}

>[!CONTEXTUALHELP]
>id="ajo_perso_library"
>title="Spara som uttrycksfragment"
>abstract="The [!DNL Journey Optimizer] Med personaliseringsredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll."

The [!DNL Journey Optimizer] Med personaliseringsredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll.

Följ stegen nedan om du vill spara innehåll som ett uttrycksfragment.

1. I [personaliseringsredigerare](../personalization/personalization-build-expressions.md) gränssnitt, skapa ett uttryck och klicka sedan på **[!UICONTROL Save as fragment]**.

1. I den högra rutan anger du ett namn och en beskrivning för uttrycket så att användarna enklare kan hitta det.

   ![](assets/expression-fragment-save-as.png)

1. Klicka **[!UICONTROL Save fragment]**.

   <!--An expression fragment cannot be nested inside another fragment.-->

1. Uttrycksfragmentet läggs till i [fragmentlista](#access-manage-fragments). Nu kan ni använda den för att skapa personaliserat innehåll.

>[!NOTE]
>
>Uttryck får inte överskrida 200 kB.
