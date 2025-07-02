---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Dela
description: Lär dig hur du använder aktiviteten Dela i en iscensatt kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 986bc566-123a-451d-a4a6-bbf5a2798849
source-git-commit: 7de878c316e966129e7dede37f132938d2abbdf8
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 0%

---

# Dela {#split}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split"
>title="Delad aktivitet"
>abstract="Med aktiviteten **Dela** kan du segmentera inkommande populationer i flera deluppsättningar baserat på olika urvalskriterier, t.ex. filtreringsregler eller populationsstorlek."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **[!UICONTROL Split]** är en **[!UICONTROL Targeting]**-aktivitet som delar in den inkommande populationen i flera deluppsättningar baserat på definierade urvalskriterier som filtreringsregler eller populationsstorlek.

## Konfigurera aktiviteten Dela {#split-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_segments"
>title="Segment för delad aktivitet"
>abstract="Lägg till så många delmängder som du vill för att segmentera den inkommande populationen.<br/></br>När aktiviteten **Dela** körs segmenteras populationen mellan de olika delmängderna i den ordning som de läggs till i aktiviteten. Innan du påbörjar din samordnade kampanj måste du se till att du har beställt delmängderna i den ordning som passar dina behov med pilknapparna."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_filter"
>title="Dela aktivitetsfilter"
>abstract="Om du vill använda ett filtreringsvillkor för delmängden klickar du på **[!UICONTROL Create filter]** och konfigurerar den önskade filtreringsregeln med frågemodelleraren. Ta till exempel med profiler från den inkommande populationen vars e-postadress finns i databasen."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_limit"
>title="Gräns för delad aktivitet"
>abstract="Om du vill begränsa antalet profiler som markeras av delmängden aktiverar du alternativet **[!UICONTROL Enable limit]** och anger antalet eller procentsatserna för den population som ska inkluderas."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_sorting"
>title="Sortering av delad aktivitet"
>abstract="När du anger en populationsgräns för en delmängd kan du rangordna de valda profilerna baserat på ett visst profilattribut i stigande eller fallande ordning. Aktivera alternativet **Aktivera sortering** om du vill göra det. Du kan till exempel begränsa en delmängd så att den endast innehåller de 50 översta profilerna med det högsta inköpspriset."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_complement"
>title="Delad generering av komplementfärg"
>abstract="När du har konfigurerat alla deluppsättningar kan du välja den återstående populationen som inte matchade någon av deluppsättningarna och inkludera dem i en ytterligare utgående övergång. Aktivera alternativet **Generera komplement** om du vill göra det."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_generatesubsets"
>title="Generera alla delmängder i samma tabell"
>abstract="Växla till det här alternativet om du vill gruppera alla delmängder i en enda utdataövergång."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_emptytransition"
>title="Hoppa över tom övergång"
>abstract="Aktivera alternativet **[!UICONTROL Skip empty transition]** om du vill inaktivera utdataövergången för den här delmängden om den inkommande populationen är tom."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_enable_overlapping"
>title="Aktivera överlappning av utdatapopulationer"
>abstract=" Med alternativet **[!UICONTROL Enable overlapping of output populations]** kan du hantera populationer som tillhör flera delmängder. När rutan inte är markerad ser delningsaktiviteten till att en mottagare inte kan finnas i flera utdataövergångar, även om den uppfyller villkoren för flera delmängder. De kommer att vara i målet för den första fliken med matchande villkor. När rutan är markerad kan mottagarna hittas i flera delmängder om de uppfyller filtervillkoren."

Så här konfigurerar du aktiviteten **[!UICONTROL Split]**:

1. Lägg till en **[!UICONTROL Split]**-aktivitet i din samordnade kampanj.

1. Aktivitetskonfigurationsrutan öppnas med en standarddelmängd. Klicka på knappen **[!UICONTROL Add segment]** om du vill lägga till så många delmängder som behövs för att segmentera den inkommande populationen.

   ![](../assets/orchestrated-split-1.png)

   >[!IMPORTANT]
   >
   >**Dela**-aktiviteten bearbetar delmängder i den ordning som de läggs till. Om den första delmängden till exempel tar 70 % av populationen tillämpas nästa på de återstående 30 %.
   >
   >Innan du kör en orkestrerad kampanj måste du se till att delmängderna är beställda på rätt sätt. Använd pilknapparna för att justera deras placering.

1. När deluppsättningar har lagts till visar aktiviteten så många utdataövergångar som det finns deluppsättningar. Vi rekommenderar starkt att du ändrar etiketten för varje delmängd för att enkelt identifiera dem i den orkestrerade kampanjarbetsytan.

1. Konfigurera filter för varje delmängd:

   1. Klicka på en delmängd för att öppna dess inställningar.

   1. Klicka på **[!UICONTROL Create filter]** om du vill definiera filtreringsregler med frågemodelleraren, till exempel, markera profiler med en giltig e-postadress.

      ![](../assets/orchestrated-split-1.png)

   1. Om du vill begränsa antalet valda profiler aktiverar du **[!UICONTROL Enable limit]** och anger ett tal eller en procentandel.

   1. Aktivera **[!UICONTROL Skip empty transition]om du vill hoppa över en övergång när delmängden är tom.**

1. Aktivera **[!UICONTROL Generate complement]** om du vill inkludera profiler som inte matchas av någon delmängd. Detta skapar en ytterligare utgående övergång för den återstående populationen.

   >[!NOTE]
   >
   >Aktivera **[!UICONTROL Generate all subsets in the same table]** för att gruppera alla delmängder i en enda övergång.

1. Använd **[!UICONTROL Enable overlapping of output populations]** om du vill tillåta att profiler visas i flera deluppsättningar:

   * **Om alternativet inte är markerat** tilldelas varje profil endast en delmängd, den första vars villkor matchar även om den kvalificerar för andra delmängder.

   * **Om det här alternativet är markerat** kan profiler inkluderas i flera deluppsättningar om de uppfyller villkoren för var och en.

Aktiviteten är nu konfigurerad. Vid genomförande av samordnade kampanjer kommer populationen att segmenteras i olika delmängder, i den ordning som de har lagts till i aktiviteten.

## Exempel{#split-example}

I följande exempel används aktiviteten **[!UICONTROL Split]** för att segmentera en målgrupp i distinkta delmängder baserat på kommunikationskanalen som vi vill använda:

* **Delmängd 1 &quot;email&quot;**: innehåller profiler som har angett ett telefonnummer.

* **Delmängd 2 &quot;sms&quot;**: Målprofiler med ett mobiltelefonnummer som lagras i databasen.

* **Kompletteringsövergång**: hämtar alla återstående profiler som inte uppfyller villkoren för någon av delmängderna.

![](../assets/orchestrated-split-3.png)
