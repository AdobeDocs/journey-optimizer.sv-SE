---
product: experience platform
solution: Experience Platform
title: Skapa en datauppsättning för att samla in händelser
description: Lär dig hur du skapar en datauppsättning för att samla in händelser
feature: Ranking, Decision Management, Datasets
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 96c1326f-be40-4738-8997-a67dc14872bb
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Skapa en datauppsättning för att samla in händelser {#create-dataset}

Om du vill samla in upplevelsehändelser måste du först skapa en datauppsättning där dessa händelser skickas.

Börja med att skapa schemat som ska användas i din datauppsättning:

1. Välj **[!UICONTROL Data Management]** på menyn **[!UICONTROL Schema]**.

1. Klicka på **[!UICONTROL Create schema]** i det övre högra hörnet, markera **[!UICONTROL Experience Event]** och klicka på **Nästa**.

   ![](../../offers/assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >Läs mer om XDM-scheman och fältgrupper i [översiktsdokumentationen för XDM-systemet](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

1. Ange ett namn och en beskrivning för ditt schema och klicka på **Slutför**.
   ![](../../offers/assets/ai-ranking-xdm-event-2.png)

1. Välj **[!UICONTROL Field groups]** i avsnittet **[!UICONTROL Add]** till vänster.

   ![](../../offers/assets/ai-ranking-fields-groups.png)

1. I fältet **[!UICONTROL Search]** skriver du &quot;Föreslå interaktion&quot;.

1. Markera fältgruppen **[!UICONTROL Experience Event - Proposition Interactions]** och klicka på **[!UICONTROL Add field groups]**.

   ![](../../offers/assets/ai-ranking-add-field-group.png)

   >[!CAUTION]
   >
   >Schemat som ska användas i datauppsättningen måste ha fältgruppen **[!UICONTROL Experience Event - Proposition Interactions]** associerad med den. Annars kan du inte använda den i AI-modellen.

1. Spara schemat.

>[!NOTE]
>
>Läs mer om att skapa scheman i [Grunderna för schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=sv-SE#understanding-schemas){target="_blank"}.

Du är nu redo att skapa en datauppsättning med det här schemat. Gör så här:

1. Välj **[!UICONTROL Data Management]** på menyn **[!UICONTROL Datasets]** och gå till fliken **[!UICONTROL Browse]**.

1. Klicka på **[!UICONTROL Create dataset]** och välj **[!UICONTROL Create dataset from schema]**.

   ![](../../offers/assets/ai-ranking-create-dataset-from-schema.png)

1. Välj det schema som du just skapade från listan och klicka på **[!UICONTROL Next]**.

1. Ange ett unikt namn för datauppsättningen i fältet **[!UICONTROL Name]** och klicka på **[!UICONTROL Finish]**.

   ![](../../offers/assets/ai-ranking-dataset-name.png)

>[!NOTE]
>
>Den här datauppsättningen kan nu väljas för att samla in händelsedata när en [AI-modell](../ranking/create-ai-models.md) skapas.
