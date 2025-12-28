---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med resor
description: Kom igång med resor
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: resa, upptäckt, komma igång
exl-id: 73cfd48b-72e6-4b72-bbdf-700a32a34bda
version: Journey Orchestration
source-git-commit: 4b78a7b2b4c437882c5e760efac1120e004bf640
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 0%

---


# Kom igång med resor{#jo-general-principle}

Med resor i Adobe Journey Optimizer kan ni skapa personaliserade kundresor i flera steg som i realtid anpassar sig efter målgruppens beteende och behov. Med en intuitiv dra-och-släpp-arbetsyta kan ni samordna meddelanden och åtgärder i flera kanaler och utnyttja sammanhangsberoende data och målgruppsanpassning för maximal effekt.

Oavsett om ni utforskar triggers i realtid, hanterar reseegenskaper eller använder avancerade verktyg som anpassade åtgärder och uttryck, ger den här guiden en tydlig färdplan för att utforma och förfina resor som levererar meningsfulla och vältajmade kundupplevelser.

## Vad är resor?

Använd [!DNL Journey Optimizer] för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor. Utforma avancerade scenarier i flera steg som svarar på kundbeteenden och affärshändelser i realtid.

Journey Optimizer resedesigner har allt som marknadsförare och reseansvariga behöver för att samordna flerstegsresor i :1 olika kanaler. Detta inkluderar en intuitiv dra-och-släpp-arbetsyta för att samordna varje steg av resan, definiera målgruppen och inkludera de meddelanden, erbjudanden och innehåll i olika kanaler som målgruppsmedlemmarna kan se baserat på beteende, kontextuella data och affärshändelser.

![Resedesignerns gränssnitt med palett, arbetsyta och egenskapspanelen](assets/journey38.png)

**Vill du börja bygga?** Lär dig hur du skapar och utformar din första resa på [den här sidan](journey-gs.md).

## Viktiga funktioner {#capabilities}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**Realtid och batchleverans**

Skicka **enhetsleverans** i realtid när en händelse tas emot, eller **i batch** med Adobe Experience Platform-målgrupper.

[Läs mer om reseanmälan](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**Sammanhangsberoende data**

Utnyttja **sammanhangsbaserade data** från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part.

[Arbeta med datakällor](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**Inbyggda åtgärder**

Använd **inbyggda kanalåtgärder** för att skicka meddelanden som är utformade i [!DNL Journey Optimizer] via e-post, push, SMS/MMS med mera.

[Skicka meddelanden under resor](journeys-message.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**Anpassade åtgärder**

Skapa **anpassade åtgärder** om du använder ett tredjepartssystem för att skicka meddelanden eller ansluta till externa API:er.

[Konfigurera anpassade åtgärder](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**Designer för visuell resa**

Med **resedesignern** kan du skapa dina flerstegsfall: enkelt dra och släppa en anmälningshändelse eller en läsningsaktivitet, lägga till villkor och skicka personaliserade meddelanden.

[Utforska resedesignern](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**Testa och optimera**

Testa dina resor innan du publicerar, övervaka deras prestanda och optimera leveransen med avancerade funktioner som optimering vid sändning.

[Testa och publicera resor](testing-the-journey.md)
:::

::::

➡️ [Upptäck Journey Optimizer i video](#video)

## Översikt över resor

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

Komma igång med att skapa resan

Stegvisa riktlinjer för att utforma, testa, publicera och spåra kundresor för att skapa personaliserade flerkanalskampanjer.

[Skapa den första resan](journey-gs.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

Hantera era resor

Hantera kundresor effektivt med verktyg för filtrering, profilhantering, tidszoner och optimeringstekniker.

[Lär dig resehantering](/help/rp_landing_pages/manage-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

Reseverksamhet

Upptäck hur ni konfigurerar och använder aktiviteter som triggers, beslutssteg, målgruppshantering och personaliserade meddelanden på resorna.

[Utforska aktiviteter](/help/rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

Skapar uttryck

Masteruttryck för dynamiska arbetsflöden, datamanipulering och avancerad resesamordning med kraftfulla verktyg och syntax.

[Läs mer om uttryck](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

Användningsexempel på resa

Utforska verkliga program i Adobe Journey Optimizer, inklusive meddelanden i flera kanaler och integration med externa system.

[Upptäck användningsexempel](/help/rp_landing_pages/journey-use-cases-landing-page.md)
:::

::::

## Användningsexempel {#use-cases}

Inom resedesignern kan marknadsförarna skicka :1-meddelanden i realtid via valfri kanal när en händelse inträffar. När en kund prenumererar på en tjänst kan den till exempel [utlösa ett välkomstmeddelande](message-to-subscribers-uc.md) som uppmanar dem att logga in i appen för första gången och ange sina inställningar. Åtgärder som att slutföra köpet, öppna e-postmeddelandet och logga in i appen kan användas för att locka nya kunder genom deras resor.

[Resedesignern](using-the-journey-designer.md) innehåller [inbyggda kanalåtgärder](journeys-message.md) som stöder utgående meddelanden, t.ex. e-post, push-meddelanden och SMS/MMS, samt inkommande kanaler, inklusive mobilappar, webbplatser och kodbaserade upplevelser som skapats direkt i Journey Optimizer. Du kan också använda tredjepartssystem för att skicka meddelanden - Journey Optimizer innehåller [anpassade åtgärder](using-custom-actions.md) som gör att dessa system kan integreras på resorna direkt från resedesignern.


:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**Lär dig mer med användningsexempel**

Utforska omfattande fallstudier av hela kundresan som visar på verkliga implementeringar och bästa praxis.

[Upptäck alla användningsfall](jo-use-cases.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**Välkommen nya prenumeranter**

Skicka en personlig välkomstresa när kunderna prenumererar på tjänsten och vägleder dem genom introduktionssteg.

[Läs mer](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**Optimera e-posttider**

Använd AI-baserad optimering för sändningstid för att leverera e-postmeddelanden när varje kund är mest benägen att engagera sig.

[Läs mer](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**Dra upp leveranser**

Öka volymen för meddelanden gradvis för att värma upp ert anseende och undvika leveransproblem.

[Läs mer](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**Mål efter veckodag**

Skicka olika innehåll baserat på vilken veckodag kunderna kommer in på din resa.

[Läs mer](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/question.svg)

**Vanliga frågor om resan**

Hitta svar på vanliga frågor om reseuppbyggnad, felsökning och metodtips.

[Visa vanliga frågor](journey-faq.md)
:::

::::

## Resetyper

Adobe Journey Optimizer har stöd för fyra olika typer av resor, var och en utformade för olika användningsfall och inresemekanismer. Välj rätt typ baserat på hur ni vill att profilerna ska gå igenom era kundupplevelser och utvecklas.

>[!BEGINTABS]

>[!TAB Unitära resor]

**Unitära resor** utlöses individuellt av en händelse när en viss åtgärd inträffar, till exempel ett köp, en appinloggning eller en formuläröverföring. Profiler tar sig in på resan en i taget när evenemanget tas emot, vilket gör det idealiskt för personaliserade, beteendestyrda upplevelser.

**Viktiga egenskaper:**

* Händelsestyrd post i realtid
* Individuell profilbearbetning
* Perfekt för transaktionsmeddelanden och omedelbara svar
* Stöder kontextuella data från utlösarhändelsen

**Användningsexempel:**

* Orderbekräftelse efter köp
* Välkomstmeddelande när någon prenumererar
* Övergivna kundvagnar orsakade av surfbeteende
* Meddelanden om återställning av lösenord

➡️ [Lär dig mer om händelsekonfiguration](../event/about-events.md) | [Allmänna händelser](general-events.md) | [Meddelande till prenumeranter - användningsfall](message-to-subscribers-uc.md)

>[!TAB Läs målgruppsresor]

**Läs målgruppsresor** börjar med en målgrupp från Adobe Experience Platform och skickar meddelanden gruppvis till alla profiler i den målgruppen. Den här typen av resa bearbetar hela målgruppen samtidigt, vilket gör den idealisk för schemalagda kampanjer och återkommande kommunikation.

**Viktiga egenskaper:**

* Gruppbearbetning av målgruppssegment
* Schemalagd eller engångskörning
* Alla profiler anges samtidigt
* Stöder storskalig kommunikation

**Användningsexempel:**

* Månatliga nyhetsbrev
* Kampanjkampanjer för målgruppssegment
* Produktmeddelanden till alla kunder
* Säsongskampanjer

➡️ [Lär dig mer om aktiviteten Läs målgrupp](read-audience.md) | [Kom igång med målgrupper](../audience/about-audiences.md) | [Användning av flerkanalsmeddelanden &#x200B;](journeys-uc.md)

>[!TAB Målgruppskvalificeringsresor]

**Målgruppskvalificeringsresor** aktiveras när profiler kvalificerar sig för (eller avslutar) ett visst målgruppssegment. Profiler tar sig in på resan individuellt när de uppfyller målgruppskriterierna i realtid, vilket möjliggör ett omedelbart engagemang när kundbeteendet förändras.

**Viktiga egenskaper:**

* Kvalificeringsbaserad post i realtid
* Kontinuerlig övervakning av medlemskap för målgrupper
* Individuell profilbearbetning när de kvalificerar sig
* Bäst med direktuppspelande målgrupper

**Användningsexempel:**

* Meddelanden om uppgraderingar av VIP-nivå
* Engagera igen när kunderna blir inaktiva
* Första prisvärda meddelanden
* Geografisk målgruppsanpassning när kunderna flyttar

➡️ [Lär dig mer om Audience Qualification](audience-qualification-events.md) | [Villkorsaktivitet](condition-activity.md) | [Skapa segmentdefinitioner &#x200B;](../audience/creating-a-segment-definition.md)

>[!TAB Affärshändelseresor]

**Affärshändelseresor** utlöses av affärshändelser (till exempel aktieuppdateringar, vädervarningar eller prisändringar) som påverkar flera profiler samtidigt. I stället för att reagera på individuella kundaktiviteter svarar dessa resor på bredare affärsförhållanden eller externa faktorer.

**Viktiga egenskaper:**

* Utlöses av händelser på företagsnivå, inte av individuella åtgärder
* Påverkar flera profiler samtidigt
* Målgrupper för en viss målgrupp när händelsen inträffar
* Kombinerar händelsestyrd timing med målgruppsanpassning

**Användningsexempel:**

* Låga lagervarningar till intresserade kunder
* Flash, utskick
* Väderbaserade kampanjer
* Meddelande om prisfall
* Aviseringar om produkter som inte finns i lager

➡️ [Läs mer om affärshändelser](general-events.md) | [Konfigurera affärshändelser](../event/about-creating-business.md) | [Anmälningshantering](entry-management.md)

>[!ENDTABS]

## Journey Designer{#journey-designer}

[Resedesignern](using-the-journey-designer.md) innehåller allt som marknadsförare och resande personer behöver för att orkestrera flerstegsresor i :1 olika kanaler. Detta inkluderar en intuitiv dra-och-släpp-arbetsyta för att samordna varje steg av resan, definiera målgruppen och inkludera de meddelanden, erbjudanden och innehåll i olika kanaler som målgruppsmedlemmarna kan se baserat på beteende, kontextuella data och affärshändelser.

Resedesignern har allt du behöver för att skapa flerstegsupplevelser:

* **[Inbyggda kanalåtgärder](journeys-message.md)** - Skicka meddelanden via e-post, push-meddelanden, SMS/MMS, appar, webb, kodbaserade upplevelser med mera, allt utformat direkt i Journey Optimizer
* **[Anpassade åtgärder](using-custom-actions.md)** - Integrera tredjepartssystem för att skicka meddelanden eller utlösa arbetsflöden på externa plattformar
* **[Organisationsaktiviteter](about-journey-activities.md)** - Lägg till logik, villkor, väntetider och målgruppsanpassning för att skapa sofistikerade kundupplevelser
* **[Villkor](condition-activity.md)** - Fördela din resa baserat på profilattribut, målgruppsmedlemskap eller realtidshändelser
* **[Uttryck](expression/expressionadvanced.md)** - Skapa avancerad logik och personalisering med uttrycksredigeraren

Lär dig hur du använder resedesignern [i dessa situationer från början till slut &#x200B;](jo-use-cases.md).

>[!NOTE]
>
>Resegarantier och begränsningar finns på [den här sidan](../start/guardrails.md)

## Instruktionsvideo {#video}

Identifiera komponenterna i en resa och förstå grunderna för hur man bygger en resa på arbetsytan.

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)


## Ytterligare resurser {#additional-resources}

* **[Felsökning av kundresor](/help/rp_landing_pages/troubleshoot-journey-landing-page.md)** - Diagnostisera och åtgärda problem med körning av resan med verktyg, felkoder och bästa praxis för felsökning och optimering
* **[Vanliga frågor om resan](journey-faq.md)** - Vanliga frågor om resor
* **[Resensaviseringar](../reports/alerts.md)** - Konfigurera aviseringar för reseövervakning och prenumerera på aviseringar för realtidsuppdateringar
* **[Felkodsreferens](error-codes-reference.md)** - Resefelkoder och felsökningssteg
* **[Felsökning](troubleshooting.md)** - Vanliga reseproblem och lösningar
* **[Självstudiekurser (videoklipp)](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** - Lär dig hur du skapar resan med praktiska videokurser som omfattar funktioner, funktioner och bästa praxis
* **[Reservoarer och begränsningar för resan](../start/guardrails.md)** - Kontrollera skyddslingar och begränsningar när du använder [!DNL Adobe Journey Optimizer]
