---
solution: Journey Optimizer
product: journey optimizer
title: Journey Orchestration - fullständig guide
description: Omfattande guide för att komma igång med resesamordning i Adobe Journey Optimizer
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
keywords: resa, orkestrering, komma igång, introduktion, funktioner
source-git-commit: 902790b2e172ef02e868592794fc110d3e14ac07
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---


# Journey Orchestration - fullständig guide{#journey-orchestration-guide}

Med resor i Adobe Journey Optimizer kan ni skapa personaliserade kundresor i flera steg som i realtid anpassar sig efter målgruppens beteende och behov. Med en intuitiv dra-och-släpp-arbetsyta kan ni samordna meddelanden och åtgärder i flera kanaler och utnyttja sammanhangsberoende data och målgruppsanpassning för maximal effekt.

Oavsett om ni utforskar triggers i realtid, hanterar reseegenskaper eller använder avancerade verktyg som anpassade åtgärder och uttryck, ger den här guiden en tydlig färdplan för att utforma och förfina resor som levererar meningsfulla och vältajmade kundupplevelser.

➡️ [Upptäck Journey Optimizer i video](#video)

>[!BEGINTABS]

>[!TAB Översikt]

## Vad är resor?

Använd [!DNL Journey Optimizer] för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor. Utforma avancerade scenarier i flera steg som svarar på kundbeteenden och affärshändelser i realtid.

Journey Optimizer resedesigner har allt som marknadsförare och reseansvariga behöver för att samordna flerstegsresor i :1 olika kanaler. Detta inkluderar en intuitiv dra-och-släpp-arbetsyta för att samordna varje steg av resan, definiera målgruppen och inkludera de meddelanden, erbjudanden och innehåll i olika kanaler som målgruppsmedlemmarna kan se baserat på beteende, kontextuella data och affärshändelser.

![Resedesignerns gränssnitt med palett, arbetsyta och egenskapspanelen](assets/journey38.png)

**Vill du börja bygga?** Lär dig hur du skapar och utformar din första resa på [den här sidan](journey-gs.md).

>[!TAB Nyckelfunktioner]

## Vad kan du göra med resor?

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/send-real-time.svg)

**Realtid och batchleverans**

Skicka **enhetsleverans** i realtid när en händelse tas emot, eller **i batch** med Adobe Experience Platform-målgrupper.

[Läs mer om reseanmälan](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/data.svg)

**Sammanhangsberoende data**

Utnyttja **sammanhangsbaserade data** från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part.

[Arbeta med datakällor](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/message.svg?lang=sv-SE)

**Inbyggda åtgärder**

Använd **inbyggda kanalåtgärder** för att skicka meddelanden som är utformade i [!DNL Journey Optimizer] via e-post, push, SMS/MMS med mera.

[Skicka meddelanden under resor](journeys-message.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code.svg?lang=sv-SE)

**Anpassade åtgärder**

Skapa **anpassade åtgärder** om du använder ett tredjepartssystem för att skicka meddelanden eller ansluta till externa API:er.

[Konfigurera anpassade åtgärder](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/canvas.svg)

**Designer för visuell resa**

Med **resedesignern** kan du skapa dina flerstegsfall: enkelt dra och släppa en anmälningshändelse eller en läsningsaktivitet, lägga till villkor och skicka personaliserade meddelanden.

[Utforska resedesignern](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/test.svg)

**Testa och optimera**

Testa dina resor innan du publicerar, övervaka deras prestanda och optimera leveransen med avancerade funktioner som optimering vid sändning.

[Testa och publicera resor](testing-the-journey.md)
:::

::::

>[!TAB Användningsexempel]

## Exempel på verkliga resor

Inom resedesignern kan marknadsförarna skicka :1-meddelanden i realtid via valfri kanal när en händelse inträffar. När en kund prenumererar på en tjänst kan den till exempel [utlösa ett välkomstmeddelande](message-to-subscribers-uc.md) som uppmanar dem att logga in i appen för första gången och ange sina inställningar. Åtgärder som att slutföra köpet, öppna e-postmeddelandet och logga in i appen kan användas för att locka nya kunder genom deras resor.

### Vanliga användningsfall för resor

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/email.svg)

**Välkommen nya prenumeranter**

Skicka en personlig välkomstresa när kunderna prenumererar på tjänsten och vägleder dem genom introduktionssteg.

[Läs mer](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar.svg?lang=sv-SE)

**Optimera e-posttider**

Använd AI-baserad optimering för sändningstid för att leverera e-postmeddelanden när varje kund är mest benägen att engagera sig.

[Läs mer](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/delivery.svg)

**Dra upp leveranser**

Öka volymen för meddelanden gradvis för att värma upp ert anseende och undvika leveransproblem.

[Läs mer](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/targeting.svg)

**Mål efter veckodag**

Skicka olika innehåll baserat på vilken veckodag kunderna kommer in på din resa.

[Läs mer](weekday-email-uc.md)
:::

::::

### Fler användningsexempel

[Resedesignern](using-the-journey-designer.md) innehåller [inbyggda kanalåtgärder](journeys-message.md) som stöder utgående meddelanden, t.ex. e-post, push-meddelanden och SMS/MMS, samt inkommande kanaler, inklusive mobilappar, webbplatser och kodbaserade upplevelser som skapats direkt i Journey Optimizer. Du kan också använda tredjepartssystem för att skicka meddelanden - Journey Optimizer innehåller [anpassade åtgärder](using-custom-actions.md) som gör att dessa system kan integreras på resorna direkt från resedesignern.

**Utforska alla användningsexempel för resan** på [den här sidan](jo-use-cases.md) för att identifiera scenarier från början till slut som du kan implementera.

>[!NOTE]
>
>Resegarantier och begränsningar finns på [den här sidan](../start/guardrails.md)

>[!TAB Utbildningsresurser]

## Bygg huvudresan

### Videosjälvstudiekurs {#video}

Identifiera komponenterna i en resa och förstå grunderna för hur man bygger en resa på arbetsytan.

>[!VIDEO](https://video.tv.adobe.com/v/3430354?captions=swe&quality=12)

### Utforska efter ämne

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=sv-SE)

**Skapa och hantera resor**

Stegvisa riktlinjer för att utforma, testa, publicera och spåra kundresor för att skapa personaliserade flerkanalskampanjer.

[Utforska skapandet av resan](/help/rp_landing_pages/create-journey-landing-page.md) | [Lär dig resehantering](/help/rp_landing_pages/manage-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg?lang=sv-SE)

**Reseaktiviteter**

Upptäck hur ni konfigurerar och använder aktiviteter som triggers, beslutssteg, målgruppshantering och personaliserade meddelanden på resorna.

[Utforska aktiviteter](/help/rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=sv-SE)

**Uttryck och villkor**

Masteruttryck för dynamiska arbetsflöden, datamanipulering och avancerad resesamordning med kraftfulla verktyg och syntax.

[Läs mer om uttryck](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/monitor.svg)

**Felsök och övervaka**

Diagnostisera och åtgärda problem med körning av resor med verktyg, felkoder och bästa praxis för felsökning och optimering.

[Felsökningsguide](/help/rp_landing_pages/troubleshoot-journey-landing-page.md)
:::

::::

### Ytterligare resurser

* **[Vanliga frågor om resan](journey-faq.md)** - Vanliga frågor om resor
* **[Felkodsreferens](error-codes-reference.md)** - Resefelkoder och felsökningssteg
* **[Varningar](../reports/alerts.md)** - Konfigurera aviseringar för reseövervakning
* **[Felsökning](troubleshooting.md)** - Vanliga reseproblem och lösningar
* **[Självstudiekurser på resa](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** - Lär dig hur du skapar resor med praktiska videokurser

>[!ENDTABS]

