---
title: Använd anpassade åtgärder
description: Lär dig hur du använder anpassade åtgärder
feature: Actions
topic: Content Management
role: User
level: Intermediate
exl-id: 2b1b3613-3096-43ec-a860-600dda1d83b2
source-git-commit: 951799a9986e4fd293f282ecf82496e5e7f2da9e
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 24%

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
| Bana | `The id of marketingCampaign + '/messages'` |

Den sammanfogade URL:en har följande format:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](assets/journey-custom-action-url.png)

### Sidhuvuden

The **[!UICONTROL URL Configuration]** -avsnittet visar de dynamiska rubrikfälten, men inte de konstanta rubrikfälten. Dynamiska rubrikfält är HTTP-rubrikfält vars värde är konfigurerat som en variabel. [Läs mer](../action/about-custom-action-configuration.md).

Ange vid behov värdet för dynamiska rubrikfält:

1. Välj den anpassade åtgärden under resan.
1. Klicka på pennikonen bredvid rubrikfältet i konfigurationsfönstret **[!UICONTROL URL Configuration]** -avsnitt.

   ![](assets/journey-dynamicheaderfield.png)

1. Markera ett fält och klicka på **[!UICONTROL OK]**.

## Åtgärdsparametrar

I **[!UICONTROL Action parameters]** visas meddelandeparametrar som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (exempel: händelser, datakällor), skicka värden manuellt eller använd den avancerade uttrycksredigeraren för avancerade användningsområden. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. Se detta [page](expression/expressionadvanced.md).

**Relaterade ämnen**

[Konfigurera en åtgärd](../action/about-custom-action-configuration.md)
