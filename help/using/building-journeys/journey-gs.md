---
solution: Journey Optimizer
product: journey optimizer
title: Skapa den första resan
description: Viktiga steg för att skapa din första resa med  [!DNL Adobe Journey Optimizer]
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: resa, första, start, snabbstart, målgrupp, händelse, åtgärd
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
version: Journey Orchestration
source-git-commit: e7586f50e9f806b7dccb6d88998c43a89feb392b
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 1%

---

# Skapa den första resan {#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="Skapa resor"
>abstract="Använd **[!DNL Adobe Journey Optimizer]** för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor."

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="Resor"
>abstract="Utforma kundresor för att leverera personaliserade, sammanhangsbaserade upplevelser. Med Journey Optimizer kan du skapa användningsfall för realtidssamordning med kontextuella data som lagras i händelser eller datakällor. Fliken **Översikt** visar en instrumentpanel med viktiga mått för dina resor. Fliken **Bläddra** visar en lista över befintliga resor."

[!DNL Adobe Journey Optimizer] innehåller en flerkanalig orchestration-arbetsyta som gör det möjligt för marknadsförare att harmonisera marknadsföringen med ett-till-ett-kundengagemang. Med användargränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan för att skapa din resa. Användargränssnittet för resan visas på [den här sidan](journey-ui.md).

![exempel på resans arbetsyta](assets/journey38.png)

De viktigaste stegen för att skapa en resa finns på den här sidan. De är smidiga enligt följande:

![steg för att skapa resa: skapa, utforma, testa och publicera](assets/journey-creation-process.png)

I den här guiden gör du följande:

* Definiera en startpunkt för en resa - ett målgruppssegment eller en realtidshändelse
* Lägg till meddelandeåtgärder över flera kanaler - e-post, push, SMS, i appen, webb, kodbaserad upplevelse, innehållskort med mera. [Se kanaler som stöds](journey-action.md)
* Testa resan med testprofiler före aktivering
* Publicera resan och övervaka dess prestanda

Bygg kundresor i flera steg för att initiera en sekvens av interaktioner, erbjudanden och meddelanden över alla kanaler i realtid. Detta arbetssätt säkerställer att kunderna engagerar sig i rätt ögonblick baserat på deras handlingar och relevanta affärssignaler.

<!--
>[!TIP]
>
>Not sure whether to use a journey or a campaign? [Learn how to choose the right approach](../start/journeys-vs-campaigns.md).
-->

## Innan du börjar {#prerequisites}

Vad du behöver konfigurera innan du bygger beror på hur din resa utlöses. De flesta resor börjar med en av dessa två ingångspunkter:

* **Målgruppsbaserad post** - Resan körs för en definierad uppsättning profiler vid en schemalagd tidpunkt. [Skapa en målgrupp](../audience/about-audiences.md) i Adobe Experience Platform innan du skapar din resa. Detta är den rekommenderade startpunkten om du inte har använt Journey Optimizer tidigare.

* **Händelsebaserad post** - Resan utlöses i realtid när en individ utför en åtgärd, till exempel ett köp eller en registrering. [Konfigurera en händelse](../event/about-events.md) för att definiera utlösaren och de data den innehåller.

Följande element är valfria, men kan behövas beroende på ditt sätt att arbeta:

* **Datakälla** - Konfigurera en [datakälla](../datasource/about-data-sources.md) om du vill förbättra resevillkor eller personalisering med data från ett externt system.

* **Anpassad åtgärd** - Om du levererar meddelanden via ett tredjepartssystem i stället för via de inbyggda kanalerna konfigurerar du en [anpassad åtgärd](../action/action.md).

>[!NOTE]
>
>* Om du är en datatekniker som ansvarar för den tekniska konfigurationen (händelser, datakällor och åtgärder), se [det här avsnittet](../configuration/about-data-sources-events-actions.md).
>
>* Reservoarer och begränsningar för resan finns på [den här sidan](../start/guardrails.md).

## Skapa en resa {#jo-build}

Så här skapar du en resa i flera steg:

1. Klicka på **[!UICONTROL Journeys]** på menyn RESURSHANTERING.

1. Klicka på knappen **[!UICONTROL Create Journey]** för att skapa en ny resa.

1. Redigera kundens konfigurationsruta för att definiera namnet på resan och ange dess egenskaper. Lär dig hur du anger egenskaper för din resa på [den här sidan](journey-properties.md).

   >[!TIP]
   >
   >**Vilken resetyp ska jag välja?** Om du inte har använt Journey Optimizer tidigare kan du börja med en målgruppsbaserad resa med en **[!UICONTROL Read Audience]** -aktivitet. Det kräver ingen tidigare händelsekonfiguration och är det enklaste sättet att bekanta sig med arbetsytan. För händelseutlösta upplevelser i realtid (till exempel respons på ett köp eller en formulärinlämning) ska du först konfigurera en händelse och använda en händelsebaserad post. Är du redo att gå djupare? [Identifiera alla resetyper och deras anmälningsregler](entry-management.md#types-of-journeys).

   ![Resegenskapspanelen med inställningar och konfigurationsalternativ](assets/jo-properties.png)

Sedan kan du börja designa din resa.

## Designa resan {#jo-design}

Med resedesignern kan du skapa flerstegsresor med ett intuitivt dra-och-släpp-gränssnitt. Aktiviteter i den vänstra paletten är ordnade i tre kategorier: **Händelser**, **Orchestration** och **Åtgärder**. En fullständig översikt över arbetsytan och dess kontroller finns på [den här sidan](using-the-journey-designer.md).

![Resedesignerns gränssnitt med aktivitetspaletten och arbetsytan](assets/journey38.png)

Så här utformar du din resa:

1. **Lägg till en startpunkt** - Dra en händelse eller en **[!UICONTROL Read Audience]**-aktivitet från paletten till arbetsytan. Detta definierar hur profiler tar sig in på resan: individuellt i realtid (händelsebaserat) eller alla samtidigt från en viss målgrupp (målgruppsbaserat).

   ![Konfiguration av målgruppsaktivitet för val av målgrupp](assets/read-segment.png)

1. **Lägg till meddelandeåtgärder** - Dra en kanalåtgärd från avsnittet **[!UICONTROL Actions]** på paletten till arbetsytan för att skicka meddelanden till profiler som löper genom resan. Det finns åtgärder för e-post, push-meddelanden, SMS med mera.

1. **Lägg till orkestreringsaktiviteter** - Använd en **[!UICONTROL Condition]**-aktivitet för att dela in resan i flera sökvägar baserat på profilattribut eller beteende. Använd en **[!UICONTROL Wait]**-aktivitet för att ange en tidsfördröjning mellan steg.

>[!TIP]
>
>För resor med flera faser eller många kontaktytor bör du överväga att bryta flödet från början till slut i mindre delresor som är kopplade till aktiviteten **[!UICONTROL Jump]**. Detta minskar komplexiteten och gör varje delresa enklare att testa separat. Läs mer i [Designstrategi: delresor i bitstorlek](jump.md#jump-strategy).

## Testa resan {#jo-test}

Testa resan innan du publicerar den när du har byggt den. Journey Optimizer erbjuder ett **testläge** som ett sätt att visa testprofiler under resan och upptäcka eventuella fel före aktiveringen. Genom att köra snabbtester kan du vara säker på att resorna fungerar som de ska så att du kan publicera dem med tillförsikt. Lär dig hur du testar din resa [i det här avsnittet](testing-the-journey.md)

Du kan även utföra din resa i **Torr körning**. Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation. Den här funktionen hjälper resenärer att få förtroende för sin resedesign och målgruppsanpassning innan de publicerar den live. Lär dig hur du publicerar en resa i körningsläget [ i det här avsnittet](journey-dry-run.md).

## Publicera resan {#jo-pub}

Du måste publicera en resa för att aktivera den och göra den tillgänglig för nya profiler för att delta i den. Innan du publicerar din resa kontrollerar du att den är giltig och att inga fel har uppstått. Du kan inte publicera en resa med fel. Läs mer om resepublikation i det här [avsnittet](publish-journey.md).

![Hela kundresan med målgrupp, villkor och åtgärder](assets/jo-journeyuc2_32bis.png)

När den publicerats kan ni övervaka er resa med de dedikerade rapporteringsverktygen för att mäta hur effektiv resan är.

![Reseanalysrapport som visar prestanda och statistik](assets/jo-dynamic_report_journey_12.png)

Läs mer om reserapporter i det här [avsnittet](../reports/live-report.md).

## Vanliga användningsfall {#use-cases}

Vet du inte var du ska börja? Här är tre typiska scenarier där resor ger mest värde:

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding" target="_blank">
        <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px">
      </a>
      <div><strong>Välkomstserie</strong><br/>Införliva automatiskt nya användare med en meddelandesekvens efter registreringen och vägleda dem genom produkten eller tjänsten.</div>
    </td>
    <td>
      <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart" target="_blank">
        <img src="../assets/do-not-localize/icon-campaign.svg" width="35px">
      </a>
      <div><strong>Återkalla kunder som lämnat ett köp genom att skicka en påminnelse med personaliserat innehåll.</strong><br/>Återanslut kunder som slutat utan att slutföra ett köp.</div>
    </td>
    <td>
      <a href="jo-use-cases.md">
        <img src="../assets/do-not-localize/icon-content.svg" width="35px">
      </a>
      <div><strong>Åter-engagemang</strong><br/>Åter inaktiva användare med riktade erbjudanden eller uppdateringar baserat på deras senaste kända beteende.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding" target="_blank"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart" target="_blank"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="jo-use-cases.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
  </tr>
</table>

## Ytterligare resurser

* **[Resetyper och profilinmatning](entry-management.md)** - Förstå alla resetyper (enställig händelse, affärshändelse, läsmålgrupp, målgruppskvalifikation) och hur profiler går in, deltar på nytt och löper genom resor.
* **[Översikt över resedesignern](using-the-journey-designer.md)** - bemästra arbetsytans gränssnitt för att designa och samordna kundresor.
* **[Reseaktiviteter](about-journey-activities.md)** - Upptäck alla tillgängliga aktiviteter, inklusive händelser, åtgärder och orkestreringskomponenter.
* **[Testar resor](testing-the-journey.md)** - Lär dig hur du testar dina resor i testläge innan du publicerar till produktion.
* **[Publicerar resor](publish-journey.md)** - Förstå processen för att publicera resan och hur du hanterar direktresor.
* **[Reserapportering](report-journey.md)** - Spåra och analysera reseprestanda med detaljerade mått och insikter.
* **[Felsökning av resor](troubleshooting.md)** - Hitta lösningar på vanliga reseproblem och bästa praxis för felsökning.
* **[Resehandledningar](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/journeys/introduction-to-building-a-journey){target="_blank"}** - Utforska steg-för-steg-videosjälvstudiekurser om resebyggande och metodtips.

