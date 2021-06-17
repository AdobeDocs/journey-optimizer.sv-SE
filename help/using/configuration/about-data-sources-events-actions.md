---
title: Administration och inställningar
description: Läs riktlinjer för administration och inställningar
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: 344bcff33895867d650f98b778cdf76c52a4b75e
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 47%

---

# Konfigurera resor

För att kunna skicka meddelanden med resor måste du konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**.

![](../assets/admin-menu.png)

## Datakällor

Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor. [Läs mer](../../using/datasource/about-data-sources.md)

## Händelser

Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan.

I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK). [Läs mer](../../using/event/about-events.md)

## Instruktioner

Journey Optimizer meddelandefunktioner är inbyggda: behöver du bara utforma innehållet och publicera meddelandet. Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. [Läs mer](../../using/action/action.md)

## Bläddra bland Adobe Experience Platform-fält {#friendly-names-display}

När du definierar [händelsers nyttolast](../event/about-creating.md#define-the-payload-fields), [fältgruppers nyttolast](../datasource/configure-data-sources.md#define-field-groups) och väljer fält i [uttrycksredigeraren](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/expressionadvanced.html) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen.

Om beskrivningar som &quot;xdm:alternateDisplayInfo&quot; anges när du ställer in scheman, ersätts visningsnamnen med de användarvänliga namnen. Det är särskilt användbart när du arbetar med&quot;eVars&quot; och generiska fält. Du kan konfigurera egna namnbeskrivningar via ett API-anrop. Mer information finns i [utvecklarhandboken för schemaregister](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](../assets/xdm-from-descriptors.png)

Om användarvänliga namn finns visas fältet som `<friendly-name>(<name>)`. Om det inte finns något användarvänligt namn visas till exempel visningsnamnet som `<display-name>(<name>)`. Om inget av dem är definierade visas bara fältets tekniska namn `<name>`.

>[!NOTE]
>
>Användarvänliga namn hämtas inte när du väljer fält från en sammanslutning av scheman.