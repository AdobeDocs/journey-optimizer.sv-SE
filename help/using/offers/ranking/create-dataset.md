---
product: experience platform
solution: Experience Platform
title: Skapa en datauppsättning för att samla in händelser
description: Lär dig hur du skapar en datauppsättning för att samla in händelser
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 99963ef4-0b19-475e-96f4-2eac3f680c6f
source-git-commit: 5abcef4ff057bb351abaafbf4dcb99e1ab61c6a9
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 7%

---

# Skapa en datauppsättning för att samla in händelser {#create-dataset}

Innan du skapar en AI-modell måste du skapa en datauppsättning där konverteringshändelser samlas in. Börja med att skapa schemat som ska användas i din datauppsättning:

1. Från **[!UICONTROL Data Management]** meny, välja **[!UICONTROL Schema]**, går till **[!UICONTROL Browse]** och klicka **[!UICONTROL Create schema]**.

   ![](../assets/ai-ranking-create-schema.png)

1. Välj **[!UICONTROL XDM ExperienceEvent]**.

   ![](../assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >Läs mer om XDM-scheman och fältgrupper i [Översikt över XDM-systemet - dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

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
>Läs mer om scheman i [Grunderna för schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#understanding-schemas){target=&quot;_blank&quot;}.

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

Datamängden är nu klar att väljas för att samla in händelsedata när [skapa en rankningsstrategi](#create-ranking-strategy).
