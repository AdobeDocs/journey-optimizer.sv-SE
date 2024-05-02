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
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 23%

---

# Använd anpassade åtgärder {#use-custom-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom"
>title="Anpassade åtgärder"
>abstract="Med anpassade åtgärder kan du konfigurera anslutningar med ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast."

Med anpassade åtgärder kan du konfigurera anslutningar med ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast.

## Samtycke- och datahantering {#privacy}

I Journey Optimizer kan du tillämpa policyer för datastyrning och samtycke på anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem eller utesluta kunder som inte har samtyckt till att ta emot e-post, push eller SMS-kommunikation. Mer information finns på följande sidor:

* [Datastyrning](../action/action-privacy.md).
* [Godkännande](../action/consent.md).

## URL-konfiguration

Konfigurationsrutan för **Anpassad åtgärd** aktiviteten visar URL-konfigurationsparametrarna och autentiseringsparametrarna som har konfigurerats för den anpassade åtgärden. Du kan inte konfigurera den statiska delen av URL-adressen i resan, utan i den globala konfigurationen för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

### Dynamisk sökväg

Om URL:en innehåller en dynamisk sökväg anger du sökvägen i **[!UICONTROL Path]** fält.

Om du vill sammanfoga fält och enkla textsträngar använder du strängfunktionerna eller plustecknet (+) i den avancerade uttrycksredigeraren. Omsluter enkla textsträngar med enkla citattecken (&#39;) eller inom dubbla citattecken (&quot;). [Läs mer](expression/expressionadvanced.md).

I den här tabellen visas ett exempel på konfiguration:

| Fält | Värde |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Sökväg | `The _id + '/messages'` |

Den sammanfogade URL:en har följande format:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;id>`/messages`

![](assets/journey-custom-action-url.png)

### Huvuden och frågeparametrar {#headers}

The **[!UICONTROL URL Configuration]** -avsnittet visar de dynamiska huvud- och frågeparameterfälten, men inte konstantfälten. Dynamiska huvud- och frågeparameterfält definieras som variabler i åtgärdskonfigurationsfönstret. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)

Om du vill ange värdet för dynamiska huvud- och frågeparameterfält klickar du i fältet eller på pennikonen och markerar önskat fält.

![](assets/journey-dynamicheaderfield.png)

## Åtgärdsparametrar

I **[!UICONTROL Action parameters]** visas meddelandeparametrar som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (till exempel händelser, datakällor), skicka värden manuellt eller använda den avancerade uttrycksredigeraren för avancerade användningsfall. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. Se detta [page](expression/expressionadvanced.md).

**Relaterade ämnen**

[Konfigurera en åtgärd](../action/about-custom-action-configuration.md)
