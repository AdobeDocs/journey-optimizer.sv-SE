---
solution: Journey Optimizer
product: journey optimizer
title: Använd anpassade åtgärder
description: Lär dig hur du använder anpassade åtgärder
feature: Journeys, Actions, Custom Actions
topic: Content Management
role: User, Developer
level: Intermediate
keywords: åtgärd, anpassad, API, resa, konfiguration, tjänst
exl-id: 2b1b3613-3096-43ec-a860-600dda1d83b2
version: Journey Orchestration
source-git-commit: 221368c7766e942143639fcd554b32f9de5ab0c9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 17%

---

# Använd anpassade åtgärder {#use-custom-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom"
>title="Anpassade åtgärder"
>abstract="Med anpassade åtgärder kan du konfigurera anslutningar med ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast."

Använd anpassade åtgärder för att aktivera anslutning till ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast.

Läs mer om anpassade åtgärder i [det här avsnittet](../action/action.md).

Lär dig skapa och konfigurera en anpassad åtgärd på [den här sidan](../action/about-custom-action-configuration.md).

Lär dig hur du använder API-anropssvar från anpassade åtgärder för personalisering på [den här sidan](../action/action-response.md).

## Samtycke- och datahantering {#privacy}

I Journey Optimizer kan du tillämpa policyer för datastyrning och samtycke på anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem eller utesluta kunder som inte har samtyckt till att ta emot e-post, push eller SMS-kommunikation. Mer information finns på följande sidor:

* [Datastyrning](../action/action-privacy.md).
* [Samtycke](../action/consent.md).

## URL-konfiguration

Konfigurationsrutan för aktiviteten **Anpassad åtgärd** visar URL-konfigurationsparametrarna och autentiseringsparametrarna som har konfigurerats för den anpassade åtgärden. Du kan inte konfigurera den statiska delen av URL-adressen i resan, utan i den globala konfigurationen för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

### Dynamisk sökväg

Om URL:en innehåller en dynamisk sökväg anger du sökvägen i fältet **[!UICONTROL Path]**.

Om du vill sammanfoga fält och enkla textsträngar använder du strängfunktionerna eller plustecknet (+) i den avancerade uttrycksredigeraren. Omsluter enkla textsträngar med enkla citattecken (&#39;) eller inom dubbla citattecken (&quot;). [Läs mer](expression/expressionadvanced.md).

I den här tabellen visas ett exempel på konfiguration:

| Fält | Värde |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Sökväg | `The _id + '/messages'` |

Den sammanfogade URL:en har följande format:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;ID>`/messages`

![](assets/journey-custom-action-url.png)

### Huvuden och frågeparametrar {#headers}

Avsnittet **[!UICONTROL URL Configuration]** visar de dynamiska huvud- och frågeparameterfälten, men inte konstantfälten. Dynamiska huvud- och frågeparameterfält definieras som variabler i åtgärdskonfigurationsfönstret. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)

Om du vill ange värdet för dynamiska huvud- och frågeparameterfält klickar du i fältet eller på pennikonen och markerar önskat fält.

![](assets/journey-dynamicheaderfield.png)

## Åtgärdsparametrar

I avsnittet **[!UICONTROL Action parameters]** ser du meddelandeparametrarna som är definierade som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (till exempel händelser, datakällor), skicka värden manuellt eller använda den avancerade uttrycksredigeraren för avancerade användningsfall. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. Se den här [sidan](expression/expressionadvanced.md).

