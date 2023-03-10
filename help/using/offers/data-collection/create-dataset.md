---
product: experience platform
solution: Experience Platform
title: Skapa en datauppsättning för att samla in händelser
description: Lär dig hur du skapar en datauppsättning för att samla in händelser
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 99963ef4-0b19-475e-96f4-2eac3f680c6f
source-git-commit: b06b545d377fcd1ffe6ed218badeb94c1bb85ef2
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Skapa en datauppsättning för att samla in händelser {#create-dataset}

Om du vill samla in upplevelsehändelser måste du först skapa en datauppsättning där dessa händelser skickas.

Börja med att skapa schemat som ska användas i din datauppsättning:

1. Från **[!UICONTROL Data Management]** meny, välja **[!UICONTROL Schema]**, går till **[!UICONTROL Browse]** och klicka **[!UICONTROL Create schema]**.

   ![](../assets/ai-ranking-create-schema.png)

1. Välj **[!UICONTROL XDM ExperienceEvent]**.

   ![](../assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >Läs mer om XDM-scheman och fältgrupper i [Översikt över XDM-systemet - dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

1. Från **[!UICONTROL Field groups]** till vänster väljer du **[!UICONTROL Add]**.

   ![](../assets/ai-ranking-fields-groups.png)

1. I **[!UICONTROL Search]** -fält, skriv&quot;interaktion för förslag&quot; och välj **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp.

   ![](../assets/ai-ranking-proposition-interactions.png)

   >[!CAUTION]
   >
   >Schemat som ska användas i datauppsättningen måste ha **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp som är associerad med den. Annars kan du inte använda den i din rankningsstrategi.

1. Klicka på **[!UICONTROL Add field groups]**.

   ![](../assets/ai-ranking-add-field-group.png)

   >[!NOTE]
   >Fältgruppen kallades tidigare för mixin.

1. Skriv ett namn och spara schemat.

>[!NOTE]
>
>Läs mer om scheman i [Grunderna för schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#understanding-schemas){target="_blank"}.

Du är nu redo att skapa en datauppsättning med det här schemat. Följ stegen nedan för att göra detta:

1. Från **[!UICONTROL Data Management]** meny, välja **[!UICONTROL Datasets]**, går till **[!UICONTROL Browse]** och klicka **[!UICONTROL Create dataset]**.

   ![](../assets/ai-ranking-create-dataset.png)

1. Välj **[!UICONTROL Create dataset from schema]**.

   ![](../assets/ai-ranking-create-dataset-from-schema.png)

1. Välj det schema du just skapade från listan.

   ![](../assets/ai-ranking-dataset-select-schema.png)

1. Klicka på **[!UICONTROL Next]**.

1. Ange ett unikt namn för datauppsättningen i **[!UICONTROL Name]** fält och klicka **[!UICONTROL Finish]**.

   ![](../assets/ai-ranking-dataset-name.png)

>[!NOTE]
>
>Den här datauppsättningen kan nu väljas för att samla in händelsedata när [skapa en rankningsstrategi](#create-ranking-strategy).
