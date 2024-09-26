---
solution: Journey Optimizer
product: journey optimizer
title: Hantera fragment
description: Lär dig hantera dina innehållsfragment
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 1fc708e1-a993-4a2a-809c-c5dc08a4bae1
source-git-commit: 62b5cfd480414c898ab6f123de8c6b9f99667b7d
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Hantera fragment {#manage-fragments}

Om du vill hantera dina fragment kan du komma åt fragmentlistan från den vänstra menyn **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]**.

Alla fragment som skapades i den aktuella sandlådan - antingen [ från **[!UICONTROL Fragments]**-menyn](#create-fragments), antingen med alternativet [Spara som fragment](#save-as-fragment) - visas.

![](assets/fragment-list-filters.png)

Du kan filtrera fragment på deras:

* Status (utkast eller Live)
* Typ (visuellt eller uttryck)
* Skapad eller ändrad den
* Delstat (arkiverad eller ej)
* Taggar

Du kan också välja att visa alla fragment eller bara de objekt som den aktuella användaren har skapat eller ändrat.

Från knappen **[!UICONTROL More actions]** bredvid varje fragment kan du:

* Duplicera ett fragment.
* Använd alternativet **[!UICONTROL Explore references]** om du vill visa de resor, kampanjer eller mallar där det används. [Läs mer](#explore-references)
* Arkivera ett fragment. [Läs mer](#archive-fragments)
* Redigera ett fragments taggar [Lär dig hur du arbetar med enhetliga taggar](../start/search-filter-categorize.md#tags).

![](assets/fragment-list-more-actions.png)

## Fragmentstatus

>[!CONTEXTUALHELP]
>id="ajo_fragment_statuses"
>title="Nya fragmentstatusar"
>abstract="Sedan statusvärdena **Utkast** och **Live** introducerades i Journey Optimizer Juniversion har alla fragment som skapats före den här versionen statusen Utkast, även om de används under en resa eller kampanj. Om du ändrar något i dessa fragment måste du publicera dem för att göra dem&quot;Live&quot; och sprida ändringarna till tillhörande kampanjer och resor. Ni måste också skapa en ny resa/kampanjversion och publicera den. <br/>Publicering kräver användarbehörighet för <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/access-control/privacy/ootb-product-profiles#content-library-manage">Publish Fragment</a>."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/access-control/privacy/ootb-product-profiles#content-library-manager" text="Läs mer om behörigheter för innehållsfragment"

Fragment kan ha flera statusar:

* **[!UICONTROL Draft]**: Fragmentet redigeras och har inte godkänts.

* **[!UICONTROL Live]**: Fragmentet har godkänts och är direktsänt. [Lär dig publicera ett fragment](../content-management/create-fragments.md#publish)

  När ett live-fragment redigeras visas en specifik ikon bredvid dess status. Klicka på den här ikonen för att öppna utkastet av fragmentet.

* **[!UICONTROL Publishing]**: Fragmentet har godkänts och publiceras.
* **[!UICONTROL Archived]**: Fragmentet har arkiverats. [Lär dig arkivera fragment](#archive-fragments)

>[!CAUTION]
>
>Sedan statusvärdena **Utkast** och **Live** introducerades i Journey Optimizer Juniversion har alla fragment som skapats före den här versionen statusen Utkast, även om de används under en resa eller kampanj. Om du ändrar något i dessa fragment måste du publicera dem för att göra dem&quot;Live&quot; och sprida ändringarna till tillhörande kampanjer och resor. Ni måste också skapa en ny resa/kampanjversion och publicera den. Publicering kräver användarbehörighet för [Publish Fragment](../administration/ootb-product-profiles.md#content-library-manager).

## Redigera fragment {#edit-fragments}

>[!CONTEXTUALHELP]
>id="ajo_fragments_update_campaigns"
>title="Fragment uppdateras i kampanjer"
>abstract="Den här kampanjen uppdateras inte om du publicerar ändringar i fragmentet. Den kräver att en ny version publiceras så att fragmentuppdateringsfunktionen kan användas."

>[!CONTEXTUALHELP]
>id="ajo_fragments_update_journeys"
>title="Fragmentuppdatering i resor"
>abstract="Den här resan uppdateras inte om du publicerar ändringar i fragmentet. Den kräver att en ny version publiceras så att fragmentuppdateringsfunktionen kan användas."

Om du vill redigera ett fragment följer du stegen nedan.

1. Klicka på önskat fragment i listan **[!UICONTROL Fragments]**.

1. Fragmentegenskaperna öppnas med en förhandsgranskning av innehållet.

1. Om fragmentet som redigeras har statusen **Live** klickar du på knappen **Ändra** för att skapa ett utkast av fragmentet. Den aktuella versionen av fragmentet fortsätter att vara aktiv tills du publicerar utkastet.

1. Gör önskade ändringar av fragmentet. Om du vill redigera innehållet klickar du på knappen **Redigera** och redigerar sedan innehållet på samma sätt som när du skapar ett fragment från grunden. [Lär dig skapa ett fragment](#create-from-scratch)

   >[!NOTE]
   >
   >När du redigerar ett uttrycksfragment kan du ta bort alla anpassningsfält, men inte lägga till nya i fragmentinnehållet. Om du vill lägga till anpassningsfält duplicerar du fragmentet för att skapa ett nytt.

   Du kan också kontrollera listan över resor, kampanjer och innehållsmallar där fragmentet används för närvarande genom att välja alternativet **Utforskaren-referenser**. [Läs mer](#explore-references)

   ![](assets/fragment-edit.png)

1. När ändringarna är klara klickar du på **Publish** för att göra ändringarna tillgängliga.

När du redigerar ett fragment sprids ändringarna automatiskt till allt innehåll som använder det fragmentet, inklusive direktresor och kampanjer, med undantag för innehåll där du har brutit arv från det ursprungliga fragmentet. Lär dig hur du bryter arv i avsnitten [Lägg till visuella fragment i e-postmeddelanden](../email/use-visual-fragments.md#break-inheritance) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md#break-inheritance).

## Utforska referenser {#explore-references}

Du kan visa en lista över de resor, kampanjer och innehållsmallar som för närvarande använder ett fragment. Om du vill göra det väljer du **[!UICONTROL Explore references]** antingen på menyn **[!UICONTROL More actions]** i fragmentlistan eller på skärmen för fragmentegenskaper.

![](assets/fragment-explore-references.png)

Välj en flik för att växla mellan resor, kampanjer, mallar och fragment. Du kan se deras status och klicka på ett namn som ska omdirigeras till motsvarande objekt där fragmentet refereras.

![](assets/fragment-usage-screen.png)

>[!NOTE]
>
>Om fragmentet används i en resa, kampanj eller mall som har en etikett som hindrar dig från att komma åt det, visas ett varningsmeddelande ovanför den valda fliken. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

## Arkivera fragment {#archive-fragments}

Du kan rensa fragmentlistan från objekt som inte längre är relevanta för ert varumärke.

Om du vill göra det klickar du på knappen **[!UICONTROL More actions]** bredvid det önskade fragmentet och väljer **[!UICONTROL Archive]**. Den försvinner från fragmentlistan, vilket förhindrar att den används i framtida e-postmeddelanden eller mallar.

![](assets/fragment-list-archive.png)

>[!NOTE]
>
>Om du arkiverar ett fragment som används i ett innehåll, <!--it will remain in the email or template, but you won't be able to select it from the fragment list to edit it--> påverkas inte innehållet.

Om du vill arkivera ett fragment, filtrerar du på **[!UICONTROL Archived]**-objekten och väljer **[!UICONTROL Unarchive]** på **[!UICONTROL More actions]**-menyn. Det är nu igen tillgängligt från fragmentlistan och kan användas i alla e-postmeddelanden och mallar.

![](assets/fragment-list-unarchive.png)

## Exportera fragment till en annan sandlåda {#export}

Med Journey Optimizer kan du kopiera ett fragment från en sandlåda till en annan. Du kan t.ex. kopiera ett fragment från sandlådemiljön på scenen till produktionssandlådan.

Kopieringsprocessen utförs via en **paketexport och import** mellan käll- och målsandlådorna. Detaljerad information om hur du exporterar objekt och importerar dem till en målsandlåda finns i det här avsnittet: [Kopiera objekt till en annan sandlåda](../configuration/copy-objects-to-sandbox.md)
