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
source-git-commit: a2a5c081ee9a8ab04bf4c7b97097c0121ef8e4f8
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 2%

---

# Åtkomstkontroll på objektnivå {#object-level-access}

>[!CONTEXTUALHELP]
>id="ajo_olac_manage_access"
>title="Åtkomstkontroll på objektnivå"
>abstract="Om du använder etiketter som du inte har åtkomst till kommer åtkomsten till objektet att återkallas."

>[!IMPORTANT]
>
>Åtkomstkontrollen på objektnivå är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.

Med åtkomstkontrollen på objektnivå (OLAC) kan du definiera behörigheter för att hantera dataåtkomst till ett urval av objekt:

* Resa
* Campaign
* Fragment
* Landningssida
* Erbjudanden
* Erbjudandesamling
* Offer decisioning
* Mall

Syftet är att skydda känsliga digitala resurser mot obehöriga användare, vilket ger ytterligare skydd för personuppgifter.

I Adobe Journey Optimizer kan du med OLAC skydda data och ge specifik åtkomst till specifika objekt.

## Skapa etiketter {#create-assign-labels}

>[!IMPORTANT]
>
>För att kunna skapa etiketter måste du vara en del av en roll med **[!UICONTROL Manage usage labels]** behörighet.

**[!UICONTROL Labels]** gör att du kan kategorisera datauppsättningar och fält enligt de användarprofiler som gäller för dessa data. **[!UICONTROL Labels]** kan tillämpas när som helst, vilket ger flexibilitet i hur du väljer att styra data.

Du kan skapa etiketter i [!DNL Permissions] produkt. Mer information finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/labels.html).

**[!UICONTROL Labels]** kan också skapas direkt i Journey Optimizer:

1. Här finns ett nyskapat objekt från Adobe Journey Optimizer **[!UICONTROL Campaign]** klickar du på **[!UICONTROL Manage access]** -knappen.

   ![](assets/olac_1.png)

1. Från **[!UICONTROL Manage access]** fönster, klicka **[!UICONTROL Create label]**.

   ![](assets/olac_2.png)

1. Konfigurera din etikett, du måste ange:
   * **[!UICONTROL Name]**
   * **[!UICONTROL Friendly name]**
   * **[!UICONTROL Description]**

   ![](assets/olac_3.png)

1. Klicka **[!UICONTROL Create]** för att spara **[!UICONTROL Label]**.

Ditt nyskapade **[!UICONTROL Label]** finns nu i listan. Om det behövs kan du ändra det i [!DNL Permissions] produkt.

## Tilldela etiketter {#assign-labels}

>[!IMPORTANT]
>
>För att kunna tilldela etiketter måste du vara en del av en roll med behörigheten Hantera, dvs. [!DNL Manage journeys], [!DNL Manage Campaigns] eller [!DNL Manage decisions]. Utan denna tillåtelse **[!UICONTROL Manage access]** knappen blir nedtonad.

Så här tilldelar du anpassade eller grundläggande dataanvändningsetiketter till dina Journey Optimizer-objekt:

1. Här finns ett nyskapat objekt från Adobe Journey Optimizer **[!UICONTROL Campaign]** klickar du på **[!UICONTROL Manage access]** -knappen.

   ![](assets/olac_1.png)

1. Från **[!UICONTROL Manage access]** väljer du egna eller grundläggande etiketter för dataanvändning för att hantera åtkomst till det här objektet.

   Mer information om etiketter för användning av kärndata finns i [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html).

   ![](assets/olac_4.png)

1. Klicka **[!UICONTROL Save]** om du vill tillämpa den här etikettbegränsningen.

För att få åtkomst till det här objektet måste användarna ha den specifika **[!UICONTROL Label]** ingår i **[!UICONTROL Roles]**.
En användare med etiketten C1 har till exempel bara åtkomst till objekt som är märkta eller omärkta med C1.

Mer information om hur du tilldelar **[!UICONTROL Label]** till **[!UICONTROL Role]**, se [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/permissions.html#manage-labels-for-a-role).
