---
solution: Journey Optimizer
product: journey optimizer
title: Hantera avanmälan
description: Lär dig hur du hanterar avanmälan och sekretess
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 8b459f71852d031dc650b77725bdc693325cdb1d
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 1%

---

# Hantera avanmälan {#consent}

Att ge mottagarna möjlighet att avbryta prenumerationen på information från ett varumärke är ett juridiskt krav, liksom att se till att detta val respekteras. Läs mer om gällande lagstiftning i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html#regulations){target="_blank"}.

**Varför är det viktigt?**

* Om ni inte följer dessa regler medför detta juridiska risker för ert varumärke.
* Det hjälper er att undvika att skicka oombedda meddelanden till era mottagare, vilket kan få dem att märka era meddelanden som skräppost och skada ert rykte.

## Hantera avbeställningar under resor och kampanjer {#opt-out-ajo}

När ni skickar meddelanden från resor eller kampanjer måste ni alltid se till att kunderna kan avbeställa dem från framtida kommunikation. När prenumerationen har avbrutits tas profilerna automatiskt bort från målgruppen för framtida marknadsföringsmeddelanden.

while **[!DNL Journey Optimizer]** innehåller sätt att hantera avanmälan i e-postmeddelanden och SMS-meddelanden. Push-meddelanden kräver ingen åtgärd från din sida, eftersom mottagarna kan avbeställa prenumerationen via sina enheter. När du till exempel hämtar eller använder programmet kan de välja att stoppa meddelanden. På samma sätt kan de ändra meddelandeinställningarna via det mobila operativsystemet.

Lär dig hur du hanterar avanmälan i Journey Optimizer e-post och SMS-meddelanden i följande avsnitt:

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../email/email-opt-out.md">
<img alt="Lead" src="../assets/do-not-localize/privacy-email-optout.jpeg" width="50%">
</a>
<div><a href="../email/email-opt-out.md"><strong>Hantering av avanmälan via e-post</strong>
</div>
<p>
</td>
<td>
<a href="../sms/sms-opt-out.md">
<img alt="Sällan" src="../assets/do-not-localize/privacy-sms-opt-out.jpeg" width="50%">
</a>
<div>
<a href="../sms/sms-opt-out.md"><strong>Hantering av SMS-avanmälan</strong></a>
</div>
<p></td>
</tr></table>

>[!NOTE]
>
>I [!DNL Journey Optimizer], samtycke hanteras av Experience Platform [Samtyckesschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target="_blank"}. By default, the value for the consent field is empty and treated as consent to receive your communications. You can modify this default value while onboarding to one of the possible values listed [here](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html#choice-values){target="_blank"}.

## Genomför personalisering {#opt-out-personalization}

Era kunder kan också välja bort att presenteras som personaliserat innehåll. När en profil har valt bort personalisering måste ni se till att deras data inte används för personalisering och ni måste ersätta allt personaliserat innehåll med en reservvariant.

### Beslutsförvaltning

När du utnyttjar erbjudanden implementeras inte personaliseringsinställningar automatiskt i [beslutsomfattningar](../offers/offer-activities/create-offer-activities.md#add-decision-scopes) används från en [beslut](../offers/api-reference/offer-delivery-api/decisioning-api.md) API-begäran eller [kantavkänning](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md) API-begäran. I det här fallet måste du manuellt framtvinga godkännande av personalisering. För att göra detta, följ nedanstående steg.

>[!NOTE]
>
>Beslutsomfattningar som används i [!DNL Journey Optimizer] skapade kanaler uppfyller detta krav från den resa eller kampanj de tillhör.



1. Skapa en [Adobe Experience Platform segment](../segment/about-segments.md) med ett profilattribut som: *&quot;Godkännande av personalisering = sant&quot;* för målanvändare som har samtyckt till personalisering.

1. När en [beslut](../offers/offer-activities/create-offer-activities.md), lägger till ett beslutsomfång och definierar ett villkor för behörighet baserat på det här segmentet för varje samling av utvärderingskriterier som innehåller personaliserade erbjudanden.

1. Skapa en [grunderbjudande](../offers/offer-library/creating-fallback-offers.md) som inte innehåller personaliserat innehåll.

1. [Tilldela](../offers/offer-activities/create-offer-activities.md#add-fallback) det icke-personaliserade reserverbjudandet till beslutet.

1. [Granska och spara](../offers/offer-activities/create-offer-activities.md#review) beslutet.

Om en användare har:

* som har samtyckt till personalisering kommer beslutsomfånget att avgöra vilket som är det bästa erbjudandet för den profilen.

* inte samtycker till personalisering, kommer motsvarande profil inte att vara berättigad till något av de erbjudanden som finns i utvärderingskriterierna och kommer därför att få det icke-personaliserade reserverbjudandet.

>[!NOTE]
>
>Medgivande för att profildata används i [datamodellering](../offers/ranking/ai-models.md) stöds inte ännu [!DNL Journey Optimizer].

