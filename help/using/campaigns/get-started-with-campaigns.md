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
source-git-commit: d4765f9084efac1fd241404dff365a66027ce5af
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 1%

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
>title="Kurskontroll"
>abstract="Ange hastighetskontroll för kampanjen genom att ange önskade hastighetsbegränsningar. Den här funktionen är särskilt användbar för att förhindra överbelastning i system längre fram i kedjan, som landningssidor eller kundtjänstplattformar."

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
>abstract="Välj kampanjtyp. Tillgängliga kanaler varierar beroende på vald typ. <br>**Schemalagda kampanjer** (åtgärdskampanjer) - Perfekt för enkel engångsbatchkommunikation som du kan schemalägga att köras vid en viss tidpunkt.<br>**API-utlösta kampanjer** - Aktiveras via ett API-anrop, vilket möjliggör automatiserade, händelsebaserade meddelanden direkt från externa system.<br>**Samordnade kampanjer** - Skapa en visuell arbetsyta med dra-och-släpp för att utforma och automatisera komplexa arbetsflöden för flerstegsmarknadsföring, från målgruppssegmentering till personaliserad meddelandeleverans över flera kanaler."

Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. När du använder resor utförs åtgärderna i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema.

![](assets/gs-campaigns.png)

Du kan skapa olika typer av kampanjer i Journey Optimizer:

* **Åtgärdskampanjer**

  Åtgärdskampanjer (eller schemalagda kampanjer) möjliggör enkel ad hoc-batchkommunikation för marknadsföringsfall som kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar. Kanaler som stöds är:

* **API-utlösta kampanjer**

  API-utlösta kampanjer gör det möjligt att antingen nå ut till en målgrupp vid rätt tidpunkt eller för transaktionsmeddelanden/operativa meddelanden till en individ som lösenordsåterställning, där behovet kan innebära personalisering inte bara genom att använda profilattribut, utan även kontextdata i realtid i utlösaren som är en REST API-nyttolast.

* **Samordnade kampanjer**

  Kampanjsamordning i Adobe Journey Optimizer driver fram sofistikerade, varumärkesinitierade marknadsföringskampanjer i alla kanaler och hjälper er att öka engagemanget, intäkterna och kundlojaliteten i stor skala.

  Flerkanalsmarknadsföring är avgörande, men samordnade kampanjer gör den sömlös. Med ett visuellt dra-och-släpp-gränssnitt kan ni utforma och automatisera komplexa marknadsföringsarbetsflöden, från segmentering till meddelandeleverans, i flera kanaler. Allt sker i en intuitiv miljö som är byggd för snabbhet, kontroll och effektivitet.

## Förhandskrav {#prerequisites}

Innan du skapar din kampanj måste du kontrollera att du har granskat villkoren nedan.

### Behörigheter

Kampanjer är bara tillgängliga för användare med lämplig behörighet som listas nedan. [Läs mer om Journey Optimizer inbyggda roller](../administration/ootb-product-profiles.md)

>[!BEGINTABS]

>[!TAB Åtgärdskampanjer]

Kampanjadministratör
Kampanjgodkännare
Kampanjchef
Kampanjvisningsprogram

>[!TAB API-utlösta kampanjer]

Kampanjadministratör
Kampanjgodkännare
Kampanjchef
Kampanjvisningsprogram

>[!TAB Samordnade kampanjer]

Orchestrated Campaign Administrator
Samlad kampanjgodkännare
Organiserad kampanjchef
Samlad kampanjvisare

>[!ENDTABS]

Om du inte kan komma åt kampanjfunktioner kontaktar du administratören för att få den behörighet som krävs.

+++Lär dig hur du tilldelar kampanjrelaterad roll

1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer en av de inbyggda kampanjrelaterade **[!UICONTROL Roles]** som beskrivs ovan.

1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

1. Ange användarens namn eller e-postadress eller markera användaren i listan och klicka på **[!UICONTROL Save]**.

   Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

+++

### Målgrupp

Målgrupper måste vara tillgängliga innan kampanjen kan skapas. [Kom igång med målgrupper](../audience/about-audiences.md).

### Kanalkonfiguration

Om du vill kunna välja en kanal måste du ha motsvarande kanalkonfiguration (dvs. förinställning) skapad och tillgänglig. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md).

## Låt oss dyka djupare

Nu när du har en förståelse för kampanjer i [!DNL Journey Optimizer] är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja skapa dina första kampanjer.

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="åtgärdskampanjer" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">Åtgärdskampanjer</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API-utlösta kampanjer</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="push" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">Samordnade kampanjer</a></td>
</tr></table>
