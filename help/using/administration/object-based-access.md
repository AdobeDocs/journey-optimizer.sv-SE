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
source-git-commit: 3cbda018a1380e13ba3670563240238367517353
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Åtkomstkontroll på objektnivå {#object-level-access}

>[!CONTEXTUALHELP]
>id="ajo_olac_manage_access"
>title="Åtkomsthanteringsetiketter"
>abstract="Du kan begränsa åtkomsten till ett objekt baserat på åtkomstetiketter. Syftet är att skydda känsliga digitala resurser mot obehöriga användare, vilket ger ytterligare skydd för personuppgifter. **Se till att endast markera etiketter som du har behörighet för.**"

Du kan begränsa åtkomsten till ett objekt baserat på åtkomstetiketter. Syftet är att skydda känsliga digitala resurser mot obehöriga användare, vilket ger ytterligare skydd för personuppgifter.

Med OLAC-funktionen (Object level access control) kan du definiera behörigheter för att hantera dataåtkomst till ett urval av objekt:

* Resa
* Campaign
* Mall
* Fragment
* Landningssida
* Erbjudande
* Statisk insamling av erbjudanden
* Beslut om erbjudandet
* Kanalkonfiguration
* IP-värmerapport


## Förhandskrav {#prereq-labels}

Om du vill kunna [skapa etiketter](#create-labels) måste du vara en del av en roll med behörigheten **[!UICONTROL Manage usage labels]**.

Om du vill kunna [tilldela etiketter](#assign-labels) måste du vara en del av en roll med behörigheten **Hantera**, dvs. [!DNL Manage journeys], [!DNL Manage Campaigns] eller [!DNL Manage decisions]. Utan den här behörigheten är knappen **[!UICONTROL Manage access]** nedtonad.

Läs mer om behörigheter i [det här avsnittet](../administration/permissions.md).

## Skapa etiketter {#create-labels}

Med **[!UICONTROL Labels]** kan du kategorisera datauppsättningar och fält enligt användarprofiler som gäller för dessa data. **[!UICONTROL Labels]** kan användas när som helst, vilket ger flexibilitet i hur du väljer att styra data.

Använd etiketter för att ge åtkomst till användare samt för att tillämpa regler för datastyrning och samtycke. Dessa styrningsetiketter kan påverka förbrukningen i efterföljande led.

Du kan skapa etiketter i produkten [!DNL Permissions]. Mer information finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/labels.html?lang=sv-SE){target="_blank"}.

Du kan också skapa **[!UICONTROL Labels]** direkt i Journey Optimizer. Så här skapar du en etikett:

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

Så här tilldelar du anpassade eller grundläggande dataanvändningsetiketter till dina Journey Optimizer-objekt:

1. Klicka på knappen **[!UICONTROL Manage access]** från ett Adobe Journey Optimizer-objekt, här en nyskapad **[!UICONTROL Campaign]**.

   ![](assets/olac_1.png)

1. I fönstret **[!UICONTROL Manage access]** väljer du egna etiketter eller etiketter för kärndataanvändning för att hantera åtkomst till det här objektet.

   Mer information om etiketter för användning av kärndata finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=sv-SE){target="_blank"}.

   ![](assets/olac_4.png)

1. Klicka på **[!UICONTROL Save]** om du vill använda den här etikettbegränsningen.

Om du vill ha åtkomst till det här objektet måste användarna ha det specifika **[!UICONTROL Label]** inkluderat i sina **[!UICONTROL Roles]**.
En användare med etiketten C1 har till exempel bara åtkomst till objekt som är märkta eller omärkta med C1.

Mer information om hur du tilldelar **[!UICONTROL Label]** till en **[!UICONTROL Role]** finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/permissions.html?lang=sv-SE#manage-labels-for-a-role){target="_blank"}.