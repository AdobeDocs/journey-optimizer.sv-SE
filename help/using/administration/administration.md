---
title: Tekniska inställningar
description: Läs riktlinjer för administration och inställningar
hidefromtoc: true
hide: true
source-git-commit: 8a94c63b4a0cba1014e9778caa24720fb975ae52
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 6%

---

# Tekniska inställningar

![](../assets/do-not-localize/badge.png)

## Ställ in brandingsparametrar{#cjm-branding}

Alla företag har grafiska och tekniska riktlinjer. Du kan definiera en uppsättning specifikationer för att presentera ett konsekvent varumärke för dina kunder, från logotyper till tekniska aspekter som e-postavsändare, domänen för spegelsidans URL eller inställningar för meddelandespårning.
Varumärken kan inte skapas eller ändras av slutanvändare: den här konfigurationen hanteras av Adobe.

Om du vill ställa in brandingsparametrar för din [!DNL Journey Optimizer]-instans måste du kontakta Adobe och dela följande information:

* Företag

* Avsändarens (Från) e-postadress

* Avsändarens (från) namn

* Svarsadress

När du har konfigurerat profileringsparametrarna kan du välja dem när du skapar meddelanden.

När du har konfigurerat profileringsparametrarna kan du välja dem när du skapar meddelanden från **[!UICONTROL Presets]**-listan. [Läs mer om att skapa](../create-message.md) innehåll.

## Konfigurera push-meddelandekanalen

Lär dig hur du konfigurerar push-kanalen i det här [avsnittet](../create-push.md).

## Delegering till underdomän

För alla nya underdomäner som ska användas i [!DNL Journey Optimizer] är det första steget att delegera den. Du måste kontakta din tekniska kontakt i Adobe.

När du implementerar en lösning finns det krav för externt vända komponenter: dessa innehåller bland annat inställningar av länkar och webbsidor som ska spåras, visning av spegelsidor.

Dessa krav hanteras via komponenter som finns både på Adobe och hos kunden, men de innehåller URL:er som kan ses av mottagarna av e-postmeddelandena.  För att undvika att ha URL:er som anger den underliggande tekniska lösningen eller värdtjänstleverantören, kan underdomäner konfigureras så att de blir genomskinliga för e-postmeddelandets mottagare.

Efter dessa delegeringar säkerställer den infrastruktur som Adobe har infört att följande tjänster utförs för varje delegerad eller CNAME-utjämnad sändande domän:

* Skapa inkorg för postmaster@ och missbruk@

* Konfigurera feedbackloopar för den delegerade domänen

* Grundläggande DMARC-postkonfiguration

Parametrar som har upprättats av Adobe är endast giltiga från den tidpunkt då delegeringen slutfördes och sedan verifierades av Adobe, och fungerar fortfarande.

[Läs mer om domändelegering](https://helpx.adobe.com/se/campaign/kb/domain-name-delegation.html).


## Skapa datakällor, händelser och åtgärder

Använd avsnittet **[!UICONTROL Admin]** för att hantera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**.

![](../assets/admin-menu.png)

### Datakällor

Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor.

Läs mer om datakällor i det här [avsnittet](../datasource/about-data-sources.md)

### Händelser

Med händelser kan ni utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som flyger in på resan.

I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK).

Läs mer om händelser i det här [avsnittet](../event/about-events.md)

### Instruktioner

[!DNL Journey Optimizer] meddelandefunktionerna är inbyggda: behöver du bara utforma innehållet och publicera meddelandet. Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd.

Läs mer om åtgärder i det här [avsnittet](../action/action.md)
