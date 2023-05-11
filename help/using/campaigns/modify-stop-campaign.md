---
solution: Journey Optimizer
product: journey optimizer
title: Ändra eller stoppa en kampanj
description: Lär dig hur du ändrar, stoppar eller duplicerar live-kampanjer i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: hantera kampanjer, status, schema, åtkomst, optimering
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: 1213a65c8a22a326e8294c51db53efb6e23fd6f9
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Hantera kampanjer {#modify-stop-campaign}

När en kampanj har aktiverats kan du när som helst ändra eller stoppa den. Dessa åtgärder är endast tillgängliga för kampanjer med en återkommande körning.

Dessutom kan ni duplicera live-kampanjer (som körs en gång eller med en återkommande körning) för att skapa nya, och arkivera slutförda eller stoppade kampanjer.

## Åtkomst till kampanjer {#access}

Kampanjerna är tillgängliga via **[!UICONTROL Campaigns]** -menyn.

Som standard visas alla kampanjer med **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** status. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/create-campaign-list.png)

Dessutom kan du filtrera listan baserat på kampanjtyp och kanal, eller de taggar som har tilldelats kampanjerna när de skapas. [Lär dig hur du tilldelar taggar till en kampanj](create-campaign.md#create)

## Kampanjstatus {#statuses}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Kampanjen redigeras, den har inte aktiverats.
* **[!UICONTROL Activating]**: Kampanjen aktiveras.
* **[!UICONTROL Live]**: Kampanjen har aktiverats.
* **[!UICONTROL Scheduled]**: Kampanjen är konfigurerad att aktiveras ett visst startdatum.
* **[!UICONTROL Stopped]**: Kampanjen har stoppats manuellt. Du kan inte aktivera eller återanvända den längre. [Lär dig stoppa en kampanj](modify-stop-campaign.md#stop)
* **[!UICONTROL Completed]**: Kampanjen är färdig. Den här statusen tilldelas automatiskt 3 dagar efter att en kampanj har aktiverats, eller vid kampanjens slutdatum om den har en återkommande körning.
* **[!UICONTROL Archived]**: Kampanjen har arkiverats. [Lär dig arkivera kampanjer](modify-stop-campaign.md#archive)

>[!NOTE]
>
>Ikonen&quot;Öppna utkast&quot; bredvid en **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** status anger att en ny version av kampanjen har skapats och ännu inte har aktiverats. [Läs mer](modify-stop-campaign.md#modify).

## Ändra en återkommande kampanj {#modify}

Så här ändrar du och skapar en ny version av en återkommande kampanj:

1. Öppna kampanjen och klicka sedan på **[!UICONTROL Modify campaign]** -knappen.

1. En ny version av kampanjen skapas. Du kan kontrollera live-versionen genom att klicka på **[!UICONTROL Open live version]**.

   ![](assets/create-campaign-draft.png)

   I kampanjlistan visas aktiverade kampanjer med ett utkast till version som pågår med en specifik ikon i **[!UICONTROL Status]** kolumn. Klicka på den här ikonen för att öppna utkastet till kampanjversionen.

   ![](assets/create-campaign-edit-list.png)

1. När ändringarna är klara kan du aktivera den nya versionen av kampanjen (se [Granska och aktivera en kampanj](create-campaign.md#review-activate)).

   >[!IMPORTANT]
   >
   >När du aktiverar utkastet ersätts kampanjens liveversion.

## Stoppa en återkommande kampanj {#stop}

Om du vill stoppa en återkommande kampanj öppnar du den och klickar sedan på **[!UICONTROL Stop campaign]** -knappen.

![](assets/create-campaign-stop.png)

>[!IMPORTANT]
>
>Att stoppa en kampanj kommer inte att stoppa en pågående sändning, men det kommer att stoppa en schemalagd sändning eller nästa förekomst om sändning redan pågår.

<!-- inbound campaign (inapp): can stop and resume -->

## Duplicera en kampanj {#duplicate}

Du kan duplicera en livekampanj och skapa en ny. Det gör du genom att öppna kampanjen och sedan klicka på **[!UICONTROL Duplicate]**.

![](assets/create-campaign-duplicate.png)

## Arkivera en kampanj {#archive}

Med tiden växer listan över kampanjer och blir så småningom svårare att hitta färdiga och stoppade kampanjer.

För att förhindra detta kan ni arkivera slutförda och stoppade kampanjer som ni inte längre behöver. Klicka på ellipsknappen och välj **[!UICONTROL Archive]**.

![](assets/create-campaign-archive.png)

Arkiverade kampanjer kan sedan hämtas med det dedikerade filtret i listan. [Lär dig hur du får tillgång till kampanjer](get-started-with-campaigns.md#access)
