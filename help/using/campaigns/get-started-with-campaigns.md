---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med kampanjer
description: Läs mer om kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: kampanj, hur, starta, optimera
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: d93b7ce225294257f49caee6ac08cfb575611a93
workflow-type: tm+mt
source-wordcount: '950'
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
>abstract="Välj kampanjtyp. Tillgängliga kanaler varierar beroende på vald typ. <br>**Schemalagda kampanjer** (åtgärdskampanjer) - Perfekt för enkel engångsbatchkommunikation som du kan schemalägga att köras vid en viss tidpunkt.<br>**API-utlösta kampanjer** - Aktiveras via ett API-anrop, vilket aktiverar automatiserade händelsebaserade meddelanden direkt från externa system.<br>**Samordnade kampanjer** - Skapa en visuell arbetsyta med dra-och-släpp för att utforma och automatisera komplexa arbetsflöden för flerstegsmarknadsföring, från målgruppssegmentering till personaliserad meddelandeleverans över flera kanaler."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_orchestration"
>title="Kampanjer"
>abstract="Skapa ett segmenteringsflöde, utforma era flerkanalsmeddelanden och planera era kampanjer. Kanaler som stöds: E-post, SMS, push-meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_marketing"
>title="Kampanjer"
>abstract="Leverera enstaka eller återkommande utgående leveranser eller pågående inkommande åtgärder."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_transactional"
>title="Kampanjer"
>abstract="Leverera enstaka eller återkommande utgående transaktionsaktiviteter."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_marketing"
>title="Kampanjer"
>abstract="Leverera personaliserad marknadskommunikation till riktade målgrupper. Kanaler som stöds: E-post, SMS, push-meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_transactional"
>title="Kampanjer"
>abstract="Skicka transaktionsinformation till enskilda profiler eller profiler. Kanaler som stöds: E-post, SMS, push-meddelanden."

Använd [!DNL Journey Optimizer] kampanjer för att leverera engångsinnehåll till en viss målgrupp i flera kanaler. Till skillnad från resor, som utför åtgärder steg för steg, utför kampanjer samtidigt - antingen direkt eller enligt ett bestämt schema.

![](assets/gs-campaigns.png)

## Kampanjtyper

[!DNL Journey Optimizer] har stöd för tre kampanjtyper. Varje typ passar olika användningsområden och har stöd för olika kanaler.

![](assets/campaign-modal.png)

>[!BEGINTABS]

>[!TAB Samordnade kampanjer]

**Samordnade kampanjer** används för sofistikerade, varumärkesinitierade marknadsföringskampanjer i alla kanaler, vilket hjälper er att öka engagemanget, intäkterna och kundlojaliteten i stor skala.

Flerkanalsmarknadsföring är avgörande, men samordnade kampanjer gör den sömlös. Med ett visuellt dra-och-släpp-gränssnitt kan ni utforma och automatisera komplexa marknadsföringsarbetsflöden, från segmentering till meddelandeleverans, i flera kanaler. Allt sker i en intuitiv miljö som är byggd för snabbhet, kontroll och effektivitet.

➡️ [Lär dig hur du arbetar med samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md).

>[!TAB Åtgärdskampanjer (eller schemalagda kampanjer)]

**Åtgärdskampanjer**, som också kallas schemalagda kampanjer, möjliggör enkel ad hoc-batchkommunikation.

* **Schemalagd - Marknadsföring** - För marknadsföringsfall som kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar. Kräver att mottagarna är invalda.
* **Schemalagd - Transaktionell** - Till skillnad från marknadsföringskampanjer kräver inte Transactional-kampanjer att mottagare väljs. Använd den här kategorin för kommunikation i samband med avbrott, kriser och annulleringar. Kanaler som stöds: e-post, SMS, push-meddelanden.

➡️ [Lär dig arbeta med åtgärdskampanjer](create-campaign.md)

>[!TAB API-utlösta kampanjer]

**API-utlösta kampanjer** gör att du kan utlösa kampanjkörningen med ett API-anrop. Kommunikationen kan skickas där behovet av anpassning kan innebära att inte bara profilattribut som lösenordsåterställning används, utan även kontextdata i realtid i utlösaren, som är en REST API-nyttolast.

* **API utlöstes - Marketing** - Skicka personaliserad marknadsföringskommunikation till målgrupper.
* **API har utlösts - Transactional** - Skicka meddelanden efter en åtgärd som har utförts av en individ, t.ex. en begäran om återställning av lösenord, ett kundvagnsinköp.

➡️ [Lär dig hur du arbetar med API-utlösta kampanjer](api-triggered-campaigns.md)


>[!ENDTABS]

## Kanaler som stöds efter kampanjtyp {#channels}

Tabellen nedan visar tillgängligheten för varje kanal mellan olika kampanjtyper, vilket visar var de stöds.

| Kanal | Åtgärd (marknadsföring) | Åtgärd (transaktionell) | API-utlöst (marknadsföring) | API-utlöst (Transactional) | Orchestrated |
|----------------------|---------------------|-------------------------|----------------------------|--------------------------------|--------------|
| E-post | ✅ | ✅ | ✅ | ✅ | ✅ |
| SMS | ✅ | ✅ | ✅ | ✅ | ✅ |
| Push-meddelande | ✅ | ✅ | ✅ | ✅ | ✅ |
| I appen | ✅ | — | — | — | — |
| Direktmeddelande | ✅ | — | — | — | — |
| Webb | ✅ | — | — | — | — |
| Kodbaserad exp. | ✅ | — | — | — | — |
| Innehållskort | ✅ | — | — | — | — |
| WhatApp | ✅ | — | — | — | — |
| Linje | ✅ | — | — | — | — |

## Förhandskrav {#prerequisites}

Innan du arbetar med kampanjer måste du kontrollera att du har granskat villkoren nedan.

* **Publiker** måste vara tillgängliga innan kampanjen kan skapas. [Kom igång med målgrupper](../audience/about-audiences.md).

* **Kanalkonfigurationer** - Om du vill kunna välja en kanal måste du ha motsvarande kanalkonfiguration (dvs. förinställning) skapad och tillgänglig. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md).

* **Behörigheter** - kampanjer är bara tillgängliga för användare med lämplig behörighet som listas nedan. Om du inte kan komma åt kampanjfunktioner kontaktar du administratören för att få den behörighet som krävs. [Läs mer om Journey Optimizer inbyggda roller](../administration/ootb-product-profiles.md)

  | Kampanjtyp | Behörigheter |
  |----------------------------|----------------------------------------------------------------------------|
  | **Åtgärdskampanjer** | Kampanjadministratör<br>Kampanjgodkännare<br>Kampanjhanterare<br>Kampanjvisningsprogram |
  | **API-utlösta kampanjer** | Kampanjadministratör<br>Kampanjgodkännare<br>Kampanjhanterare<br>Kampanjvisningsprogram |
  | **Samordnade kampanjer** | Orchestrated Campaign Administrator<br>Orchestrated Campaign Approver<br>Orchestrated Campaign Manager<br>Orchestrated Campaign Viewer |

  +++Lär dig hur du tilldelar kampanjrelaterad roll

   1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer en av de inbyggda kampanjrelaterade **[!UICONTROL Roles]** som beskrivs ovan.

   1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

   1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

      Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/ui/users).

  Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

  +++

## Låt oss dyka djupare

Nu när du har en förståelse för kampanjer i [!DNL Journey Optimizer] är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja skapa dina första kampanjer.

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="åtgärdskampanjer" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">Åtgärdskampanjer</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API-utlösta kampanjer</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="push" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">Samordnade kampanjer</a></td>
</tr></table>
