---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med API-utlösta kampanjer
description: Lär dig hur du aktiverar kampanjer med Journey Optimizer API:er.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
source-git-commit: 81e54a3e3428d58818805b5dcb397ede4039436a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 1%

---


# Arbeta med API-utlösta kampanjer {#trigger-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_overview_api_triggered"
>title="API-utlösta kampanjer"
>abstract="**Transaktionellt API-utlöste kampanjer**<br/> Utlös meddelanden i realtid via API-anrop <br/><br/>**Marknadsföringsmeddelanden**<br/> Kampanjinnehåll (kräver deltagande, i enlighet med affärsregler)<br/><br/>**Transaktionsmeddelanden**<br/> Tjänstrelaterat innehåll (bekräftelse, varningar, som inte kräver godkännande av marknadsföringen)<br/><br/>**Tillgängliga kanaler**<br/> E-post, SMS, push-meddelanden"

## Om API-utlösta kampanjer {#about}

API-utlösta kampanjer gör det möjligt att antingen nå ut till en målgrupp vid rätt tidpunkt eller för transaktionsmeddelanden/operativa meddelanden till en individ som lösenordsåterställning, där behovet av personalisering inte bara kan innebära att profilattribut används, utan även kontextdata i realtid i utlösaren, vilket är en REST API-nyttolast.

För att göra detta måste du först skapa en API-utlöst kampanj i Journey Optimizer och sedan starta körningen via ett API-anrop med [Interactive Message Execution REST API](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution).

➡️ [Upptäck den här funktionen i en video](#video)

>[!NOTE]
>
>Mer information om vilka kanaler som stöds finns i tabellen i det här avsnittet: [Kanaler i resor och kampanjer](../channels/gs-channels.md#channels).
>
>Vilka kanaler som är tillgängliga varierar beroende på licensmodell och tillägg.

## Viktiga steg för att skapa API-utlösta kampanjer {#steps}

Innan du börjar med kampanjer bör du kontrollera följande krav som anges [i det här avsnittet](get-started-with-campaigns.md#prerequisites). När dessa förutsättningar är uppfyllda kan ni börja skapa kampanjen:

1. [Definiera kampanjegenskaperna](api-triggered-campaign-properties.md)
1. [Konfigurera kampanjåtgärden](api-triggered-campaign-action.md)
1. [Redigera kampanjinnehållet](api-triggered-campaign-content.md)
1. [Definiera kampanjmålgruppen](api-triggered-campaign-audience.md)
1. [Schemalägg kampanjen](api-triggered-campaign-schedule.md)
1. [Granska och aktivera kampanjen](review-activate-api-triggered-campaign.md)
1. [Utlösa kampanjkörningen](trigger-campaigns.md)

## Instruktionsfilmer {#video}

Lär dig hur du skapar en kampanj och utlöser den från ett externt system baserat på användarinteraktioner med hjälp av REST-API:t för interaktiv meddelandekörning.

>[!VIDEO](https://video.tv.adobe.com/v/3425358?quality=12)
