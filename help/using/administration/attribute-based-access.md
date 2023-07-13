---
solution: Journey Optimizer
product: journey optimizer
title: Attributbaserad åtkomstkontroll
description: Med attributbaserad åtkomstkontroll (ABAC) kan du definiera behörigheter för att hantera dataåtkomst för specifika team eller grupper av användare.
feature: Access Management
topic: Administration
role: Admin,Leader
level: Intermediate
keywords: abac, attribute, authorized, data, access, sensitive, assets
exl-id: 162b0848-313a-447e-9237-5a6dbc8102c6
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---

# Attributbaserad åtkomstkontroll {#attribute-based-access}

Med attributbaserad åtkomstkontroll (ABAC) kan du definiera behörigheter för att hantera dataåtkomst för specifika team eller grupper av användare. Syftet är att skydda känsliga digitala resurser mot obehöriga användare, vilket ger ytterligare skydd för personuppgifter.

I Adobe Journey Optimizer kan du med ABAC skydda data och ge specifik åtkomst till specifika fältelement, inklusive XDM-scheman (Experience Data Model), profilattribut och målgrupper.

En mer detaljerad lista över de termer som används med ABAC finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/overview.html).

I det här exemplet vill vi lägga till en etikett i **Nationalitet** schemafält för att hindra obehöriga användare från att använda det. För att detta ska fungera måste du utföra följande steg:

1. Skapa ett nytt  **[!UICONTROL Role]** och tilldela den med motsvarande  **[!UICONTROL Label]** så att användare kan komma åt och använda schemafältet.

1. Tilldela en  **[!UICONTROL Label]** till **Nationalitet** schemafält i Adobe Experience Platform.

1. Använd  **[!UICONTROL Schema field]** i Adobe Journey Optimizer.

Observera att **[!UICONTROL Roles]**, **[!UICONTROL Policies]** och **[!UICONTROL Products]** kan också nås med attributbaserad API för åtkomstkontroll. Mer information finns i [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/abac-api/overview.html).

## Skapa en roll och tilldela etiketter {#assign-role}

>[!IMPORTANT]
>
>Innan du hanterar behörigheter för en roll måste du skapa en profil. Mer information finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/policies.html).

**[!UICONTROL Roles]** är en uppsättning användare som delar samma behörigheter, etiketter och sandlådor inom organisationen. Varje användare som tillhör en **[!UICONTROL Role]** har rätt till de program och tjänster i Adobe som ingår i produkten.
Du kan också skapa egna **[!UICONTROL Roles]** om du vill finjustera användarnas åtkomst till vissa funktioner eller objekt i gränssnittet.

Vi vill nu ge utvalda användare åtkomst till **Nationalitet** fält, märkt C2. För att göra det måste vi skapa en ny **[!UICONTROL Role]** med en specifik uppsättning användare och ge dem etiketten C2 så att de kan använda **Nationalitet** information i en **[!UICONTROL Journey]**.

1. Från [!DNL Permissions] produkt, välj **[!UICONTROL Role]** från den vänstra panelmenyn och klicka på **[!UICONTROL Create role]**. Observera att du även kan lägga till **[!UICONTROL Label]** till inbyggda roller.

   ![](assets/role_1.png)

1. Lägg till en **[!UICONTROL Name]** och **[!UICONTROL Description]** till dina nya **[!UICONTROL Role]**, här: Begränsad rolldemografi.

1. I listrutan väljer du **[!UICONTROL Sandbox]**.

   ![](assets/role_2.png)

1. Från **[!UICONTROL Resources]** meny, klicka **[!UICONTROL Adobe Experience Platform]** för att öppna de olika funktionerna. Här väljer vi **[!UICONTROL Journeys]**.

   ![](assets/role_3.png)

1. I listrutan väljer du **[!UICONTROL Permissions]** länkad till den valda funktionen, t.ex. **[!UICONTROL View journeys]** eller **[!UICONTROL Publish journeys]**.

   ![](assets/role_6.png)

1. När du har sparat dina nyskapade **[!UICONTROL Role]**, klicka **[!UICONTROL Properties]** för att ytterligare konfigurera åtkomst till din roll.

   ![](assets/role_7.png)

1. Klicka på **[!UICONTROL Add users]** på fliken **[!UICONTROL Users]**.

   ![](assets/role_8.png)

1. På fliken **[!UICONTROL Labels]** väljer du **[!UICONTROL Add label]**.

   ![](assets/role_9.png)

1. Välj **[!UICONTROL Labels]** du vill lägga till i din roll och klicka på **[!UICONTROL Save]**. I det här exemplet ger vi användare etiketten C2 åtkomst till det tidigare begränsade schemats fält.

   ![](assets/role_4.png)

Användarna i **Begränsad rolldemografi** rollen har nu åtkomst till de C2-märkta objekten.

## Tilldela etiketter till ett objekt i Adobe Experience Platform {#assign-label}

>[!WARNING]
>
>Felaktig etikettanvändning kan bryta åtkomsten till personer och utlösa policyöverträdelser.

**[!UICONTROL Labels]** kan användas för att tilldela specifika funktionsområden med hjälp av attributbaserad åtkomstkontroll.
I det här exemplet vill vi begränsa åtkomsten till **Nationalitet** fält. Det här fältet är endast tillgängligt för användare med motsvarande **[!UICONTROL Label]** till  **[!UICONTROL Role]**.

Observera att du även kan lägga till  **[!UICONTROL Label]** till  **[!UICONTROL Schema]**,  **[!UICONTROL Datasets]** och  **[!UICONTROL Audiences]**.

1. Skapa **[!UICONTROL Schema]**. Mer information finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html).

   ![](assets/label_1.png)

1. I den nyskapade **[!UICONTROL Schema]**, lägger vi först till **[!UICONTROL Demographic details]** fältgrupp som innehåller **Nationalitet** fält.

   ![](assets/label_2.png)

1. Från **[!UICONTROL Labels]** kontrollerar du namnet på det begränsade fältet här **Nationalitet**. Välj sedan i den högra panelmenyn **[!UICONTROL Edit governance labels]**.

   ![](assets/label_3.png)

1. Välj motsvarande **[!UICONTROL Label]** i det här fallet kan inte C2 - Data exporteras till tredje part. En detaljerad lista över tillgängliga etiketter finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html#contract-labels).

   ![](assets/label_4.png)

1. Anpassa schemat ytterligare om det behövs och aktivera det sedan. Detaljerade anvisningar om hur du aktiverar ditt schema finns i [page](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#profile).

Fältet i schemat är nu bara synligt och kan nu bara användas av användare som är en del av en roll som har angetts med C2-etiketten.
Genom att använda en **[!UICONTROL Label]** till **[!UICONTROL Field name]** Observera att **[!UICONTROL Label]** används automatiskt på **Nationalitet** i alla skapade scheman.

![](assets/label_5.png)

## Få åtkomst till märkta objekt i Adobe Journey Optimizer {#attribute-access-ajo}

Efter märkning av **Nationalitet** fältnamn i ett nytt schema och vår nya roll, vi kan nu se hur den här begränsningen påverkar Adobe Journey Optimizer.
Till exempel kommer den första användaren X med åtkomst till objekt som är märkta C2 att skapa en resa med ett villkor som har målinriktningen begränsad **[!UICONTROL Field name]**. En andra användare, Y, utan åtkomst till objekt som är märkta C2, måste sedan publicera resan.

1. Från Adobe Journey Optimizer måste du först konfigurera **[!UICONTROL Data source]** med ditt nya schema.

   ![](assets/journey_1.png)

1. Lägg till en ny **[!UICONTROL Field group]** av dina nyskapade **[!UICONTROL Schema]** till det inbyggda **[!UICONTROL Data source]**. Du kan också skapa en ny extern **[!UICONTROL data source]** och associerade **[!UICONTROL Field groups]**.

   ![](assets/journey_2.png)

1. När du har valt en tidigare version **[!UICONTROL Schema]**, klicka **[!UICONTROL Edit]** från **[!UICONTROL Fields]** kategori.

   ![](assets/journey_3.png)

1. Välj **[!UICONTROL Field name]** som du vill rikta. Här väljer vi de begränsade **Nationalitet** fält.

   ![](assets/journey_4.png)

1. Skapa sedan en resa som skickar ett e-postmeddelande till användare med en viss nationalitet. Lägg till en **[!UICONTROL Event]** sedan en **[!UICONTROL Condition]**.

   ![](assets/journey_5.png)

1. Välj begränsad **Nationalitet** för att börja bygga ditt uttryck.

   ![](assets/journey_6.png)

1. Redigera **[!UICONTROL Condition]** för att inrikta sig på en viss population med begränsad **Nationalitet** fält.

   ![](assets/journey_7.png)

1. Anpassa din resa efter behov, här lägger vi till en **[!UICONTROL Email]** åtgärd.

   ![](assets/journey_8.png)

Om användaren Y utan åtkomst till etikett C2-objekt behöver komma åt den här resan med det här begränsade fältet:

* Användare Y kan inte använda det begränsade fältnamnet eftersom det inte visas.

* Användare Y kan inte redigera uttrycket med det begränsade fältnamnet i avancerat läge. Följande fel visas `The expression is invalid. Field is no longer available or you don't have enough permission to see it`.

* Användare Y kan ta bort uttrycket.

* Användare Y kan inte testa resan.

* Användare Y kan inte publicera resan.
