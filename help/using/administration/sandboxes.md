---
title: Hantering av sandlådor
description: Lär dig hantera sandlådor
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
exl-id: null
feature: Kontrollgrupper
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 28%

---

# Hantering av sandlådor {#sandboxes}

## Använd sandlådor {#using-sandbox}

Med [!DNL Journey Optimizer] kan du partitionera instansen i separerade virtuella miljöer som kallas för sandlådor.
Sandlådor tilldelas via produktprofiler i Admin Console. [Lär dig hur du tilldelar sandlådor](permissions.md#create-product-profile).

[!DNL Journey Optimizer] speglar Adobe Experience Platform-sandlådor som har skapats för en viss organisation.
Sandlådorna i Adobe Experience Platform kan skapas eller återställas från din instans i Adobe Experience Platform. [Läs mer i användarhandboken](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html) för Sandbox.

Du hittar kontrollen för att välja sandlåda längst upp till vänster på skärmen. Klicka på den för närvarande aktiva sandlådan i väljaren för att växla från en sandlåda till en annan och välj sedan en annan sandlåda på rullgardinsmenyn.

## Tilldela sandlådor {#assign-sandboxes}

>[!IMPORTANT]
>
> Hantering av sandlådor kan bara utföras av en **[!UICONTROL Product]**- eller **[!UICONTROL System]**-administratör. Mer information finns i [Admin Console-dokumentationen](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html).

Du kan välja att tilldela olika sandlådor till körklara eller anpassade **[!UICONTROL Product profiles]**.

Så här tilldelar du sandlådor:

1. Välj **[!UICONTROL Adobe Experience Platform Apps]**-produkten på fliken **[!UICONTROL Products]** i [!DNL Admin Console].

1. Välj en **[!UICONTROL Product profile]**.  

   ![](../assets/sandbox_1.png)

1. Klicka på fliken **[!UICONTROL Permissions]**.  

1. Välj funktionen **[!UICONTROL Sandboxes]**.

   ![](../assets/sandbox_2.png)

1. Klicka på plusikonen (+) i **[!UICONTROL Available Permissions Items]** för att tilldela sandlådor till profilen. [Läs mer om sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html).

   ![](../assets/sandbox_3.png)

1. Om det behövs, under **[!UICONTROL Included Permission Items]**, klickar du på X-ikonen bredvid Ta bort sandlådeåtkomst till din **[!UICONTROL Product profile]**.

   ![](../assets/sandbox_4.png)

1. Klicka på **[!UICONTROL Save]**.

## Åtkomst till innehåll {#content-access}

Om du vill konfigurera innehållets tillgänglighet måste du tilldela en delad mapp till var och en av sandlådorna. Du kan skapa och konfigurera din delade mapp på fliken **[!UICONTROL Storage]** som visas i [!DNL Admin Console] för administratörer. Om du har åtkomst till [!DNL Admin Console] som systemadministratör kan du skapa delade mappar och lägga till delegater med olika åtkomstnivå till dina delade mappar.

![](../assets/do-not-localize/content_access.png)

Observera att om ditt innehåll ska kunna synkroniseras med rätt sandlåda måste du följa samma syntax som sandlådan, t.ex. om din sandlåda kallas för utveckling ska din delade mapp ha samma namn.

[Lär dig hur du hanterar delade mappar](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-adobe-storage.ug.html).
