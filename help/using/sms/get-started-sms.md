---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med textmeddelanden (SMS/MMS/RCS)
description: Lär dig skapa och skicka textmeddelanden i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: c1027268-0bbe-4e35-a5a6-2aef78083dd3
source-git-commit: 73a347c104fe28799c264f9a8b6c3e5e12c8d892
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 1%

---

# Kom igång med textmeddelanden {#get-started-sms}

Använd [!DNL Journey Optimizer] för att skicka textmeddelanden (SMS/MMS/RCS) till dina kunder på deras mobila enheter. Du kan skapa, anpassa och förhandsgranska meddelanden i textformat från SMS/MMS/RCS-redigeraren.

Textmeddelanden kan skapas och skickas på en resa eller i en kampanj. För SMS, MMS och RCS använder du SMS-åtgärden.

* På en **resa**. Skapa en resa, lägg till en SMS-aktivitet och definiera grundläggande inställningar. Bläddra sedan till rutan SMS-åtgärder till höger för att skapa innehållet för SMS-, MMS- eller RCS-meddelandet. [Lär dig skapa en resa](../building-journeys/journey-gs.md)

* I en **kampanj**. Skapa en kampanj, välj SMS som åtgärd och definiera grundläggande inställningar. Redigera sedan meddelandeinnehållet för att definiera SMS-, MMS- eller RCS-meddelandet som ska skickas. Lär dig skapa [en åtgärdskampanj](../campaigns/campaign-action.md#action-campaign-action) | [en API-utlöst kampanj](../campaigns/api-triggered-campaigns.md) | [en orkestrerad kampanj](../orchestrated/create-orchestrated-campaign.md#create)

>[!IMPORTANT]
>
>Om det är första gången du skapar textmeddelanden kontrollerar du att SMS-kanalen har konfigurerats. [Läs mer](sms-configuration.md)

## Textmeddelandefunktioner {#sms-capabilities}

Adobe Journey Optimizer har omfattande funktioner för textmeddelanden så att ni kan engagera era kunder i flera kanaler:

**SMS (Short Message Service)**

Skicka SMS med upp till 160 tecken. SMS är det mest använda textmeddelandeformatet på alla mobila enheter.

**MMS (Multimedia Message Service)**

Förbättra kommunikationen med multimediematerial som video, bilder, ljudklipp och GIF-filer. MMS-meddelanden kan innehålla upp till 1 600 tecken utöver mediefiler. [Läs mer om MMS-begränsningar](../start/guardrails.md#sms-guardrails)

**RCS (Rich Communication Services)**

Skicka varumärkesprofilerade, interaktiva meddelanden med avancerade funktioner som karuseller, grafikkort, funktionsförslag och förbättrat mediestöd. RCS ger en mer omfattande meddelandeupplevelse på enheter som stöds.

## Viktiga funktioner {#key-features}

**Personalization &amp; dynamiskt innehåll**

Skapa personaliserade textmeddelanden med personaliseringsredigeraren. Lägg till profilattribut, villkorsstyrt innehåll och dynamiska data för att skräddarsy meddelanden för enskilda mottagare. [Läs om personalisering](../personalization/personalize.md)

**Stöd för flera leverantörer**

Adobe Journey Optimizer kan integreras med ledande leverantörer av SMS-tjänster:

* **Sinch** - [Konfigurationsguide](sms-configuration-sinch.md)
* **Twilio** - [Konfigurationsguide](sms-configuration-twilio.md)
* **Infobip** - [Konfigurationsguide](sms-configuration-infobip.md)
* **Anpassade providers** - Konfigurera andra SMS-providrar med hjälp av anpassad API-integrering. [Läs mer](sms-configuration-custom.md)

**URL-förkortning och -spårning**

Lägg till förkortade, spårbara URL:er i era meddelanden för att övervaka engagemanget. Underdomänskonfiguration krävs för förkortning av URL-adresser. [Lär dig konfigurera SMS-underdomäner](sms-subdomains.md)

**Hantering av avanmälan**

Säkerställ att branschens standarder och bestämmelser följs genom inbyggd hantering av avanmälan. Journey Optimizer hanterar automatiskt standardnyckelord för avanmälan (STOP, QUIT, CANCEL osv.) för Sinch- och Infobip-leverantörer. [Läs mer om hantering av avanmälan](sms-opt-out.md)

**Förhandsgranska och testa**

Testa textmeddelandena innan du skickar dem med testprofiler och exempeldata. Förhandsgranska personalisering, innehåll och formatering för att säkerställa att budskapen visas korrekt. [Lär dig skicka meddelanden](send-sms.md)

**Rapportering och analys**

Spåra resultatet av era SMS-kampanjer och resor med omfattande rapporteringsfunktioner:

* [Kampanjrapporter för SMS](../reports/campaign-global-report-cja-sms.md)
* [SMS-reserapporter](../reports/journey-global-report-cja-sms.md)

## Konfigurationskrav {#configuration-requirements}

Innan du skickar textmeddelanden måste du:

1. **Välj en SMS-provider** - Välj mellan Sinch, Twilio, Infobip eller konfigurera en anpassad provider
2. **Konfigurera API-autentiseringsuppgifter** - Integrera din leverantörs API-token och tjänst-ID med Journey Optimizer
3. **Skapa kanalkonfigurationer** - Konfigurera SMS-konfigurationer för marknadsföring och transaktionsmeddelanden
4. **Konfigurera underdomäner (valfritt)** - krävs bara om du tänker använda URL-förkortning i dina meddelanden

Dessa konfigurationssteg utförs vanligtvis av en systemadministratör. [Kom igång med SMS-konfiguration](sms-configuration.md)

## Snabbstartsguide {#quick-start}

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="sms-configuration.md">
<img alt="Validering" src="../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="sms-configuration.md"><strong>Konfigurera SMS-kanal</strong></a>
</div>
<p>Konfigurera din SMS-leverantör och kanal</p>
</td>
<td>
<a href="create-sms.md">
<img alt="Lead" src="../assets/do-not-localize/sms-create.jpeg">
</a>
<div><a href="create-sms.md"><strong>Skapa ett textmeddelande</strong></a>
</div>
<p>Designa och personalisera ert SMS-, MMS- eller RCS-material</p>
</td>
<td>
<a href="send-sms.md">
<img alt="Sällan" src="../assets/do-not-localize/sms-sending.jpg">
</a>
<div>
<a href="send-sms.md"><strong>Förhandsgranska och skicka</strong></a>
</div>
<p>Testa och skicka dina textmeddelanden till din publik</p>
</td>
<td>
<a href="sms-opt-out.md">
<img alt="Validering" src="../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-opt-out.md"><strong>Hantera avanmälan</strong></a>
</div>
<p>Hantera avbeställningar och säkerställ regelefterlevnaden</p>
</td>
</tr></table>

## Ytterligare resurser {#additional-resources}

Bläddra bland avsnitten nedan om du vill veta mer om textmeddelanden i Journey Optimizer.

+++Konfigurationsguider

Lär dig hur du konfigurerar och konfigurerar din SMS-miljö:

* [Översikt över konfiguration av SMS-kanal](sms-configuration.md)
* [Skapa SMS-kanalkonfigurationer](sms-configuration-surface.md)
* [Konfigurera SMS-underdomäner för URL-förkortning](sms-subdomains.md)

+++

+++Handböcker för providerinställningar

Stegvis konfiguration för varje SMS-tjänstleverantör:

* [Konfigurera Sinch-provider](sms-configuration-sinch.md)
* [Konfigurera Twilio-provider](sms-configuration-twilio.md)
* [Konfigurera Infobip-provider](sms-configuration-infobip.md)
* [Konfigurera anpassad SMS-provider](sms-configuration-custom.md)

+++

+++Skapa och hantera innehåll

Skapa, anpassa och hantera textmeddelandeinnehåll:

* [Skapa SMS/MMS-meddelanden](create-sms.md)
* [Förhandsgranska, testa och skicka meddelanden](send-sms.md)
* [Personalization i textmeddelanden](../personalization/personalize.md)
* [Dynamiskt innehåll](../personalization/get-started-dynamic-content.md)

+++

+++Efterlevnad och sekretess

Säkerställ att textmeddelandena följer gällande bestämmelser och sekretesskrav:

* [Hantering av avanmälan](sms-opt-out.md)
* [Sekretess och medgivande](../privacy/opt-out.md#opt-out-decision-management)

+++

+++Prestandaspårning

Övervaka och analysera era SMS-kampanjer och kundresan:

* [Kampanjrapporter för SMS](../reports/campaign-global-report-cja-sms.md)
* [SMS-reserapporter](../reports/journey-global-report-cja-sms.md)

+++

+++Integrering av resor och kampanjer

Lär dig hur ni kan införliva SMS i era kundresor och kampanjer:

* [Lägg till SMS-meddelanden på resor](../building-journeys/journeys-message.md)
* [Skapa SMS-kampanjer](../campaigns/create-campaign.md)

+++

## Instruktionsfilmer {#videos}

**Konfigurera och skicka SMS-meddelanden**

Lär dig hur du konfigurerar, redigerar och inkluderar SMS-meddelanden i dina kundresor.

+++Se videon

>[!VIDEO](https://video.tv.adobe.com/v/3428916?captions=swe&learn=on)

+++

**Utforska funktioner för mobilmeddelanden**

Upptäck de omfattande mobilmeddelandefunktionerna som Adobe Journey Optimizer erbjuder marknadsförarna.

+++Se videon

>[!VIDEO](https://video.tv.adobe.com/v/3430381?captions=swe&quality=12&learn=on)

+++

**Skicka profilerade RCS-meddelanden**

Lär dig hur du konfigurerar och skickar varumärkesanpassade, interaktiva RCS-meddelanden i Adobe Journey Optimizer med en anpassad SMS-leverantör.

+++Se videon

>[!VIDEO](https://video.tv.adobe.com/v/3464759?captions=swe)

+++

**Relaterade ämnen**

* [Lägg till meddelanden under resor](../building-journeys/journeys-message.md)
* [Skapa marknadsföringskampanjer](../campaigns/create-campaign.md)
* [Skyddsritningar och begränsningar](../start/guardrails.md#sms-guardrails)
* [Självstudiekurser för SMS och mobilmeddelanden](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview){target="_blank"}
