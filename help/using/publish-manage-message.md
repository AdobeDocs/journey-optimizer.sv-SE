---
title: Publicera och ändra ett meddelande
description: Lär dig hur du publicerar och uppdaterar meddelanden
snippet: y
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 4%

---

# Publicera dina meddelanden {#publish-manage-messages}

## Publicera ett meddelande {#publish-message}

När meddelandet har skapats kan du publicera det så att det blir tillgängligt för körning.

>[!CAUTION]
>
>Kontrollera och åtgärda varningar innan du publicerar. [Läs mer](alerts.md).

![](assets/publish-message.png)

När meddelandet har publicerats läggs det till i meddelandelistan med statusen **[!UICONTROL Published]**.

Den är nu klar att aktiveras av en eller flera [resor](building-journeys/journey.md).

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

<!--For batch messages, the audience/segment being processed in the previous execution will not be affected by the new version. Only the next incoming API call with an audience/segment will generate a new message execution with the new version.-->
