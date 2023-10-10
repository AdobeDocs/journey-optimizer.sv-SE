---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med fragment
description: Lär dig hur du skapar fragment som kan återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 7131a953-baca-4e7c-a8df-97c0bd6ac567
source-git-commit: b00a4e174e978121687428147b5b3861077c5182
workflow-type: tm+mt
source-wordcount: '1481'
ht-degree: 2%

---

# Arbeta med fragment {#fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_fragment"
>title="Definiera egna fragment"
>abstract="Skapa och hantera fristående fragment för att göra innehållet återanvändbart på flera resor och i flera kampanjer."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/personalized-dynamic-content/reusable-content/fragments.html#create-fragments" text="Skapa fragment"

Ett fragment är en återanvändbar komponent som kan refereras i en eller flera e-postmeddelanden som [!DNL Journey Optimizer] kampanjer och resor.

Med den här funktionen kan man skapa flera anpassade innehållsblock som kan användas av marknadsföringsanvändare för att snabbt sammanställa e-postinnehåll i en förbättrad designprocess.

![](../rn/assets/do-not-localize/fragments.gif)

➡️ [Lär dig hur du hanterar, redigerar och använder fragment i dessa videofilmer](#video-fragments)

Så här använder du fragment på bästa sätt:

* Skapa egna fragment. Du kan skapa visuella fragment eller uttrycksfragment. [Läs mer](#create-fragments)

* Använd dem så många gånger som behövs i ert innehåll. Se [Lägg till visuella fragment](../email/use-visual-fragments.md) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md)

## Före start {#fragment-prerequisites}

Om du vill skapa, redigera och arkivera fragment måste du ha **[!DNL Manage Library Items]** behörighet som ingår i **[!DNL Content Library Manager]** produktprofil. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)

I den här versionen gäller följande begränsningar:

* Visuella fragment är bara tillgängliga för e-postkanalen

* Uttrycksfragment är inte tillgängliga för webben och appkanaler

## Få åtkomst till och hantera fragment {#access-manage-fragments}

Om du vill komma åt fragmentlistan väljer du **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** från den vänstra menyn.

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

* Kopiera ett fragment till en annan sandlåda. <!--Learn more?-->

* Arkivera ett fragment. [Läs mer](#archive-fragments)

* Redigera ett fragment [taggar](../start/search-filter-categorize.md#tags).

![](assets/fragment-list-more-actions.png)

### Redigera fragment {#edit-fragments}

Om du vill redigera ett fragment följer du stegen nedan.

1. Klicka på önskat objekt på **[!UICONTROL Fragments]** lista.
1. Från fragmentegenskaperna kan du [utforska referenser](#explore-references), [hantera åtkomsten](../administration/object-based-access.md)och uppdatera fragmentinformationen inklusive [taggar](../start/search-filter-categorize.md#tags).

   ![](../email/assets/fragment-edit-content.png)

1. Markera motsvarande knapp om du vill redigera innehåll på samma sätt som när du skapar ett fragment från början. [Läs mer](#create-from-scratch)

>[!NOTE]
>
>När du redigerar ett fragment sprids ändringarna automatiskt till allt innehåll som använder det fragmentet, utom innehåll som används i **[!UICONTROL Live]** resor eller kampanjer. Du kan också bryta arv från det ursprungliga fragmentet. Läs mer i [Lägg till visuella fragment i e-postmeddelanden](../email/use-visual-fragments.md#break-inheritance) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md#break-inheritance) -avsnitt.

### Utforska referenser {#explore-references}

Du kan visa en lista över de resor, kampanjer och innehållsmallar som för närvarande använder ett fragment.

Om du vill göra det väljer du **[!UICONTROL Explore references]** antingen från **[!UICONTROL More actions]** i fragmentlistan eller från skärmen för fragmentegenskaper.

![](assets/fragment-explore-references.png)

Välj en flik för att växla mellan resor, kampanjer, mallar och fragment. Du kan se deras status och klicka på ett namn som ska omdirigeras till motsvarande objekt där fragmentet refereras.

![](assets/fragment-usage-screen.png)

>[!NOTE]
>
>Om fragmentet används i en resa, kampanj eller mall som har en etikett som hindrar dig från att komma åt det, visas ett varningsmeddelande ovanför den valda fliken. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

### Arkivera fragment {#archive-fragments}

Du kan rensa fragmentlistan från objekt som inte längre är relevanta för ert varumärke.

Klicka på **[!UICONTROL More actions]** -knapp intill önskat fragment och markera **[!UICONTROL Archive]**. Den försvinner från fragmentlistan, vilket förhindrar att den används i framtida e-postmeddelanden eller mallar.

![](assets/fragment-list-archive.png)

>[!NOTE]
>
>Om du arkiverar ett fragment som används i ett innehåll, <!--it will remain in the email or template, but you won't be able to select it from the fragment list to edit it-->att innehållet inte påverkas.

Om du vill arkivera ett fragment, filtrera på **[!UICONTROL Archived]** objekt och markera **[!UICONTROL Unarchive]** från **[!UICONTROL More actions]** -menyn. Det är nu igen tillgängligt från fragmentlistan och kan användas i alla e-postmeddelanden och mallar.

![](assets/fragment-list-unarchive.png)

## Skapa fragment {#create-fragments}

Det finns två sätt att skapa fragment:

* Skapa ett fragment från grunden med **[!UICONTROL Fragments]** egen meny. [Lär dig mer](#create-from-scratch)

* När du utformar innehåll sparar du en del av innehållet som fragment. [Lär dig mer](#save-as-fragment)

När fragmentet har sparats är det tillgängligt för användning under en resa, en kampanj eller en mall. Oavsett om du har skapat från grunden eller från ett befintligt innehåll kan du nu använda det här avsnittet när du skapar innehåll i [!DNL Journey Optimizer]. Se [Lägg till visuella fragment](../email/use-visual-fragments.md) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md)

### Skapa från grunden {#create-from-scratch}

Följ stegen nedan om du vill skapa ett fragment från grunden.

1. [Åtkomst till fragmentlistan](#access-manage-fragments) via **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny.

1. Välj **[!UICONTROL Create fragment]**.

1. Fyll i fragmentinformationen, dvs. namn och beskrivning (om det behövs).

   ![](assets/fragment-details.png)

1. Välj fragmenttyp: [Visual fragment](#create-visual-fragment) eller [Uttrycksfragment](#create-expression-fragment).

1. Om du vill tilldela egna eller grundläggande dataanvändningsetiketter till fragmentet väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Markera eller skapa Adobe Experience Platform-taggar från **[!UICONTROL Tags]** fält för att kategorisera fragmentet för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Klicka på **[!UICONTROL Create]**.

### Skapa ett Visual fragment {#create-visual-fragment}

>[!CONTEXTUALHELP]
>id="ajo_create_visual_fragment"
>title="Markera den visuella typen"
>abstract="Skapa ett fristående visuellt fragment för att göra innehållet återanvändbart i ett e-postmeddelande inom en resa eller kampanj, eller i en innehållsmall."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/email/design-email/add-content/use-visual-fragments.html" text="Lägg till visuella fragment i e-postmeddelanden"

1. [Skapa ett fragment](#create-from-scratch) från **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny och välj **[!UICONTROL Visual fragment]** typ.

   >[!NOTE]
   >
   >För närvarande endast för visuella fragment **E-post** kanalen stöds.

1. The [E-postdesigner](../email/get-started-email-design.md) visas. Redigera innehåll efter behov, på samma sätt som du gör för alla e-postmeddelanden som finns på en resa eller en kampanj.

   >[!NOTE]
   >
   >Du kan lägga till anpassningsfält och dynamiskt innehåll, men kontextuella attribut stöds inte i fragment.

   ![](assets/fragment-designer.png)

1. När fragmentet är klart klickar du **[!UICONTROL Save]**. Den läggs till i [fragmentlista](#access-manage-fragments).

1. Klicka vid behov på pilen bredvid fragmentnamnet för att gå tillbaka till **[!UICONTROL Details]** och redigera.

   ![](assets/fragment-designer-back.png)

Det här fragmentet är nu klart att användas när du skapar [e-post](../email/get-started-email-design.md) eller [innehållsmall](content-templates.md) inom [!DNL Journey Optimizer]. [Lär dig mer](../email/use-visual-fragments.md)

### Skapa ett uttryck {#create-expression-fragment}

>[!CONTEXTUALHELP]
>id="ajo_create_expression_fragment"
>title="Välj uttryckstyp"
>abstract="Skapa ett fristående uttrycksfragment som gör att innehållet kan återanvändas på flera resor och i flera kampanjer. När du använder uttrycksredigeraren kan du utnyttja alla uttrycksfragment som har skapats i den aktuella sandlådan."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/personalized-dynamic-content/personalization/expression-editor/use-expression-fragments.html" text="Utnyttja uttrycksfragment"

1. [Skapa ett fragment](#create-from-scratch) från **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]** vänster meny och välj **[!UICONTROL Expression fragment]** typ.

1. Välj den typ av kod som du vill använda: **[!UICONTROL HTML]**, **[!UICONTROL JSON]** eller **[!UICONTROL Text]**.

   ![](assets/fragment-expression-type.png)

   <!--Expression fragments can be used in any channel.-->

1. Klicka på **[!UICONTROL Create]**. Uttrycksredigeraren öppnas.

1. Du kan använda [!DNL Journey Optimizer] Uttrycksredigeraren med alla dess funktioner för personalisering och redigering. [Läs mer](../personalization/personalization-build-expressions.md)

   ![](assets/fragment-expression-editor.png)

1. När fragmentet är klart klickar du **[!UICONTROL Save]**. Den läggs till i [fragmentlista](#access-manage-fragments).

1. Klicka vid behov på pilen bredvid fragmentnamnet för att gå tillbaka till **[!UICONTROL Details]** och redigera.

Det här avsnittet är nu klart att användas när du skapar innehåll i [!DNL Journey Optimizer] Uttrycksredigerare. [Lär dig mer](../personalization/use-expression-fragments.md)

## Spara som fragment {#save-as-fragment}

När du redigerar innehåll i [!DNL Journey Optimizer]kan du spara hela eller delar av innehållet som fragment för framtida återanvändning.

### Spara som visuellt fragment {#save-as-visual-fragment}

När du utformar en [innehållsmall](content-templates.md) eller en [e-post](../email/get-started-email-design.md) i en kampanj eller en resa kan du spara en del av innehållet som ett visuellt fragment. Följ stegen nedan för att göra detta.

1. I [E-postdesigner](../email/get-started-email-design.md)klickar du på ellipsen högst upp till höger på skärmen.

1. Välj **[!UICONTROL Save as fragment]** i listrutan.

   ![](assets/fragment-save-as.png)

1. The **[!UICONTROL Save as fragment]** visas. Här väljer du de element som du vill inkludera i fragmentet, inklusive anpassningsfält och dynamiskt innehåll. Observera att kontextuella attribut inte stöds i fragment.

   >[!CAUTION]
   >
   >Du kan bara markera intilliggande avsnitt. Du kan inte markera en tom struktur eller ett annat fragment.

   ![](assets/fragment-save-as-screen.png)

1. Klicka på **[!UICONTROL Create]**. Fyll i fragmentinformationen, dvs. namn och beskrivning (om det behövs).

1. Om du vill tilldela egna eller grundläggande dataanvändningsetiketter till fragmentet väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Markera eller skapa Adobe Experience Platform-taggar från **Taggar** fält för att kategorisera mallen för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Klicka **[!UICONTROL Create]** igen. Fragmentet sparas i [fragmentlista](#access-manage-fragments), kan du nå från [!DNL Journey Optimizer] egen meny.

   Det blir ett fristående fragment som kan [använd](#access-manage-fragments), [redigerad](#edit-fragments) och [arkiverad](#archive-fragments) som alla andra objekt i den listan.

Du kan nu använda det här fragmentet när du skapar [e-post](../email/get-started-email-design.md) eller [innehållsmall](content-templates.md) inom [!DNL Journey Optimizer]. [Lär dig mer](../email/use-visual-fragments.md)

>[!NOTE]
>
>Ändringar i det nya fragmentet sprids inte till e-postmeddelandet eller mallen som det kommer från. På samma sätt ändras inte det nya fragmentet när det ursprungliga innehållet redigeras i e-postmeddelandet eller mallen.

### Spara som uttrycksfragment {#save-as-expression-fragment}

>[!CONTEXTUALHELP]
>id="ajo_perso_library"
>title="Spara som uttrycksfragment"
>abstract="The [!DNL Journey Optimizer] Med uttrycksredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll."

The [!DNL Journey Optimizer] Med uttrycksredigeraren kan du spara innehåll som uttrycksfragment. Uttrycken är sedan tillgängliga för att skapa personaliserat innehåll.

Följ stegen nedan om du vill spara innehåll som ett uttrycksfragment.

1. I [Uttrycksredigerare](../personalization/personalization-build-expressions.md) gränssnitt, skapa ett uttryck och klicka sedan på **[!UICONTROL Save as fragment]**.

1. I den högra rutan anger du ett namn och en beskrivning för uttrycket så att användarna enklare kan hitta det.

   ![](assets/expression-fragment-save-as.png)

1. Klicka på **[!UICONTROL Save fragment]**.

   <!--An expression fragment cannot be nested inside another fragment.-->

1. Uttrycksfragmentet läggs till i [fragmentlista](#access-manage-fragments). Nu kan ni använda den för att skapa personaliserat innehåll.

>[!NOTE]
>
>Uttryck får inte överskrida 200 kB.

## Instruktionsvideo {#video-fragments}

Lär dig hur du hanterar, redigerar och använder visuella fragment i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3419932/?quality=12)

Lär dig hur du hanterar, redigerar och använder uttrycksfragment i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3424587/?quality=12)
