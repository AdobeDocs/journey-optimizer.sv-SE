---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med kampanjer
description: Läs mer om kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: kampanj, hur, starta, optimera
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="Kampanjschema"
>abstract="Som standard börjar kampanjer vid manuell aktivering och avslutas omedelbart efter att meddelandet har skickats en gång. Du kan ange ett specifikt datum och en speciell tid för meddelandet som ska skickas. Dessutom kan du ange ett slutdatum för återkommande åtgärdskampanjer. I åtgärdsutlösarna kan du även konfigurera meddelandets sändningsfrekvens så att den passar dina inställningar."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_start"
>title="Kampanjstart"
>abstract="Ange ett datum och en tidpunkt då meddelandet ska skickas."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_end"
>title="Kampanjslut"
>abstract="Ange när en återkommande kampanj ska sluta köras."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_triggers"
>title="Kampanjåtgärdsutlösare"
>abstract="Definiera en frekvens som kampanjens meddelande ska skickas med."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_throttling"
>title="Kontroll av begränsningsfrekvens"
>abstract="Kontroll av begränsningsfrekvens"

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="Skapa kampanjer"
>abstract="Använd **Adobe Journey Optimizer** för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. När du använder resor utförs åtgärderna i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema."

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Skapa kampanjer för att leverera engångsinnehåll till en viss målgrupp i olika kanaler. Innan du skapar en kampanj bör du kontrollera att du har en kanalkonfiguration och en Adobe Experience Platform-målgrupp klar att använda."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="Kampanjtyp"
>abstract="**Schemalagda kampanjer** körs omedelbart eller på ett angivet datum och är avsedda att skicka meddelanden av marknadsföringstyp. **API-utlösta** kampanjer körs med ett API-anrop. Syftet är att skicka antingen marknadsföringsmeddelanden (reklammeddelanden som kräver användarens samtycke) eller transaktionsmeddelanden (icke-kommersiella meddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang)."

Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. När du använder resor utförs åtgärderna i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema.

![](assets/gs-campaigns.png)

Du kan skapa olika typer av kampanjer i Journey Optimizer:

* **Åtgärdskampanjer**

  Åtgärdskampanjer (eller schemalagda kampanjer) möjliggör enkel ad hoc-batchkommunikation för marknadsföringsfall som kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.

* **API-utlösta kampanjer**

  API-utlösta kampanjer gör det möjligt att antingen nå ut till en målgrupp vid rätt tidpunkt eller för transaktionsmeddelanden/operativa meddelanden till en individ som lösenordsåterställning, där behovet kan innebära personalisering inte bara genom att använda profilattribut, utan även kontextdata i realtid i utlösaren som är en REST API-nyttolast.

<!--* **Orchestrated campaigns**

    Campaign Orchestration in Adobe Journey Optimizer powers sophisticated, brand-initiated marketing campaigns across channels, helping you drive engagement, revenue, and customer loyalty at scale.

    While cross-channel marketing is essential, orchestrated campaigns make it seamless. With a visual, drag-and-drop interface, you can design and automate complex marketing workflows, from segmentation to message delivery, across multiple channels. Everything happens in one intuitive environment, built for speed, control, and efficiency.-->

## Före start {#campaign-prerequisites}

Kontrollera följande krav innan du börjar skapa din första kampanj i [!DNL Journey Optimizer]:

1. **Du behöver rätt behörighet**. Kampanjer är bara tillgängliga för användare med åtkomst till en kampanj som är relaterad till **[!UICONTROL Product profile]**, till exempel Campaign-administratör, Campaign-godkännare, Campaign-hanterare och/eller Campaign-visningsprogram. Om du inte kan komma åt kampanjer måste din behörighet utökas.

   +++Lär dig hur du tilldelar kampanjrelaterad roll

   1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer en av de inbyggda kampanjrelaterade **[!UICONTROL Roles]**: Kampanjadministratör, Kampanjgodkännare, Kampanjhanterare eller Kampanjvisningsprogram.

   1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

   1. Ange användarens namn eller e-postadress eller markera användaren i listan och klicka på **[!UICONTROL Save]**.

      Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/ui/users).

   Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

   +++

1. **Du behöver en målgrupp**. Målgrupper måste vara tillgängliga innan kampanjen kan skapas. [Kom igång med målgrupper](../audience/about-audiences.md).

1. **Du behöver en kanalkonfiguration**. Om du vill kunna välja en kanal måste du ha motsvarande kanalkonfiguration (dvs. förinställning) skapad och tillgänglig. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md).

## Låt oss dyka djupare

Nu när du har en förståelse för kampanjer i [!DNL Journey Optimizer] är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja skapa dina första kampanjer.

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img alt="åtgärdskampanjer" src="assets/do-not-localize/gs-action-campaign.png" width="50%"></a><br/><a href="create-campaign.md">Åtgärdskampanjer</a></td>
<td><a href="api-triggered-campaigns.md"><img alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png" width="50%"></a><br/><a href="api-triggered-campaigns.md">API-utlösta kampanjer</a></td>
</tr></table>

<!--
<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img alt="action campaigns" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">Action campaigns</a></td>
<td><a href="api-triggered-campaigns.md"><img alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API triggered campaigns</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img alt="push" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">Orchestrated campaigns</a></td>
</tr></table>-->
