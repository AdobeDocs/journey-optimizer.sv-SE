---
title: Kom igång med kampanjer
description: Läs mer om kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 8d8586a6c70b6fc01dbd1c2a8833079f422c93f7
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Med Campaigns kan ni leverera engångsinnehåll till ett visst segment i flera kanaler. Innan du skapar en ny kampanj måste du se till att du har en kanalyta (t.ex. en meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att användas."

## Om kampanjer {#about}

Med kampanjer kan ni leverera engångsinnehåll till ett visst segment med hjälp av flera kanaler. Till skillnad från resor, där åtgärder är utformade för att utföras i sekvens, kör kampanjer samtidigt, antingen direkt eller enligt ett angivet schema.

På så sätt kan ni skicka enkla ad hoc-batchmeddelanden för marknadsföringsändamål som kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.

➡️ [Upptäck den här funktionen i en video](#video)

<!--You can create two types of campaigns:

* **Scheduled campaigns** allow for simple ad-hoc batch communications for marketing use cases like promotional offers, engagement campaigns, announcements, legal notices, or policy updates.
* **API Triggered Campaigns** allow for simple transactional/operational messages with REST APIs (password reset, card abandonment, etc.), where the need may involve personalization using profile attributes and contextual data from payload.-->

## Förutsättningar {#campaign-prerequisites}

Campaign är bara tillgängligt för användare som har åtkomst till en Campaign-relaterad **[!UICONTROL Product profile]** som Campaign-administratör, Campaign-godkännare, Campaign-chef och/eller Campaign-visningsprogram.

Tilldela motsvarande **[!UICONTROL Product profile]** till användarna:

1. Från [!DNL Admin console]väljer du [!DNL Adobe Experience Platform] produkt.

1. Från **[!UICONTROL Product profile]** väljer du en av de inbyggda Campaign-relaterade **[!UICONTROL Product profile]**: Kampanjadministratör, Kampanjgodkännare, Kampanjhanterare eller Kampanjvisningsprogram.

   Mer information om Campaign **[!UICONTROL Product profiles]** och **[!UICONTROL Permissions]**, se [page](../administration/ootb-product-profiles.md).

   ![](assets/do-not-localize/admin_1.png)

1. Klicka **[!UICONTROL Add user]** för att tilldela användaren det valda **[!UICONTROL Product profile]**.

   ![](assets/do-not-localize/admin_2.png)

1. Ange användarens namn, grupp eller e-postadress och klicka på **[!UICONTROL Save]**.

Användaren kan nu komma åt **[!UICONTROL Campaigns]**.

## Åtkomst till kampanjer {#access}

Kampanjerna är tillgängliga via **[!UICONTROL Campaigns]** -menyn.

Som standard visas alla kampanjer med **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** status. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/create-campaign-list.png)

## Kampanjstatus {#statuses}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Kampanjen redigeras, den har inte aktiverats.
* **[!UICONTROL Activating]**: Kampanjen aktiveras.
* **[!UICONTROL Live]**: Kampanjen har aktiverats.
* **[!UICONTROL Scheduled]**: Kampanjen har konfigurerats för att aktiveras ett visst startdatum.
* **[!UICONTROL Stopped]**: Kampanjen har stoppats manuellt. Du kan inte aktivera eller återanvända den längre (se [Stoppa en kampanj](modify-stop-campaign.md#stop))
* **[!UICONTROL Completed]**: Kampanjen är färdig. Den här statusen tilldelas automatiskt 3 dagar efter att en kampanj har aktiverats, eller vid kampanjens slutdatum om den har en återkommande körning.
* **[!UICONTROL Archived]**: Kampanjen har arkiverats.

>[!NOTE]
>
>Ikonen&quot;Öppna utkast&quot; bredvid en **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** status anger att en ny version av kampanjen har skapats och ännu inte har aktiverats (se [Ändra en kampanj](modify-stop-campaign.md#modify)).

## Instruktionsvideo {#video}

Lär dig hur du skapar din första kampanj.

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
