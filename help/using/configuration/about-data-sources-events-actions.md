---
title: Konfigurera resor
description: Lär dig hur du konfigurerar datakällor, händelser och åtgärder.
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: c144d44f-031f-4ca2-800e-d3878af400a5
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 44%

---

# Konfigurera resor {#configure-journeys}

För att kunna skicka meddelanden med resor måste du konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**.

![](assets/admin-menu.png)

## Datakällor {#data-sources}

Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor. [Läs mer](../../using/datasource/about-data-sources.md)

## Händelser {#events}

Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan.

I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK). [Läs mer](../../using/event/about-events.md)

## Instruktioner {#actions}

Journey Optimizer meddelandefunktioner är inbyggda: behöver du bara utforma innehållet och publicera meddelandet. Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. [Läs mer](../../using/action/action.md)

## Bläddra bland Adobe Experience Platform-fält {#friendly-names-display}

När du definierar [händelsers nyttolast](../event/about-creating.md#define-the-payload-fields), [fältgruppers nyttolast](../datasource/configure-data-sources.md#define-field-groups) och väljer fält i [uttrycksredigeraren](../building-journeys/expression/expressionadvanced.md) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen.

Om beskrivningar som &quot;xdm:alternateDisplayInfo&quot; anges när du ställer in scheman, ersätts visningsnamnen med de användarvänliga namnen. Det är särskilt användbart när du arbetar med&quot;eVars&quot; och generiska fält. Du kan konfigurera egna namnbeskrivningar via ett API-anrop. Mer information finns i [Utvecklarhandbok för schemaregister](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html){target=&quot;_blank&quot;}.

![](assets/xdm-from-descriptors.png)

Om användarvänliga namn finns visas fältet som `<friendly-name>(<name>)`. Om det inte finns något användarvänligt namn visas till exempel visningsnamnet som `<display-name>(<name>)`. Om inget av dem är definierade visas bara fältets tekniska namn `<name>`.

>[!NOTE]
>
>Användarvänliga namn hämtas inte när du väljer fält från en sammanslutning av scheman.