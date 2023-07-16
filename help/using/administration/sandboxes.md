---
solution: Journey Optimizer
product: journey optimizer
title: Hantering av sandlådor
description: Lär dig hantera sandlådor
feature: Sandboxes
topic: Administration
role: Admin, Architect, Developer
level: Experienced
keywords: sandlådor, virtuella, miljöer, organisation, plattform
exl-id: 14f80d5d-0840-4b79-9922-6d557a7e1247
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 15%

---

# Hantering av sandlådor {#sandboxes}

## Använda sandlådor {#using-sandbox}

Med [!DNL Journey Optimizer] kan du partitionera instansen i separerade virtuella miljöer som kallas för sandlådor.
Sandlådor tilldelas via roller i Behörigheter. [Lär dig hur du tilldelar sandlådor](permissions.md#create-product-profile).

[!DNL Journey Optimizer] speglar Adobe Experience Platform-sandlådor som har skapats för en viss organisation.
Sandlådorna i Adobe Experience Platform kan skapas eller återställas från din instans i Adobe Experience Platform. [Läs mer i användarhandboken för Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html){target="_blank"}.

Du hittar kontrollen för sandlådeväljaren högst upp till höger på skärmen bredvid organisationens namn. Klicka på den för närvarande aktiva sandlådan i väljaren för att växla från en sandlåda till en annan och välj sedan en annan sandlåda på rullgardinsmenyn.

![](assets/sandbox_5.png)

➡️ [Läs mer om sandlådor i den här videon](#video)

## Tilldela sandlådor {#assign-sandboxes}

>[!IMPORTANT]
>
> Hantering av sandlådor kan endast utföras av en **[!UICONTROL Product]** eller **[!UICONTROL System]** administratör. Mer information finns i [Dokumentation till Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html){target="_blank"}.

Du kan välja att tilldela olika sandlådor till färdiga eller anpassade **[!UICONTROL Roles]**.

Så här tilldelar du sandlådor:

1. I [!DNL Permissions], från **[!UICONTROL Roles]** -flik, välja en **[!UICONTROL Role]**.

   ![](assets/sandbox_1.png)

1. Klicka på **[!UICONTROL Edit]**.

1. Från **[!UICONTROL Sandboxes]** i den nedrullningsbara resurslistan väljer du den sandlåda som ska tilldelas din roll.

   ![](assets/sandbox_3.png)

1. Om det behövs klickar du på X-ikonen bredvid för att ta bort sandlådeåtkomst till **[!UICONTROL Role]**.

   ![](assets/sandbox_4.png)

1. Klicka på **[!UICONTROL Save]**.

## Åtkomst till innehåll {#content-access}

Om du vill konfigurera innehållets tillgänglighet måste du tilldela en delad mapp till var och en av sandlådorna. Du kan skapa och konfigurera din delade mapp i **[!UICONTROL Storage]** som visas i [!DNL Admin Console] för administratörer. Om du har åtkomst till [!DNL Admin Console] Som systemadministratör kan du skapa delade mappar och lägga till delegater med olika åtkomstnivå till dina delade mappar.

![](assets/do-not-localize/content_access.png)

Observera att om ditt innehåll ska kunna synkroniseras med rätt sandlåda måste du följa samma syntax som sandlådan, t.ex. om din sandlåda kallas för utveckling ska din delade mapp ha samma namn.

[Lär dig hantera delade mappar](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-adobe-storage.ug.html){target="_blank"}.

## Instruktionsvideo{#video}

Förstå vad sandlådor är och hur du skiljer mellan utvecklings- och produktionssandlådor. Lär dig hur du skapar, återställer och tar bort sandlådor.

>[!VIDEO](https://video.tv.adobe.com/v/334355?quality=12)