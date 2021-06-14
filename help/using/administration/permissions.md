---
title: Hantera användare och produktprofiler
description: Lär dig hur du hanterar behörigheter
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
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: Kontrollgrupper
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 13%

---

# Hantera användare och produktprofiler {#manage-permissions}

![](../assets/do-not-localize/badge.png)

>[!IMPORTANT]
>
> Var och en av nedanstående procedurer kan bara utföras av en **[!UICONTROL Product]**- eller **[!UICONTROL System]**-administratör. Mer information finns i [Admin Console-dokumentationen](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html).

**[!UICONTROL Product profiles]** är uppsättningar användare som delar samma behörigheter och sandlådor i organisationen.

Med [!DNL Journey Optimizer]-produkten kan du välja mellan olika färdiga **[!UICONTROL Product profiles]** med olika behörighetsnivåer att tilldela användarna. Mer information om **[!UICONTROL Product profiles]** finns på den här [sidan](ootb-product-profiles.md).

Alla användare som tillhör en **[!UICONTROL Product profiles]** har rätt till de program och tjänster i Adobe som ingår i produkten.

Du kan också skapa en egen **[!UICONTROL Product profiles]** om du vill finjustera användarnas åtkomst till vissa funktioner eller objekt i gränssnittet.

## Tilldela en produktprofil {#assigning-product-profile}

Du kan välja att tilldela användarna en färdig eller anpassad **[!UICONTROL Product profile]**.

Listan över alla färdiga produktprofiler med tilldelade behörigheter finns i [avsnittet Inbyggda produktprofiler](ootb-product-profiles.md).

Så här tilldelar du en **[!UICONTROL Product profile]**:

1. Välj **[!UICONTROL Experience Cloud - Platform powered applications]**-produkten på fliken **[!UICONTROL Products]** i [!DNL Admin Console].

1. Välj en **[!UICONTROL Product profile]**.  

   ![](../assets/access_control_2.png)

1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

   ![](../assets/access_control_3.png)

1. Skriv in användarens namn eller e-postadress och markera användaren.

   Om användaren inte redan har skapats i [!DNL Admin Console], se [dokumentationen till Lägg till användare](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users).

   ![](../assets/access_control_4.png)

1. Utför samma steg som ovan för att lägga till andra användare i din **[!UICONTROL Product profile]**. Klicka sedan på **[!UICONTROL Save]**.

Användaren får sedan ett e-postmeddelande som omdirigerar denne till din instans i .

Mer information om användarhantering finns i [Admin Console-dokumentationen](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html).

När användaren öppnar instansen visas en specifik vy beroende på de tilldelade behörigheterna i **[!UICONTROL Product profile]**. Om användaren inte har rätt åtkomst till en funktion visas följande skärm.

![](../assets/access_control_1.png)

## Redigera en befintlig produktprofil {#edit-product-profile}

För användningsklara eller anpassade **[!UICONTROL Product profiles]** kan du när som helst bestämma om du vill lägga till eller ta bort behörigheter.

I det här exemplet vill vi lägga till **[!UICONTROL Permissions]** som är relaterat till funktionen **[!UICONTROL Message]** för användare som är tilldelade till resevisningsprogrammet **[!UICONTROL Product profile]**. Användarna kan sedan publicera meddelanden.

Observera, att om du ändrar ett **[!UICONTROL Product profile]** som är klart att användas eller anpassat påverkar detta alla användare som är tilldelade denna **[!UICONTROL Product profile]**.

1. Välj **[!UICONTROL Experience Cloud - Platform powered applications]**-produkten på fliken **[!UICONTROL Products]** i [!DNL Admin Console].

1. Välj visningsprogrammet för resan **[!UICONTROL Product profile]**.

1. Klicka på fliken **[!UICONTROL Permissions]**.  

   På fliken **[!UICONTROL Permissions]** visas en lista med funktioner som gäller för produkten ***[!UICONTROL Experience Cloud - Platform powered applications]**.

   ![](../assets/access_control_5.png)

1. Välj funktionen **[!UICONTROL Messages]**.

   ![](../assets/access_control_6.png)

1. I listan **[!UICONTROL Available Permission Items]** väljer du de behörigheter du vill tilldela till din **[!UICONTROL Product profile]** genom att klicka på plusikonen (+).

   Här lägger vi till behörigheten **[!UICONTROL Publish messages]**.

   ![](../assets/access_control_7.png)

1. Klicka vid behov på X-ikonen under **[!UICONTROL Included Permission Items]** bredvid respektive behörighet till din produktprofil.

1. Klicka på **[!UICONTROL Save]** när du är klar.

   ![](../assets/access_control_8.png)

Om det behövs kan du även skapa en ny produktprofil med specifika behörigheter. Mer information finns i [Skapa en produktprofil](#create-product-profile).

## Skapa en produktprofil {#create-product-profile}

[!DNL Journey Optimizer] I kan du skapa egna  **[!UICONTROL Product profiles]** och tilldela en uppsättning behörigheter och sandlådor till dina användare. Med **[!UICONTROL Product profiles]** kan du auktorisera eller neka åtkomst till vissa funktioner eller objekt i gränssnittet.

Se [dokumentationen om Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html) för mer information om hur du skapar och hanterar sandlådor.

I det här exemplet skapar vi en produktprofil med namnet **Skrivskyddad resa** där vi ger skrivskyddad behörighet till resefunktionen. Användare kan bara komma åt och visa resor och kan inte komma åt andra funktioner som **[!UICONTROL Decision management]** eller **[!UICONTROL Messages]** i [!DNL Journey Optimizer].

Så här skapar du våra **resor med skrivskydd** **[!UICONTROL product profiles]**:

1. Gå till [!DNL Admin Console].

1. Välj **[!UICONTROL Experience Cloud - Platform powered applications]**-produkten på fliken **[!UICONTROL Products]**.

1. Klicka på **[!UICONTROL New Profile]**.

   ![](../assets/access_control_9.png)

1. Lägg till en **[!UICONTROL Product Profile Name]**, **[!UICONTROL Display Name]** och **[!UICONTROL Description]** för din nya **[!UICONTROL product profiles]**.

   ![](../assets/access_control_10.png)

1. I kategorin **[!UICONTROL Notifications]** väljer du om användare ska meddelas via e-post när de läggs till i eller tas bort från den här produktprofilen.

1. När du är klar klickar du på **[!UICONTROL Save]** och väljer din nya **[!UICONTROL product profiles]**.

1. Om du vill lägga till behörigheter för användare så att de får åtkomst till olika funktioner väljer du fliken **[!UICONTROL Permissions]**.

1. Välj mellan de olika funktioner som **[!UICONTROL Messages]**, **[!UICONTROL Segments]** eller **[!UICONTROL Decision management]** som är tillgängliga i [!DNL Journey Optimizer] i den vänstra menyn.

   Här väljer vi funktionen **[!UICONTROL Journeys]**.

   ![](../assets/access_control_11.png)

1. I listan **[!UICONTROL Available Permission Items]** väljer du de behörigheter du vill tilldela till din **[!UICONTROL Product profile]** genom att klicka på plusikonen (+).

   Här väljer vi **[!UICONTROL View journeys]** och **[!UICONTROL View journeys event, data sources, actions]**.

   ![](../assets/access_control_12.png)

1. Välj **[!UICONTROL Sandbox access]**-funktionen för att välja vilka sandlådor som ska tilldelas till din **[!UICONTROL Product profile]**.

   ![](../assets/access_control_13.png)

1. Klicka på plusikonen (+) i **[!UICONTROL Available Permissions Items]** för att tilldela sandlådor till profilen. [Läs mer om sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html).

1. Klicka på **[!UICONTROL Save]** när du är klar.

Din **[!UICONTROL Product profile]** har nu skapats och konfigurerats. Du måste nu tilldela den till användare.

Mer information om hur du skapar och hanterar produktprofiler finns i [Admin Console-dokumentationen](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-product-profiles.ug.html).
