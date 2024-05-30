---
solution: Journey Optimizer
product: journey optimizer
title: Hantera fragment
description: Lär dig hantera dina innehållsfragment
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 83997271d16e15fb0d7ccdd21aa8ac8b8221a0d5
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 2%

---


# Hantera fragment {#manage-fragments}

Om du vill hantera dina fragment kan du komma åt fragmentlistan från **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny.

![](assets/fragment-list.png)

Alla fragment som skapades i den aktuella sandlådan - antingen [från **[!UICONTROL Fragments]** meny](#create-fragments), antingen med [Spara som fragment](#save-as-fragment) -alternativ visas.

Du kan filtrera fragment på deras:

* Typ: **[!UICONTROL Visual]** eller **[!UICONTROL Expression]**
* Taggar
* Skapad eller ändrad den

Du kan välja att visa alla fragment eller bara de objekt som den aktuella användaren har skapat eller ändrat.

Du kan även visa **[!UICONTROL Archived]** fragment. [Läs mer](#archive-fragments)

![](assets/fragment-list-filters.png)

Från **[!UICONTROL More actions]** intill varje fragment kan du:

* Duplicera ett fragment.

* Använd **[!UICONTROL Explore references]** möjlighet att se resorna, kampanjerna eller mallarna där de används. [Läs mer](#explore-references)

* Arkivera ett fragment. [Läs mer](#archive-fragments)

* Redigera ett fragment [taggar](../start/search-filter-categorize.md#tags).

![](assets/fragment-list-more-actions.png)

## Redigera fragment {#edit-fragments}

Om du vill redigera ett fragment följer du stegen nedan.

1. Klicka på önskat objekt på **[!UICONTROL Fragments]** lista.
1. Från fragmentegenskaperna kan du [utforska referenser](#explore-references), [hantera åtkomsten](../administration/object-based-access.md)och uppdatera fragmentinformationen inklusive [taggar](../start/search-filter-categorize.md#tags).

   ![](../email/assets/fragment-edit-content.png)

1. Markera motsvarande knapp om du vill redigera innehåll på samma sätt som när du skapar ett fragment från början. [Läs mer](#create-from-scratch)

>[!NOTE]
>
>När du redigerar ett fragment sprids ändringarna automatiskt till allt innehåll som använder det fragmentet, utom innehåll som används i **[!UICONTROL Live]** resor eller kampanjer. Du kan också bryta arv från det ursprungliga fragmentet. Läs mer i [Lägg till visuella fragment i e-postmeddelanden](../email/use-visual-fragments.md#break-inheritance) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md#break-inheritance) -avsnitt.

## Utforska referenser {#explore-references}

Du kan visa en lista över de resor, kampanjer och innehållsmallar som för närvarande använder ett fragment.

Om du vill göra det väljer du **[!UICONTROL Explore references]** antingen från **[!UICONTROL More actions]** i fragmentlistan eller från skärmen för fragmentegenskaper.

![](assets/fragment-explore-references.png)

Välj en flik för att växla mellan resor, kampanjer, mallar och fragment. Du kan se deras status och klicka på ett namn som ska omdirigeras till motsvarande objekt där fragmentet refereras.

![](assets/fragment-usage-screen.png)

>[!NOTE]
>
>Om fragmentet används i en resa, kampanj eller mall som har en etikett som hindrar dig från att komma åt det, visas ett varningsmeddelande ovanför den valda fliken. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

## Arkivera fragment {#archive-fragments}

Du kan rensa fragmentlistan från objekt som inte längre är relevanta för ert varumärke.

Klicka på **[!UICONTROL More actions]** -knapp intill önskat fragment och markera **[!UICONTROL Archive]**. Den försvinner från fragmentlistan, vilket förhindrar att den används i framtida e-postmeddelanden eller mallar.

![](assets/fragment-list-archive.png)

>[!NOTE]
>
>Om du arkiverar ett fragment som används i ett innehåll, <!--it will remain in the email or template, but you won't be able to select it from the fragment list to edit it-->att innehållet inte påverkas.

Om du vill arkivera ett fragment, filtrera på **[!UICONTROL Archived]** objekt och markera **[!UICONTROL Unarchive]** från **[!UICONTROL More actions]** -menyn. Det är nu igen tillgängligt från fragmentlistan och kan användas i alla e-postmeddelanden och mallar.

![](assets/fragment-list-unarchive.png)
