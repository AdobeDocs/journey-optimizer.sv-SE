---
solution: Journey Optimizer
product: journey optimizer
title: Ändra eller stoppa en kampanj
description: Lär dig hur du ändrar, stoppar eller duplicerar live-kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: hantera kampanjer, status, schema, åtkomst, optimering
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: b9630c922ff67b0a402af5f950ee4e5a442bb1b1
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---

# Hantera kampanjer {#modify-stop-campaign}

När en kampanj har aktiverats kan du när som helst ändra eller stoppa den. Dessa åtgärder är endast tillgängliga för kampanjer med en återkommande körning.

Dessutom kan ni duplicera live-kampanjer (som körs en gång eller med en återkommande körning) för att skapa nya, och arkivera slutförda eller stoppade kampanjer.

## Åtkomst till kampanjer {#access}

Kampanjer är tillgängliga på menyn **[!UICONTROL Campaigns]**.

Som standard visas alla kampanjer med statusvärdena **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** i listan. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/create-campaign-list.png)

Dessutom kan du filtrera listan baserat på kampanjtyp och kanal, eller de taggar som har tilldelats kampanjerna när de skapas. [Lär dig hur du tilldelar taggar till en kampanj](create-campaign.md#create)

## Kampanjstatus och larm {#statuses}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Kampanjen redigeras, den har inte aktiverats.
* **[!UICONTROL Activating]**: Kampanjen aktiveras.
* **[!UICONTROL Processing]** *(endast e-postkampanjer)*: Målgruppsexporten är klar, kampanjen publiceras.
* **[!UICONTROL Live]**: Kampanjen har aktiverats.
* **[!UICONTROL Scheduled]**: Kampanjen är konfigurerad att aktiveras ett visst startdatum.
* **[!UICONTROL Stopped]**: Kampanjen har stoppats manuellt. Du kan inte aktivera eller återanvända den längre. [Lär dig stoppa en kampanj](modify-stop-campaign.md#stop)
* **[!UICONTROL Completed]**: Kampanjen är slutförd. Den här statusen tilldelas automatiskt 3 dagar efter att en kampanj har aktiverats, eller vid kampanjens slutdatum om den har en återkommande körning.
* **[!UICONTROL Archived]**: Kampanjen har arkiverats. [Lär dig arkivera kampanjer](modify-stop-campaign.md#archive)

>[!NOTE]
>
>Ikonen Öppna utkast till version bredvid statusen **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** anger att en ny version av kampanjen har skapats och inte har aktiverats än. [Läs mer](modify-stop-campaign.md#modify).

När ett fel inträffar inom en av era kampanjer visas en varningsikon bredvid kampanjens status. Klicka på den för att visa information om varningen. Dessa varningar kan inträffa i olika situationer, t.ex. när kampanjmeddelandet inte har publicerats eller om den valda ytan är felaktig.

![](assets/campaign-alerts.png)

## Ändra en återkommande kampanj {#modify}

Så här ändrar du och skapar en ny version av en återkommande kampanj:

1. Öppna kampanjen och klicka sedan på knappen **[!UICONTROL Modify campaign]**.

1. En ny version av kampanjen skapas. Du kan kontrollera live-versionen genom att klicka på **[!UICONTROL Open live version]**.

   ![](assets/create-campaign-draft.png)

   I kampanjlistan visas aktiverade kampanjer med en pågående utkastversion med en specifik ikon i kolumnen **[!UICONTROL Status]**. Klicka på den här ikonen för att öppna utkastet till kampanjversionen.

   ![](assets/create-campaign-edit-list.png)

1. När ändringarna är klara kan du aktivera den nya versionen av kampanjen (se [Granska och aktivera en kampanj](create-campaign.md#review-activate)).

   >[!IMPORTANT]
   >
   >När du aktiverar utkastet ersätts kampanjens liveversion.

## Stoppa en återkommande kampanj {#stop}

Om du vill stoppa en återkommande kampanj öppnar du den och klickar sedan på knappen **[!UICONTROL Stop campaign]**.

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

För att förhindra detta kan ni arkivera slutförda och stoppade kampanjer som ni inte längre behöver. Om du vill göra det klickar du på ellipsknappen och väljer **[!UICONTROL Archive]**.

![](assets/create-campaign-archive.png)

Arkiverade kampanjer kan sedan hämtas med det dedikerade filtret i listan. [Lär dig hur du får åtkomst till kampanjer](get-started-with-campaigns.md#access)
