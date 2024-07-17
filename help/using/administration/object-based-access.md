---
solution: Journey Optimizer
product: journey optimizer
title: Åtkomstkontroll på objektnivå
description: Lär dig mer om åtkomstkontroll på objektnivå som gör att du kan definiera behörigheter för att hantera dataåtkomst till ett urval objekt
feature: Access Management
topic: Administration
role: Admin, Developer, Architect
level: Experienced
keywords: objekt, nivå, åtkomst, kontroll, etiketter, plats, auktorisering
exl-id: 02ccdd95-426c-4b61-9834-7f2dcd5abdbb
source-git-commit: 342b9210f79266cb11628dcdc411f90844a84e37
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Åtkomstkontroll på objektnivå {#object-level-access}

>[!CONTEXTUALHELP]
>id="ajo_olac_manage_access"
>title="Åtkomstkontroll på objektnivå"
>abstract="Om du vill behålla åtkomsten till det här objektet använder du bara de etiketter som du har behörighet för."

Med åtkomstkontrollen på objektnivå (OLAC) kan du definiera behörigheter för att hantera dataåtkomst till ett urval av objekt:

* Resa
* Campaign
* Mall
* Fragment
* Landningssida
* Erbjudande
* Statisk insamling av erbjudanden
* Beslut om erbjudandet
* Kanalyta
* IP-värmerapport

Syftet är att skydda känsliga digitala resurser mot obehöriga användare, vilket ger ytterligare skydd för personuppgifter.

I Adobe Journey Optimizer kan du med OLAC skydda data och ge specifik åtkomst till specifika objekt.

## Skapa etiketter {#create-assign-labels}

>[!IMPORTANT]
>
>Om du vill kunna skapa etiketter måste du vara en del av en roll med behörigheten **[!UICONTROL Manage usage labels]**.

Med **[!UICONTROL Labels]** kan du kategorisera datauppsättningar och fält enligt användarprofiler som gäller för dessa data. **[!UICONTROL Labels]** kan användas när som helst, vilket ger flexibilitet i hur du väljer att styra data.

Du kan skapa etiketter i produkten [!DNL Permissions]. Mer information finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/labels.html).

**[!UICONTROL Labels]** kan också skapas direkt i Journey Optimizer:

1. Klicka på knappen **[!UICONTROL Manage access]** från ett Adobe Journey Optimizer-objekt, här en nyskapad **[!UICONTROL Campaign]**.

   ![](assets/olac_1.png)

1. Klicka på **[!UICONTROL Create label]** i fönstret **[!UICONTROL Manage access]**.

   ![](assets/olac_2.png)

1. Konfigurera din etikett, du måste ange:
   * **[!UICONTROL Name]**
   * **[!UICONTROL Friendly name]**
   * **[!UICONTROL Description]**

   ![](assets/olac_3.png)

1. Klicka på **[!UICONTROL Create]** om du vill spara **[!UICONTROL Label]**.

Din nyskapade **[!UICONTROL Label]** är nu tillgänglig i listan. Om det behövs kan du ändra det i [!DNL Permissions]-produkten.

## Tilldela etiketter {#assign-labels}

>[!IMPORTANT]
>
>Om du vill kunna tilldela etiketter måste du vara en del av en roll med behörigheten Hantera, dvs. [!DNL Manage journeys], [!DNL Manage Campaigns] eller [!DNL Manage decisions]. Utan den här behörigheten kommer knappen **[!UICONTROL Manage access]** att vara nedtonad.

Så här tilldelar du anpassade eller grundläggande dataanvändningsetiketter till dina Journey Optimizer-objekt:

1. Klicka på knappen **[!UICONTROL Manage access]** från ett Adobe Journey Optimizer-objekt, här en nyskapad **[!UICONTROL Campaign]**.

   ![](assets/olac_1.png)

1. I fönstret **[!UICONTROL Manage access]** väljer du egna etiketter eller etiketter för kärndataanvändning för att hantera åtkomst till det här objektet.

   Mer information om etiketter för användning av kärndata finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html).

   ![](assets/olac_4.png)

1. Klicka på **[!UICONTROL Save]** om du vill använda den här etikettbegränsningen.

Om du vill ha åtkomst till det här objektet måste användarna ha det specifika **[!UICONTROL Label]** inkluderat i sina **[!UICONTROL Roles]**.
En användare med etiketten C1 har till exempel bara åtkomst till objekt som är märkta eller omärkta med C1.

Mer information om hur du tilldelar **[!UICONTROL Label]** till en **[!UICONTROL Role]** finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/permissions.html#manage-labels-for-a-role).