---
solution: Journey Optimizer
product: journey optimizer
title: Översikt över användarhantering
description: Lär dig definiera och hantera behörigheter
feature: Access Management
topic: Administration
role: Admin, Developer
level: Intermediate
keywords: behörigheter, rättigheter, begränsningar, åtkomst, sandlåda
exl-id: b8e266b1-d8eb-4c77-9341-9761b82609b0
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Kom igång med åtkomstkontroll {#permissions-overview}

Med [!DNL Journey Optimizer] kan du definiera och hantera behörigheter som tilldelats olika användare. Behörigheter är en uppsättning rättigheter och begränsningar som ger eller nekar åtkomst till funktioner och funktioner i produkten.

Åtkomstkontroll för [!DNL Journey Optimizer] tillhandahålls via **Behörigheter** i Adobe Experience Cloud. Den här funktionen utnyttjar roller och principer som länkar användare med behörigheter och sandlådor.

Om du vill konfigurera åtkomstkontroll för Journey Optimizer måste du ha system- eller produktadministratörsbehörighet för din organisation. Minimirollen som kan bevilja eller återkalla behörigheter är en produktadministratör. Andra administratörsroller som kan hantera behörigheter är systemadministratörer (inga begränsningar). Mer information finns i [Adobe Help Center-artikeln](https://helpx.adobe.com/enterprise/using/admin-roles.html){target="_blank"} om administrativa roller.

<!-- A high-level workflow for gaining and assigning access permissions can be summarized as follows:

* After licensing [!DNL Journey Optimizer], an email is sent to the administrator specified during licensing.
* The administrator logs in to Adobe Admin Console and selects [!DNL Journey Optimizer] from the list of products on the overview page.
* To grant access to [!DNL Journey Optimizer], it is recommended that the administrator add users to the default product profile
* In Experience Platform Permissions, the administrator can create new roles or edit the permissions and users for any existing roles.
* When creating or editing a role, the administrator adds users to the role using the users tab, and grants permissions to these users (such as "Read Datasets" or "Manage Schemas") by editing the role's permissions. Similarly, the administrator can assign access to sandboxes using the same editing option.
* When users log in to the Journey Optimizer user interface, their access to capabilities is driven by the permissions that have been granted to them from the previous step. For example, if a user does not have the View Datasets permission, the Datasets tab in the side menu will not be visible to that user.-->


Användarhantering i [!DNL Journey Optimizer] baseras på följande nyckelbegrepp:

* **[!UICONTROL Roles]**: Roller refererar till en samling användare som delar samma behörigheter och sandlådor. Med de här rollerna kan du enkelt hantera åtkomst och behörigheter för olika användargrupper i organisationen. En roll har en uppsättning enhetsbehörigheter (behörigheter) som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet.
Med [!DNL Journey Optimizer] kan du välja mellan ett intervall av befintliga **[!UICONTROL Roles]**, var och en med olika behörighetsnivåer, som ska tilldelas dina användare. Läs mer om de tillgängliga **inbyggda rollerna** på [den här sidan](ootb-product-profiles.md).

* **[!UICONTROL Permissions]**: Behörigheter är enhetsbehörigheter som gör att du kan definiera de behörigheter som tilldelats **[!UICONTROL Roles]**. Varje behörighet samlas under resurser, t.ex. Resor eller Erbjudanden, som representerar olika funktioner eller objekt i [!DNL Journey Optimizer]. Läs mer i avsnittet [Behörighetsnivåer](high-low-permissions.md).

  ![](assets/do-not-localize/permissions_2.png)

* **[!UICONTROL Sandboxes]**: Virtuella sandlådor, partitionsinstanser till separata, isolerade virtuella miljöer. Sandlådor tilldelas via roller i behörigheter. Läs mer om [att använda sandlådor](sandboxes.md).

* **Objektbaserad åtkomstkontroll**: Etiketter som begränsar åtkomsten till ett objekt. Detta tillvägagångssätt skyddar känsliga digitala resurser från obehöriga användare och säkerställer ytterligare skydd av personuppgifter. Läs mer om [Objektbaserad åtkomsthantering](object-based-access.md).

* **Attributbaserad åtkomstkontroll**: Behörigheter att hantera dataåtkomst för specifika team eller användargrupper. Attributbaserad åtkomstkontroll gör att administratörer kan styra åtkomsten till specifika objekt och/eller funktioner baserat på attribut. Attribut kan läggas till i ett objekt, t.ex. en etikett som lagts till i ett schemafält eller segment. En administratör definierar åtkomstprinciper som innehåller attribut för att hantera behörigheter för användaråtkomst. Läs mer om [Attributbaserad åtkomsthantering](attribute-based-access.md).


## Låt oss dyka djupare

Nu när du har en förståelse för åtkomstkontrollsbegrepp i **[!DNL Journey Optimizer]** är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja konfigurera behörigheter.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="permissions.md">
<img alt="Behörigheter" src="assets/do-not-localize/role.jpg">
</a>
<div>
<a href="permissions.md"><strong>Bevilja åtkomst</strong></a>
</div>
<p>
</td>
<td>
<a href="ootb-permissions.md">
<img alt="Inbyggda behörigheter" src="assets/do-not-localize/select.jpg">
</a>
<div>
<a href="ootb-permissions.md"><strong>Inbyggda behörigheter</strong></a>
</div>
<p>
</td>
<td>
<a href="sandboxes.md">
<img alt="hantera sandlådor" src="assets/do-not-localize/sandboxes.jpg">
</a>
<div>
<a href="sandboxes.md"><strong>Hantera sandlådor</strong></a>
</div>
<p></td>
<td>
<a href="attribute-based-access.md">
<img alt="Attributbaserad åtkomstkontroll" src="assets/do-not-localize/data-access.jpeg">
</a>
<div>
<a href="attribute-based-access.md"><strong>Attributbaserad åtkomstkontroll</strong></a>
</div>
<p>
</td>
</tr></table>