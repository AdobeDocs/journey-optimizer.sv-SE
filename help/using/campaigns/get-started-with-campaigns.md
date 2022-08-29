---
title: Kom igång med kampanjer
description: Läs mer om kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: b73d4495a231a40d833f4fee4dc094b808d659bd
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Skapa kampanjer för att leverera engångsinnehåll till ett specifikt segment i olika kanaler. Innan du skapar din kampanj måste du se till att du har en kanalyta (t.ex. en meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att användas."

Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till ett visst segment via olika kanaler. När du använder resor är åtgärderna utformade för att utföras i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema.

Skapa kampanjer för att skicka enkla ad hoc-batchmeddelanden för marknadsföringsfall som kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.

➡️ [Upptäck den här funktionen i en video](#video)

<!--You can create two types of campaigns:

* **Scheduled campaigns** allow for simple ad-hoc batch communications for marketing use cases like promotional offers, engagement campaigns, announcements, legal notices, or policy updates.
* **API Triggered Campaigns** allow for simple transactional/operational messages with REST APIs (password reset, card abandonment, etc.), where the need may involve personalization using profile attributes and contextual data from payload.-->

## Före start {#campaign-prerequisites}

Kontrollera följande innan du börjar skapa din första kampanj i Journey Optimizer:

1. **Du behöver rätt behörigheter**. Kampanjer är bara tillgängliga för användare med tillgång till en kampanjrelaterad **[!UICONTROL Product profile]** som Campaign-administratör, Campaign-godkännare, Campaign-chef och/eller Campaign-visningsprogram.

   Om du inte kan komma åt kampanjer måste din behörighet utökas. Om du har åtkomst till [Adobe Admin Console](https://adminconsole.adobe.com/){target=&quot;_blank&quot;} för din organisation, följ stegen nedan. Om inte, kontakta Journey Optimizer-administratören.

   +++Lär dig hur du tilldelar kampanjbehörigheter

   Tilldela motsvarande **[!UICONTROL Product profile]** till användarna:

   1. Från [!DNL Admin console]väljer du [!DNL Adobe Experience Platform] produkt.

   1. Från **[!UICONTROL Product profile]** väljer du en av de inbyggda Campaign-relaterade **[!UICONTROL Product profile]**: Kampanjadministratör, Kampanjgodkännare, Kampanjhanterare eller Kampanjvisningsprogram.

      Mer information om Journey Optimizer kampanj **[!UICONTROL Product profiles]** och **[!UICONTROL Permissions]**, [hänvisa till denna sida](../administration/ootb-product-profiles.md).

      ![](assets/do-not-localize/admin_1.png)

   1. Klicka **[!UICONTROL Add user]** för att tilldela användaren det valda **[!UICONTROL Product profile]**.

      ![](assets/do-not-localize/admin_2.png)

   1. Ange användarens namn, grupp eller e-postadress och klicka på **[!UICONTROL Save]**.
   Användaren kan nu komma åt **[!UICONTROL Campaigns]**.

+++

1. **Ni behöver en målgrupp**. Målgruppssegment måste vara tillgängliga innan kampanjen kan skapas. Läs mer om målgruppsframtagning [på den här sidan](../segment/about-segments.md).
1. **Du behöver en kanalyta**. Om du vill kunna markera en kanal måste du ha motsvarande kanalyta (dvs. förinställning) skapad och tillgänglig. Läs mer om kanalytor [på den här sidan](../configuration/channel-surfaces.md)

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
