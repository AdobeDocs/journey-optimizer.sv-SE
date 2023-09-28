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
source-git-commit: be372f8f80d304067748d539fb8e210df6280721
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 2%

---

# Hantera användare och roller {#manage-permissions}

>[!IMPORTANT]
>
> Var och en av de procedurer som beskrivs nedan kan endast utföras av en **[!UICONTROL Product]** eller **[!UICONTROL System]** administratör.

**[!UICONTROL Roles]** refererar till en samling användare som delar samma behörigheter och sandlådor. Med de här rollerna kan du enkelt hantera åtkomst och behörigheter för olika användargrupper i organisationen.

Med [!DNL Journey Optimizer] kan du välja mellan ett antal befintliga **[!UICONTROL Roles]**, vart och ett med olika behörighetsnivåer, att tilldela användarna. Mer information finns på **[!UICONTROL Roles]**, se det här [page](ootb-product-profiles.md).

När en användare tillhör en **[!UICONTROL Role]** får de tillgång till Adobe program och tjänster som ingår i produkten.

Om de befintliga rollerna inte uppfyller organisationens specifika behov kan du även skapa anpassade **[!UICONTROL Roles]** för att finjustera åtkomsten till vissa funktioner eller objekt i gränssnittet. På så sätt kan du se till att alla användare bara har tillgång till de resurser och verktyg de behöver för att kunna utföra sina uppgifter på ett effektivt sätt.

## Tilldela en roll {#assigning-role}

Du kan välja att tilldela en färdig eller anpassad **[!UICONTROL Role]** för användarna.

Listan över alla färdiga roller med tilldelade behörigheter finns i [Inbyggda roller](ootb-product-profiles.md) -avsnitt.

Tilldela en **[!UICONTROL Role]**:

1. Tilldela en roll till en användare i [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och välj önskad roll.

   ![](assets/do-not-localize/access_control_2.png)

1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

   ![](assets/do-not-localize/access_control_3.png)

1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

   Om användaren inte redan har skapats i [!DNL Admin Console], se [Lägga till användardokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/users.html).

   ![](assets/do-not-localize/access_control_4.png)

Användaren får sedan ett e-postmeddelande som omdirigerar denne till din instans i .

Mer information om användarhantering finns i [Åtkomstkontrolldokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

När du får åtkomst till instansen visas en specifik vy beroende på de tilldelade behörigheterna i **[!UICONTROL Role]**. Om användaren inte har rätt åtkomst till en funktion visas följande meddelande:

`You don't have permission to access this feature. Permission needed: XX.`

## Redigera en befintlig roll {#edit-product-profile}

För färdiga eller anpassade **[!UICONTROL Roles]** kan du när som helst bestämma om du vill lägga till eller ta bort behörigheter.

I det här exemplet vill vi lägga till **[!UICONTROL Permissions]** i relation till **[!UICONTROL Journeys]** resurs för användare som har tilldelats visningsprogrammet för resan **[!UICONTROL Role]**. Användarna kan sedan publicera resor.

Observera att om du ändrar ett ej ifyllt program eller anpassat **[!UICONTROL Role]** påverkar det alla användare som tilldelas detta **[!UICONTROL Role]**.

1. Tilldela en roll till en användare i [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och välj önskad roll här i resevisningsprogrammet **[!UICONTROL Role]**.
   ![](assets/do-not-localize/access_control_5.png)

1. Från **[!UICONTROL Role]** kontrollpanel, klicka **[!UICONTROL Edit]**.

   ![](assets/do-not-localize/access_control_6.png)

1. The **[!UICONTROL Resources]** visas en lista med de resurser som gäller för **[!UICONTROL Experience Cloud - Platform powered applications]** produkt. Dra och släpp resurser för att tilldela behörighet.

   Från **[!UICONTROL Journeys]** nedrullningsbar resursmeny, väljer vi här för Publish-resan **[!UICONTROL Permission]**.

   ![](assets/do-not-localize/access_control_14.png)

1. Vid behov, under **[!UICONTROL Included Permission Items]** klickar du på X-ikonen bredvid för att ta bort behörigheter eller resurser till din roll.

1. Klicka på **[!UICONTROL Save]** när du är klar.

Om det behövs kan du även skapa en ny roll med specifika behörigheter. Mer information finns i [Skapa en ny roll](#create-product-profile).

## Skapa en ny roll {#create-product-profile}

[!DNL Journey Optimizer] gör att du kan skapa egna **[!UICONTROL Roles]** och tilldela en uppsättning behörigheter och sandlådor till användarna. Med **[!UICONTROL Roles]** kan du tillåta eller neka åtkomst till vissa funktioner eller objekt i gränssnittet.

Mer information om hur du skapar och hanterar sandlådor finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html){target="_blank"}.

I det här exemplet skapar vi en roll med namnet **Skrivskyddade resor** där vi ger läsbehörighet till resefunktionen. Användare kommer endast att kunna komma åt och visa resor och kommer inte att kunna komma åt andra funktioner som **[!DNL  Decision management]** in [!DNL Journey Optimizer].

Skapa **Skrivskyddade resor** **[!UICONTROL Role]**:

1. Tilldela en roll till en användare i [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och klicka **[!UICONTROL Create role]**.

   ![](assets/do-not-localize/access_control_9.png)

1. Lägg till en **[!UICONTROL Name]** och **[!UICONTROL Description]** för dina nya **[!UICONTROL Role]**. Klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/do-not-localize/access_control_10.png)

1. Från **[!UICONTROL Sandbox]** nedrullningsbar resurs, välj vilken eller vilka sandlådor som ska tilldelas din **[!UICONTROL Role]**. [Läs mer om sandlådor](sandboxes.md).

   ![](assets/do-not-localize/access_control_13.png)

1. Välj mellan olika resurser som **[!DNL Journeys]**, **[!DNL Segments]** eller **[!DNL Decision management]** finns i [!DNL Journey Optimizer] som visas på den vänstra menyn.

   Här väljer vi **[!UICONTROL Journeys]** resurs.

   ![](assets/do-not-localize/access_control_11.png)

1. Från **[!UICONTROL Journeys]** väljer du de behörigheter du vill tilldela **[!UICONTROL Role]**.

   Här väljer vi **[!DNL View journeys]**, **[!DNL View journeys report]**  och **[!DNL View journeys event, data sources, actions]**.

   ![](assets/do-not-localize/access_control_12.png)

1. Klicka på **[!UICONTROL Save]** när du är klar.

Dina **[!UICONTROL Role]** har nu skapats och konfigurerats. Du måste nu tilldela den till användare.

Mer information om att skapa och hantera roller finns i [Admin Console dokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/roles.html).
