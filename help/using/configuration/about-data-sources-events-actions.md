---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera resor
description: Lär dig konfigurera datakällor, händelser och åtgärder
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
keywords: konfiguration, resa, kontrollpanel, datakällor, händelser, åtgärder
exl-id: c144d44f-031f-4ca2-800e-d3878af400a5
source-git-commit: 65b7b8323e37a0143a3941af1b9c2fb8b595a376
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 28%

---

# Konfigurera datakällor, händelser och åtgärder {#configure-journeys}

>[!CONTEXTUALHELP]
>id="ajo_journey_configuration_dashboard"
>title="Om konfiguration av resan"
>abstract="För att kunna skicka meddelanden med resor måste du konfigurera datakällor, händelser och åtgärder. Med datakällor kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel under dina förhållanden. Med händelser kan du utlösa dina resor när en händelse tas emot. Med anpassade åtgärder kan du ansluta till ett tredjepartssystem för att skicka meddelanden. Om du använder Journey Optimizer inbyggda meddelandefunktioner behöver du inte konfigurera någon åtgärd."

Du måste konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]** för att kunna skicka meddelanden med resor.

![](assets/admin-menu.png)

Du kan också konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du till exempel berika dina resor med data från ett externt bokningssystem eller skicka meddelanden med ett tredjepartssystem som Epsilon eller Facebook. Lär dig [integrera Journey Optimizer med externa system](external-systems.md).

## Datakällor {#data-sources}

Med Data Source-konfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. [Läs mer](../../using/datasource/about-data-sources.md)

## Händelser {#events}

Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan.

I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API:er för direktuppspelning av inmatning för autentiserade och oautentiserade händelser (t.ex. Adobe Mobile SDK-händelser). [Läs mer](../../using/event/about-events.md)

## Instruktioner {#actions}

Journey Optimizer meddelandefunktioner är inbyggda: du behöver bara lägga till en kanalåtgärd på din resa. Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. [Läs mer](../../using/action/action.md)

## Bläddra bland Adobe Experience Platform-fält {#friendly-names-display}

När du definierar [händelsers nyttolast](../event/about-creating.md#define-the-payload-fields), [fältgruppers nyttolast](../datasource/configure-data-sources.md#define-field-groups) och väljer fält i [uttrycksredigeraren](../building-journeys/expression/expressionadvanced.md) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen.

Om beskrivningar som &quot;xdm:alternateDisplayInfo&quot; anges när du ställer in scheman, ersätts visningsnamnen med de användarvänliga namnen. Det är särskilt användbart när du arbetar med&quot;eVars&quot; och generiska fält. Du kan konfigurera egna namnbeskrivningar via ett API-anrop. Mer information finns i [utvecklarhandboken för schemaregister](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=sv-SE){target="_blank"}.

![](assets/xdm-from-descriptors.png)

Om användarvänliga namn finns visas fältet som `<friendly-name>(<name>)`. Om det inte finns något användarvänligt namn visas till exempel visningsnamnet som `<display-name>(<name>)`. Om inget av dem är definierade visas bara fältets tekniska namn `<name>`.

>[!NOTE]
>
>Användarvänliga namn hämtas inte när du väljer fält från en sammanslutning av scheman.
