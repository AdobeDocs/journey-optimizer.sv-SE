---
title: Kom igång med kampanjer
description: Läs mer om kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Med Campaigns kan ni leverera engångsinnehåll till ett visst segment i flera kanaler. Innan du skapar en ny kampanj måste du se till att du har en kanalyta (t.ex. en meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att användas."

## Om kampanjer {#about}

Med kampanjer kan ni leverera engångsinnehåll till ett visst segment med hjälp av flera kanaler. Till skillnad från resor, där åtgärder är utformade för att utföras i sekvens, kör kampanjer samtidigt, antingen direkt eller enligt ett angivet schema.

Du kan skapa två typer av kampanjer:

* **Schemalagda kampanjer** möjliggör enkel ad hoc-batchkommunikation för marknadsföringsfall som reklamerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.
* **API-utlösta kampanjer** möjliggör enkla transaktions-/driftsmeddelanden med REST API:er (lösenordsåterställning, övergivna kort osv.), där behovet kan innebära personalisering med hjälp av profilattribut och sammanhangsbaserade data från nyttolast.

Lär dig hur du arbetar med kampanjer:
* [Skapa en kampanj](create-campaign.md)
* [Skapa API-utlösta kampanjer](api-triggered-campaigns.md)
* [Ändra eller stoppa en kampanj](modify-stop-campaign.md)
* [Kampanjrapport](campaign-live-report.md)
* [Global kampanjrapport](campaign-global-report.md)

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
