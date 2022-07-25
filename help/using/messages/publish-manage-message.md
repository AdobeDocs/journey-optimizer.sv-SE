---
title: Publicera och ändra ett meddelande
description: Lär dig hur du publicerar och uppdaterar meddelanden
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 116e2223-a806-4f68-9a8c-c0bde6008010
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%

---

# Publicera meddelanden {#publish-manage-messages}

## Publicera ett meddelande {#publish-message}

När meddelandet har skapats kan du publicera det så att det blir tillgängligt för körning.

>[!CAUTION]
>
>Kontrollera och åtgärda varningar innan du publicerar. [Läs mer](alerts.md)

![](assets/publish-message.png)

När meddelandet har publicerats läggs det till i meddelandelistan med **[!UICONTROL Published]** status.

Den är nu klar att aktiveras av en eller flera [resor](../building-journeys/journey.md).

>[!NOTE]
>
>När du uppdaterar ett erbjudande, ett reserverbjudande, en erbjudandesamling eller ett erbjudandebeslut som direkt eller indirekt hänvisas till i ett publicerat meddelande, återspeglas uppdateringarna nu automatiskt i motsvarande meddelande, utan att det behöver publiceras på nytt. [Läs mer om erbjudanden](../offers/get-started/starting-offer-decisioning.md)

## Uppdatera ett skrivskyddat meddelande {#modify-message}

Efter publiceringen är ett meddelande i skrivskyddat läge. Du kan fortfarande uppdatera den genom att skapa ett nytt utkast av det meddelandet.

På så sätt kan du uppdatera innehåll eller åtgärda ett problem, till exempel utan att publicera om hela resan där meddelandet används.

>[!NOTE]
>
>Utkastversionen kan redigeras medan den publicerade versionen fortfarande är publicerad och aktiv.

Så här uppdaterar du ett publicerat meddelande:

1. I meddelandelistan markerar du meddelandet för att öppna det.

1. Klicka på **[!UICONTROL Modify]**.

   ![](assets/message-modify.png)

1. Bekräfta ditt val. Ett utkast av meddelandet skapas.

   ![](assets/message-modify-v2.png)

1. Redigera innehållet eller ändra inställningarna efter behov.
1. Klicka på **[!UICONTROL Publish]**. Den här åtgärden publicerar den nya versionen av meddelandet som ska användas för nästa körning.

Så snart den nya versionen har publicerats genereras en ny meddelandekörning vid nästa API-anrop. Nästa inkommande profil får den nya versionen.

<!--For batch messages, the audience/segment being processed in the previous execution will not be affected by the new version. Only the next incoming API call with an audience/segment will generate a new message execution with the new version. -->
