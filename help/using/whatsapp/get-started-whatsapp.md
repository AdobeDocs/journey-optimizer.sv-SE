---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med whatsApp-meddelanden
description: Lär dig hur du skapar och skickar meddelanden om whatsApp i Journey Optimizer
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
exl-id: 22df2bfa-4d86-464e-ad83-3aa457e3a747
source-git-commit: 73a347c104fe28799c264f9a8b6c3e5e12c8d892
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Kom igång med whatsApp-meddelanden {#get-started-whatsapp}

Du kan nu skicka whatsApp-meddelanden direkt via Journey Optimizer via Meta [Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/). Den här funktionen möjliggör smidig integrering av WhatsApp i resor och kampanjer, vilket förbättrar kommunikationen och engagemanget med mottagarna.

* På en **resa**. Skapa en resa, lägg till en **whatsApp**-aktivitet och definiera grundläggande inställningar. Bläddra sedan till den högra panelen i **[!UICONTROL Actions: WhatsApp]** för att skapa innehållet för WhatsApp-meddelandet. Lär dig skapa en resa på [den här sidan](../building-journeys/journey-gs.md).

* I en **kampanj**. Skapa en kampanj, välj **WhatsApp** som åtgärd och definiera grundläggande inställningar. Redigera sedan meddelandeinnehållet för att definiera det WhatsApp-meddelande som ska skickas. Lär dig skapa [en åtgärdskampanj](../campaigns/campaign-action.md#action-campaign-action) | [en API-utlöst kampanj](../campaigns/api-triggered-campaigns.md) | [en orkestrerad kampanj](../orchestrated/create-orchestrated-campaign.md#create)

![](assets/do-not-localize/whatsapp-beta.png){zoomable="yes"}

## Krav {#prereq}

Integrering av WhatsApp med Journey Optimizer kräver följande:

* Meta Business Manager-konto
* [WhatsApp Business Account med verifierat avsändarnamn och telefonnummer](https://developers.facebook.com/docs/whatsapp/overview/business-accounts/)
* [Token för användarauktorisering med lämplig behörighet](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [Godkända Meta-mallar](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)

Du måste även bekräfta följande innan du fortsätter med integreringen:

* [Innehållsregler för whatsApp](https://www.whatsapp.com/legal/messaging-guidelines)
* [Efterlevnad med Meta-principer](https://www.whatsapp.com/legal)
* [Konversationsgränsen 24 timmar](https://developers.facebook.com/docs/whatsapp/messaging-limits/)

## Begränsningar {#limitations}

Följande begränsningar gäller för WhatsApp-kanalen:

* WhatsApp-kanalen i Adobe Journey Optimizer är HIPAA-klar, men tredjepartsleverantörer omfattas inte av Adobe BAA. Kunderna ansvarar för sin egen regelefterlevnad och leverantörsvalidering.

* Observera att automatiska eller fördefinierade svarsmeddelanden ännu inte stöds.

* Från och med april 2025 har leveransen av alla marknadsföringsmallmeddelanden till WhatsApp-användare som har ett amerikanskt telefonnummer (ett nummer bestående av en +1-uppringningskod och en amerikansk riktnummer) tillfälligt stoppats. [Läs mer i Meta-dokumentationen](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/send-message-templates#per-user-marketing-template-message-limits)

* Integreringsfunktionen tillåter inte integrering med Business Service Provider (BSP) från tredje part.

## Instruktionsvideo {#video}

I videon nedan visas hur du integrerar WhatsApp som en inbyggd kanal i Adobe Journey Optimizer för att leverera säkra, personaliserade meddelanden i realtid i stor skala.

+++ Se videon

>[!VIDEO](https://video.tv.adobe.com/v/3470244?learn=on)

+++

## Ytterligare utbildningsresurser

Utforska fler videosjälvstudiekurser om meddelanden och konfiguration i whatsApp.

➡️ [Självstudiekurser för whatsApp-kanal](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction){target="_blank"}

