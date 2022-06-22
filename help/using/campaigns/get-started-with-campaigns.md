---
title: Kom igång med kampanjer
description: Läs mer om kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: b9fa6bff926eb8cee476fa53feb38ed783e048fc
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 2%

---


# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Med Campaigns kan ni leverera engångsinnehåll till ett visst segment i flera kanaler. Innan du skapar en ny kampanj måste du se till att du har en meddelandeförinställning och ett Adobe Experience Platform-segment klart att användas."

## Om kampanjer {#about}

Med kampanjer kan ni leverera engångsinnehåll till ett visst segment med hjälp av flera kanaler.

Till skillnad från resor, där åtgärder är utformade för att utföras i sekvens, kör kampanjer samtidigt, antingen direkt eller enligt ett angivet schema. Ni kan till exempel använda dem för att leverera kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.

<!--Additionally, campaigns' content experiment feature allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.-->

Lär dig hantera kampanjer &lt;!>—och innehållsexperiment&lt;>:
* [Skapa en kampanj](create-campaign.md)
* [Ändra eller stoppa en kampanj](modify-stop-campaign.md)
<!--* [Create a content experiment](content-experiment.md)-->

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
* **[!UICONTROL Completed]**: Kampanjen är färdig.
* **[!UICONTROL Archived]**: Kampanjen har arkiverats.

>[!NOTE]
>
>Ikonen&quot;Öppna utkast&quot; bredvid en **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** status anger att en ny version av kampanjen har skapats och ännu inte har aktiverats (se [Ändra en kampanj](modify-stop-campaign.md#modify)).
