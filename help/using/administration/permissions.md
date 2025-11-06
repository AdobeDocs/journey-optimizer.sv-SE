---
solution: Journey Optimizer
product: journey optimizer
title: Hantera användare och roller
description: Lär dig hantera användare och roller
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
keywords: produkt, profiler, sandlåda
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 3%

---

# Hantera användare och roller {#manage-permissions}

**[!UICONTROL Roles]** refererar till en samling användare som delar samma behörigheter och sandlådor. Med de här rollerna kan du enkelt hantera åtkomst och behörigheter för olika användargrupper i organisationen.

Med [!DNL Journey Optimizer]-produkten kan du välja mellan ett intervall av befintliga **[!UICONTROL Roles]**, var och en med olika behörighetsnivåer, som du kan tilldela användarna. Mer information om tillgängliga **[!UICONTROL Roles]** finns på den här [sidan](ootb-product-profiles.md).

När en användare tillhör en **[!UICONTROL Role]** får de tillgång till de Adobe-program och -tjänster som ingår i produkten.

Om de befintliga rollerna inte uppfyller organisationens specifika behov kan du även skapa anpassade **[!UICONTROL Roles]** för att finjustera åtkomsten till vissa funktioner eller objekt i gränssnittet. På så sätt ser du till att alla användare bara har tillgång till de resurser och verktyg de behöver för att kunna utföra sina uppgifter på ett effektivt sätt.


>[!IMPORTANT]
>
>Steg och procedurer som beskrivs nedan kan bara utföras av en **[!UICONTROL Product]**- eller **[!UICONTROL System]**-administratör.


## Tilldela en roll {#assigning-role}

Du kan tilldela dina användare en användbar eller anpassad **[!UICONTROL Role]**.

Listan över alla användningsklara roller med tilldelade behörigheter finns i avsnittet [Inbyggda roller](ootb-product-profiles.md).

Så här tilldelar du en **[!UICONTROL Role]**:

1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer önskad roll.

   ![](assets/do-not-localize/access_control_2.png)

1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

   ![](assets/do-not-localize/access_control_3.png)

1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

   Om användaren inte redan har skapats i [!DNL Admin Console] kan du läsa [dokumentationen om att lägga till användare](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/users.html){target="_blank"}.

   ![](assets/do-not-localize/access_control_4.png)

Användaren får ett e-postmeddelande som dirigerar om dem till din instans.

Mer information om användarhantering finns i [Åtkomstkontrollsdokumentationen](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html){target="_blank"}.

När du får åtkomst till instansen ser din användare en specifik vy beroende på de tilldelade behörigheterna i **[!UICONTROL Role]**. Om användaren inte har rätt åtkomst till en funktion visas följande meddelande:

`You do not have permission to access this feature. Permission needed: XX.`

## Redigera en befintlig roll {#edit-product-profile}

För inbyggda eller anpassade **[!UICONTROL Roles]** kan du när som helst bestämma om du vill lägga till eller ta bort behörigheter.

I exemplet nedan vill vi lägga till **[!UICONTROL Permissions]** som är relaterad till resursen **[!UICONTROL Journeys]** för användare som är tilldelade till visningsprogrammet **[!UICONTROL Role]**. Användarna kan sedan publicera resor.

>[!IMPORTANT]
>
>Ändringar som görs i en inbyggd eller anpassad roll påverkar alla användare som tilldelats den rollen.

1. Om du vill redigera en roll i produkten [!DNL Permissions] går du till fliken **[!UICONTROL Roles]** och väljer önskad roll här i resevisningsprogrammet **[!UICONTROL Role]**.
   ![](assets/do-not-localize/access_control_5.png)

1. Klicka på **[!UICONTROL Role]** på din **[!UICONTROL Edit]**-instrumentpanel.

   ![](assets/do-not-localize/access_control_6.png)

1. Menyn **[!UICONTROL Resources]** visar en lista med resurser som gäller för produkten **[!UICONTROL Experience Cloud - Platform powered applications]**. Dra och släpp resurser för att tilldela behörigheter.

   I resurslistrutan **[!UICONTROL Journeys]** väljer vi här Publiceringsresa **[!UICONTROL Permission]**.

   ![](assets/do-not-localize/access_control_14.png)

1. Klicka vid behov på X-ikonen under **[!UICONTROL Included Permission Items]** för att ta bort behörigheter eller resurser från din roll.

1. Klicka på **[!UICONTROL Save]** när du är klar.

Om det behövs kan du även skapa en ny roll med specifika behörigheter.

## Skapa en ny roll {#create-product-profile}

Med [!DNL Journey Optimizer] kan du skapa egna **[!UICONTROL Roles]** och tilldela en uppsättning behörigheter och sandlådor till dina användare. Med **[!UICONTROL Roles]** kan du auktorisera eller neka åtkomst till vissa funktioner eller objekt i gränssnittet.

Se [dokumentationen om Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html){target="_blank"} för mer information om hur du skapar och hanterar sandlådor.

I det här exemplet skapar vi en roll med namnet **Journeys skrivskyddad**, där vi ger skrivskyddad behörighet till resefunktionen. Användare kommer endast att kunna komma åt och visa resor och kommer inte att kunna komma åt andra funktioner som **[!DNL Decision management]** i [!DNL Journey Optimizer].

Så här skapar du våra **resor med skrivskydd** **[!UICONTROL Role]**:

1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och klickar på **[!UICONTROL Create role]**.

   ![](assets/do-not-localize/access_control_9.png)

1. Lägg till en **[!UICONTROL Name]** och **[!UICONTROL Description]** för din nya **[!UICONTROL Role]**. Klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/do-not-localize/access_control_10.png)

1. Välj vilka sandlådor som ska tilldelas **[!UICONTROL Sandbox]** i den nedrullningsbara listan **[!UICONTROL Role]**-resurser. [Läs mer om sandlådor](sandboxes.md).

   ![](assets/do-not-localize/access_control_13.png)

1. Välj bland de olika resurser som **[!DNL Journeys]**, **[!DNL Segments]** eller **[!DNL Decision management]** som finns i [!DNL Journey Optimizer] i listan till vänster.

   Här väljer vi resursen **[!UICONTROL Journeys]**.

   ![](assets/do-not-localize/access_control_11.png)

1. I listrutan **[!UICONTROL Journeys]** väljer du de behörigheter du vill tilldela din **[!UICONTROL Role]**.

   Här väljer vi **[!DNL View journeys]**, **[!DNL View journeys report]** och **[!DNL View journeys event, data sources, actions]**.

   ![](assets/do-not-localize/access_control_12.png)

1. Klicka på **[!UICONTROL Save]** när du är klar.

**[!UICONTROL Role]** har skapats och konfigurerats. Du måste nu tilldela den till användare.

Mer information om att skapa och hantera roller finns i [Adobe Admin Console-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/roles.html){target="_blank"}.
