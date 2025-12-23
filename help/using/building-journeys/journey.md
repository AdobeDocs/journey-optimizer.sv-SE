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
source-git-commit: a6c80e4326454868d60e9ba335e509f806d3220f
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 0%

---


# Kom igång med resor{#jo-general-principle}

Med resor i Adobe Journey Optimizer kan ni skapa personaliserade kundresor i flera steg som i realtid anpassar sig efter målgruppens beteende och behov. Med en intuitiv dra-och-släpp-arbetsyta kan ni samordna meddelanden och åtgärder i flera kanaler och utnyttja sammanhangsberoende data och målgruppsanpassning för maximal effekt. Oavsett om ni utforskar triggers i realtid, hanterar reseegenskaper eller använder avancerade verktyg som anpassade åtgärder och uttryck, ger det här avsnittet en tydlig färdplan som hjälper er att utforma och förfina resor som levererar meningsfulla och aktuella kundupplevelser.

Använd [!DNL Journey Optimizer] för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor. Du kan utforma avancerade scenarier i flera steg med följande funktioner:

* Skicka **enhetsleverans** i realtid när en [händelse](general-events.md) tas emot, eller **i batch** med Adobe Experience Platform [målgrupper](read-audience.md).

* Utnyttja **sammanhangsbaserade data** från [händelser](../event/about-events.md), information från Adobe Experience Platform eller data från tredjeparts API-tjänster via [datakällor](../datasource/about-data-sources.md).

* Använd de **[inbyggda åtgärderna](journeys-message.md)** för att skicka meddelanden som är utformade i [!DNL Journey Optimizer] eller skapa **[anpassade åtgärder](using-custom-actions.md)** om du använder ett tredjepartssystem för att skicka meddelanden.

* Med **[resedesignern](using-the-journey-designer.md)** kan du skapa dina flerstegsfall: enkelt dra och släppa en anmälningshändelse eller en [läs målgruppsaktivitet](read-audience.md), lägga till [villkor](condition-activity.md) och skicka personliga meddelanden.

Journey Optimizer [resedesigner](using-the-journey-designer.md) innehåller allt som marknadsförare och reseansvariga behöver för att kunna genomföra flerstegsresor i 1:1 över flera kanaler. Detta inkluderar en intuitiv dra-och-släpp-arbetsyta för att samordna varje steg av resan, definiera målgruppen och inkludera de meddelanden, erbjudanden och innehåll i olika kanaler som målgruppsmedlemmarna kan se baserat på beteende, kontextuella data och affärshändelser. Utforska [användningsexempel från verkligheten](jo-use-cases.md) och se hur du kan använda dessa funktioner.

➡️ [Upptäck Journey Optimizer i video](#video)

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

## Översikt över resor

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=sv-SE)

Komma igång med att skapa resan

Stegvisa riktlinjer för att utforma, testa, publicera och spåra kundresor för att skapa personaliserade flerkanalskampanjer.

[Skapa den första resan](journey-gs.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=sv-SE)

Journey Orchestration - komplett guide

Omfattande dokumentation som täcker alla aspekter av att skapa, hantera och optimera resor i Adobe Journey Optimizer.

[Utforska hela guiden](journey-get-started.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=sv-SE)

Hantera era resor

Hantera kundresor effektivt med verktyg för filtrering, profilhantering, tidszoner och optimeringstekniker.

[Lär dig resehantering](/help/rp_landing_pages/manage-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg?lang=sv-SE)

Reseverksamhet

Upptäck hur ni konfigurerar och använder aktiviteter som triggers, beslutssteg, målgruppshantering och personaliserade meddelanden på resorna.

[Utforska aktiviteter](/help/rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=sv-SE)

Skapar uttryck

Masteruttryck för dynamiska arbetsflöden, datamanipulering och avancerad resesamordning med kraftfulla verktyg och syntax.

[Läs mer om uttryck](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=sv-SE)

Användningsexempel på resa

Utforska verkliga program i Adobe Journey Optimizer, inklusive meddelanden i flera kanaler och integration med externa system.

[Upptäck användningsexempel](/help/rp_landing_pages/journey-use-cases-landing-page.md)
:::

::::

## Användningsfall{#uc-journey}

Inom resedesignern kan marknadsförarna skicka :1-meddelanden i realtid via valfri kanal när en händelse inträffar. När en kund prenumererar på en tjänst kan den till exempel [utlösa ett välkomstmeddelande](message-to-subscribers-uc.md) som uppmanar dem att logga in i appen för första gången och ange sina inställningar. Åtgärder som att slutföra köpet, öppna e-postmeddelandet och logga in i appen kan användas för att locka nya kunder genom deras resor.

[Resedesignern](using-the-journey-designer.md) innehåller [inbyggda kanalåtgärder](journeys-message.md) som stöder utgående meddelanden, t.ex. e-post, push-meddelanden och SMS/MMS, samt inkommande kanaler, inklusive mobilappar, webbplatser och kodbaserade upplevelser som skapats direkt i Journey Optimizer. Du kan också använda tredjepartssystem för att skicka meddelanden - via e-post, text eller andra kanaler - i Journey Optimizer ingår [anpassade åtgärder](using-custom-actions.md) så att dessa system kan integreras på resorna direkt från kunddesignern.

Lär dig hur du skapar resor [&#x200B; i dessa fall av typen end-to-end &#x200B;](jo-use-cases.md).

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
* **[Självstudiekurser (videoklipp)](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** - Lär dig hur du skapar resan med praktiska videokurser som omfattar funktioner, funktioner och bästa praxis
