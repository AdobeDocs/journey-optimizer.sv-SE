---
solution: Journey Optimizer
product: journey optimizer
title: Spara innehåll som fragment
description: Lär dig spara innehåll som fragment för att återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 70e88ea0-f2b0-4c13-8693-619741762429
source-git-commit: 893f7146b358da48153b1e6bc74b8f622028df76
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---

# Spara innehåll som fragment {#save-as-fragment}

När du redigerar innehåll i [!DNL Journey Optimizer]kan du spara hela eller delar av innehållet som fragment för framtida återanvändning. Du kan spara innehåll som fragment antingen [från e-postdesignern](#save-as-visual-fragment), eller [från uttrycksredigeraren](#save-as-expression-fragment).

## Spara som visuellt fragment {#save-as-visual-fragment}

Så här sparar du innehåll från e-postdesignern som fragment:

1. I [E-postdesigner](../email/get-started-email-design.md)klickar du på ellipsen högst upp till höger på skärmen.

1. Välj **[!UICONTROL Save as fragment]** i listrutan.

   ![](assets/fragment-save-as.png)

1. The **[!UICONTROL Save as fragment]** visas. Här väljer du de element som du vill inkludera i fragmentet, inklusive anpassningsfält och dynamiskt innehåll. Observera att kontextuella attribut inte stöds i fragment.

   ![](assets/fragment-save-as-screen.png)

   >[!CAUTION]
   >
   >Du kan bara markera intilliggande avsnitt. Du kan inte markera en tom struktur eller ett annat fragment.

1. Klicka **[!UICONTROL Create]** och fyll i fragmentnamnet och beskrivningen (om det behövs).

1. Klicka på knappen **[!UICONTROL Manage access]** i skärmens övre del. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Markera eller skapa Adobe Experience Platform-taggar från **Taggar** fält för att kategorisera mallen för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Klicka på **[!UICONTROL Create]**. Fragmentet läggs till i [fragmentlista](#access-manage-fragments) med **Utkast** status. Det blir ett fristående fragment som kan användas som vilket annat visuellt fragment som helst från den listan.

   >[!NOTE]
   >
   >Ändringar i det nya fragmentet sprids inte till e-postmeddelandet eller mallen som det kommer från. På samma sätt ändras inte det nya fragmentet när det ursprungliga innehållet redigeras i e-postmeddelandet eller mallen.

1. För att kunna använda fragmentet i era resor och kampanjer måste ni göra det levande. [Lär dig förhandsgranska och publicera ett fragment](../content-management/create-fragments.md#publish)

>[!NOTE]
>
>Fragmentpublicering lanseras gradvis under flera dagar efter Journey Optimizer juni-utgåvan. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer. Om den här förbättringen ännu inte är tillgänglig i din miljö, observera att fragmentpublicering inte krävs för att använda fragment på era resor och i era kampanjer.

## Spara som uttrycksfragment {#save-as-expression-fragment}

>[!CONTEXTUALHELP]
>id="ajo_perso_library"
>title="Spara som uttrycksfragment"
>abstract="The [!DNL Journey Optimizer] Med personaliseringsredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll."

The [!DNL Journey Optimizer] Med personaliseringsredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll.

Följ stegen nedan om du vill spara innehåll som ett uttrycksfragment.

1. I [personaliseringsredigerare](../personalization/personalization-build-expressions.md) gränssnitt, skapa ett uttryck och klicka sedan på **[!UICONTROL Save as fragment]**.

   >[!NOTE]
   >
   >Uttryck får inte överskrida 200 kB.

1. I den högra rutan anger du ett namn och en beskrivning för uttrycket så att användarna enklare kan hitta det.

   ![](assets/expression-fragment-save-as.png)

1. Klicka på **[!UICONTROL Save fragment]**.

   <!--An expression fragment cannot be nested inside another fragment.-->

1. Fragmentet läggs till i [fragmentlista](#access-manage-fragments) med **Utkast** status. Det blir ett fristående fragment som kan användas som andra uttrycksfragment från den listan.

1. För att kunna använda fragmentet i era resor och kampanjer måste ni göra det levande. [Lär dig förhandsgranska och publicera ett fragment](../content-management/create-fragments.md#publish)

>[!NOTE]
>
>Fragmentpublicering lanseras gradvis under flera dagar efter Journey Optimizer juni-utgåvan. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer. Om den här förbättringen ännu inte är tillgänglig i din miljö, observera att fragmentpublicering inte krävs för att använda fragment på era resor och i era kampanjer.
