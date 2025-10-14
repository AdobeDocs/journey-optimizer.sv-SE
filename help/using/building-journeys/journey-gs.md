---
solution: Journey Optimizer
product: journey optimizer
title: Skapa den första resan
description: Viktiga steg för att skapa din första resa med Adobe Journey Optimizer
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: resa, första, start, snabbstart, målgrupp, händelse, åtgärd
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
version: Journey Orchestration
source-git-commit: 96b8813ebad35f51986cc62d847d9d3d256b08be
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 3%

---

# Skapa den första resan {#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="Skapa resor"
>abstract="Använd **Adobe Journey Optimizer** för att skapa användningsfall för realtidssamordning med kontextuella data som lagras i händelser eller datakällor."

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="Resor"
>abstract="Utforma kundresor för att leverera personaliserade, sammanhangsbaserade upplevelser. Med Journey Optimizer kan du skapa användningsfall för realtidssamordning med kontextuella data som lagras i händelser eller datakällor. Fliken **Översikt** visar en instrumentpanel med viktiga mått för dina resor. Fliken **Bläddra** visar en lista över befintliga resor."

Adobe Journey Optimizer har en flerkanalig orkestreringsyta som gör att marknadsförarna kan harmonisera marknadsföringen med ett-till-ett-kundengagemang. Med användargränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan för att skapa din resa. Användargränssnittet för resan visas på [den här sidan](journey-ui.md).

![exempel på resans arbetsyta](assets/journey38.png)

De viktigaste stegen för att skapa en resa finns på den här sidan. De är smidiga enligt följande:

![steg för att skapa resa: skapa, utforma, testa och publicera](assets/journey-creation-process.png)


Bygg kundresor i flera steg för att initiera en sekvens av interaktioner, erbjudanden och meddelanden över alla kanaler i realtid. Detta arbetssätt säkerställer att kunderna engagerar sig i rätt ögonblick baserat på deras handlingar och relevanta affärssignaler. Målgrupper definieras utifrån beteende, kontextuella data och affärshändelser. Förutsättningar beror på ditt användningsfall och vilken [typ av resa](entry-management.md#types-of-journeys) du skapar.

Innan du börjar bygga din resa måste du se till att de relevanta konfigurationsstegen är slutförda:

* Om du vill utlösa dina resor individuellt när en händelse tas emot, **konfigurerar du en händelse**. Definiera den förväntade informationen och hur den ska behandlas. [Läs mer](../event/about-events.md).

<!--   ![](assets/jo-event7bis.png)  -->

* Din resa kan även lyssna på Adobe Experience Platform målgrupper för att skicka meddelanden i grupper till en viss uppsättning profiler. För detta skapar **målgrupper**. [Läs mer](../audience/about-audiences.md).

<!--   ![](assets/segment2.png)  -->

* Definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel i dina villkor. Den här anslutningen är beroende av en **datakälla**. [Läs mer](../datasource/about-data-sources.md).

<!--   ![](assets/jo-datasource.png)  -->

* Journey Optimizer har [inbyggda meddelandefunktioner](../building-journeys/journeys-message.md). Om du använder ett tredjepartssystem för att skicka meddelanden kan du **skapa en anpassad åtgärd**. Läs mer i det här [avsnittet](../action/action.md).

<!--    ![](assets/custom2.png)  -->


Som datatekniker beskrivs stegen för att konfigurera dina resor, inklusive datakällor, händelser och åtgärder i [det här avsnittet](../configuration/about-data-sources-events-actions.md).


>[!NOTE]
>
>Resegarantier och begränsningar finns på [den här sidan](../start/guardrails.md)

## Skapa en resa {#jo-build}

Så här skapar du en resa i flera steg:

1. Klicka på **[!UICONTROL Journeys]** på menyn RESURSHANTERING.

1. Klicka på knappen **[!UICONTROL Create Journey]** för att skapa en ny resa.

1. Redigera kundens konfigurationsruta för att definiera namnet på resan och ange dess egenskaper. Lär dig hur du anger egenskaper för din resa på [den här sidan](journey-properties.md).

   ![](assets/jo-properties.png)

Sedan kan du börja designa din resa.

## Designa resan {#jo-design}

Flerkanalsdesignern hjälper er att skapa flerstegsresor med riktade målgrupper, uppdateringar baserade på kundinteraktioner eller affärsinteraktioner i realtid och flerkanalsmeddelanden med ett intuitivt dra-och-släpp-gränssnitt.

![](assets/journey38.png)

1. Börja med att dra och släppa en händelse eller en **Läs publikens**-aktivitet från paletten till arbetsytan. Mer information om resedesign finns i [det här avsnittet](using-the-journey-designer.md).

   ![](assets/read-segment.png)

1. Börja med att dra och släppa en händelse eller en **Läs publikens**-aktivitet från paletten till arbetsytan. Mer information om resedesign finns i [det här avsnittet](using-the-journey-designer.md).

## Testa resan {#jo-test}

Testa resan innan du publicerar den när du har byggt den. Journey Optimizer erbjuder ett **testläge** som ett sätt att visa testprofiler under resan och upptäcka eventuella fel före aktiveringen. Genom att köra snabbtester kan du vara säker på att resorna fungerar som de ska så att du kan publicera dem med tillförsikt. Lär dig hur du testar din resa [i det här avsnittet](testing-the-journey.md)

Du kan även utföra din resa i **Torr körning**. Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation. Den här funktionen hjälper resenärer att få förtroende för sin resedesign och målgruppsanpassning innan de publicerar den live. Lär dig hur du publicerar en resa i körningsläget [&#x200B; i det här avsnittet](journey-dry-run.md).

## Publicera resan {#jo-pub}

Du måste publicera en resa för att aktivera den och göra den tillgänglig för nya profiler för att delta i den. Innan du publicerar din resa kontrollerar du att den är giltig och att inga fel har uppstått. Du kan inte publicera en resa med fel. Läs mer om resepublikation i det här [avsnittet](publishing-the-journey.md).

![](assets/jo-journeyuc2_32bis.png)

När den publicerats kan ni övervaka er resa med de dedikerade rapporteringsverktygen för att mäta hur effektiv resan är.

![](assets/jo-dynamic_report_journey_12.png)

Läs mer om reserapporter i det här [avsnittet](../reports/live-report.md).

>[!NOTE]
>
>Om du behöver ändra en **live**-resa [skapar du en ny version](journey-ui.md#journey-versions) av din resa.
